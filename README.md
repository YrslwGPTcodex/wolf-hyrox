# wolf-hyrox — HYROX Sydney 1:15 Coaching System

> **Operating system for training decisions. Built for one purpose: HYROX Sydney 2026-07-03 at 1:15:00.**

---

## How To Use

### With Claude Code (primary — full automation)

```bash
cd ~/wolf-hyrox
claude
```

Claude reads `CLAUDE.md` automatically and knows how to operate. Then:

- **Morning:** paste readiness → Claude calibrates plan, commits to git
- **Post-session:** paste data → Claude writes report, updates trackers + STATE, commits
- **Sunday:** "Sunday close-out" → Claude archives week, generates next week, syncs everything, pushes to GitHub

### With Claude Project (mobile fallback)

Attach these files to Project Knowledge for read-only context:
- `CLAUDE.md`
- `STATE.md`
- `state/current_week.md`
- `state/limiters_now.md`
- `reference/coaching_values.md`

File updates require manual re-upload (Project does not auto-write).

---

## Structure

```
wolf-hyrox/
├── CLAUDE.md                    ← agent operating manual (read first)
├── STATE.md                     ← single source of truth
├── README.md                    ← you are here
├── PORTAL.html                  ← Wolf Portal navigation entry point (GitHub Pages)
│
├── plans/                       ← wolf_wNN_plan.html (one per week)
├── completed/                   ← wolf_wNN_completed.html (one per completed week)
├── master/                      ← master plan HTML pages
├── analytics/                   ← dashboard and performance analysis HTML
│
├── state/                       ← LIVE, daily updates
│   ├── current_week.md          ← daily-append buffer (THE working doc)
│   ├── current_week_plan.md     ← this week's planned sessions
│   └── limiters_now.md          ← active limiter + risks (high frequency)
│
├── reference/                   ← STATIC profile + strategy + logic
│   ├── athlete_profile.md       ← identity, body, training history
│   ├── medical.md               ← B12/pernicious anemia, calves, cardiac
│   ├── coaching_values.md       ← language rules, decision philosophy, tone
│   ├── master_plan.md           ← phases, dates, weekly templates, race day
│   ├── race_strategy.md         ← race-day pacing logic
│   ├── decision_rules.md        ← Green/Yellow/Red gates
│   ├── probe_rules.md           ← probe placement + stop rules
│   ├── time_protocol.md         ← mandatory time anchor verification
│   └── masters_protocols.md     ← 45-49 evidence base (placeholder, to research)
│
├── archive/2026/                ← IMMUTABLE history (Sunday close-out output)
│   ├── week_NN_report.md
│   └── week_NN_plan.md
│
├── trackers/                    ← APPEND-ONLY KPI logs
│   ├── wb_tracker.md
│   ├── sled_push_tracker.md
│   ├── sled_pull_tracker.md
│   ├── run_tracker.md
│   ├── bbj_tracker.md
│   ├── lunge_tracker.md
│   ├── probe_log.md
│   └── readiness_trend.md
│
```

---

## Write Contract

Read `CLAUDE.md` for full workflow specifications. Summary:

| Event | Who writes | Where |
|---|---|---|
| Morning readiness | Athlete (paste) → Claude (append plan) | `state/current_week.md` |
| Session data | Athlete (paste) → Claude (write report) | `state/current_week.md` |
| Lock change | Claude | `STATE.md` Locks + `trackers/<station>.md` |
| Probe done | Claude | `trackers/probe_log.md` + STATE |
| Limiter shift | Claude | `state/limiters_now.md` + STATE |
| Sunday close-out | Claude | rename current → archive, new current, new plan, sync STATE, push |
| Medical / preference update | Claude | `reference/medical.md` or `reference/coaching_values.md` |

**Rules:**
- Trackers append-only
- Archive immutable after creation
- STATE.md auto-derived from trackers
- All changes git-committed

---

## Language

- **Conversation:** Ukrainian or English (default English)
- **Documentation:** English only (every file)
- Reference: `reference/coaching_values.md` for full language and tone rules

---

## Race Target

**HYROX Sydney 2026-07-03 — 1:15:00**

Component splits required:
- 8 × 1 km running: ~32–34 min @ 4:00–4:15 / km
- WB 100 reps: ~5:00–5:30 (70+ UB ideal, or 50+50 with reset)
- Sled push 50 m: 1:20–1:40
- Sled pull 50 m: 2:30–3:30
- Transitions ×8: ≤15 sec each
- Total station time: ~38–42 min

Reference: `reference/race_strategy.md`

---

## Setup (one-time, on local Mac/Ubuntu)

```bash
# 1. Extract package
tar -xzf wolf-hyrox-v3.tar.gz
mv wolf-hyrox-v3 ~/wolf-hyrox

# 2. Init git
cd ~/wolf-hyrox
git init
git add .
git commit -m "Initial wolf-hyrox state W20 Build Day 48"

# 3. Connect to GitHub (if you have a repo)
git remote add origin git@github.com:yaroriver/wolf-hyrox.git
git branch -M main
git push -u origin main

# 4. Verify Claude Code can run
claude --version
cd ~/wolf-hyrox
claude
# Claude will read CLAUDE.md and STATE.md automatically
```

---

## Daily Cycle Example (W21+)

```
07:00 — Yaro on phone (Claude Project)
        Pastes morning readiness
        Claude calibrates plan in chat (no file write from Project)

19:00 — Yaro at home, opens terminal
        cd ~/wolf-hyrox && claude
        Pastes session data
        Claude writes report → state/current_week.md
        Claude updates trackers if lock changed
        Claude commits to git, pushes to GitHub

Sunday 18:00 — Yaro: "Sunday close-out"
        Claude:
          1. Generates W summary
          2. Archives week
          3. Creates next week's plan
          4. Syncs STATE
          5. Updates Wolf Portal HTML
          6. Pushes to GitHub
        Wolf Portal HTML updates automatically
```

---

## Update Protocol for This README

Updated only when:
- Folder structure changes
- Workflow contract changes (CLAUDE.md also updates)
- New setup steps required

Day-to-day operations do not modify this file.

Last updated: 2026-05-16
