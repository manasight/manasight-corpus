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
| 2026-04-11 | `session_2026-04-11_1930_clumsy-outbound-ranked.log` | Connection health: clumsy outbound D4 (#528) |
| 2026-04-12 | `session_2026-04-12_0844_edge-cases.log` | Connection health: edge cases E1/E2 (#528) |
| 2026-04-12 | `session_2026-04-12_1010_pfctl-bidirectional.log` | Connection health: macOS pfctl bidirectional C1/C2/E4 (#529) |
| 2026-04-12 | `session_2026-04-12_1045_pfctl-directional.log` | Connection health: macOS pfctl directional D1/D3/D2/D4 + mid-match recovery (#529) |
| 2026-04-12 | `session_2026-04-12_1145_wifi-disable.log` | Connection health: macOS Wi-Fi disable B1/B2/B3 — no RST, only B1 (60s) disconnected (#529) |
| 2026-04-12 | `session_2026-04-12_1240_edge-cases.log` | Connection health: macOS edge cases E1/E2 + broken-reconnect during Bo3 sideboard (#529) |
| 2026-04-14 | `session_2026-04-14_1720.log` | Inactivity-timer investigation — bot / Play / Ladder BO1 auto-concede mechanics |
| 2026-04-25 | `session_2026-04-25_0841_deck-management-store.log` | PR #154 corpus coverage — deck CRUD, store/inbox/pack actions, server-kicked disconnect, 1 conceded Bo1 |
| 2026-04-26 | `session_2026-04-26_2209.log` | Historic Bo1 (2-4) — live repro session for action log destruction-attribution and event-ordering bugs |
| 2026-04-27 | `session_2026-04-27_2230.log` | Standard Bo1 (1-2) — verification session for PR #498/#499/#500 action log attribution fixes |
| 2026-04-29 | `session_2026-04-29_2128.log` | Alchemy Bo1 (2-0) — Conjure-mechanic capture session |

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

---

### Session 2026-04-11_1930_clumsy-outbound-ranked

Connection health log data collection ([manasight-docs#528](https://github.com/manasight/manasight-docs/issues/528), D4). Single clumsy outbound drop test on a ranked match. User saw opponent play a card, then froze 20-30s before being kicked to main screen.

| Field | Value |
|-------|-------|
| Date | 2026-04-11 |
| MTGA Version | TBD |
| Raw file | `session_2026-04-11_1930_clumsy-outbound-ranked.log` |
| Format | Standard Bo1 (1 ranked) |
| Record | N/A — disconnect testing |
| Session log size (raw) | 6,260,667 (5.9 MB) |
| Session log size (gzip) | 470,045 (~0.4 MB) |
| Compression ratio | ~13.3:1 |

#### Test Details

| Test | Method | Match | Behavior |
|------|--------|-------|----------|
| D4 | Outbound drop 45s | Ranked | Saw opponent's card → froze 20-30s → kicked to menu |

#### Parser Coverage

| Metric | Value |
|--------|------:|
| Total entries | 182 |
| Routed | 100 |
| Unknown | 82 |
| Timestamp failures | 62 |

#### Event Breakdown

| Event Type | Count |
|------------|------:|
| ClientAction | 45 |
| DetailedLoggingStatus | 1 |
| EventLifecycle | 2 |
| GameState | 115 |
| Inventory | 2 |
| MatchState | 1 |
| Rank | 2 |
| Session | 4 |

---

### Session 2026-04-12_0844_edge-cases

Connection health log data collection ([manasight-docs#528](https://github.com/manasight/manasight-docs/issues/528), Log 4). Edge case adapter-disable tests: E1 (mulligan phase, bot match), E2 (sideboarding phase, Bo3 ranked). Both showed identical behavior to B-series tests — instant "Connection Lost" dialog, forfeit on reconnect. E3 (between games) skipped as redundant. Includes a full Bo3 game 1 before E2.

| Field | Value |
|-------|-------|
| Date | 2026-04-12 |
| MTGA Version | TBD |
| Raw file | `session_2026-04-12_0844_edge-cases.log` |
| Format | 1 bot match (E1) + 1 Bo3 ranked game 1 + sideboard disconnect (E2) |
| Record | N/A — disconnect testing |
| Session log size (raw) | 12,238,957 (11.6 MB) |
| Session log size (gzip) | 875,904 (~0.8 MB) |
| Compression ratio | ~13.9:1 |

#### Test Details

| Test | Method | Phase | Behavior |
|------|--------|-------|----------|
| E1 | Adapter disable 10s | Mulligan (bot) | Instant "Connection Lost" → forfeit |
| E2 | Adapter disable 10s | Sideboarding (Bo3 ranked) | Instant "Connection Lost" → forfeit |
| E3 | — | Between games | Skipped — identical behavior confirmed |

#### Parser Coverage

| Metric | Value |
|--------|------:|
| Total entries | 1,381 |
| Routed | 1,231 |
| Unknown | 150 |
| Timestamp failures | 128 |

#### Event Breakdown

| Event Type | Count |
|------------|------:|
| ClientAction | 476 |
| DetailedLoggingStatus | 1 |
| EventLifecycle | 2 |
| GameResult | 1 |
| GameState | 1,084 |
| Inventory | 3 |
| MatchState | 2 |
| Rank | 3 |
| Session | 12 |

---

### Session 2026-04-12_1010_pfctl-bidirectional

Connection health macOS test session — pfctl bidirectional block tests (C1, C2, E4) for [#529](https://github.com/manasight/manasight-docs/issues/529). First macOS disconnect data. Key finding: macOS TCP retransmit timeouts are ~3x longer than Windows.

| Field | Value |
|-------|-------|
| Date | 2026-04-12 |
| Platform | macOS Tahoe 26.3, Apple Silicon (aarch64), Wi-Fi (en1) |
| MTGA Version | Current (native macOS client via Epic) |
| Raw file | `session_2026-04-12_1010_pfctl-bidirectional.log` |
| Format | Connection health testing — bot + ranked Standard Bo1 |
| Record | N/A — disconnect tests |
| Session log size (raw) | 12,490,831 (11.9 MB) |
| Session log size (gzip) | 919,798 (~0.9 MB) |
| Compression ratio | ~13.6:1 |

#### Test Results

| Test | Method | Match | Detection | Behavior |
|------|--------|-------|:---------:|----------|
| C1-mac-a | pfctl both 30s | Bot | **None** | Froze 30s → auto-resumed, no disconnect |
| C1-mac-b | pfctl both 60s | Bot | **~49s** | "Waiting for server" → kicked to menu |
| C2 | pfctl both 75s | Ranked | **~29s** | Rope warning → "Waiting for server" → kicked |
| E4 | pfctl both 75s (pre-match) | Pre-match | **~79s** | "Waiting for server" frozen → kicked after block lifted |

#### Key Findings

- **30s bidirectional block = no disconnect on macOS** (Windows: 3-15s detection)
- **macOS SocketException 10060** (connection timed out) vs Windows 10054 (connection reset)
- **E4 on macOS: ~79s to fail** (connect timeout) vs Windows: near-instant (WSAEACCES)
- **closeType:9 for E4** matches Windows (pre-match failure code)
- **FrontDoor (port 30010) stayed alive** during all matchdoor blocks

#### Parser Coverage

| Metric | Value |
|--------|------:|
| Total entries | 412 |
| Routed | 238 |
| Unknown | 174 |
| Timestamp failures | 142 |

#### Event Breakdown

| Event Type | Count |
|------------|------:|
| ClientAction | 117 |
| DetailedLoggingStatus | 1 |
| EventLifecycle | 2 |
| GameState | 243 |
| Inventory | 4 |
| MatchState | 2 |
| Rank | 4 |
| Session | 14 |

---

### Session 2026-04-12_1045_pfctl-directional

Connection health macOS test session — pfctl directional drop tests (D1, D3, D2, D4) for [#529](https://github.com/manasight/manasight-docs/issues/529). Most important session for GRE silence detection validation. Major finding: macOS Arena successfully reconnects to in-progress ranked matches after disconnect (never observed on Windows).

| Field | Value |
|-------|-------|
| Date | 2026-04-12 |
| Platform | macOS Tahoe 26.3, Apple Silicon (aarch64), Wi-Fi (en1) |
| MTGA Version | Current (native macOS client via Epic) |
| Raw file | `session_2026-04-12_1045_pfctl-directional.log` |
| Format | Connection health testing — bot + ranked Standard Bo1 |
| Record | N/A — disconnect tests (won both ranked matches after reconnect) |
| Session log size (raw) | 23,458,713 (22.4 MB) |
| Session log size (gzip) | 1,680,054 (~1.6 MB) |
| Compression ratio | ~14.0:1 |

#### Test Results

| Test | Direction | Match | macOS Detection | Windows Detection | Recovery? |
|------|-----------|-------|:---:|:---:|:---------:|
| D1 | Inbound 120s | Bot | **~58s** | ~29s | No (kicked to menu) |
| D3 | Outbound 90s | Bot | **~42s** | ~14s | No (kicked to menu) |
| D2 | Inbound 120s | Ranked | **~43s** | ~22s | **Yes — full mid-match recovery** |
| D4 | Outbound 90s | Ranked | **~46s** | ~19s | **Yes — full mid-match recovery** |

#### Key Findings

- **macOS ~2-3x slower** than Windows across all directional tests
- **Mid-match recovery on macOS** — both ranked matches (D2, D4) successfully reconnected after block lifted. State machine: `Playing → Disconnected → ConnectedToMatchDoor → Playing`. Never observed on Windows.
- **Bot matches do NOT recover** — kicked to menu same as Windows
- **Inbound vs outbound gap smaller on macOS** (~43-58s vs ~42-46s) compared to Windows (~22-29s vs ~14-19s)
- **Connection health state machine must handle `Disconnected → Playing` recovery**

#### Parser Coverage

| Metric | Value |
|--------|------:|
| Total entries | 1221 |
| Routed | 930 |
| Unknown | 291 |
| Timestamp failures | 248 |

#### Event Breakdown

| Event Type | Count |
|------------|------:|
| ClientAction | 429 |
| DetailedLoggingStatus | 1 |
| EventLifecycle | 4 |
| GameResult | 2 |
| GameState | 880 |
| Inventory | 7 |
| MatchState | 8 |
| Rank | 7 |
| Session | 30 |

---

### Session 2026-04-12_1145_wifi-disable

Connection health macOS test session — Wi-Fi adapter disable tests (B1, B2, B3) for [#529](https://github.com/manasight/manasight-docs/issues/529). Major finding: macOS Wi-Fi disable does NOT send TCP RST (unlike Windows). Only B1 (60s) caused disconnect; B2 (1s) and B3 (10s) survived because the connection recovered before TCP timeout.

| Field | Value |
|-------|-------|
| Date | 2026-04-12 |
| Platform | macOS Tahoe 26.3, Apple Silicon (aarch64), Wi-Fi (en1) |
| MTGA Version | Current (native macOS client via Epic) |
| Raw file | `session_2026-04-12_1145_wifi-disable.log` |
| Format | Connection health testing — bot + ranked Standard Bo1 |
| Record | N/A — disconnect tests |
| Session log size (raw) | 18,154,742 (17.3 MB) |
| Session log size (gzip) | 1,220,653 (~1.2 MB) |
| Compression ratio | ~14.9:1 |

#### Test Results

| Test | Method | Match | Duration | Total Downtime | Detection | Behavior |
|------|--------|-------|----------|:-:|:---------:|----------|
| B1 | Wi-Fi off | Bot | 60s | ~66s | **~52s** | "Waiting for server" → "Connection Lost" → Reconnect → kicked |
| B2 | Wi-Fi off (quick) | Bot | 1s | ~7s | **None** | No visible interruption |
| B3 | Wi-Fi off | Ranked | 10s | ~21s | **None** | Brief pause, then resumed |

#### Key Findings

- **macOS Wi-Fi disable does NOT send TCP RST** — connections go dead silently (SocketException 10049 "address not valid" instead of Windows 10054 "connection reset")
- **B2 and B3 survived on macOS** (Windows: all three triggered instant disconnect via RST)
- **macOS adapter-disable behaves like pfctl** (silent drop) not like Windows adapter-disable (instant RST)
- **B1 showed "Connection Lost" dialog** (same UI as Windows) — this is the adapter-disable-specific response, but only fires if the timeout is actually reached
- **Two-stage error in B1:** first exception hit a non-game connection (SocketException 10049), second hit matchdoor (10060 timeout)

#### Parser Coverage

| Metric | Value |
|--------|------:|
| Total entries | 939 |
| Routed | 790 |
| Unknown | 149 |
| Timestamp failures | 112 |

#### Event Breakdown

| Event Type | Count |
|------------|------:|
| ClientAction | 413 |
| DetailedLoggingStatus | 1 |
| EventLifecycle | 2 |
| GameResult | 2 |
| GameState | 827 |
| Inventory | 4 |
| MatchState | 5 |
| Rank | 4 |
| Session | 8 |

---

### Session 2026-04-12_1240_edge-cases

Connection health macOS test session — edge case Wi-Fi disable tests (E1, E2) for [#529](https://github.com/manasight/manasight-docs/issues/529). E3 deferred. Confirms phase-independent disconnect behavior. Major finding: reconnecting to a Bo3 match during sideboarding skips the sideboard phase and produces a frozen UI (broken-reconnect state).

| Field | Value |
|-------|-------|
| Date | 2026-04-12 |
| Platform | macOS Tahoe 26.3, Apple Silicon (aarch64), Wi-Fi (en1) |
| MTGA Version | Current (native macOS client via Epic) |
| Raw file | `session_2026-04-12_1240_edge-cases.log` |
| Format | Connection health testing — bot match (E1) + Bo3 Traditional (E2) |
| Record | N/A — disconnect tests |
| Session log size (raw) | 13,903,912 (13.3 MB) |
| Session log size (gzip) | 850,792 (~0.8 MB) |
| Compression ratio | ~16.3:1 |

#### Test Results

| Test | Method | Phase | Detection | Behavior |
|------|--------|-------|:---------:|----------|
| E1 | Wi-Fi off 75s | Mulligan (bot) | **~52s** | "Waiting for server" → "Connection Lost" → kicked to menu |
| E2 | Wi-Fi off 75s | Sideboard (Bo3) | **~60s** | "Connection Lost" → reconnected → sideboard skipped → frozen black screen → inactivity timeout |
| E3 | — | Between games | — | Deferred |

#### Key Findings

- **Phase-independent detection** — mulligan (~52s) and sideboard (~60s) produce same timing as mid-gameplay (B1: ~52s). Matches Windows finding.
- **Sideboard skipped on reconnect** — Arena reconnected to active Bo3 match but jumped straight to game 2 without sideboard. Pre-sideboard deck was used. Gameplay-impacting consequence.
- **Broken-reconnect during Bo3** — after reconnecting and skipping sideboard, game 2 showed frozen black screen (GRE data arriving, UI unresponsive). Same edge case as Windows D2. Match ended via inactivity timeout after 10+ minutes.
- **Worse outcome than Windows E2** — Windows adapter-disable during sideboard produced instant clean disconnect. macOS slow timeout + reconnect creates broken UI state.

#### Parser Coverage

| Metric | Value |
|--------|------:|
| Total entries | 553 |
| Routed | 402 |
| Unknown | 151 |
| Timestamp failures | 130 |

#### Event Breakdown

| Event Type | Count |
|------------|------:|
| ClientAction | 199 |
| DetailedLoggingStatus | 1 |
| EventLifecycle | 2 |
| GameResult | 2 |
| GameState | 412 |
| Inventory | 3 |
| MatchState | 4 |
| Rank | 3 |
| Session | 15 |

---

### Session 2026-04-14_1720

Investigation of Arena inactivity timing / auto-concede mechanics — 4-minute-idle test across bot, unranked Play, and ranked Ladder matches. Findings written up at `manasight-docs/docs/research/2026-04-14_mtga-inactivity-timer-mechanics.md`.

| Field | Value |
|-------|-------|
| Date | 2026-04-14 |
| MTGA Version | TBD |
| Raw file | `session_2026-04-14_1720.log` |
| Format | Inactivity-timer investigation — bot / Play / Ladder BO1 |
| Record | N/A — diagnostic tests |
| Session log size (raw) | 4,126,647 (4.0 MB) |
| Session log size (gzip) | 477,876 (~0.5 MB) |
| Compression ratio | ~8.6:1 |

#### Test Results

| Test | Mode | Scenario | Outcome | Kick mechanism |
|------|------|----------|---------|----------------|
| 1 | Bot match | 4-min idle pre-first-action, then manual concede | Concede | — (user-triggered) |
| 2 | Play queue (vs human) | Full-idle after match start | Timeout loss | `TimerType_Inactivity` 150s |
| 3 | Ladder BO1 (vs human, iPhone opp) | Full-idle after match start | Timeout match loss | `TimerType_Inactivity` 150s |

#### Key Findings

- **Arena publishes authoritative countdown timers** in the GRE stream: `TimerType_ActivePlayer` (61s, `TakeControl` — AI goldfish auto-passes) and `TimerType_Inactivity` (150s, `Timeout` — match auto-concedes).
- **Full per-seat timer set** is broadcast as `GREMessageType_TimerStateMessage` (adds `Prologue` 120s, `Epilogue` 145s, `NonActivePlayer` 45s, `Delay` 2s).
- **Parser extracts `GameStateMessage.timers`** (`manasight-parser/src/parsers/gre/game_state.rs:81,116-175`) but classifies `TimerStateMessage` as noise at `mod.rs:89,98-102,180-190` and drops its payload.
- **Desktop ignores all timer data** — the desktop client's game-state mapper makes zero references to `timers`, and no overlay countdown component exists.
- **UI-level hovers do not reset `TimerType_Inactivity`** — only GRE-level actions (pass/play/activate) reset it. Empirically observed: two `ClientToGREUIMessage` onHover events during test 3 did not delay the kick.
- **Pre-match idle writes zero bytes to Player.log** — no heartbeats, no keepalives; Arena's local logging is fully event-driven.

#### Parser Coverage

| Metric | Value |
|--------|------:|
| Total entries | 282 |
| Routed | 168 |
| Unknown | 114 |
| Timestamp failures | 91 |

#### Event Breakdown

| Event Type | Count |
|------------|------:|
| ClientAction | 24 |
| DetailedLoggingStatus | 1 |
| EventLifecycle | 4 |
| GameResult | 3 |
| GameState | 246 |
| Inventory | 4 |
| MatchState | 6 |
| Rank | 4 |
| Session | 4 |
| Unknown | 19 |

---

### Session 2026-04-25_0841_deck-management-store

Comprehensive corpus-coverage session for [manasight-parser PR #154](https://github.com/manasight/manasight-parser/pull/154) (deck collection parser). Goal was to capture every API method touched by deck management, store, inbox, and pack-opening actions to confirm what is logged vs. what is a Player.log blind spot. One Standard Bo1 game played and conceded to capture a second `<== StartHook` after deck changes.

| Field | Value |
|-------|-------|
| Date | 2026-04-25 |
| MTGA Version | TBD |
| Raw file | `session_2026-04-25_0841_deck-management-store.log` |
| Format | Standard Bo1 (1 game, conceded) |
| Record | 0-1 (concede) |
| Session log size (raw) | 3,000,051 (2.9 MB) |
| Session log size (gzip) | 367,251 (~359 KB) |
| Compression ratio | ~8.1:1 |

#### Actions Tested

| Action | API methods produced | Blind spot? |
|--------|---------------------|:-----------:|
| Login / startup | `StartHook` (with `DeckSummaries` + `Decks`), `DeckGetAllPreconDecksV3`, `RankGet*`, `QuestGetQuests`, `PeriodicRewardsGetStatus`, `EventGetCoursesV2`, `EventGetActiveMatches`, `GetFormats`, `GraphGetGraphState` | No |
| Inbox daily reward claim | None — UI-side only | **Yes** |
| Open pack (×2, current set + Edge of Eternities) | None — `Client.SceneChange` to `BoosterChamber` only | **Yes** |
| Spend orbs on mastery pass | `GraphGetGraphState` ×16 (`BattlePass_SOS`, `BattlePass_TMT`) | Partial |
| Store purchase (cash — Spark bundle) | None directly; reconnect path used `DeckGetDeckSummariesV3` | **Yes** |
| Store purchase (gold) | None | **Yes** |
| Store purchase (gems) | None | **Yes** |
| Sign-in on second device → kicked | `Client.TcpConnection.Close` `status: 7` `"Closed by remote end"` | No |
| Reconnect after kick | `DeckGetDeckSummariesV3`, `QuestGetQuests`, `PeriodicRewardsGetStatus`, `EventGetCoursesV2` — **no `StartHook`** (fast-reconnect path) | No |
| Open deck in deckbuilder | `DeckGetDeckSummariesV3` (on Home re-entry) | No |
| Edit deck (swap card) + save | `DeckUpsertDeckV3` `ActionType: "Updated"` | No |
| Apply card styles | `DeckUpsertDeckV3` `ActionType: "Updated"` with populated `CardSkins` | No |
| Delete deck | `DeckDeleteDeck` → bare string `"Success"` | No |
| Import deck (paste decklist) | `DeckUpsertDeckV3` `ActionType: "Imported"` | No |
| Create new deck manually | `DeckUpsertDeckV3` `ActionType: "CreatedNew"` | No |
| Craft cards (wildcard spend) | None | **Yes** |
| Play + concede Bo1 | Standard match flow + return-to-lobby `StartHook` (post-deck-changes) | No |

#### Notable Findings

- **First-ever captures in corpus** of `DeckGetDeckSummariesV3` (uses `"Summaries"` field), `DeckUpsertDeckV3` (V2→V3 API version bump first seen Apr 14), and the three distinct `ActionType` values: `"Updated"`, `"Imported"`, `"CreatedNew"`.
- **`DeckGetAllPreconDecksV3`** captured outside the single Apr 14 session that previously had it.
- **Confirmed Player.log blind spots:** pack opening, store purchases (cash/gold/gems), inbox reward claims, card crafting. None produce any `<==`/`==>` API call — transactions are processed server-side and the client only refreshes UI state locally.
- **Server-kicked disconnect** (status 7, "Closed by remote end") is a different code path from network-drop disconnects in the existing corpus — no reconnect attempt, since the server explicitly terminated the session.
- **Fast-reconnect path** uses `DeckGetDeckSummariesV3` instead of a full `StartHook` — first observation of this reconnect flavor.
- **PR #154 coverage:** two `<== StartHook` events captured (login + post-match-exit), both containing both `"DeckSummaries"` and `"Decks"`. Edge cases (missing `DeckId`, orphaned `DeckId`, non-object `Decks`) confirmed unreachable across all observed payloads — strong candidates for dead-code removal under [#157](https://github.com/manasight/manasight-parser/issues/157).

#### Parser Coverage

| Metric | Value |
|--------|------:|
| Total entries | 213 |
| Routed | 49 |
| Unknown | 164 |
| Timestamp failures | 119 |

#### Event Breakdown

| Event Type | Count |
|------------|------:|
| ClientAction | 19 |
| DetailedLoggingStatus | 1 |
| GameResult | 1 |
| GameState | 33 |
| Inventory | 2 |
| MatchState | 2 |
| Rank | 2 |
| Session | 2 |
| Unknown | 10 |

#### Games

| # | Format | Your Archetype | Opponent Colors | Result | Turns | P/D | Notes |
|---|--------|----------------|-----------------|--------|:-----:|:---:|-------|
| 1 | Standard Bo1 | Unknown | Unknown | Loss (concede) | — | — | Conceded mid-game to trigger a second `StartHook` reflecting in-session deck changes (1 imported, 1 created, 1 deleted) |

---

### Session 2026-04-26_2209

Historic Bo1 session captured during `/debug-game` to reproduce an action log destruction-attribution bug. Played a BG midrange brew with **Summon: Bahamut**, **Vraska, Golgari Queen**, **Boseiju, Who Endures**, **Cut Down**, and **Bone Splinters** specifically to exercise the four destruction code paths the bug touches: triggered-ability (saga chapter), spell-driven SBA, channel activated ability, and planeswalker activated ability. Captured **10 misattributions across all four flavors**. Investigation also surfaced a separate event-ordering bug where "died" entries print before the "dealt damage" entry that caused them — observed in the Sparky game 6 (Shock → Stitcher's Supplier).

| Field | Value |
|-------|-------|
| Date | 2026-04-26 |
| MTGA Version | TBD |
| Raw file | `session_2026-04-26_2209.log` |
| Format | Historic Bo1 |
| Record | 2-4 |
| Session log size (raw) | 12,071,107 (11.5 MB) |
| Session log size (gzip) | 1,091,028 (~1.0 MB) |
| Compression ratio | ~11.1:1 |

#### Parser Coverage

| Metric | Value |
|--------|------:|
| Total entries | 2,153 |
| Routed | 1,937 |
| Unknown | 216 |
| Timestamp failures | 189 |

#### Event Breakdown

| Event Type | Count |
|------------|------:|
| ClientAction | 1,086 |
| DetailedLoggingStatus | 1 |
| EventLifecycle | 8 |
| GameResult | 6 |
| GameState | 1,809 |
| Inventory | 7 |
| MatchState | 12 |
| Rank | 7 |
| Session | 9 |
| Unknown | 52 |

#### Games

| # | Format | Your Archetype | Opponent Colors | Result | Turns | P/D | Notes |
|---|--------|----------------|-----------------|--------|:-----:|:---:|-------|
| 1 | Historic Bo1 | BG Bahamut Reanimator | Sparky (UW Flyers) | Win | 9 | P | Repro: 4× saga-chapter destroy attribution wrong (Warden of Evos, Sworn Guardian, River's Favor, Warden again); 2× Cut Down SBA destroy attribution wrong (Zephyr Gull, Armored Whirl Turtle) |
| 2 | Historic Bo1 | BG Bahamut Reanimator | UW (Phlage, Force of Negation, Path to Exile) | Loss | 5 | P | Phlage cascade — no destructions to attribute |
| 3 | Historic Bo1 | BG Bahamut Reanimator | UB Affinity (Drix Interlacer, Thought Monitor, Frogmyr Enforcer, Myr Enforcer) | Loss | 4 | D | Mulled aggressively, ran over by 4-mana 4/4s |
| 4 | Historic Bo1 | BG Bahamut Reanimator | UR (Lotus Field, Thespian's Stage, Pore Over the Pages, Stock Up) | Loss | 5 | P | Lotus Field combo — Vraska +2 only (no -3 target) |
| 5 | Historic Bo1 | BG Bahamut Reanimator | BR Aurora Awakener (Death // Life, Agadeem) | Loss | 4 | D | Repro: 1× Boseiju channel destroy attribution wrong (Agadeem, the Undercrypt) — channel from-hand activated ability flavor |
| 6 | Historic Bo1 | BG Bahamut Reanimator | Sparky (Mono-R Goblins) | Win | 7 | P | Repro: 2× Vraska -3 destroy attribution wrong (Nest Robber, Hurloon Minotaur) — planeswalker activated ability flavor; 2× saga-chapter destroy attribution wrong (Nest Robber, Hurloon Minotaur). Also captured event-ordering bug: Shock→Stitcher's Supplier "died" line printed before "dealt 2 damage" line at 21:18:07 |

#### Issue Repros Captured

Total **10 destruction-attribution misattributions** across 4 flavors:

| Flavor | Count | Cards |
|--------|-------|-------|
| Saga chapter (triggered ability) | 6 | Summon: Bahamut II/III destroying various creatures + River's Favor |
| Spell-driven SBA | 2 | Cut Down (-3/-3 toughness reduction → SBA death) |
| Channel activated ability | 1 | Boseiju, Who Endures destroying Agadeem, the Undercrypt |
| Planeswalker activated ability | 2 | Vraska, Golgari Queen -3 destroying Nest Robber, Hurloon Minotaur |

Pattern: in every case, *your* ability destroyed *opponent's* permanent, but the action log attributed the destruction to opponent (the destroyed permanent's owner) instead of to you (the ability source's controller). Reverse polarity (opponent's ability destroys your permanent) was not landed this session and remains an open repro target.

**Event-ordering bug**: 1 capture — Shock killing Stitcher's Supplier (game 6, turn 2 opp, 21:18:07). Order shown was `cast → died → resolved → damage → trigger`; expected `cast → damage → died → resolved → trigger`. Raw GRE in Player.log (gameStateId 71, msgId 108) confirms `DamageDealt` annotation id 143 precedes `ZoneTransfer` annotation id 152, so Arena's order is correct on the wire — bug is in the desktop client's annotation-emission pipeline.

---

### Session 2026-04-27_2230

Manual verification session for PR #498/#499/#500 (action log attribution fixes). Vraska/Boseiju/Bahamut deck targeted at AGENT_DRIVEN destruction (#499) and SBA walk-back (#500). Confirmed Boseiju Channel, Vraska -3, Summon: Bahamut chapters, Bone Splinters, forced-sac via Living End, return via Colossal Skyturtle, Cut Down SBA_ZeroToughness all attribute correctly post-fix. Both Reddit-reported bugs from issue #496 (u/xgolt01: Boseiju channel destroying opp's land; forced sacrifice via opponent's spell) now produce correct "You destroyed" / "Opponent sacrificed" attribution. Build under test: `Manasight_1.1.13_x64-setup.exe` from CI run 25033586212 on branch `issue/497-sba-damage-walkback`.

| Field | Value |
|-------|-------|
| Date | 2026-04-27 |
| MTGA Version | TBD |
| Raw file | `session_2026-04-27_2230.log` |
| Format | Standard Bo1 |
| Record | 1-2 |
| Session log size (raw) | 12,070,532 (11.5 MB) |
| Session log size (gzip) | 949,054 (~0.9 MB) |
| Compression ratio | ~12.7:1 |

#### Parser Coverage

| Metric | Value |
|--------|------:|
| Total entries | 2,189 |
| Routed | 2,067 |
| Unknown | 122 |
| Timestamp failures | 100 |

#### Event Breakdown

| Event Type | Count |
|------------|------:|
| ClientAction | 1,183 |
| DetailedLoggingStatus | 1 |
| EventLifecycle | 2 |
| GameResult | 3 |
| GameState | 1,999 |
| Inventory | 4 |
| MatchState | 6 |
| Rank | 4 |
| Session | 4 |
| Unknown | 26 |

#### Games

| # | Format | Your Archetype | Opponent Colors | Result | Turns | P/D | Notes |
|---|--------|----------------|-----------------|--------|:-----:|:---:|-------|
| 1 | Standard Bo1 | BG Bahamut Reanimator | Sparky (Mono-G stompy: Treetop Warden, Woodland Mystic, Rumbling Baloth, Rabid Bite) | Loss | 7 | P | Land-flooded; one Rabid Bite SBA_Damage death of Llanowar Elves but no destruction triggers landed |
| 2 | Standard Bo1 | BG Bahamut Reanimator | SiniyBoy (Living End cascade: Bloodbraid Marauder, Violent Outburst, Living End) | Loss | 9 | P | Verified: Vraska -3 (×2), Boseiju Channel (×2 — opp lands and Saiba Trespassers), Bone Splinters destroy, Living End forced-sac of your Llanowar Elves correctly attributed to opp, Colossal Skyturtle bounce of your Llanowar Elves correctly attributed to opp |
| 3 | Standard Bo1 | BG Bahamut Reanimator | Sparky (Mono-G ramp: Woodland Mystic, Ilysian Caryatid, Treetop Warden, Sentinel Spider, Affectionate Indrik) | Win | 16 | P | Verified: Cut Down (×2, including SBA_ZeroToughness destroy with explicit "You destroyed" attribution — first observed visible signal for #500 walk-back), Summon: Bahamut chapter destroys (×7), Vraska -3, Bone Splinters, Zombify reanimate, mutual combat trade |

#### Verification Outcome

| PR | Status | Confidence |
|----|--------|------------|
| #498 (retire parallel test pipeline) | N/A in-game (test debt only); behavior unchanged across 3 games | High |
| #499 (AGENT_DRIVEN attribution) | **Verified** — 7 distinct fix scenarios across 4 categories (Destroy via spell/saga/Channel/planeswalker, Sacrifice forced, Return forced, Discard/Surveil regression) | High |
| #500 (SBA walk-back) | **Verified for SBA_ZeroToughness** (Cut Down with explicit "You destroyed" attribution); SBA_Damage path indirectly confirmed via shared walker logic but combat-damage death log format hides destroyer | High for SBA_ZeroToughness, indirect for SBA_Damage |

#### Issues Surfaced (not fix-blocking)

| # | Type | Description |
|---|------|-------------|
| 1 | Perf | Idle CPU sustained ~14% of one core (memory stable at ~57 MB; no leak). Settled value, not startup transient |
| 2 | Walker logging | INFO-level log shows annotation counts only, not per-event walker decisions (which path fired). Would help in-session verification |
| 3 | Action log format asymmetry | Combat-damage SBA_Damage deaths render as "Y died" (no destroyer); spell-driven SBAs (Cut Down) render as "X destroyed Y". Asymmetric visibility of attribution |

---

### Session 2026-04-29_2128

Alchemy Bo1 corpus-capture session focused on the Conjure mechanic. Played to surface various Conjure-trigger flavors (cards conjured into hand/library/battlefield) for parser and action log coverage. Won both games.

| Field | Value |
|-------|-------|
| Date | 2026-04-29 |
| MTGA Version | TBD |
| Raw file | `session_2026-04-29_2128.log` |
| Format | Alchemy Bo1 |
| Record | 2-0 |
| Session log size (raw) | 8,719,745 (8.3 MB) |
| Session log size (gzip) | 704,968 (~688 KB) |
| Compression ratio | ~12.4:1 |

#### Parser Coverage

| Metric | Value |
|--------|------:|
| Total entries | 1,196 |
| Routed | 1,110 |
| Unknown | 86 |
| Timestamp failures | 66 |

#### Event Breakdown

| Event Type | Count |
|------------|------:|
| ClientAction | 826 |
| DetailedLoggingStatus | 1 |
| GameResult | 2 |
| GameState | 1,145 |
| Inventory | 3 |
| MatchState | 4 |
| Rank | 3 |
| Session | 2 |
| Unknown | 14 |
