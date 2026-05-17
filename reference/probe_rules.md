# Probe Rules

> **A probe is a controlled stretch above the current confirmed baseline. Probes update locks. They are not training sessions; they are diagnostic events.**

---

## Core Principles

### One Probe Per Session
- Only one probe element per session, maximum
- Multi-axis probes lose diagnostic value
- If session has WB probe, no sled probe same day
- If session has 1 km transition probe, no WB density probe same day

### One Probe Per Week
- Default placement: Saturday
- Skip is acceptable; double is not
- Mid-week probes only by exception (specific phase entry tests)

### Probe vs Build Session
- **Probe:** tries to extend a known boundary; stops at technical failure
- **Build:** repeats known load to consolidate; does not chase new numbers
- Distinguish in plan: probe sessions explicitly labeled "PROBE" with target floor/ceiling

---

## Probe Types by Station

### Wall Ball

**Density probe:** clean reps to technical break under defined fatigue
- Floor: current confirmed clean count
- Ceiling: previous demonstrated peak
- Stop: technical failure, not rep target

**Volume probe:** total reps across sets under fatigue
- Used for accumulating broken-set capacity
- Format: 3-round HYROX sim + finisher = 130–160 total

**Race-fragment probe:** WB after 1 km run entry
- Tests transition under HR 145–160 entry
- Floor: 40 clean; ceiling: 60+

### Sled Push

**Load probe:** new weight at confirmed rest
- Only after current load is clean at reduced rest (1:30 or below)
- Increment 5 kg at a time
- One sled probe per phase, maximum

**Rest probe:** reduce rest at current weight
- Default progression mechanism
- 1:45 → 1:30 → 1:15

**Race-distance probe:** 40 m at race-weight
- Only in Phase 3+

### Sled Pull

**Same structure as push**

### Running

**Pace probe:** 1 km repeats at faster pace
- After 4-5 confirmed sessions at current pace
- Increment 5 sec/km at a time

**Compromised pace probe:** running pace inside fragment
- Tests pacing discipline under station fatigue

### BBJ

**Rhythm probe:** confirming new pacing model
- Used when limiter pattern needs to be tested
- Round 1 paced slower deliberately to preserve Round 2

---

## Probe Placement Rules

### Pre-Probe Requirements

Before scheduling a probe, must be true:
1. Athlete entering Green or strong Yellow morning
2. Previous 24-48 hours did not include another probe
3. Recovery markers acceptable (sleep, HRV)
4. No active acute issue (calf, sleep, cardiac)
5. Phase context supports the probe direction

### Cancel a Probe (downgrade to build)

Any of:
- Morning readiness Yellow with HRV suppressed
- Calves above 3/10
- Sleep below 6h30
- Two consecutive nights below 7h00
- Recent injury signal in adjacent area
- Athlete subjective "not today"

### Move a Probe

If Saturday probe cancelled:
- Default: skip the week, retain previous lock
- Optional: move to Sunday if Saturday was unforeseen (e.g., scheduling conflict)
- Never push to mid-week unless phase context demands

---

## Stop Rules During Probe

### Wall Ball Probe Stop Rules

Stop at FIRST occurrence of:
- Throw height drops below target (10 ft / 3.05 m)
- Catch becomes messy (multiple bobbles)
- Squat depth changes (cuts short, raises knee tracking)
- Torso collapses
- Breathing turns to panic
- Shoulders start compensating (rocking, jerk)
- Rhythm becomes ugly (>1.5 sec irregular gap)
- Two consecutive ugly reps

Log the rep before the break as the clean count.

### Sled Probe Stop Rules

Stop at first occurrence of:
- Stall during push/pull (failure to move sled for > 3 sec)
- Form breakdown (back rounding, asymmetric drive)
- Wrong load detected mid-set

### Running Probe Stop Rules

Stop at first occurrence of:
- Pace drift > 10 sec/km off target on Rep 3+
- HR exceeds session cap by > 5 bpm
- Calf signal during work
- Cadence drops below floor

---

## Logging Protocol

Every probe is logged in `trackers/probe_log.md`:

```md
| Date | Element | Format | Floor | Target | Result | Stop reason | Lock change |
|------|---------|--------|-------|--------|--------|-------------|-------------|
| YYYY-MM-DD | WB density | 4-round + 3:00 rest | 40 | 50 | 52 clean | technical (throw height drop) | WB clean lock 40 → 52 |
```

After probe:
- If new lock: update `STATE.md` immediately + relevant `trackers/[station]_tracker.md`
- If failed (below floor): note in tracker, hold previous lock, plan re-test
- If skipped (Red day): log skip with reason

---

## Probe Progression Examples (Wall Ball Path)

| Saturday | Date | Probe | Status |
|---|---|---|---|
| W19 | 2026-05-09 | 40 clean under fragment | ✓ 40 clean confirmed |
| W20 | 2026-05-16 | Ceiling re-touch (target 50–60+) | PENDING |
| W21 | 2026-05-23 | Volume day OR skip if probe hit | Conditional |
| W22 (Phase 3) | 2026-05-30 | 80 with one break | PENDING |
| W23 | 2026-06-06 | 100 attempt under fragment | PENDING |
| W24 | 2026-06-13 | Race simulation 100 UB | PENDING |
| W25 (Taper) | 2026-06-20 | 50 fresh skill touch | PENDING |
| W26 | 2026-06-27 | 30 fresh skill touch | PENDING |
| RACE | 2026-07-03 | 100 UB at race | TARGET |

---

## Update Protocol

This file updates only when:
- New probe type emerges from training experience
- Phase transition introduces new probe categories
- Athlete-specific stop rule needs codification

For probe history: `trackers/probe_log.md` is append-only.
