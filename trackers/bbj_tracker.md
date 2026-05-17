# Burpee Broad Jump (BBJ) Tracker

> **NEW PRIMARY LIMITER identified 2026-05-14. Append-only log.**

**Race standard:** 80 reps over ~30 m at HYROX
**Working distances in training:** 20 m (race-fragment) and 30 m (compromised testing)

---

## BBJ Performance History

### Thursday HYROX Rhythm — 2-round fragments

| Date | Week | Distance | R1 | R2 | Fade | Notes |
|---|---|---|---|---|---|---|
| 2026-04-16 W16 THU | Sydney W3 Phase 1 | 30 m | ~2:00 | 2:27 | 27 sec | First BBJ data in current arc |
| 2026-04-23 W17 THU | Sydney W4 Phase 2 W1 | 30 m | 2:23 | 2:26 | 3 sec | Consistent, slow |
| 2026-04-30 W18 THU | Sydney W5 Phase 2 W2 | 30 m | 1:56 | 2:10 | 14 sec | R1 pace dropped, R2 fade emerged |
| 2026-05-07 W19 THU | Sydney W6 Phase 2 W3 | (calf-protected) | — | — | — | BBJ likely removed or reduced |
| 2026-05-14 W20 THU | Sydney W7 Phase 2 W4 | 30 m | **1:34** | **2:06** | **32 sec** | LIMITER CONFIRMED; R1 too fast → R2 collapse |

### Saturday race-fragment — 20 m (W18, W19, W20)

| Date | Week | Distance | Format | Notes |
|---|---|---|---|---|
| 2026-05-02 W18 SAT | Sydney W5 | 20 m | 4 rounds within fragment | Controlled, no fade noted |
| 2026-05-09 W19 SAT | Sydney W6 | 20 m | 4 rounds within fragment | Calf-controlled; clean |
| 2026-05-16 W20 SAT | Sydney W7 | 20 m | 4 rounds within fragment | **R4 1:27; mild calf awareness, athlete slowed correctly, NO cramp/pulling; NO R1→R2 fade pattern (race-distance format)** |

---

## Limiter Analysis (Refined 2026-05-16 W20 SAT)

### Distance-Specific Pattern (NEW INSIGHT)

The R1→R2 fade is **distance-specific**, not general:

- **30 m (Thursday rhythm format):** R1 over-pace → R2 collapse persists across W17–W20
- **20 m (Saturday race-fragment format):** No fade observed; controlled rhythm holds
- **W20 SAT R4 BBJ 1:27 @ 20 m** — proves race-distance pacing is locked

### Root Cause (cross-reference Brisbane W12, still applicable for 30m)
W12 SUN Baby Hyrox identified the same root cause:
- Quad fatigue post-lunges
- Lactate at WB entry
- Lack of reset before high-cost stations
- Diagnosed in March; resolved at 20 m, NOT at 30 m

### Fix Protocol
1. **Round 1 pacing discipline at 30 m:** target 1:50–2:00 (NOT 1:34)
2. **Race-distance (20–30 m HYROX-spec):** already locked
3. **Practice in Phase 3 Thursday sessions:** controlled R1 to preserve R2 at 30 m
4. **Probe test in Phase 3:** confirm new pacing model under fragment fatigue at 30 m

### Status (post W20 SAT)
- Race-fragment BBJ: **resolved** ✓
- Long-distance (30 m) BBJ pacing: **still active limiter**
- Calf interaction: managed by athlete pacing intelligence

---

## Race Target

- 80 BBJ over 30 m at HYROX as Station 5 of 8
- Target time: 4:00–4:30 (steady cost; not a station to chase)
- Required: R1 pacing discipline to preserve later stations (WB above all)

---

## Append Protocol

Every BBJ-relevant session adds a new row.

Source data: session reports in `state/current_week.md` or `archive/2026/week_NN_report.md`.

Special attention: this is the active primary limiter. Every Thursday and Saturday entry must capture R1 vs R2 timing for fade pattern tracking.
