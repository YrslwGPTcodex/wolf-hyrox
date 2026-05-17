# Running Tracker

> **Append-only log of all running data. STATE.md derives pace zones from this file.**

---

## Race-Fragment 400m Runs (within Saturday WB fragments)

| Date | Week | R1 | R2 | R3 | R4 | Notes |
|---|---|---|---|---|---|---|
| 2026-05-16 W20 SAT | Sydney W7 | 2:04 @ HR 122 | 1:50 @ HR 147 | 1:59 @ HR 144 | 2:04 @ HR 144 | Controlled; HR stayed sub-cap; created fatigue without burning probe |

## Race-Entry 1 km Runs (post-fragment, pre-probe)

| Date | Distance | Time | Avg Pace | Avg HR | Notes |
|---|---|---|---|---|---|
| 2026-05-16 W20 SAT | 1.09 km | 5:34 | 5:05/km | 145 bpm | Correct entry zone; preserved WB probe; final segment 5:25/km HR 149 |

## 1 km Repeat Sessions (Monday — Speed Economy)

| Date | Week | Block | Reps | Best | Average | HR | Cadence | Notes |
|---|---|---|---|---|---|---|---|---|
| 2026-03-02 | W10 MON | Brisbane W1 | — | — | — | — | — | Data not logged |
| 2026-03-09 | W11 MON | Brisbane W2 | 6×1km | **4:09 R5** | ~4:24 | 150–160 | 163–171 | Best single rep of build; cap respected |
| 2026-03-23 | W13 MON | Brisbane W4 | 5×1km | 4:20–4:24 | 4:22 | — | — | Threshold, minimal HR drift |
| 2026-04-06 | W15 MON | Sydney W2 Phase 1 | 4×1km Yellow | — | — | — | — | Yellow stop at 4; R2 hot |
| 2026-04-13 | W16 MON | Sydney W3 Phase 1 | 3×800m Yellow | controlled | — | — | — | Lower-back tightness; Yellow correct |
| 2026-04-20 | W17 MON | Sydney W4 Phase 2 W1 | 6×800m | **R4 4:16** | 4:16–4:29 | 141–143 | 167→178 | Phase 2 opener; race-pace corridor |
| 2026-04-27 | W18 MON | Sydney W5 Phase 2 W2 | 5×1km | **R2 4:14** | 4:17 | 145–146 | 171→181 | Grade A; plan was 4:25–4:35 |
| 2026-05-11 | W20 MON | Sydney W7 Phase 2 W4 | 4×1km Yellow | 4:22 | 4:22–4:26 | 142–144 | — | Yellow; HRV suppressed |

---

## Aerobic Reset (Friday — Z2)

| Date | Week | Distance | Time | Avg Pace | Avg HR | Notes |
|---|---|---|---|---|---|---|
| 2026-03-06 | W10 FRI | 5.16 km | 31:09 | 6:02/km | 134 | Z2 with negative split |
| 2026-03-13 | W11 FRI | 6.69 km (row) | 30:06 | — | 122 | Rowing instead of run |
| 2026-04-03 | W14 FRI | 8.05 km | 47:23 | 5:53/km | 129 | Z2 dominant 29:11 |
| 2026-04-10 | W15 FRI | 5.02 km | 31:24 | 6:15/km | 122 | Perfect reset; HRV 67 ms |
| 2026-04-17 | W16 FRI | 8.04 km | 47:07 | 5:52/km | 129 | Aerobic free 5:15/km at 137 bpm |
| 2026-04-24 | W17 FRI | 8.04 km | 45:12 | 5:37/km | 129 | Completely rested; Z3 only 0:35 |
| 2026-05-01 | W18 FRI | 5.03 km | 29:17 | 5:49/km | 130 | Splits 5:43–5:54 |
| 2026-05-08 | W19 FRI | 5.03 km | — | — | 123 | No Z3+ |
| 2026-05-15 | W20 FRI | 5.04 km | — | 5:50/km | 127 | No Z3+; clean reset |

---

## Long Aerobic / 10 km

| Date | Week | Distance | Time | Avg Pace | Best km | Notes |
|---|---|---|---|---|---|---|
| 2026-03-29 | W13 SUN | 10.03 km | 52:31 | 5:14/km | **4:44 (km 7)** | Progressive 6:26→4:44; 0 cardiac events |
| 2026-04-05 | W14 SUN | 7.31 km | 45:31 | 6:13/km | — | Fully aerobic recovery |
| 2026-04-12 | W15 SUN | 5.03 km | 31:05 | 6:10/km | — | Wind + cold adapted |
| 2026-04-19 | W16 SUN | 6.08 km | — | 6:03/km | — | Yellow recovery |
| 2026-04-26 | W17 SUN | 4.28 km walk | 48:59 | 11:26/km | — | Walk only; correct |
| 2026-05-03 | W18 SUN | 5.39 km walk | 58:50 | 10:55/km | — | HRV 34 → walk only |

---

## Demonstrated Capacity (Locks)

- **Best 1 km single rep:** 4:09 / km (Brisbane W11 R5)
- **Best 800 m single rep:** 4:16 / km (W17 MON R4)
- **5×1 km fresh average:** 4:17 / km (W18 MON)
- **5×1 km Yellow average:** 4:22 / km (W20 MON)
- **10 km progressive best km:** 4:44 / km (W13 SUN)
- **Cadence fresh:** 171–181 spm (W17, W18 MON peak)
- **Cadence aerobic:** 157–166 spm
- **HR control on intervals:** cap 155 respected consistently

---

## Race Target

- 8 × 1 km running spread across HYROX format
- Target pace: 4:00–4:15 / km for 1:15 total
- Compromised pace (after stations): must hold 4:15–4:25 / km in middle race
- Current Yellow 4:22–4:26 closely matches compromised target

---

## Append Protocol

Every running session added as new row, in correct sub-table.

**Never edit existing rows.** If correction needed, append new row with note.

Source data: session reports in `state/current_week.md` or `archive/2026/week_NN_report.md`.
