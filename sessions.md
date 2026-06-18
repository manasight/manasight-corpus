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
| 2026-04-29 | `session_2026-04-29_2201.log` | Alchemy Bo1 (1-0) — Spellbook + Conjure mechanic capture session |
| 2026-04-29 | `session_2026-04-29_2311.log` | Standard Bo1 bot matches — mulligan stress testing from full hand down to empty hand |
| 2026-04-30 | `session_2026-04-30_0000.log` | Yorion deck — 1 game, result not recorded |
| 2026-04-30 | `session_2026-04-30_2304.log` | Standard Bo1 — opponent auto-conceded (healthy connection, opponent idle); rare edge-case log |
| 2026-05-01 | `session_2026-05-01_1657_sealed-purchase.log` | Sealed entry: 1 SealedToken paid, 6-pack pool revealed (`Sealed_SOS_20260421`, Lorehold archetype) |
| 2026-05-01 | `session_2026-05-01_1715_sealed-deckbuild.log` | Sealed deck construction: 40-card "Sealed Deck (3)" submitted via `EventSetDeckV3` |
| 2026-05-01 | `session_2026-05-01_1751_sealed-matches.log` | Sealed Bo1 matches (2-0): 2 complete games of `Sealed_SOS_20260421`, both wins (concede + lethal) |
| 2026-05-06 | `session_2026-05-06_0859_phantom-bootstrap-drift.log` | First-game-of-day with 90 deck_tracker drift dumps (gap=-2 to -4); preserves older "phantom-deck-origin" failure mode for regression bisection |
| 2026-05-06 | `session_2026-05-06_1412_rename-collision-cancelled-cast.log` | Standard match — original repro for the rename-collision bug (cancelled Torch the Tower → Fanatical Firebrand OIC overwrite); drove PR #558 |
| 2026-05-06 | `session_2026-05-06_1746_pr554-fix-delayed-collision-disproof.log` | Disproof of PR #554's "relocate orphan to old_id" fix — initial cancel looked clean but Warleader's Call OIC + later diffDeleted reaped the orphan |
| 2026-05-06 | `session_2026-05-06_2224_parser-type-field-drop-trigger.log` | Smoking gun for `manasight-parser#182` — diagnostic logging proved gameStateMessage.type is dropped, gating the rollback-aware fix off in production |
| 2026-05-06 | `session_2026-05-06_2344_stale-limbo-rollback-overclear.log` | Smoking gun for `manasight-desktop#561` — full GSM payload capture of stale Limbo-history rollback over-clear (12 stale renamed_out IDs, 6 phantoms) |
| 2026-05-13 | `session_2026-05-13_0952_recycle-defect-trigger.log` | Canonical example of the truncation→recycle drift defect (manasight-docs#657 epic); 1 `[Message summarized…]` marker + recycled instance_id 549 across the truncation, 53 drift WARNs follow |
| 2026-06-14 | `session_2026-06-14_1409_name-a-card.log` | Standard play Bo1, 1-0 (Boros aggro vs Mono-B devotion). Regression fixture for `manasight-parser#221` — Petrified Hamlet "name a card" (`AnnotationType_ChoiceResult` Domain=13 / `LinkInfo ChooseLinkType=CardName`, named card = Agna Qel'a, locId 1071244) |
| 2026-06-17 | `session_2026-06-17_1543_alchemy.log` | Alchemy Bo1 Play match, Bant control/conjure, 1-0. First **Alchemy** Format deck-submission sample (`manasight-corpus#36` / `manasight-parser#232`) — `Format:"Alchemy"` carried by **EventSetDeckV3** with `EventName:"Alchemy_Play"` |
| 2026-06-17 | `session_2026-06-17_1655_timeless.log` | Timeless Bo1 Play match, Mardu Energy (Lurrus companion), 1 game played. First **Timeless** Format deck-submission sample (`manasight-corpus#36` / `manasight-parser#232`) — `Format:"Timeless"` carried by **EventSetDeckV3** with `EventName:"Timeless_Play"`. Confirms Timeless is a distinct deck-`Format` value (unlike Explorer/Pioneer → `Historic`) |
| 2026-06-17 | `session_2026-06-17_1615_pioneer-historic.log` | Pioneer Bo1 Play (`EventName:"Explorer_Play"`), Rakdos Fling, 1 game (result not recorded). KEY `manasight-parser#232` evidence — a Pioneer-legal deck submits with deck `Format:"Historic"`, proving non-Standard Pioneer collapses to Historic; only `Explorer_Play` signals Pioneer (`manasight-corpus#36`) |
| 2026-06-17 | `session_2026-06-17_1601_pioneer.log` | Pioneer Bo1 match via the **Explorer_Play** queue (1 game). First `Explorer_Play` sample (`manasight-corpus#36` / `manasight-parser#232`). FINDING: deck "Boros Tokens" is Standard-registered, so its EventSetDeckV3 `Format` attribute reads **`Standard`**, NOT the queue/match format — deck `Format` = the deck's registered build format, while the precise match format rides on `EventName` (`Explorer_Play`) |

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

---

### Session 2026-04-29_2201

Alchemy Bo1 corpus-capture session focused on the Spellbook mechanic, with additional Conjure coverage. Won the single game played.

| Field | Value |
|-------|-------|
| Date | 2026-04-29 |
| MTGA Version | TBD |
| Raw file | `session_2026-04-29_2201.log` |
| Format | Alchemy Bo1 |
| Record | 1-0 |
| Session log size (raw) | 6,043,797 (5.8 MB) |
| Session log size (gzip) | 521,802 (~510 KB) |
| Compression ratio | ~11.6:1 |

#### Parser Coverage

| Metric | Value |
|--------|------:|
| Total entries | 983 |
| Routed | 905 |
| Unknown | 78 |
| Timestamp failures | 60 |

#### Event Breakdown

| Event Type | Count |
|------------|------:|
| ClientAction | 695 |
| DetailedLoggingStatus | 1 |
| GameResult | 1 |
| GameState | 597 |
| Inventory | 2 |
| MatchState | 2 |
| Rank | 2 |
| Session | 2 |
| Unknown | 10 |

---

### Session 2026-04-29_2311

Standard Bo1 bot matches with mulligan stress testing — kept taking mulligans on each new game, going from a full opening hand down to an empty hand. Won each match until the hand was reduced to 3 or fewer cards.

| Field | Value |
|-------|-------|
| Date | 2026-04-29 |
| MTGA Version | TBD |
| Raw file | `session_2026-04-29_2311.log` |
| Format | Standard Bo1 (bot matches) |
| Record | Won until hand reached 3 or fewer cards (mulligan stress test) |
| Session log size (raw) | 12,995,334 (12.4 MB) |
| Session log size (gzip) | 1,174,944 (~1.1 MB) |
| Compression ratio | ~11.1:1 |

#### Parser Coverage

| Metric | Value |
|--------|------:|
| Total entries | 1,793 |
| Routed | 1,572 |
| Unknown | 221 |
| Timestamp failures | 199 |

#### Event Breakdown

| Event Type | Count |
|------------|------:|
| ClientAction | 919 |
| DetailedLoggingStatus | 1 |
| GameResult | 8 |
| GameState | 2,229 |
| Inventory | 9 |
| MatchState | 16 |
| Rank | 9 |
| Session | 9 |
| Unknown | 63 |

---

### Session 2026-04-30_0000

Single game piloting a Yorion deck. Result was not recorded.

| Field | Value |
|-------|-------|
| Date | 2026-04-30 |
| MTGA Version | TBD |
| Raw file | `session_2026-04-30_0000.log` |
| Format | Yorion deck |
| Record | N/A (not recorded) |
| Session log size (raw) | 6,656,133 (6.3 MB) |
| Session log size (gzip) | 511,346 (~500 KB) |
| Compression ratio | ~13.0:1 |

#### Parser Coverage

| Metric | Value |
|--------|------:|
| Total entries | 638 |
| Routed | 555 |
| Unknown | 83 |
| Timestamp failures | 61 |

#### Event Breakdown

| Event Type | Count |
|------------|------:|
| ClientAction | 359 |
| DetailedLoggingStatus | 1 |
| GameResult | 1 |
| GameState | 654 |
| Inventory | 2 |
| MatchState | 2 |
| Rank | 2 |
| Session | 1 |
| Unknown | 9 |

### Session 2026-04-30_2304

Standard Bo1 game where the opponent took no actions and auto-conceded. Connection was healthy on our side throughout. Rare edge case useful for verifying game-entry detection when opponent does nothing.

| Field | Value |
|-------|-------|
| Date | 2026-04-30 |
| MTGA Version | TBD |
| Raw file | `session_2026-04-30_2304.log` |
| Format | Standard Bo1 |
| Record | 1-0 (opponent auto-conceded) |
| Session log size (raw) | 3,132,390 (3.0 MB) |
| Session log size (gzip) | 384,064 (~375 KB) |
| Compression ratio | ~8.2:1 |

#### Parser Coverage

| Metric | Value |
|--------|------:|
| Total entries | 145 |
| Routed | 52 |
| Unknown | 93 |
| Timestamp failures | 67 |

#### Event Breakdown

| Event Type | Count |
|------------|------:|
| ClientAction | 19 |
| DeckCollection | 3 |
| DetailedLoggingStatus | 1 |
| EventLifecycle | 4 |
| GameResult | 1 |
| GameState | 9 |
| MatchState | 2 |
| Rank | 4 |
| Session | 2 |
| Unknown | 8 |

#### Games

| # | Format | Your Archetype | Opponent Colors | Result | Turns | P/D | Notes |
|---|--------|----------------|-----------------|--------|:-----:|:---:|-------|
| 1 | Standard Bo1 | Unknown | Unknown | Win | ~1 | ? | Opponent did nothing and auto-conceded |

---

### Session 2026-05-01_1657_sealed-purchase

Sealed event entry — paid 1 `SealedToken` to enter `Sealed_SOS_20260421` with the Lorehold archetype choice. The full 6-pack sealed pool was revealed in the `EventGetCourse` payload: 4× SOS main collation (`200060`) + 2× SOS bonus (`700035`) + 1× Special Guest (`700035001`) = 85 `grpId` entries. Scene transitioned `Home → SealedBoosterOpen → DeckBuilder`. Process exited before deck submission (deck construction continued in the next session, `2026-05-01_1715_sealed-deckbuild`). Source: archive `UTC_Log - 05-01-2026 23.57.07.log`.

| Field | Value |
|-------|-------|
| Date | 2026-05-01 |
| MTGA Version | 2026.58.20.12269 |
| Source | `UTC_Log - 05-01-2026 23.57.07.log` (archive) |
| Raw file | `session_2026-05-01_1657_sealed-purchase.log` |
| Format | Limited Sealed (entry phase only — no matches) |
| Record | N/A — pre-match capture |
| Session log size (raw, post-strip) | 2,066,213 (2.0 MB) |
| Session log size (gzip) | 251,804 (~246 KB) |
| Compression ratio | ~8.2:1 |

#### Parser Coverage

| Metric | Value |
|--------|------:|
| Total entries | 47 |
| Routed | 4 |
| Unknown | 43 |
| Timestamp failures | 28 |

#### Event Breakdown

| Event Type | Count |
|------------|------:|
| DeckCollection | 1 |
| DetailedLoggingStatus | 1 |
| EventLifecycle | 1 |
| Rank | 1 |

Low routed/total ratio is expected for the sealed-entry phase — most lines are HTTP API exchanges (`EventJoin`, `EventGetCoursesV2`, `OpenedSealedDeck` / `EventPayEntry` inventory updates) that the router does not currently dispatch as game events.

---

### Session 2026-05-01_1715_sealed-deckbuild

Sealed deck construction phase for the same `Sealed_SOS_20260421` course. `EventSetDeckV3` + `DeckUpsertDeckV3` submitted "Sealed Deck (3)" with a 40-card MainDeck (73 distinct entries; format `DirectGameLimited`; sleeve `CardBack_SOS_457664`). No match play. Final scene transition was `FactionalizedEvent → DeckListViewer`. Source: archive `UTC_Log - 05-02-2026 00.15.14.log`.

| Field | Value |
|-------|-------|
| Date | 2026-05-01 |
| MTGA Version | 2026.58.20.12269 |
| Source | `UTC_Log - 05-02-2026 00.15.14.log` (archive) |
| Raw file | `session_2026-05-01_1715_sealed-deckbuild.log` |
| Format | Limited Sealed (deck construction only — no matches) |
| Record | N/A — pre-match capture |
| Session log size (raw, post-strip) | 2,030,941 (1.9 MB) |
| Session log size (gzip) | 251,277 (~245 KB) |
| Compression ratio | ~8.1:1 |

#### Parser Coverage

| Metric | Value |
|--------|------:|
| Total entries | 52 |
| Routed | 3 |
| Unknown | 49 |
| Timestamp failures | 31 |

#### Event Breakdown

| Event Type | Count |
|------------|------:|
| DeckCollection | 1 |
| DetailedLoggingStatus | 1 |
| Rank | 1 |

Similar to the entry phase, deck-builder API exchanges (`EventSetDeckV3`, `DeckUpsertDeckV3`) are not currently routed as game events.

---

### Session 2026-05-01_1751_sealed-matches

Sealed Bo1 match play for `Sealed_SOS_20260421` — 2 complete matches end-to-end, both won. Match 1 (matchId `017b1408-...`) ended via opponent concede (`ResultReason_Concede`). Match 2 (matchId `dbab7bda-...`) ended via lethal (`ResultReason_Game`); opponent's `platformId: iPad`. Both used `MatchWinCondition_SingleElimination` (Bo1) and `superFormat: SuperFormat_Limited`. Source: archive `UTC_Log - 05-02-2026 00.51.35.log`.

| Field | Value |
|-------|-------|
| Date | 2026-05-01 |
| MTGA Version | 2026.58.20.12269 |
| Source | `UTC_Log - 05-02-2026 00.51.35.log` (archive) |
| Raw file | `session_2026-05-01_1751_sealed-matches.log` |
| Format | Limited Sealed Bo1 |
| Record | 2-0 |
| Session log size (raw, post-strip) | 8,170,702 (7.8 MB) |
| Session log size (gzip) | 693,025 (~677 KB) |
| Compression ratio | ~11.8:1 |

#### Parser Coverage

| Metric | Value |
|--------|------:|
| Total entries | 1,636 |
| Routed | 1,546 |
| Unknown | 90 |
| Timestamp failures | 69 |

#### Event Breakdown

| Event Type | Count |
|------------|------:|
| ClientAction | 770 |
| DeckCollection | 3 |
| DetailedLoggingStatus | 1 |
| EventLifecycle | 2 |
| GameResult | 2 |
| GameState | 1450 |
| MatchState | 4 |
| Rank | 3 |
| Session | 2 |
| Unknown | 12 |

#### Games

| # | Format | Your Archetype | Opponent Colors | Result | Turns | P/D | Notes |
|---|--------|----------------|-----------------|--------|:-----:|:---:|-------|
| 1 | Sealed Bo1 | Lorehold (RW) | Unknown | Win | ? | ? | Opponent concede (`ResultReason_Concede`); matchId `017b1408-...` |
| 2 | Sealed Bo1 | Lorehold (RW) | Unknown | Win | ? | ? | Lethal (`ResultReason_Game`); opponent on iPad; matchId `dbab7bda-...` |

---

### Session 2026-05-06_0859_phantom-bootstrap-drift

First-game-of-day session that produced 90 `deck_tracker` drift dumps in ~2 minutes with signature `gap=-2 to -4`, `missing=-3 to -6` (extra `is_deck_origin` instances created beyond `original_deck` size, ~47-48 unresolved-`grpId` library entries). Captured before the parser-type-field bug was understood; preserves the older "phantom-deck-origin" failure mode for regression bisection. Source: archive `UTC_Log - 05-06-2026 15.59.01.log`.

| Field | Value |
|-------|-------|
| Date | 2026-05-06 |
| MTGA Version | 2026.58.20.12269 |
| Source | `UTC_Log - 05-06-2026 15.59.01.log` (archive) |
| Raw file | `session_2026-05-06_0859_phantom-bootstrap-drift.log` |
| Format | Standard Bo1 (bootstrap drift capture) |
| Record | N/A — drift-only capture |
| Session log size (raw, post-strip) | 5,912,404 (5.6 MB) |
| Session log size (gzip) | 592,543 (~579 KB) |
| Compression ratio | ~10.0:1 |

#### Parser Coverage

| Metric | Value |
|--------|------:|
| Total entries | 740 |
| Routed | 624 |
| Unknown | 116 |
| Timestamp failures | 95 |

#### Event Breakdown

| Event Type | Count |
|------------|------:|
| ClientAction | 427 |
| DeckCollection | 4 |
| DetailedLoggingStatus | 1 |
| GameResult | 3 |
| GameState | 651 |
| MatchState | 6 |
| Rank | 4 |
| Session | 3 |
| Unknown | 23 |

---

### Session 2026-05-06_1412_rename-collision-cancelled-cast

Standard match where the user cast Torch the Tower (`grpId 86855`) at 14:25:47, the cast was rolled back (Full GSM at 14:25:57 returned source 164 to Hand, no `diffDeletedInstanceIds`), then casting Fanatical Firebrand at 14:26:19 triggered an OIC `orig=162 new=376` that silently overwrote the orphan at 376. Drift opened with `gap=+1, missing=+1` and persisted through end of game — the original repro for the rename-collision bug fixed in PR #558. Source: archive `UTC_Log - 05-06-2026 21.12.05.log`.

| Field | Value |
|-------|-------|
| Date | 2026-05-06 |
| MTGA Version | 2026.58.20.12269 |
| Source | `UTC_Log - 05-06-2026 21.12.05.log` (archive) |
| Raw file | `session_2026-05-06_1412_rename-collision-cancelled-cast.log` |
| Format | Standard Bo1 |
| Record | TBD |
| Session log size (raw, post-strip) | 5,982,296 (5.7 MB) |
| Session log size (gzip) | 560,952 (~548 KB) |
| Compression ratio | ~10.7:1 |

#### Parser Coverage

| Metric | Value |
|--------|------:|
| Total entries | 819 |
| Routed | 734 |
| Unknown | 85 |
| Timestamp failures | 72 |

#### Event Breakdown

| Event Type | Count |
|------------|------:|
| ClientAction | 536 |
| DeckCollection | 3 |
| DetailedLoggingStatus | 1 |
| GameResult | 2 |
| GameState | 706 |
| MatchState | 4 |
| Rank | 3 |
| Session | 2 |
| Unknown | 20 |

---

### Session 2026-05-06_1746_pr554-fix-delayed-collision-disproof

Test of v1.1.51 (PR #554's "relocate orphan to `old_id`" approach). User cancelled Torch the Tower at 17:55:49, the fix appeared to work at 17:55:52 (no immediate drift), but casting Warleader's Call at 17:58:52 then triggered OIC `orig=285 new=381` that re-collided when Arena later emitted `diffDeletedInstanceIds: [162]` and reaped the orphan. Confirmed PR #554 only delayed the bug rather than fixing it; led to PR #554 being closed and the parser-type-field investigation. Source: archive `UTC_Log - 05-07-2026 00.46.42.log`.

| Field | Value |
|-------|-------|
| Date | 2026-05-06 |
| MTGA Version | 2026.58.20.12269 |
| Source | `UTC_Log - 05-07-2026 00.46.42.log` (archive) |
| Raw file | `session_2026-05-06_1746_pr554-fix-delayed-collision-disproof.log` |
| Format | Standard Bo1 |
| Record | TBD |
| Session log size (raw, post-strip) | 5,100,902 (4.9 MB) |
| Session log size (gzip) | 501,403 (~490 KB) |
| Compression ratio | ~10.2:1 |

#### Parser Coverage

| Metric | Value |
|--------|------:|
| Total entries | 620 |
| Routed | 537 |
| Unknown | 83 |
| Timestamp failures | 65 |

#### Event Breakdown

| Event Type | Count |
|------------|------:|
| ClientAction | 355 |
| DeckCollection | 3 |
| DetailedLoggingStatus | 1 |
| GameResult | 2 |
| GameState | 576 |
| MatchState | 4 |
| Rank | 3 |
| Session | 2 |
| Unknown | 14 |

---

### Session 2026-05-06_2224_parser-type-field-drop-trigger

Test of v1.1.52 (PR #555 diagnostic logging). Game with cancelled Burst Lightning + Stadium Headliner / Voice of Victory token creation produced 31 drift dumps, all with `gap=+1, missing=+1`. Diagnostic trace immediately revealed every `step_7_5_rollback_detect gsm_id=N payload_type=game_state_message early_return=true` — proving manasight-parser drops the inner `gameStateMessage.type` field, so the rollback-aware fix's `payload["type"] == "GameStateType_Full"` gate never fires in production. Smoking gun for `manasight-parser#182` and `manasight-desktop#556`. Source: archive `UTC_Log - 05-07-2026 05.24.15.log`.

| Field | Value |
|-------|-------|
| Date | 2026-05-06 |
| MTGA Version | 2026.58.20.12269 |
| Source | `UTC_Log - 05-07-2026 05.24.15.log` (archive) |
| Raw file | `session_2026-05-06_2224_parser-type-field-drop-trigger.log` |
| Format | Standard Bo1 |
| Record | TBD |
| Session log size (raw, post-strip) | 3,646,288 (3.5 MB) |
| Session log size (gzip) | 373,413 (~365 KB) |
| Compression ratio | ~9.8:1 |

#### Parser Coverage

| Metric | Value |
|--------|------:|
| Total entries | 308 |
| Routed | 248 |
| Unknown | 60 |
| Timestamp failures | 47 |

#### Event Breakdown

| Event Type | Count |
|------------|------:|
| ClientAction | 163 |
| DeckCollection | 2 |
| DetailedLoggingStatus | 1 |
| GameResult | 1 |
| GameState | 276 |
| MatchState | 2 |
| Rank | 2 |
| Session | 1 |
| Unknown | 10 |

---

### Session 2026-05-06_2344_stale-limbo-rollback-overclear

Test of v1.1.53 (PR #556 + PR #560 permanent diagnostics). Game with cancelled Burst Lightning + Stadium Headliner produced 73 drift dumps with `gap=-2, missing=-2`. With `MANASIGHT_DECK_TRACE_FULL_PAYLOAD=1` capturing every GSM, Python replay identified GSM 132 (Full snapshot, `msg_id=182`) as the trigger: Arena emitted 12 stale `renamed_out` source IDs in Limbo zone descriptors, step 7.5 over-cleared the skip-list, step 7 re-inserted 6 phantoms. Six phantom `instance_id`s: 161, 164, 280, 282, 289, 302. Smoking gun for `manasight-desktop#561` — captured GSM 131 + GSM 132 payloads are the test fixtures. Source: archive `UTC_Log - 05-07-2026 06.44.58.log`.

| Field | Value |
|-------|-------|
| Date | 2026-05-06 |
| MTGA Version | 2026.58.20.12269 |
| Source | `UTC_Log - 05-07-2026 06.44.58.log` (archive) |
| Raw file | `session_2026-05-06_2344_stale-limbo-rollback-overclear.log` |
| Format | Standard Bo1 |
| Record | TBD |
| Session log size (raw, post-strip) | 3,366,364 (3.2 MB) |
| Session log size (gzip) | 363,126 (~355 KB) |
| Compression ratio | ~9.3:1 |

#### Parser Coverage

| Metric | Value |
|--------|------:|
| Total entries | 283 |
| Routed | 223 |
| Unknown | 60 |
| Timestamp failures | 47 |

#### Event Breakdown

| Event Type | Count |
|------------|------:|
| ClientAction | 140 |
| DeckCollection | 2 |
| DetailedLoggingStatus | 1 |
| GameResult | 1 |
| GameState | 248 |
| MatchState | 2 |
| Rank | 2 |
| Session | 1 |
| Unknown | 10 |

12 Unknown events in the matches log are worth investigating — may include sealed-specific signals not yet recognized by the router.

---

### Session 2026-05-13_0952_recycle-defect-trigger

Canonical example of the truncation→recycle drift defect identified during `/debug-drift` verification of `manasight-desktop#607`. Standard Bo1 vs Sparky (1-0). During turn 6 + turn 8 the user cast Indris, the Hydrostatic Surge twice (4 + 4 conjures into library each, budget grows to 8). At 10:01:12 local (gsm=459, the Voltage Surge resolve event), MTGA emitted a `[Message summarized because one or more GameStateMessages exceeded the 50 GameObject or 50 Annotation limit.]` marker (63 GameObjects + 4 Annotations) — parser silently dropped the GSM. At gsm=473 Arena recycled instance_id 549 (originally cast Voltage Surge instance from gsm=458) for a discard of Slickshot Show-Off; deck_tracker's `rename_instances` overwrote the orphaned 549 entry, producing 53 contiguous `(derived_total=N+1 != expected=N)` drift WARNs across gsm 473-525. Drift "self-heals" at gsm=526 via a coincidental phantom-insert. Full investigation at `manasight-docs/docs/research/2026-05-13_player-log-truncation-correlation.md`. Source: archive `UTC_Log - 05-13-2026 16.52.13.log`.

| Field | Value |
|-------|-------|
| Date | 2026-05-13 |
| MTGA Version | TBD |
| Source | `UTC_Log - 05-13-2026 16.52.13.log` (archive) |
| Raw file | `session_2026-05-13_0952_recycle-defect-trigger.log` |
| Format | Standard Bo1 (vs Sparky) |
| Record | 1-0 |
| Session log size (raw, post-strip) | 5,961,034 (5.7 MB) |
| Session log size (gzip) | 518,309 (~507 KB) |
| Compression ratio | ~11.5:1 |

#### Parser Coverage

| Metric | Value |
|--------|------:|
| Total entries | 830 |
| Routed | 769 |
| Unknown | 61 |
| Timestamp failures | 46 |

#### Event Breakdown

| Event Type | Count |
|------------|------:|
| ClientAction | 596 |
| DeckCollection | 2 |
| DetailedLoggingStatus | 1 |
| GameResult | 1 |
| GameState | 563 |
| MatchState | 2 |
| Rank | 2 |
| Session | 1 |
| Unknown | 9 |

Deck: Grixis spells-leaning Standard (Indris, the Hydrostatic Surge; Voltage Surge; Think Twice; Stock Up; Shellfish Scholar; Fear of Missing Out; Slickshot Show-Off; Lightning Bolt; Dazzling Flameweaver; Torch the Tower; Three Steps Ahead; Refute; Spell Pierce). 60-card deck verified via original_deck = 24 unique grp_ids.

Used as the regression-test fixture for the deck_tracker recycle-defect fix track (`manasight-docs#657` epic, child issues `#658`/`#659`/`#660`).

---

### Session 2026-06-14_1409_name-a-card

Standard play Bo1, 1-0. Boros (R/W) aggro vs Mono-Black devotion. Captured during a `/debug-game` session as the regression fixture for the **"name a card" action-log gap** — the parser extracts the choice annotations (`manasight-parser#221`) and a downstream desktop consumer surfaces the named card in the action log. On turn 1 the opponent's **Petrified Hamlet** (grpId 102718, instance 291) resolved its *"choose a land card name"* ability and named **Agna Qel'a**. The choice rides on `AnnotationType_ChoiceResult` (`Choice_Domain=13` = CardName, `Choice_Value=1071244`) correlated via `AnnotationType_LinkInfo` (`ChooseLinkType="CardName"`, `sourceAbilityGRPID=204544`) — both annotation types are currently dropped by the parser's closed allow-list, so this session exercises the fix end-to-end. Source: archive `UTC_Log - 06-14-2026 21.09.38.log`.

| Field | Value |
|-------|-------|
| Date | 2026-06-14 |
| MTGA Version | TBD |
| Source | `UTC_Log - 06-14-2026 21.09.38.log` (archive) |
| Raw file | `session_2026-06-14_1409_name-a-card.log` |
| Format | Standard play Bo1 (vs Mono-B devotion) |
| Record | 1-0 |
| Session log size (raw, post-strip) | 4,294,477 (4.1 MB) |
| Session log size (gzip) | 420,717 (~411 KB) |
| Compression ratio | ~10.2:1 |

#### Parser Coverage

| Metric | Value |
|--------|------:|
| Total entries | 508 |
| Routed | 426 |
| Unknown | 82 |
| Timestamp failures | 65 |

#### Event Breakdown

| Event Type | Count |
|------------|------:|
| ClientAction | 118 |
| DeckCollection | 2 |
| DetailedLoggingStatus | 1 |
| EventLifecycle | 2 |
| GameResult | 1 |
| GameState | 563 |
| MatchState | 2 |
| Rank | 2 |
| Session | 2 |
| Unknown | 7 |

Deck (yours): Boros (R/W) aggro — Voice of Victory, Raphael Tough Turtle, Stadium Headliner, Shocking Sharpshooter, Fanatical Firebrand, Howlsquad Heavy, Warleader's Call, Sunbillow Verge, Mountain. Opponent: Mono-Black devotion — Day of Black Sun, Unholy Annex // Ritual Chamber, Soul-Guide Lantern, Duress, Requiting Hex, Strategic Betrayal, Petrified Hamlet, Fountainport, Deathcap Glade.

Used as the regression-test fixture for the "name a card" action-log fix — parser-side extraction lands in `manasight-parser#221`; downstream desktop surfacing is tracked separately.

---

### Session 2026-06-17_1543_alchemy

Alchemy Bo1 Play match, Bant control/conjure, 1-0. First **Alchemy** deck-submission Format sample for the corpus — captured for `manasight/manasight-corpus#36` to unblock `manasight/manasight-parser#232`. Confirmed live: `Format:"Alchemy"` carried by an **EventSetDeckV3** request with `EventName:"Alchemy_Play"`. Confirms Alchemy routes its precise format through the deck-submission path. Source: archive `UTC_Log - 06-17-2026 22.43.39.log`.

| Field | Value |
|-------|-------|
| Date | 2026-06-17 |
| MTGA Version | TBD |
| Source | `UTC_Log - 06-17-2026 22.43.39.log` (archive) |
| Raw file | `session_2026-06-17_1543_alchemy.log` |
| Format | Alchemy (Bo1, Play queue — `EventName: "Alchemy_Play"`) |
| Record | 1-0 (win) |
| Session log size (raw, post-strip) | 3,768,657 (3.59 MB) |
| Session log size (gzip) | 395,239 (~386 KB) |
| Compression ratio | ~9.5:1 |

#### Parser Coverage

| Metric | Value |
|--------|------:|
| Total entries | 339 |
| Routed | 273 |
| Unknown | 66 |
| Timestamp failures | 47 |

#### Event Breakdown

| Event Type | Count |
|------------|------:|
| ClientAction | 144 |
| DeckCollection | 2 |
| DetailedLoggingStatus | 1 |
| EventLifecycle | 2 |
| GameResult | 1 |
| GameState | 306 |
| MatchState | 2 |
| Rank | 2 |
| Session | 1 |
| Unknown | 6 |

Deck (yours): Bant (G/W/U) control/conjure — "Bant Conjure" (DeckId `aa16b1ab-...`). Submitted via **EventSetDeckV3** with `EventName:"Alchemy_Play"`; the deck `Summary.Attributes` carry `Format:"Alchemy"`. This is the corpus's first sample proving Alchemy's precise format is surfaced through the deck-submission path (not just the generic event/queue name) — directly relevant to `manasight-parser#232`.

---

### Session 2026-06-17_1655_timeless

First **Timeless** deck-submission Format sample in the corpus. `Format:"Timeless"` via **EventSetDeckV3**, `EventName:"Timeless_Play"`. The deck registered as Timeless because it contains Timeless-only cards (Ragavan = Historic-banned, Modern Horizons 3 staples, Strip Mine). KEY: confirms **Timeless IS a distinct deck-`Format` value** — unlike Explorer/Pioneer, which collapses to `Historic` (see session_2026-06-17_1615_pioneer-historic). Captured for `manasight/manasight-corpus#36`; data for `manasight/manasight-parser#232`. Source: archive `UTC_Log - 06-17-2026 23.55.35.log`.
### Session 2026-06-17_1615_pioneer-historic

Second Pioneer/`Explorer_Play` sample, and the KEY evidence for `manasight/manasight-parser#232`'s format model. The deck "Rakdos Fling" is a legal Explorer/Pioneer deck (the `Explorer_Play` queue accepted it), yet its **EventSetDeckV3** `Format` attribute reads **`Historic`**, not Explorer/Pioneer. Proves there is NO Explorer/Pioneer deck-`Format` value — a non-Standard Pioneer deck collapses to `Historic`; the only Pioneer signal is `EventName:"Explorer_Play"`. Pairs with `session_2026-06-17_1601_pioneer` (a Standard-registered deck in the same queue → `Format:Standard`). Together they show deck `Format` = deck build legality, NOT the match/queue format. Captured for `manasight/manasight-corpus#36`. Source: archive `UTC_Log - 06-17-2026 23.15.49.log`.
### Session 2026-06-17_1601_pioneer

Pioneer match via the **Explorer_Play** queue (Bo1, Play; Arena's internal name for Pioneer is still "Explorer"). 1 game played (result not recorded). First `Explorer_Play` queue sample in the corpus — captured for `manasight/manasight-corpus#36`.

**IMPORTANT FINDING for `manasight/manasight-parser#232`:** the submitted deck ("Boros Tokens") is **Standard-registered**, so the EventSetDeckV3 `Format` attribute reads **`Standard`**, NOT the queue/match format. This shows the deck `Format` attribute = the deck's registered/build format (narrowest legal), not the match format; for format-named queues the precise format is carried by `EventName` (`Explorer_Play`), and the deck `Format` can under-report. Contrast with the `2026-06-17_1543_alchemy` session, where the Alchemy-registered deck's `Format` happened to match the queue. Source: archive `UTC_Log - 06-17-2026 23.01.25.log`.

| Field | Value |
|-------|-------|
| Date | 2026-06-17 |
| MTGA Version | TBD |
| Source | `UTC_Log - 06-17-2026 23.55.35.log` (archive) |
| Raw file | `session_2026-06-17_1655_timeless.log` |
| Format | Timeless (Bo1, Play queue — `EventName: "Timeless_Play"`) |
| Record | 1 game played (result not recorded) |
| Session log size (raw, post-strip) | 4,289,930 (4.09 MB) |
| Session log size (gzip) | 448,451 (~438 KB) |
| Compression ratio | ~9.6:1 |
| Source | `UTC_Log - 06-17-2026 23.15.49.log` (archive) |
| Raw file | `session_2026-06-17_1615_pioneer-historic.log` |
| Format | Pioneer (Bo1, Play queue — internal `EventName: "Explorer_Play"`) |
| Record | 1 game played (result not recorded) |
| Session log size (raw, post-strip) | 4,700,389 (4.48 MB) |
| Session log size (gzip) | 462,627 (~452 KB) |
| Compression ratio | ~10.2:1 |
| Source | `UTC_Log - 06-17-2026 23.01.25.log` (archive) |
| Raw file | `session_2026-06-17_1601_pioneer.log` |
| Format | Pioneer (Bo1, Play queue — internal `EventName: "Explorer_Play"`; Arena's internal name for Pioneer is still "Explorer") |
| Deck / archetype | Boros Tokens (a Standard-REGISTERED deck) |
| Record | 1 game played (result not recorded) |
| Session log size (raw, post-strip) | 5,213,839 (4.97 MB) |
| Session log size (gzip) | 487,372 (~476 KB) |
| Compression ratio | ~10.7:1 |

#### Parser Coverage

| Metric | Value |
|--------|------:|
| Total entries | 806 |
| Routed | 631 |
| Unknown | 175 |
| Timestamp failures | 147 |
| Total entries | 713 |
| Routed | 627 |
| Unknown | 86 |
| Timestamp failures | 63 |
| Total entries | 833 |
| Routed | 765 |
| Unknown | 68 |
| Timestamp failures | 53 |

#### Event Breakdown

| Event Type | Count |
|------------|------:|
| ClientAction | 269 |
| ClientAction | 283 |
| ClientAction | 275 |
| DeckCollection | 2 |
| DetailedLoggingStatus | 1 |
| EventLifecycle | 2 |
| GameResult | 1 |
| GameState | 548 |
| MatchState | 2 |
| Rank | 2 |
| Session | 1 |
| Unknown | 6 |

Deck (yours): **Mardu Energy Timeless** (Lurrus of the Dream-Den companion; Lurrus card 71293 appears in both `Sideboard` and `Companions`). DeckId `43c54f3b-...`, submitted via **EventSetDeckV3** with `EventName:"Timeless_Play"`; the deck `Summary.Attributes` carry `Format:"Timeless"`. The deck registered as Timeless because it contains Timeless-only cards — Ragavan (Historic-banned), Modern Horizons 3 staples, Strip Mine. This is the corpus's first sample confirming **Timeless is a distinct deck-`Format` value**, unlike Explorer/Pioneer which collapses to `Historic` (cf. `session_2026-06-17_1615_pioneer-historic`) — directly relevant to `manasight-parser#232`.
| GameState | 578 |
| GameState | 769 |
| MatchState | 2 |
| Rank | 2 |
| Session | 1 |
| Unknown | 10 |

Deck (yours): "Rakdos Fling" (Rakdos prowess/aggro; DeckId `46309f58-...`) — an Explorer/Pioneer-legal build (the `Explorer_Play` queue accepted it) but registered as **Historic**. Submitted via **EventSetDeckV3** with `EventName:"Explorer_Play"`, while the deck `Summary.Attributes` carry `Format:"Historic"`. This is the KEY evidence for `manasight-parser#232`: there is no `Explorer`/`Pioneer` deck-`Format` value — a non-Standard Pioneer deck collapses to `Historic`, so the only Pioneer signal is the queue's `EventName:"Explorer_Play"`. The single (EventName, Format) deck-submission pair in this log is `(Explorer_Play, Historic)`. Pairs with `session_2026-06-17_1601_pioneer` (Standard-registered deck in the same queue → `Format:Standard`) to show deck `Format` reflects deck build legality, NOT match/queue format.
Deck (yours): "Boros Tokens" (a **Standard-registered** deck). Submitted via **EventSetDeckV3** with `EventName:"Explorer_Play"`; the deck `Summary.Attributes` carry `Format:"Standard"` (the deck's registered build format), even though the match format is Pioneer. This is the corpus's first `Explorer_Play` sample and demonstrates that the deck-submission `Format` attribute can under-report the actual match format — the precise format must be read from `EventName`. Directly relevant to `manasight-parser#232`.

