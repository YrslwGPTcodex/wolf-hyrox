# Readiness Trend Tracker

> **Append-only daily readiness log. Used for HRV / sleep trend analysis and Phase transition gate evaluation.**

---

## Format

| Date | Day | Sleep h | Restful % | HRV ms | HRV %vs baseline | Calves L | Calves R | Body feel | Notes |
|---|---|---|---|---|---|---|---|---|---|

---

## W18 (2026-04-27 to 2026-05-03)

| Date | Day | Sleep h | Restful % | HRV ms | HRV %vs baseline | Calves L | Calves R | Body feel | Notes |
|---|---|---|---|---|---|---|---|---|---|
| 2026-04-27 | MON | 7h53 | — | 88 | +high | — | — | — | Sleep score 87★ |
| 2026-04-28 | TUE | 7h45 | — | 77 | — | — | — | — | Sleep score 85★; near-cramp after session |
| 2026-04-29 | WED | — | — | — | — | — | — | — | Calf-protect day |
| 2026-04-30 | THU | 7h25 | — | 47 | suppressed | — | — | — | Wrong sled load incident |
| 2026-05-01 | FRI | — | — | — | — | — | — | — | Aerobic reset; clean |
| 2026-05-02 | SAT | — | — | — | — | — | — | — | WB probe 30 clean |
| 2026-05-03 | SUN | 8h15 | — | 34 | suppressed | — | — | — | Walk only; correct |

---

## W19 (2026-05-04 to 2026-05-10)

| Date | Day | Sleep h | Restful % | HRV ms | HRV %vs baseline | Calves L | Calves R | Body feel | Notes |
|---|---|---|---|---|---|---|---|---|---|
| 2026-05-09 | SAT | 8h25 | 65% | 56 | neutral | OK | OK | OK | Probe 40 clean WB; 3-day target 100% |

(Other days W19 data not extracted)

---

## W20 (2026-05-11 to 2026-05-17 in progress)

| Date | Day | Sleep h | Restful % | HRV ms | HRV %vs baseline | Calves L | Calves R | Body feel | Notes |
|---|---|---|---|---|---|---|---|---|---|
| 2026-05-11 | MON | 6h15 | 35% (only 35 min restful) | 50.5 | +14% | — | — | — | Sleep score 75 |
| 2026-05-12 | TUE | 6h05 | 65% (4h00) | 39.8 | -9% | 2.5/10 | 2.5/10 | 6/10 | Yellow day; calf-protected |
| 2026-05-13 | WED | — | — | 32.2 | -25% RED | — | — | — | No formal training |
| 2026-05-14 | THU | 7h59 | — | 51 sleeping / 43.6 daily | +1% recovered | improved post-B12 | improved post-B12 | Yellow-Green | B12 injection; B12 corrected calves |
| 2026-05-15 | FRI | — | — | — | — | held | held | — | Aerobic reset 5.04 km clean |
| 2026-05-16 | SAT | 9h35 (effective ~8h30) | 53% (5h05 restful) | 67 (avg sleeping) / 53.2 (24h) / 62 (morning) | **+54%** vs 30-day | OK (mild during BBJ) | OK (mild during BBJ) | strong | **Green; 3-day target 105%; sleep dip 19%; sleeping HR 54; resp 17.2 brpm; SpO2 95% — probe day breakthrough conditions** |

---

## 7-day Rolling Averages (computed during Sunday close-out)

**To be updated each Sunday close-out.**

---

## Phase 2 Build — HRV Pattern Observations

- Sleep volume averages 6h54 across W17–W20 — chronically below 7h30 Green threshold
- HRV swings observed: 88 → 34 ms (W18), 50.5 → 32.2 → 51 ms (W20)
- Mid-week crashes followed by recovery — pattern visible
- Best nights: W18 MON 88 ms, W17 SAT 80 ms post-recovery
- Sleep onset issue identified as primary mechanism (not sleep duration once asleep)

---

## Append Protocol

After every Sunday close-out and after every morning readiness gate:
- Append row for the day
- Note B12 injections in Notes column
- Note any deviation (illness, travel, etc.) in Notes

**Never edit existing rows.** Corrections via new row with note.

Source data: morning readiness blocks in `state/current_week.md`.
