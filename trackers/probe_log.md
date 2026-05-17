# Probe Log

> **Append-only log of every probe event. Probes update station locks. STATE.md derives from this.**

---

## Probe Events

| # | Date | Element | Format | Floor | Target | Result | Stop reason | Lock change |
|---|---|---|---|---|---|---|---|---|
| 1 | 2026-02-28 | WB density | W09 SAT Baby Hyrox + rest | — | — | 40 UB / 1:49 (+10 broken = 50 total) | Grip pause | WB UB lock established at 40 |
| 2 | 2026-03-07 | WB density | W10 SAT Baby Hyrox + rest | 40 | 45 | **50 UB / 2:39 PR** (+20 = 70 total) | Clean finish | WB UB lock 40 → 50 |
| 3 | 2026-03-14 | WB density | W11 SAT Baby Hyrox + rest | 50 | 50 clean | 50 ≈ UB / 2:25 (2 micro-pauses) + 30 = 80 total | Sweat on hands (grip) | UB lock held at 50; chalk added to protocol |
| 4 | 2026-03-19 | WB volume sim | W12 THU HYROX sim 3R + finisher | 100 total | 130 total | 130 total (3×30 + 20+20) | Clean | Volume ceiling lock 130 |
| 5 | 2026-03-22 | WB UB under fragment | W12 SUN Baby Hyrox + rest | 50 UB | 60+ UB | **60 with 2 breaks / 3:39** (+20 = 80 total) | Quad fatigue + entry lactate (limiter ID) | UB fragment-fatigue lock 60; limiter: quad/entry not shoulder |
| 6 | 2026-03-24 | Sled push load | W13 TUE gym | 220 kg | 225 kg | **225 kg S1 51s / S2 49s PR** | Clean | Sled push lock 220 → 225 |
| 7 | 2026-03-31 | Sled push fresh PR | W14 TUE gym | 225 kg | 240 kg | **240 kg / 20 m / 44s fresh PR** | Clean | Sled push fresh PR 240 |
| 8 | 2026-04-11 | WB intra-set progression | W15 SAT 4×25 + finisher | maintain | progress | 0:58 → 0:55 → 0:53 → 0:53 + 140 total | Clean | Round-set capacity lock: progressive arc confirmed |
| 9 | 2026-04-18 | WB SAT | W16 SAT WB Dev Day | — | 4×25 + dev | **CANCELLED** | HRV 27 + 13 hr life load | Lock held; correct cancel |
| 10 | 2026-04-21 | Sled push working PR | W17 TUE gym fresh | 240 kg | 245 kg | **245 kg / 3×18 m / 50–51–53s PR** | Clean | Sled push working load 240 → **245** |
| 11 | 2026-04-25 | WB fresh capacity | W17 SAT 4×25 + primer | maintain | confirm | 58 / 59 / 61 / 59 sec — "iron stability" | Clean | Round capacity lock confirmed; HRV 80 |
| 12 | 2026-05-02 | WB clean line under fragment | W18 SAT 4-round + probe | — | establish | **30 clean / 1:09** | Technical stop | Clean fragment lock established at 30 |
| 13 | 2026-05-09 | WB clean line under fragment | W19 SAT 4-round + probe | 30 | 40 | **40 clean** | Clean line stop | Clean fragment lock 30 → **40** |
| 14 | 2026-05-16 | WB ceiling under harder fatigue | W20 SAT 4-round + 1.09 km entry + max set | 40 | 45 | **50 reps / 1:59 @ 9 kg** | Athlete stop (target exceeded +5; no technical break reported) | Clean fragment lock 40 → **50**; total volume PR 140 → **150**; round stability lock 61/61/62/61 |

---

## Pending Probes

| Date | Element | Format | Floor | Target | Status |
|---|---|---|---|---|---|
| 2026-05-23 | WB consolidation under harder fatigue | W21 SAT 4-round + extended entry (1.2 km OR +1 round) | 50 | 50 clean repeat (NOT 70) | SCHEDULED — judgment: avoid reckless jump per W20 post-session note |
| 2026-05-30 | WB 60 under fragment | W22 SAT Phase 3 W1 | 50 | 60 | PLANNED |
| 2026-06-06 | WB 80 under fragment | W23 SAT Phase 3 W2 | 60 | 80 | PLANNED |
| 2026-06-13 | WB 100 attempt / race sim | W24 SAT Phase 3 W3 | 80 | 100 | PLANNED |
| 2026-06-20 | Skill touch | W25 SAT Phase 4 W1 (taper) | — | 50 fresh | PLANNED |
| 2026-06-27 | Skill touch | W26 SAT Phase 4 W2 (taper) | — | 30 fresh | PLANNED |
| 2026-07-03 | **RACE** | HYROX Sydney | — | 100 UB | TARGET |

---

## Probe Trajectory Summary

### Wall Ball Clean Line (under fragment fatigue)
30 (W18) → 40 (W19) → **50 (W20, under deeper fatigue including 1.09 km entry)** → consolidate 50 (W21) → 60 (Phase 3 W1) → 80 (Phase 3 W2) → 100 (Phase 3 W3) → 100 UB (race)

**Trajectory note:** W20 result accelerated the path by ~1 week. Phase 3 entry stronger than planned.

### Sled Push Working Load
204 kg → 220 kg → 225 kg → 240 kg → **245 kg (current)** → progression by rest reduction

### Sled Pull Working Load
164 kg → 184 kg → 204 kg → 204 kg refined (efficiency probes, no load change)

---

## Stop Rules Summary

Per `reference/probe_rules.md`:
- WB: technical failure (throw height, catch, squat depth, torso, breathing, rhythm)
- Sled: stall or form breakdown
- Run: pace drift > 10 sec/km, HR over cap, calf signal
- Always: cardiac sensation = immediate abort, no exception

---

## Append Protocol

After every probe session, append a new row.

If probe cancelled (Red day): log as cancelled row with reason.

If probe target not reached but floor maintained: log result honestly; previous lock held.

If new PR / new lock: update `STATE.md` Current Locks section AND relevant `trackers/[station]_tracker.md`.

**Never edit existing rows.** Corrections via new row with note.
