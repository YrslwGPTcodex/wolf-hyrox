# Decision Rules — Green / Yellow / Red System

> **The decision system that maps morning readiness data to session calibration. Read for every daily plan.**

---

## Morning Readiness Gate

Every training day, before any plan is finalized, the following inputs are collected:
1. Sleep duration (hours + restful %)
2. Daily HRV (ms)
3. Calf rating right + left (0–10 scale)
4. Body feel (subjective 1–10)
5. Cramp signal overnight (yes/no)
6. Under-knee pulling sensation (yes/no)

### GREEN Gate — Full Plan

All conditions must be true:
- Sleep duration ≥ 7h00 OR 7h30+ if probe day
- Restful sleep ≥ 40%
- HRV neutral or positive vs 30-day baseline
- Calves both ≤ 2/10
- No overnight cramp signal
- No under-knee pulling sensation
- Body feel ≥ 7/10

→ **Action:** execute planned session in full

### YELLOW Gate — Modified Plan

Any of the following:
- Sleep 6h00–6h59
- Restful sleep 30–39%
- HRV slightly suppressed (5–15% below baseline)
- Calves 2.5–3.5/10
- Body feel 5–6/10
- Two consecutive nights below 7h00 (auto-Yellow even if other markers green)

→ **Action:** apply Yellow modification (see session-type specific rules below)

### RED Gate — No Quality / Recovery Only

Any of the following:
- Sleep < 6h00
- HRV crashed (>20% below baseline) OR < 35 ms absolute
- Calves 4/10+
- Overnight cramp signal returned
- Under-knee pulling during warm-up
- Cardiac sensation (any palpitation feel) — see `reference/medical.md`

→ **Action:** Red protocol (walk/bike easy, no intensity, no probe, mobility)

---

## Session-Type Specific Modifications

### Speed Economy (Monday-type)

**Green:** 5 × 1 km @ 4:18–4:24/km, rest 2:00 jog, HR cap 152
**Yellow:** 4 × 1 km same pace target, no 5th rep, HR cap 145
**Red:** 30–40 min Z2 only, no intervals

### Heavy Lower + Sled (Tuesday-type)

**Green:** full strength block + 3×push 240 + 3×pull 204 + 32+32 lunges 30m × 2
**Yellow:** 2×push 240 + 2×pull 204 + 32+32 lunges 30m × 1; reduce DBs to 80% if needed
**Red:** mobility only or bike easy 20 min

### Upper + Aerobic (Wednesday-type)

**Green:** full upper block + 20–25 min Z2 aerobic
**Yellow:** trimmed upper (drop heaviest set or accessory), skip aerobic
**Red:** rest, mobility only

### HYROX Rhythm / Compromised (Thursday-type)

**Green:** 2–3 rounds full structure
**Yellow:** 2 rounds with reduced BBJ distance (20 m → 15 m) or load reduction
**Red:** easy aerobic + WB 5×15 technique only

### Aerobic Reset (Friday-type)

**Green:** 40–45 min Z2 outdoor, HR 120–132
**Yellow:** 30 min Z2 or 4 km easy
**Red:** walk only

### Wall-Ball Development / Race Fragment (Saturday-type — probe slot)

**Green:** full fragment + probe element (one probe maximum)
**Yellow:** 4 rounds without probe, target maintenance
**Red:** bike + 5×15 WB technique, no fragment, no probe

### Recovery Run (Sunday-type)

**Green:** easy jog 25–35 min Z1+Z2
**Yellow:** walk 30–45 min or short Z2 5 km
**Red:** walk only or full rest

---

## Adjustment Rules During Session

### Mid-session Cut Rules

**Drop one tier (Green → Yellow, Yellow → Red mid-session) if:**
- HR exceeds session cap on Rep 2–3 of any block
- Calf rating rises above 3/10 during work
- Pacing collapses by > 15 sec/km from target
- Wall-ball times exceed 1:08 inside fragment rounds
- BBJ Round 2 exceeds 2:10 (for 30 m) or 1:40 (for 20 m)

### Mid-session Stop Rules

**Stop session entirely if:**
- Calf rating reaches 4/10 during work
- Sharp pain (any location) appears
- Cardiac sensation returns
- Two consecutive sets of any element show technical failure
- Athlete subjective state shifts to "wrong" or "off"

---

## Phase-Specific Overlay

### Phase 2 — Build (current through 2026-05-24)
- Focus: capacity building, station consolidation
- WB target: 4-round stability + density probes
- Run target: 1 km repeat zones (fresh 4:18–4:24, Yellow 4:22–4:30)
- Sled: progression via rest reduction, not weight
- Saturday probe: weekly default unless Red

### Phase 3 — Specific Peak (2026-05-25 to 2026-06-14)
- Focus: race-specific fragments, ceiling exposure
- WB target: 60–100 reps under fragment fatigue
- Run target: 4:15–4:20 compromised pace
- Sled: race-distance simulation
- Saturday: full race-simulation fragments

### Phase 4 — Taper (2026-06-15 to 2026-06-28)
- Focus: skill preservation, freshness
- Volume reduced 40–60%, intensity preserved 80–90%
- WB: skill touches only, 30–50 reps fresh
- No probes after 2026-06-20

### Race Week (2026-06-29 to 2026-07-03)
- Specific protocol in `reference/race_strategy.md`

---

## Phase Transition Gates

**Move from Phase 2 → Phase 3 only if most of these are true:**
- Wall-ball repeatability under fatigue has clearly improved ✓
- Compromised running is moving toward race-specific pace without collapse ✓
- Lunge and sled durability are high enough to support specific race fragments ✓
- Recovery is good enough to absorb specific peak work

**Move from Phase 3 → Phase 4 only if:**
- Race-simulation fragment hit close to 1:15 splits
- WB ceiling test confirmed 80+ under fatigue
- No injury accumulation
- Sleep / HRV trend stable or improving

---

## Decision Hierarchy (When Multiple Inputs Conflict)

When data points conflict, this hierarchy decides:

1. **Cardiac signal** — overrides everything; immediate Red
2. **Cramp signal / acute calf pain** — Red regardless of other markers
3. **Sleep duration** — primary trump above intensity preferences
4. **HRV** — secondary; can shift Green → Yellow
5. **Calf rating** — tertiary; can shift session type but not full Green/Red
6. **Body feel** — informational; calibration not gate
7. **Pacing/HR mid-session** — adjusts inside the session
8. **Athlete intent** — last; respected when other gates allow

---

## Update Protocol

This file updates only when:
- New decision pattern emerges from athlete experience
- Phase boundary changes structural logic
- Medical update changes gate thresholds (e.g., new cardiac protocol)

For day-to-day calibration: applied per session, not modified.

---

**Bottom line: data first, hierarchy clear, no override without explicit acknowledgment of risk.**
