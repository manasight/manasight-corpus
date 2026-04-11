---
description: Save MTGA Player.log, sanitize, and open a corpus PR
argument-hint: [session-suffix]
allowed-tools: Bash(cp:*), Bash(ls:*), Bash(stat:*), Bash(gzip:*), Bash(gunzip:*), Bash(cat:*), Bash(cd:*), Bash(uname:*), Bash(wc:*), Bash(date:*), Bash(tar:*), Bash(gh:*), Bash(mkdir:*), Bash(rm:*), Bash(git:*), Bash(cargo:*), Bash(grep:*), Bash(sha256sum:*), Bash(python3:*), Bash(chmod:*), Bash(find:*), Read, Edit, Write, Grep, Glob, AskUserQuestion
---

# Harvest Log

Save the current MTGA `Player.log`, sanitize it, and open a PR in `manasight-corpus`. On merge, `publish-corpus.yml` creates a release automatically. Also runs a local parser smoke test for immediate coverage feedback and updates `sessions.md`.

## Arguments

- `$ARGUMENTS`: Optional session suffix (e.g., `_draft`, `_game01`). If omitted, no suffix is added.

## Instructions

### Step 1: Determine Session Name

Generate the session filename:
- Base: `session_YYYY-MM-DD_HHMM` (today's date + current hour/minute in local time)
- If `$ARGUMENTS` is provided, append it: `session_YYYY-MM-DD_HHMM$ARGUMENTS`
- File extension: `.log`

Example: `session_2026-03-06_1830.log` or `session_2026-03-06_1830_draft.log`

### Step 2: Copy Player.log

The MTGA Player.log lives at:
- **WSL path:** `/mnt/c/Users/<WIN_USER>/AppData/LocalLow/Wizards Of The Coast/MTGA/Player.log`
- **macOS path:** `~/Library/Logs/Wizards Of The Coast/MTGA/Player.log`

Detect the platform, resolve the user's home directory, and copy to a temp working directory:
```bash
mkdir -p /tmp/harvest-work
PLATFORM=$(uname -s)
if [ "$PLATFORM" = "Linux" ] && grep -qi microsoft /proc/version 2>/dev/null; then
  # WSL — resolve Windows username
  WIN_USER=$(powershell.exe -NoProfile -Command '[Environment]::UserName' 2>/dev/null | tr -d '\r')
  cp "/mnt/c/Users/$WIN_USER/AppData/LocalLow/Wizards Of The Coast/MTGA/Player.log" /tmp/harvest-work/<session-name>.log
else
  # macOS
  cp ~/Library/Logs/Wizards\ Of\ The\ Coast/MTGA/Player.log /tmp/harvest-work/<session-name>.log
fi
```

Record the raw file size in bytes and human-readable form.

### Step 3: Sanitize

Download the `scrub` binary from the latest `manasight-parser` release and sanitize the log:

```bash
# Detect platform
PLATFORM=$(uname -s)
case "$PLATFORM" in
  Linux*)  ASSET="scrub-linux-x86_64.tar.gz" ;;
  Darwin*) ARCH=$(uname -m); if [ "$ARCH" = "arm64" ]; then ASSET="scrub-macos-aarch64.tar.gz"; else ASSET="scrub-macos-x86_64.tar.gz"; fi ;;
esac

# Download and extract
gh release download --repo manasight/manasight-parser --pattern "$ASSET" --dir /tmp --clobber
mkdir -p /tmp/scrub-bin
tar xzf /tmp/$ASSET -C /tmp/scrub-bin
SCRUB=$(find /tmp/scrub-bin -name scrub -type f | head -1)
chmod +x "$SCRUB"

# Sanitize in place
"$SCRUB" < /tmp/harvest-work/<session-name>.log > /tmp/harvest-work/<session-name>.scrubbed.log
mv /tmp/harvest-work/<session-name>.scrubbed.log /tmp/harvest-work/<session-name>.log
```

### Step 4: Compress

```bash
gzip -k /tmp/harvest-work/<session-name>.log
```

Record the compressed file size and compression ratio.

### Step 5: Check for Conflicts

Check if a file with this session name already exists in the corpus:
```bash
ls corpus/<session-name>.log.gz 2>/dev/null
```

If it exists, ask the user whether to overwrite or pick a different suffix.

### Step 6: Commit to Branch and Open PR

1. **Create a branch in manasight-corpus:**
```bash
cd "$(git rev-parse --show-toplevel)"
git checkout main && git pull
git checkout -b add-<session-name>
```

2. **Copy the compressed log into the corpus:**
```bash
cp /tmp/harvest-work/<session-name>.log.gz corpus/
```

3. **Update `smoke-corpus-manifest.toml`** — compute sha256 and size from the **uncompressed sanitized** log and append:
```bash
sha256sum /tmp/harvest-work/<session-name>.log | awk '{print $1}'
stat --format='%s' /tmp/harvest-work/<session-name>.log
```
Append a new `[[files]]` block:
```toml
[[files]]
filename      = "<session-name>.log"
sha256        = "<sha256-from-above>"
size_bytes    = <size-from-above>
date_captured = "YYYY-MM-DD"
```

4. **Commit and push:**
```bash
git add corpus/<session-name>.log.gz smoke-corpus-manifest.toml sessions.md
git commit -m "Add <session-name> to corpus"
git push -u origin add-<session-name>
```

5. **Open PR:**
```bash
gh pr create --repo manasight/manasight-corpus \
  --title "Add <session-name> to corpus" \
  --body "Add sanitized Player.log from <date>.

Raw size: <raw-size>
Compressed: <gzip-size> (<ratio>:1)

CI will validate sanitization via check-log-sanitization.yml.
On merge, publish-corpus.yml creates a new release automatically."
```

6. Report the PR URL.

### Step 7: Run Local Smoke Test

Run the parser router-level smoke test against the **sanitized uncompressed** log for immediate coverage feedback:

```bash
PARSER_DIR="$(git rev-parse --show-toplevel)/../manasight-parser"
cd "$PARSER_DIR" && MANASIGHT_TEST_LOGS=/tmp/harvest-work/ cargo test smoke_test_router_real_logs -- --nocapture 2>&1
```

From the output, extract the report section for the new file. Parse out:
- Total entries
- Routed count
- Unknown count
- Timestamp failures
- Event type breakdown (each type and its count)

### Step 8: Ask User for Session Details

Use AskUserQuestion to gather information about the session. Ask all relevant questions in a single prompt. Adapt the questions based on what events the smoke test found (e.g., if DraftHuman events exist, ask about the draft; if GameResult events exist, ask about games played):

**Always ask:**
- What format/game mode was this? (e.g., Pick2 Draft, Premier Draft, Standard Bo1, etc.)
- Any notes about this session?

**If draft events detected** (DraftHuman, DraftBot, DraftComplete):
- What archetype/colors did you draft?

**If game events detected** (GameResult, MatchState with count > 0):
- What was your record (W-L)?
- For each game: opponent colors, result, who was on play/draw?

**If no game events detected:**
- Confirm: "No games detected in the log -- draft/lobby only?"

### Step 9: Update Sessions Doc

Edit `sessions.md` in the repo root (same branch as step 6):

1. **Add a new session section** at the end of the Sessions list, following the existing format:

```markdown
---

### Session YYYY-MM-DD_HHMM[suffix]

[User's notes or brief description]

| Field | Value |
|-------|-------|
| Date | YYYY-MM-DD |
| MTGA Version | TBD |
| Raw file | `session_YYYY-MM-DD_HHMM[suffix].log` |
| Format | [from user] |
| Record | [from user, or "N/A -- draft only"] |
| Session log size (raw) | X (Y MB) |
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
| DraftHuman | X |
| ... | ... |
```

If game details were provided, include the Games table as in existing sessions.

2. **Update the Summary table** at the top of the file with the new session row.

### Step 10: Clean Up

```bash
rm -rf /tmp/harvest-work /tmp/scrub-bin /tmp/scrub-*.tar.gz
```

### Step 11: Report

Present a summary:

```
## Log Harvest Complete

- Session: <session-name>
- Player.log: <size> (<compressed size> gzip, <ratio>:1)
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
