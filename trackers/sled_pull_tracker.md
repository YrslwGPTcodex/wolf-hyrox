# Sled Pull Tracker

> **Append-only log. STATE.md derives current working load from this file.**

**Iron Viking Gym track: 18 m (working format)**
**Race standard: 50 m at HYROX-spec weight (~103 kg male)**

---

## Working Load Progression

| Date | Week | Block | Load | Format | Times | Notes |
|---|---|---|---|---|---|---|
| 2026-03-02 onward | W10–W11 | Brisbane | 184 kg | race-style | ~3:00 | Brisbane race-spec; consistent |
| 2026-03-19 | W12 THU | Brisbane | 184 kg | 3 rounds sim | 2:38–3:13 | R2 had load error (corrected back to 184) |
| 2026-03-24 | W13 TUE | Brisbane | — | — | — | Tuesday lower trimmed; pull skipped |
| 2026-03-26 | W13 THU | Brisbane | 184 kg | 2 rounds | R1 2:38, R2 with error → 3:13 | Error recovery clean |
| 2026-03-31 | W14 TUE | Sydney W1 | **205 kg** | gym fresh | manageable | Athlete dashboard logged 205 |
| 2026-04-14 | W16 TUE | Sydney W3 | **204 kg** | gym | "highly repeatable" | Lock established |
| 2026-04-21 | W17 TUE | Sydney W4 | 204 kg | 3×18 m | 1:35 / 1:33 / 1:32 | Near-identical sets |
| 2026-04-28 | W18 TUE | Sydney W5 | 204 kg | 3×18 m | 1:50 / 1:35 / 1:30 | Progressive faster sets |
| 2026-05-12 | W20 TUE | Sydney W7 | 204 kg | 3×18 m Yellow | 1:33 / 1:17 / 1:11 | S2–S3 went faster than planned |

---

## Thursday HYROX Rhythm — Race-Style Pull at 184 kg (W14 onward)

| Date | Format | R1 | R2 | Notes |
|---|---|---|---|---|
| 2026-04-16 W16 THU | 181 kg / 2 rounds | clean | ~1:30 | Slightly lighter test |
| 2026-04-23 W17 THU | 184 kg / 2 rounds | 1:23 | 1:24 | Near-identical |
| 2026-04-30 W18 THU | 164 kg (wrong load) / 2 rounds | 1:04 | 0:58 | Wrong load used; cleanly executed |
| 2026-05-14 W20 THU | 184 kg / 2 rounds | 1:30 | 1:30 | Race-fragment rhythm |

---

## Demonstrated Capacity (Locks)

- **Working load (gym 18 m):** 204 kg
- **Best 3-set arc:** 1:33 / 1:17 / 1:11 (W20 TUE 2026-05-12) — efficiency rising sharply
- **Race-style 184 kg:** 1:23–1:24 (W17 THU)
- **Race-distance reference:** 184 kg / 40 m / 3:00 (Brisbane)

**Status:** sled pull is becoming a weapon (W20 TUE shows fastest efficiency to date)

---

## Race Target

- HYROX Pro Men 45–49 sled pull: ~103 kg / 50 m
- Required time: 2:30–3:30
- Current working capacity exceeds race demand
- Phase 3 focus: race-distance simulation, transition timing

---

## Append Protocol

Every sled pull session result added as new row.

**Never edit existing rows.** If correction needed, append new row with note.

Source data: session reports in `state/current_week.md` or `archive/2026/week_NN_report.md`.
