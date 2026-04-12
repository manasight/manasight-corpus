# Session Log

Ongoing log of per-session measurements from MTGA's `Player.log`.

## How to update

This file is updated automatically by the `/harvest-log` command when adding new logs to the corpus. Each session gets a summary row in the table below and a detailed section with parser coverage and event breakdowns.

To add a session manually, copy the template below and fill in the fields.

## Template

<!-- Copy this block to start a new measured session -->
<!--
### Session YYYY-MM-DD_HHMM[suffix]

[Description]

| Field | Value |
|-------|-------|
| Date | YYYY-MM-DD |
| MTGA Version | TBD |
| Raw file | `session_YYYY-MM-DD_HHMM[suffix].log` |
| Format | |
| Record | |
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
| ... | ... |

#### Games

| # | Format | Your Archetype | Opponent Colors | Result | Turns | P/D | Notes |
|---|--------|----------------|----------------|--------|:-----:|:---:|-------|
| 1 | | | | | | | |
-->

## Summary

| Date | Raw File | Description |
|------|----------|-------------|
| 2026-02-22 | `session_2026-02-22_0000_ecl-premier-bg-elves.log` | ECL Premier Draft games (1-3), BG Elves |
| 2026-02-22 | `session_2026-02-22_0000_ecl-premier-uw-merfolk.log` | ECL Premier Draft + games (1-3), UW Merfolk |
| 2026-02-23 | `session_2026-02-23_0000_standard-bo1.log` | 2 Standard Bo1 games (Mono-W Aggro, UB Dimir) |
| 2026-02-23 | `session_2026-02-23_game01.log` | Segment: Standard Bo1 game 1 |
| 2026-02-23 | `session_2026-02-23_game02.log` | Segment: Standard Bo1 game 2 |
| 2026-03-05 | `session_2026-03-05_0000.log` | *(undocumented)* |
| 2026-03-06 | `session_2026-03-06_0000_pick2-draft-only.log` | Pick2 Draft only (no games) |
| 2026-03-06 | `session_2026-03-06_0000_pick2-draft-game.log` | Pick2 Draft game 1(0-1) |
| 2026-03-08 | `session_2026-03-08_1103_standard-bo1-log-rotated.log` | Standard Bo1 debug session (LogFileRotated), 1W |
| 2026-03-11 | `session_2026-03-11_1847_quick-draft-selesnya.log` | Quick Draft (WG Selesnya), 0-1 |
| 2026-03-11 | `session_2026-03-11_2124_trad-standard-bo3.log` | Traditional Standard Bo3, 2-0 |
| 2026-03-15 | `session_2026-03-15_1157_detailed_logs_disabled.log` | Standard Bo1, 1W — **detailed logs disabled** |
| 2026-03-17 | `session_2026-03-17_1933_standard-bo1-debug.log` | Standard Bo1 debug session, 1W |
| 2026-03-21 | `session_2026-03-21_0905_standard-bo3-skeleton.log` | Standard BO3, 0-2 (Skeleton deck) |
| 2026-04-11 | `session_2026-04-11_1108.log` | Standard Bo3, 0-2 |
| 2026-04-11 | `session_2026-04-11_1542_adapter-disable.log` | Connection health: adapter disable tests B1/B2/B3 (#528) |
| 2026-04-11 | `session_2026-04-11_1835_firewall.log` | Connection health: firewall tests C1/C2/E4 (#528) |
| 2026-04-11 | `session_2026-04-11_1900_clumsy-directional.log` | Connection health: clumsy directional D1/D3/D2 + reconnect edge case (#528) |

---

## Sessions

### Session 2026-03-06_b

Single game following a Pick2 draft. Lost after 15 turns.

| Field | Value |
|-------|-------|
| Date | 2026-03-06 |
| MTGA Version | TBD |
| Raw file | `session_2026-03-06_0000_pick2-draft-game.log` |
| Format | Pick2 Draft |
| Record | 0-1 |
| Session log size (raw) | 12,048,985 (11.5 MB) |
| Session log size (gzip) | 833,697 (~0.8 MB) |
| Compression ratio | ~14.5:1 |

#### Parser Coverage

| Metric | Value |
|--------|------:|
| Total entries | 2,305 |
| Routed | 2,225 |
| Unknown | 80 |
| Timestamp failures | 55 |

#### Event Breakdown

| Event Type | Count |
|------------|------:|
| ClientAction | 1,157 |
| EventLifecycle | 1 |
| GameResult | 2 |
| GameState | 1,657 |
| Inventory | 2 |
| MatchState | 2 |
| Rank | 2 |
| Session | 2 |

---

### Session 2026-03-06

Pick2 draft only (no games played).

| Field | Value |
|-------|-------|
| Date | 2026-03-06 |
| MTGA Version | TBD |
| Raw file | `session_2026-03-06_0000_pick2-draft-only.log` |
| Format | Pick2 Draft |
| Session log size (raw) | 3,276,640 (3.1 MB) |

---

### Session 2026-02-23

| Field | Value |
|-------|-------|
| Date | 2026-02-23 |
| MTGA Version | TBD |
| Raw file | `session_2026-02-23_0000_standard-bo1.log` |
| Baseline log size | 3,121,214 (3.0 MB) |
| Total games played | 2 |
| Session log size (raw) | 16,111,137 (15.4 MB) |
| Session log size (gzip) | 1,153,434 (~1.1 MB) |
| Compression ratio | ~14.0:1 |

#### Games

| # | Format | Your Archetype | Opponent Colors | Result | Turns | P/D | Duration (min) | Log Before | Log After | Log Delta | Notes |
|---|--------|----------------|----------------|--------|:-----:|:---:|:--------------:|-----------:|----------:|----------:|-------|
| 1 | Standard Bo1 | Mono-W Aggro | G | Win | 8 | Draw | 2 | 3,274,826 | 4,365,561 | 1,090,735 | Opponent conceded |
| 2 | Standard Bo1 | UB Dimir Excruciator | UG Simic Ouroboroid | Loss | 14 | Play | 7 | 9,588,903 | 16,094,651 | 6,505,748 | |

---

### Session 2026-02-22_b (Player.log)

Harvested retroactively. Includes a full ECL Premier Draft (draft + 4 games).
Record: 1-3.

| Field | Value |
|-------|-------|
| Date | 2026-02-22 |
| MTGA Version | TBD |
| Raw file | `session_2026-02-22_0000_ecl-premier-uw-merfolk.log` |
| Format | ECL Premier Draft |
| Record | 1-3 |
| Session log size (raw) | 23,726,538 (22.6 MB) |
| Session log size (gzip) | 1,638,400 (~1.6 MB) |
| Compression ratio | ~14.4:1 |

#### Games

| # | Format | Your Archetype | Opponent Colors | Result | Turns | P/D | Notes |
|---|--------|----------------|----------------|--------|:-----:|:---:|-------|
| 1 | ECL Premier Draft Bo1 | UW Merfolk | WBRG | Win | 11 | Draw | |
| 2 | ECL Premier Draft Bo1 | UW Merfolk | BG | Loss | 6 | Play | |
| 3 | ECL Premier Draft Bo1 | UW Merfolk | BR | Loss | 9 | Play | |
| 4 | ECL Premier Draft Bo1 | UW Merfolk | BG | Loss | 8 | Draw | |

---

### Session 2026-02-22_a (Player-prev.log)

Harvested retroactively. Includes games from an ECL Premier Draft (draft may have been done in an earlier session).
Record: 1-3.

| Field | Value |
|-------|-------|
| Date | 2026-02-22 |
| MTGA Version | TBD |
| Raw file | `session_2026-02-22_0000_ecl-premier-bg-elves.log` |
| Format | ECL Premier Draft |
| Record | 1-3 |
| Session log size (raw) | 31,194,170 (29.8 MB) |
| Session log size (gzip) | 2,252,800 (~2.2 MB) |
| Compression ratio | ~13.6:1 |

#### Games

| # | Format | Your Archetype | Opponent Colors | Result | Turns | P/D | Notes |
|---|--------|----------------|----------------|--------|:-----:|:---:|-------|
| 1 | ECL Premier Draft Bo1 | BG Elves | BRG | Win | 12 | Play | |
| 2 | ECL Premier Draft Bo1 | BG Elves | UBR | Loss | 9 | Play | |
| 3 | ECL Premier Draft Bo1 | BG Elves | WG | Loss | 7 | Draw | |
| 4 | ECL Premier Draft Bo1 | BG Elves | UBG | Loss | 11 | Draw | |

---

### Session 2026-03-08_1103

Debug session testing LogFileRotated event handling. Verified log rotation detection works correctly.

| Field | Value |
|-------|-------|
| Date | 2026-03-08 |
| MTGA Version | 2026.57.10.11536 |
| Raw file | `session_2026-03-08_1103_standard-bo1-log-rotated.log` |
| Format | Standard Bo1 |
| Record | 1W |
| Session log size (raw) | 9,859,259 (9.4 MB) |
| Session log size (gzip) | 711,251 (~696 KB) |
| Compression ratio | ~13.9:1 |

#### Parser Coverage

| Metric | Value |
|--------|------:|
| Total entries | 460 |
| Routed | 363 |
| Unknown | 97 |
| Timestamp failures | 65 |

#### Event Breakdown

| Event Type | Count |
|------------|------:|
| ClientAction | 254 |
| EventLifecycle | 2 |
| GameResult | 2 |
| GameState | 307 |
| Inventory | 3 |
| MatchState | 2 |
| Rank | 3 |
| Session | 2 |

---

### Session 2026-03-11_1847

Quick Draft session, WG Selesnya. Lost game 1.

| Field | Value |
|-------|-------|
| Date | 2026-03-11 |
| MTGA Version | TBD |
| Raw file | `session_2026-03-11_1847_quick-draft-selesnya.log` |
| Format | Quick Draft |
| Archetype | WG (Selesnya) |
| Record | 0-1 |
| Session log size (raw) | 16,424,517 (~15.7 MB) |
| Session log size (gzip) | 1,257,914 (~1.2 MB) |
| Compression ratio | ~13.1:1 |

#### Games

| Game | Opponent Colors | Result | Play/Draw |
|------|----------------|--------|-----------|
| 1 | Unknown | Loss | Unknown |

#### Parser Coverage

| Metric | Value |
|--------|------:|
| Total entries | 1,842 |
| Routed | 1,654 |
| Unknown | 188 |
| Timestamp failures | 111 |

#### Event Breakdown

| Event Type | Count |
|------------|------:|
| ClientAction | 740 |
| EventLifecycle | 3 |
| GameResult | 1 |
| GameState | 1,334 |
| Inventory | 3 |
| MatchState | 3 |
| Rank | 3 |
| Session | 2 |

---

### Session 2026-03-11_2124

Traditional Standard Bo3, 2-0.

| Field | Value |
|-------|-------|
| Date | 2026-03-11 |
| MTGA Version | TBD |
| Raw file | `session_2026-03-11_2124_trad-standard-bo3.log` |
| Format | Traditional Standard (Bo3) |
| Record | 2-0 |
| Session log size (raw) | 11,460,803 (~10.9 MB) |
| Session log size (gzip) | 785,313 (~767 KB) |
| Compression ratio | ~14.6:1 |

#### Games

| Game | Opponent Colors | Result | Play/Draw |
|------|----------------|--------|-----------|
| 1 | Unknown | Win | Unknown |
| 2 | Unknown | Win | Unknown |

#### Parser Coverage

| Metric | Value |
|--------|------:|
| Total entries | 1,158 |
| Routed | 1,085 |
| Unknown | 73 |
| Timestamp failures | 48 |

#### Event Breakdown

| Event Type | Count |
|------------|------:|
| ClientAction | 405 |
| EventLifecycle | 2 |
| GameResult | 2 |
| GameState | 1,093 |
| Inventory | 2 |
| MatchState | 2 |
| Rank | 2 |
| Session | 2 |

---

### Session 2026-03-15_1157_detailed_logs_disabled

Captured with Arena's "Detailed Logs (Plugin Support)" setting disabled to test parser behavior without structured headers. One Standard Bo1 game was played (win), but zero game events were parseable.

| Field | Value |
|-------|-------|
| Date | 2026-03-15 |
| MTGA Version | 2026.57.20.11631 |
| Raw file | `session_2026-03-15_1157_detailed_logs_disabled.log` |
| Format | Standard Bo1 |
| Record | 1W |
| Detailed Logs | **DISABLED** |
| Session log size (raw) | 158,711 (~155 KB) |
| Session log size (gzip) | 5,204 (~5 KB) |
| Compression ratio | ~30.5:1 |

#### Parser Coverage

| Metric | Value |
|--------|------:|
| Total entries | 15 |
| Routed | 0 |
| Unknown | 15 |
| Timestamp failures | 15 |

#### Event Breakdown

No events — all entries are headerless lines discarded by the entry splitter.

#### Notes

- Line 24: `DETAILED LOGS: DISABLED`
- Match state changes visible (`STATE CHANGED` lines) but not parseable without structured headers
- DuelScene loaded/unloaded — a full game was played
- Log size is ~100x smaller than a typical detailed-logs-enabled session (~155 KB vs ~10-15 MB)
- Compression ratio (~30.5:1) is much higher than normal (~14:1) due to repetitive unstructured text

---

### Session 2026-03-17_1933

Debug session testing a CI build. Standard Bo1, won the game.

| Field | Value |
|-------|-------|
| Date | 2026-03-17 |
| MTGA Version | TBD |
| Raw file | `session_2026-03-17_1933_standard-bo1-debug.log` |
| Format | Standard Bo1 |
| Record | 1-0 |
| Session log size (raw) | 12,975,108 (12.4 MB) |
| Session log size (gzip) | 912,681 (~0.9 MB) |
| Compression ratio | ~14.2:1 |

#### Parser Coverage

| Metric | Value |
|--------|------:|
| Total entries | 645 |
| Routed | 532 |
| Unknown | 113 |
| Timestamp failures | 77 |

#### Event Breakdown

| Event Type | Count |
|------------|------:|
| ClientAction | 393 |
| DetailedLoggingStatus | 1 |
| GameResult | 2 |
| GameState | 456 |
| Inventory | 3 |
| MatchState | 4 |
| Rank | 3 |
| Session | 3 |

---

### Session 2026-03-21_0905

First BO3 session. Skeleton deck. Lost 0-2.

| Field | Value |
|-------|-------|
| Date | 2026-03-21 |
| MTGA Version | TBD |
| Raw file | `session_2026-03-21_0905_standard-bo3-skeleton.log` |
| Format | Standard BO3 |
| Record | 0-2 |
| Session log size (raw) | 8,398,236 (8.0 MB) |
| Session log size (gzip) | 590,417 (~0.6 MB) |
| Compression ratio | ~14:1 |

#### Parser Coverage

| Metric | Value |
|--------|------:|
| Total entries | 712 |
| Routed | 638 |
| Unknown | 74 |
| Timestamp failures | 50 |

#### Event Breakdown

| Event Type | Count |
|------------|------:|
| ClientAction | 325 |
| DetailedLoggingStatus | 1 |
| EventLifecycle | 2 |
| GameResult | 2 |
| GameState | 671 |
| Inventory | 2 |
| MatchState | 2 |
| Rank | 2 |
| Session | 1 |

---

### Session 2026-04-11_1108

Standard Bo3, lost 0-2. Opponent played a map token in game 1.

| Field | Value |
|-------|-------|
| Date | 2026-04-11 |
| MTGA Version | TBD |
| Raw file | `session_2026-04-11_1108.log` |
| Format | Standard Bo3 |
| Record | 0-2 |
| Session log size (raw) | 15,086,275 (14.4 MB) |
| Session log size (gzip) | 1,036,930 (~1.0 MB) |
| Compression ratio | ~14.5:1 |

#### Parser Coverage

| Metric | Value |
|--------|------:|
| Total entries | 1,872 |
| Routed | 1,770 |
| Unknown | 102 |
| Timestamp failures | 67 |

#### Event Breakdown

| Event Type | Count |
|------------|------:|
| ClientAction | 521 |
| DetailedLoggingStatus | 1 |
| EventLifecycle | 2 |
| GameResult | 2 |
| GameState | 1,762 |
| Inventory | 2 |
| MatchState | 2 |
| Rank | 2 |
| Session | 1 |

---

### Session 2026-04-11_1542_adapter-disable

Connection health log data collection ([manasight-docs#528](https://github.com/manasight/manasight-docs/issues/528), Log 1). Three adapter-disable disconnect tests: B1 (60s, bot), B2 (1s, bot), B3 (10s, ranked). All tests showed instant "Connection Lost" dialog on adapter disable, forfeit on reconnect (kicked to main menu).

| Field | Value |
|-------|-------|
| Date | 2026-04-11 |
| MTGA Version | TBD |
| Raw file | `session_2026-04-11_1542_adapter-disable.log` |
| Format | Standard Bo1 (2 bot + 1 ranked) |
| Record | N/A — disconnect testing |
| Session log size (raw) | 14,602,103 (13.9 MB) |
| Session log size (gzip) | 1,077,147 (~1.0 MB) |
| Compression ratio | ~13.5:1 |

#### Test Details

| Test | Method | Duration | Match | Detection | After reconnect |
|------|--------|----------|-------|-----------|-----------------|
| B1 | Wi-Fi adapter disable | 60s | Bot | Instant | Forfeit, kicked to menu |
| B2 | Wi-Fi adapter disable | 1s | Bot | Instant | Forfeit, kicked to menu |
| B3 | Wi-Fi adapter disable | 10s | Ranked | Instant | Forfeit, kicked to menu |

#### Parser Coverage

| Metric | Value |
|--------|------:|
| Total entries | 322 |
| Routed | 95 |
| Unknown | 227 |
| Timestamp failures | 198 |

#### Event Breakdown

| Event Type | Count |
|------------|------:|
| ClientAction | 21 |
| DetailedLoggingStatus | 1 |
| EventLifecycle | 2 |
| GameResult | 1 |
| GameState | 89 |
| Inventory | 5 |
| MatchState | 5 |
| Rank | 5 |
| Session | 25 |

---

### Session 2026-04-11_1835_firewall

Connection health log data collection ([manasight-docs#528](https://github.com/manasight/manasight-docs/issues/528), Log 2). Three firewall disconnect tests: C1 (bot), C2 (ranked), E4 (pre-match). All tests showed "Waiting for server" within a few seconds, then auto-kicked to main menu (~2s). No "Connection Lost" dialog (unlike adapter-disable tests).

Note: first C1 attempt used `-LocalPort` instead of `-RemotePort` and had no effect. Fixed to `-RemotePort 30003` for all subsequent tests. The failed attempt is also in the log.

| Field | Value |
|-------|-------|
| Date | 2026-04-11 |
| MTGA Version | TBD |
| Raw file | `session_2026-04-11_1835_firewall.log` |
| Format | Standard Bo1 (1 bot + 1 ranked + 1 pre-match) |
| Record | N/A — disconnect testing |
| Session log size (raw) | 11,876,842 (11.3 MB) |
| Session log size (gzip) | 885,724 (~0.8 MB) |
| Compression ratio | ~13.4:1 |

#### Test Details

| Test | Method | Match | Detection | Behavior |
|------|--------|-------|-----------|----------|
| C1 | Firewall block remote port 30003 (both) | Bot | ~15s | "Waiting for server" → auto-kicked to menu |
| C2 | Firewall block remote port 30003 (both) | Ranked | ~3s | "Waiting for server" → auto-kicked to menu |
| E4 | Firewall block before queueing | Pre-match | instant | Queue starts → "Waiting for server" → auto-kicked to menu |

#### Parser Coverage

| Metric | Value |
|--------|------:|
| Total entries | 313 |
| Routed | 150 |
| Unknown | 163 |
| Timestamp failures | 135 |

#### Event Breakdown

| Event Type | Count |
|------------|------:|
| ClientAction | 81 |
| DetailedLoggingStatus | 1 |
| EventLifecycle | 2 |
| GameState | 164 |
| Inventory | 4 |
| MatchState | 2 |
| Rank | 4 |
| Session | 14 |

---

### Session 2026-04-11_1900_clumsy-directional

Connection health log data collection ([manasight-docs#528](https://github.com/manasight/manasight-docs/issues/528), Log 3). Clumsy directional drop tests: D1 (inbound, bot), D3 (outbound, bot), D2 (inbound, ranked). Also captured a broken-reconnect edge case after D2 where Arena reconnected to the active match but the UI was frozen, resulting in a timeout loss.

| Field | Value |
|-------|-------|
| Date | 2026-04-11 |
| MTGA Version | TBD |
| Raw file | `session_2026-04-11_1900_clumsy-directional.log` |
| Format | Standard Bo1 (2 bot + 1 ranked + 1 broken reconnect) |
| Record | N/A — disconnect testing |
| Session log size (raw) | 14,737,598 (14.0 MB) |
| Session log size (gzip) | 1,101,441 (~1.0 MB) |
| Compression ratio | ~13.3:1 |

#### Test Details

| Test | Method | Match | Silence Duration | Behavior |
|------|--------|-------|:----------------:|----------|
| D1 | Inbound drop 45s | Bot | ~29s | Can't act ~20s → "Waiting for server" → kicked |
| D3 | Outbound drop 45s | Bot | ~14s | Land played (optimistic) → froze → kicked |
| D2 | Inbound drop 45s | Ranked | ~22s | Spell cast → hung ~20s → kicked |
| — | Broken reconnect | Ranked | — | Reconnected to active match, UI frozen, timed out |

#### Parser Coverage

| Metric | Value |
|--------|------:|
| Total entries | 383 |
| Routed | 165 |
| Unknown | 218 |
| Timestamp failures | 188 |

#### Event Breakdown

| Event Type | Count |
|------------|------:|
| ClientAction | 48 |
| DetailedLoggingStatus | 1 |
| EventLifecycle | 4 |
| GameResult | 1 |
| GameState | 154 |
| Inventory | 5 |
| MatchState | 5 |
| Rank | 5 |
| Session | 26 |
