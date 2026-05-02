---
description: Save MTGA UTC_Log session, strip frame prefix, sanitize, and open a corpus PR
argument-hint: [<utc-substring> [<session-suffix>]]
allowed-tools: Bash(cp:*), Bash(ls:*), Bash(stat:*), Bash(gzip:*), Bash(gunzip:*), Bash(cat:*), Bash(cd:*), Bash(uname:*), Bash(wc:*), Bash(date:*), Bash(tar:*), Bash(gh:*), Bash(mkdir:*), Bash(rm:*), Bash(git:*), Bash(cargo:*), Bash(grep:*), Bash(sed:*), Bash(sha256sum:*), Bash(python3:*), Bash(chmod:*), Bash(find:*), Read, Edit, Write, Grep, Glob, AskUserQuestion
---

# Harvest Log

Save an MTGA per-session archive log (`UTC_Log - <MM-DD-YYYY> <HH.MM.SS>.log`), strip its `[N] ` frame-counter prefix, sanitize it, and open a PR in `manasight-corpus`. On merge, `publish-corpus.yml` creates a release automatically. Also runs a local parser smoke test for immediate coverage feedback and updates `sessions.md`.

## Why UTC_Log, not Player.log

UTC_Log files are MTGA's permanent per-process archive (one file per game launch, never overwritten). The previously-targeted `Player.log` is overwritten on every launch and `Player-prev.log` updates infrequently and is unreliable. The desktop client's raw-log uploader (`raw_log_upload.rs`) already targets UTC_Logs; this skill aligns with that source.

UTC_Log content is identical to Player.log content for the same process, modulo a `[N] ` Unity frame-counter prefix on framing lines. The parser's entry detector (`manasight-parser/src/log/entry.rs`) regex is anchored to start-of-line and does not tolerate that prefix, so Step 3 strips it before sanitization.

Archive log directory discovery follows `manasight-desktop/src-tauri/src/archive_logs/mod.rs:120-200`.

## Arguments

`$ARGUMENTS` is `[<utc-substring>] [<session-suffix>]`:
- No args → most recent UTC_Log (excluding active session within 5-min mtime skew); no session suffix
- One arg starting with `_` → suffix only; latest UTC_Log
- One arg not starting with `_` → UTC_Log substring filter; no suffix
- Two args → first is UTC substring filter, second is suffix

Examples:
- `/harvest-log` → most recent UTC_Log, no suffix
- `/harvest-log _draft` → latest UTC_Log + suffix `_draft`
- `/harvest-log 23.57.07` → UTC_Log matching `23.57.07`, no suffix
- `/harvest-log 23.57.07 _sealed-purchase` → that UTC_Log + suffix

## Instructions

### Step 1: Resolve archive directory and select source file

Resolve the archive directory:
```bash
PLATFORM=$(uname -s)
if [ -n "$MANASIGHT_MTGA_INSTALL_DIR" ]; then
  ARCHIVE_DIR="$MANASIGHT_MTGA_INSTALL_DIR/MTGA_Data/Logs/Logs"
elif [ "$PLATFORM" = "Linux" ] && grep -qi microsoft /proc/version 2>/dev/null; then
  ARCHIVE_DIR="/mnt/c/Program Files/Wizards of the Coast/MTGA/MTGA_Data/Logs/Logs"
elif [ "$PLATFORM" = "Darwin" ]; then
  ARCHIVE_DIR="$HOME/Library/Application Support/com.wizards.mtga/Logs/Logs"
fi
[ -d "$ARCHIVE_DIR" ] || { echo "Archive dir not found: $ARCHIVE_DIR"; exit 1; }
```

Parse `$ARGUMENTS` into `UTC_SUBSTRING` and `SUFFIX`:
- Split on whitespace into up to two tokens.
- If a token starts with `_`, it's the suffix.
- Otherwise it's the UTC substring filter.

Select the source file:
```bash
if [ -n "$UTC_SUBSTRING" ]; then
  # Substring match — must match exactly one file
  matches=$(find "$ARCHIVE_DIR" -maxdepth 1 -name "UTC_Log*${UTC_SUBSTRING}*" -type f | sort)
  match_count=$(echo "$matches" | grep -c .)
  [ "$match_count" -eq 1 ] || { echo "Substring '$UTC_SUBSTRING' matched $match_count files; need exactly 1:"; echo "$matches"; exit 1; }
  SOURCE="$matches"
else
  # Latest UTC_Log with mtime older than 5 min (skip active session, per archive_logs/mod.rs:88)
  SOURCE=$(find "$ARCHIVE_DIR" -maxdepth 1 -name "UTC_Log - *.log" -type f -mmin +5 -printf '%T@ %p\n' 2>/dev/null | sort -n | tail -1 | cut -d' ' -f2-)
fi
[ -n "$SOURCE" ] && [ -f "$SOURCE" ] || { echo "No UTC_Log selected"; exit 1; }
```

### Step 2: Determine session name

UTC_Log filenames encode the process startup time in UTC: `UTC_Log - MM-DD-YYYY HH.MM.SS.log`. Convert to local time for the session name:

```bash
basename=$(basename "$SOURCE")
ts_part=${basename#UTC_Log - }; ts_part=${ts_part%.log}
SESSION_BASE=$(python3 -c "
from datetime import datetime, timezone
dt = datetime.strptime('$ts_part', '%m-%d-%Y %H.%M.%S').replace(tzinfo=timezone.utc).astimezone()
print('session_' + dt.strftime('%Y-%m-%d_%H%M'))
")
SESSION_NAME="${SESSION_BASE}${SUFFIX}"
```

Example: `UTC_Log - 05-02-2026 00.51.35.log` (UTC) → local `2026-05-01_1751` → session name `session_2026-05-01_1751_sealed-matches` (with suffix `_sealed-matches`).

### Step 3: Copy and strip `[N] ` frame-counter prefix

```bash
mkdir -p /tmp/harvest-work
cp "$SOURCE" /tmp/harvest-work/${SESSION_NAME}.raw.log
sed -E 's/^\[[0-9]+\] //' /tmp/harvest-work/${SESSION_NAME}.raw.log > /tmp/harvest-work/${SESSION_NAME}.log
rm /tmp/harvest-work/${SESSION_NAME}.raw.log
```

Record the post-strip raw file size in bytes and human-readable form.

### Step 4: Sanitize

Download the `scrub` binary from the latest `manasight-parser` release and sanitize the log:

```bash
PLATFORM=$(uname -s)
case "$PLATFORM" in
  Linux*)  ASSET="scrub-linux-x86_64.tar.gz" ;;
  Darwin*) ARCH=$(uname -m); if [ "$ARCH" = "arm64" ]; then ASSET="scrub-macos-aarch64.tar.gz"; else ASSET="scrub-macos-x86_64.tar.gz"; fi ;;
esac

gh release download --repo manasight/manasight-parser --pattern "$ASSET" --dir /tmp --clobber
mkdir -p /tmp/scrub-bin
tar xzf /tmp/$ASSET -C /tmp/scrub-bin
SCRUB=$(find /tmp/scrub-bin -name scrub -type f | head -1)
chmod +x "$SCRUB"

"$SCRUB" < /tmp/harvest-work/${SESSION_NAME}.log > /tmp/harvest-work/${SESSION_NAME}.scrubbed.log
mv /tmp/harvest-work/${SESSION_NAME}.scrubbed.log /tmp/harvest-work/${SESSION_NAME}.log
```

### Step 5: Compress

```bash
gzip -k /tmp/harvest-work/${SESSION_NAME}.log
```

Record the compressed file size and compression ratio.

### Step 6: Check for conflicts

Operate in the corpus repo (skill may be invoked from any workspace repo via symlink):
```bash
CORPUS_DIR="$(git rev-parse --show-toplevel)"
case "$(basename "$CORPUS_DIR")" in
  manasight-corpus) ;;
  *) CORPUS_DIR="$(dirname "$CORPUS_DIR")/manasight-corpus" ;;
esac
ls "$CORPUS_DIR/corpus/${SESSION_NAME}.log.gz" 2>/dev/null
```

If the file exists, ask whether to overwrite or pick a different suffix.

### Step 7: Commit to branch and open PR

```bash
cd "$CORPUS_DIR"
git checkout main && git pull
git checkout -b add-${SESSION_NAME}
cp /tmp/harvest-work/${SESSION_NAME}.log.gz corpus/
```

Compute sha256 + size from the **uncompressed sanitized + frame-stripped** log:
```bash
SHA=$(sha256sum /tmp/harvest-work/${SESSION_NAME}.log | awk '{print $1}')
SIZE=$(stat --format='%s' /tmp/harvest-work/${SESSION_NAME}.log)
```

Append to `smoke-corpus-manifest.toml`:
```toml
[[files]]
filename      = "<session-name>.log"
sha256        = "<sha-from-above>"
size_bytes    = <size-from-above>
date_captured = "YYYY-MM-DD"
```

Commit, push, and open PR:
```bash
git add corpus/${SESSION_NAME}.log.gz smoke-corpus-manifest.toml sessions.md
git commit -m "Add ${SESSION_NAME} to corpus"
git push -u origin add-${SESSION_NAME}

gh pr create --repo manasight/manasight-corpus \
  --title "Add ${SESSION_NAME} to corpus" \
  --body "Add sanitized UTC_Log session from <local-date> (source: \`$(basename "$SOURCE")\`).

Frame-counter prefix stripped (UTC_Log → Player.log-equivalent format).

Raw size: <raw-size>
Compressed: <gzip-size> (<ratio>:1)

CI will validate sanitization via check-log-sanitization.yml.
On merge, publish-corpus.yml creates a new release automatically."
```

Report the PR URL.

### Step 8: Run local smoke test

```bash
PARSER_DIR="$(dirname "$CORPUS_DIR")/manasight-parser"
cd "$PARSER_DIR" && MANASIGHT_TEST_LOGS=/tmp/harvest-work/ cargo test smoke_test_router_real_logs -- --nocapture 2>&1
```

Extract the report section for the new file: total entries, routed count, unknown count, timestamp failures, event type breakdown.

### Step 9: Ask user for session details

Use AskUserQuestion to gather session info. Adapt questions based on what events the smoke test found:

**Always ask:**
- What format/game mode? (e.g., Sealed, Pick2 Draft, Standard Bo1)
- Notes about this session?

**If draft events detected:** What archetype/colors?

**If game events detected:** Record (W-L)? Per-game opponent colors / result / play-or-draw?

**If no game events:** Confirm "no games — pre-game / lobby / deck-build only?"

### Step 10: Update sessions doc

Edit `sessions.md` in `$CORPUS_DIR`:

1. Add a new session section at the end of the Sessions list:

```markdown
---

### Session YYYY-MM-DD_HHMM[suffix]

[User's notes or brief description]

| Field | Value |
|-------|-------|
| Date | YYYY-MM-DD |
| MTGA Version | TBD |
| Source | `UTC_Log - MM-DD-YYYY HH.MM.SS.log` (archive) |
| Raw file | `session_YYYY-MM-DD_HHMM[suffix].log` |
| Format | [from user] |
| Record | [from user, or "N/A — pre-match only"] |
| Session log size (raw, post-strip) | X (Y MB) |
| Session log size (gzip) | X (~Y MB) |
| Compression ratio | ~X:1 |

#### Parser Coverage

| Metric | Value |
|--------|------:|
| Total entries | X |
| Routed | X |
| Unknown | X |
| Timestamp failures | X |

#### Event Breakdown

| Event Type | Count |
|------------|------:|
| ClientAction | X |
| ... | ... |
```

If game details were provided, include the Games table as in existing sessions.

2. Update the Summary table at the top of the file with the new session row.

### Step 11: Clean up

```bash
rm -rf /tmp/harvest-work /tmp/scrub-bin /tmp/scrub-*.tar.gz
```

### Step 12: Report

```
## Log Harvest Complete

- Session: <session-name>
- Source: UTC_Log - MM-DD-YYYY HH.MM.SS.log (archive)
- Raw (post-strip): <size>
- Compressed: <size> (<ratio>:1)
- Corpus PR: <PR URL>
- Parser coverage: <routed>/<total> entries (<percent>%)
- Event types: <count> distinct types detected

### Event Breakdown
| Event Type | Count |
|------------|------:|
| ... | ... |

Corpus PR: <PR URL> (merge to trigger release + parser baseline update)
Sessions updated: manasight-corpus/sessions.md
```
