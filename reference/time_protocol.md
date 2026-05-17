# Time Protocol — Mandatory Time Anchor on Every Turn

> **The discipline that prevents date drift across long-running coaching conversations. Drift broke this system on 2026-05-14. This protocol prevents recurrence.**

---

## The Problem

LLM conversations have no inherent time awareness. Claude relies on:
1. System prompt time hint
2. Dates inside files/messages
3. Memory references

All three can drift, conflict, or go stale. A 1-day drift today becomes a 7-day drift in a week. Phase logic depends on exact dates. Stale anchor = wrong plan.

---

## Mandatory Protocol — Every Training-Related Turn

### Step 1: Verify time at start

Before any plan, report, decision, or probe analysis:

**Primary:** call `user_time_v0` tool
**Fallback (if user_time_v0 unavailable):** run `bash date "+%Y-%m-%d %H:%M %Z"`
**Last resort:** use system prompt date with explicit caveat

### Step 2: Cross-check against STATE.md

Read `STATE.md` "Last verified" timestamp.
- If drift < 24 hours: proceed; light update STATE if same day
- If drift 24–168 hours (1–7 days): update STATE phase fields before planning
- If drift > 168 hours: hard pause; treat as new state; request weekly close-out

### Step 3: Display anchor in response header

Every plan, report, or decision opens with:

```
TIME ANCHOR (verified [method] [timestamp])
- Date: YYYY-MM-DD (Weekday)
- Local time: HH:MM (timezone)
- Build Day NN of ~95
- Build Week N · Annual Week NN
- Phase X — [Name] (Week M of K)
- Days to race: NN
- Next phase boundary: YYYY-MM-DD (X days)
```

### Step 4: Use only verified time for all downstream math

- Days to race: compute from verified date, not memory
- Phase position: compute from verified date vs `reference/master_plan.md` boundaries
- Build day: compute from verified date vs Sydney Build start 2026-03-30
- Weekday of next session: compute, do not infer

---

## Key Date Anchors (Reference)

| Anchor | Date | Day |
|--------|------|-----|
| Sydney Build Day 1 | 2026-03-30 | Monday |
| Phase 1 Stabilize start | 2026-03-30 | Monday |
| Phase 1 Stabilize end | 2026-04-19 | Sunday |
| Phase 2 Build start | 2026-04-20 | Monday |
| Phase 2 Build end | 2026-05-24 | Sunday |
| Phase 3 Specific Peak start | 2026-05-25 | Monday |
| Phase 3 Specific Peak end | 2026-06-14 | Sunday |
| Phase 4 Taper start | 2026-06-15 | Monday |
| Phase 4 Taper end | 2026-06-28 | Sunday |
| Race week start | 2026-06-29 | Monday |
| **RACE DAY** | **2026-07-03** | **Friday** |

## Build Day Math

`Build Day = (verified_date - 2026-03-30) + 1`

Examples:
- 2026-03-30 → Build Day 1
- 2026-04-30 → Build Day 32
- 2026-05-15 → Build Day 47
- 2026-05-25 → Build Day 57 (Phase 3 start)
- 2026-07-03 → Build Day 96 (race)

## Sydney Build Week Math

`Build Week = ceil(Build Day / 7)`

Examples:
- Build Day 1–7 → Build Week 1
- Build Day 47 → Build Week 7
- Build Day 96 → Build Week 14 (race week)

## Annual Week Math

`Annual Week = ISO week number of verified date`

Examples:
- 2026-03-30 → Annual Week 14
- 2026-05-15 → Annual Week 20
- 2026-07-03 → Annual Week 27

---

## Drift Detection

### Self-check during turn

If reasoning produces a date that does NOT match verified time:
- Stop reasoning
- Re-anchor with `user_time_v0`
- Restart computation from verified time

### Cross-conversation drift

If user uploads a file with a date that conflicts with current system time:
- File date wins for that file's content
- System time wins for "today"
- Flag the conflict explicitly in response

### Memory drift

If memory recalls a date that conflicts with verified time:
- Verified time wins
- Note memory drift explicitly
- Update STATE.md if memory was wrong

---

## Failure Mode Caught By This Protocol

**Case study (2026-05-14 / 2026-05-15):**
- Yaro's Thursday session report dated 2026-05-14
- Conversation opened presuming today = 2026-05-14
- Reality: today was 2026-05-15 (Friday); Thursday session was yesterday
- 1-day drift carried through 5 messages before Yaro flagged it
- Time anchor not verified until explicitly requested

**With this protocol:** drift caught at Step 1, no downstream errors.

---

## Update Protocol

This file updates only when:
- New tool for time verification becomes available
- Phase boundaries change (race rescheduled, etc.)
- New drift failure mode discovered

---

**Bottom line: time anchor first, always. No exceptions. Drift caught at the door.**
