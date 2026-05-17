# wolf-hyrox Operational Workflows

> Formal smoke-test contract for the coaching loop. Documentation language: English only.

---

## 1. `/morning` — Morning Readiness Calibration

### Trigger Phrase
Yaro types `/morning` and pastes morning readiness data.

### Input Expected
- Date or clear "today" context
- Sleep duration
- Restful sleep percentage or restful duration
- HRV in ms and baseline comparison if available
- Calf rating left/right, 0-10
- Body feel, 1-10
- Overnight cramp signal: yes/no
- Under-knee pulling: yes/no
- Cardiac sensation: yes/no

### Files Read
- `/home/citadel/Documents/wolf-hyrox_Gpt/STATE.md`
- `/home/citadel/Documents/wolf-hyrox_Gpt/state/current_week.md`
- `/home/citadel/Documents/wolf-hyrox_Gpt/state/current_week_plan.md`
- `/home/citadel/Documents/wolf-hyrox_Gpt/state/limiters_now.md`
- `/home/citadel/Documents/wolf-hyrox_Gpt/reference/coaching_values.md`
- `/home/citadel/Documents/wolf-hyrox_Gpt/reference/decision_rules.md`
- `/home/citadel/Documents/wolf-hyrox_Gpt/reference/time_protocol.md`
- `/home/citadel/Documents/wolf-hyrox_Gpt/reference/medical.md` when calves, B12, sleep, or cardiac signals are present

### Files Written / Modified
- `/home/citadel/Documents/wolf-hyrox_Gpt/state/current_week.md` — append
- `/home/citadel/Documents/wolf-hyrox_Gpt/trackers/readiness_trend.md` — append
- `/home/citadel/Documents/wolf-hyrox_Gpt/STATE.md` — overwrite only if time anchor or active state has drifted

### Git Operations
- `git add -A`
- `git commit -m "YYYY-MM-DD readiness: <day> morning readiness + calibrated plan"`
- `git push origin main` after remote is configured

### Output To Yaro
- TIME ANCHOR block
- Green / Yellow / Red classification
- Reason for classification
- Calibrated session plan with numbers
- Hard rules and cut rules
- One "Today's principle" line

### Failure Modes
- Missing readiness data blocks classification
- Date drift greater than 24 hours requires state refresh
- Cardiac signal forces Red and blocks quality
- Calf rating 4/10+ blocks high-impact training
- Git unavailable blocks commit/push only, not coaching response

---

## 2. `/session` — Post-Session Report And Tracker Sync

### Trigger Phrase
Yaro types `/session` and pastes completed session data.

### Input Expected
- Session date
- Planned session reference if available
- Completed work with loads, reps, distances, times
- HR data and zones where available
- Subjective feedback
- Calf status pre/during/post
- Stop reason for probes or cut sessions
- Any PR, lock change, or failed target

### Files Read
- `/home/citadel/Documents/wolf-hyrox_Gpt/STATE.md`
- `/home/citadel/Documents/wolf-hyrox_Gpt/state/current_week.md`
- `/home/citadel/Documents/wolf-hyrox_Gpt/state/current_week_plan.md`
- `/home/citadel/Documents/wolf-hyrox_Gpt/state/limiters_now.md`
- `/home/citadel/Documents/wolf-hyrox_Gpt/reference/coaching_values.md`
- `/home/citadel/Documents/wolf-hyrox_Gpt/reference/decision_rules.md`
- `/home/citadel/Documents/wolf-hyrox_Gpt/reference/probe_rules.md` for probe sessions
- `/home/citadel/Documents/wolf-hyrox_Gpt/reference/medical.md` when risk signals appear
- Relevant tracker files under `/home/citadel/Documents/wolf-hyrox_Gpt/trackers/`

### Files Written / Modified
- `/home/citadel/Documents/wolf-hyrox_Gpt/state/current_week.md` — append raw data and structured report
- `/home/citadel/Documents/wolf-hyrox_Gpt/trackers/probe_log.md` — append when probe occurs
- `/home/citadel/Documents/wolf-hyrox_Gpt/trackers/wb_tracker.md` — append when WB data changes
- `/home/citadel/Documents/wolf-hyrox_Gpt/trackers/run_tracker.md` — append when running data changes
- `/home/citadel/Documents/wolf-hyrox_Gpt/trackers/bbj_tracker.md` — append when BBJ data changes
- `/home/citadel/Documents/wolf-hyrox_Gpt/trackers/sled_push_tracker.md` — append when sled push data changes
- `/home/citadel/Documents/wolf-hyrox_Gpt/trackers/sled_pull_tracker.md` — append when sled pull data changes
- `/home/citadel/Documents/wolf-hyrox_Gpt/trackers/lunge_tracker.md` — append when lunge data changes
- `/home/citadel/Documents/wolf-hyrox_Gpt/trackers/readiness_trend.md` — append if readiness row was missing
- `/home/citadel/Documents/wolf-hyrox_Gpt/state/limiters_now.md` — overwrite when limiter changes
- `/home/citadel/Documents/wolf-hyrox_Gpt/STATE.md` — overwrite when locks, limiter, or time anchor change

### Git Operations
- `git add -A`
- `git commit -m "YYYY-MM-DD session: <session type> report"`
- `git push origin main` after remote is configured

### Output To Yaro
- TIME ANCHOR block
- Execution summary
- Key data interpreted
- Comparison to plan
- Lock and tracker updates
- Limiter status
- Risk notes
- One "Today's principle" line

### Failure Modes
- Missing session numbers force "Data not provided"
- Probe without stop reason can still log result with stop reason marked "Data not provided"
- Tracker append blocked by file permission failure
- Conflicting source values require explicit correction before lock update
- Git unavailable blocks commit/push only

---

## 3. `/update-portal` — Wolf Portal HTML Generation

### Trigger Phrase
Yaro types `/update-portal`.

### Input Expected
- Target week number
- Whether generating a plan page, completed page, or both
- Source Markdown file exists for each generated page

### Files Read
- `/home/citadel/Documents/wolf-hyrox_Gpt/STATE.md`
- `/home/citadel/Documents/wolf-hyrox_Gpt/state/limiters_now.md`
- `/home/citadel/Documents/wolf-hyrox_Gpt/state/current_week_plan.md` for current plan pages
- `/home/citadel/Documents/wolf-hyrox_Gpt/archive/2026/week_NN_report.md` for completed pages
- `/home/citadel/Documents/wolf-hyrox_Gpt/trackers/*`
- Existing templates under `/home/citadel/Documents/wolf-hyrox_Gpt/plans/` and `/home/citadel/Documents/wolf-hyrox_Gpt/completed/`
- `/home/citadel/Documents/wolf-hyrox_Gpt/PORTAL.html`

### Files Written / Modified
- `/home/citadel/Documents/wolf-hyrox_Gpt/completed/wolf_wNN_completed.html` — new or overwrite generated HTML
- `/home/citadel/Documents/wolf-hyrox_Gpt/plans/wolf_wNN_plan.html` — new or overwrite generated HTML
- `/home/citadel/Documents/wolf-hyrox_Gpt/PORTAL.html` — overwrite targeted card section

### Git Operations
- `git add -A`
- `git commit -m "YYYY-MM-DD portal: update Wolf Portal WNN"`
- `git push origin main`

### Output To Yaro
- TIME ANCHOR block
- Files generated
- Source files used
- Portal cards updated
- Git commit hash and push result
- GitHub Pages URL if available

### Failure Modes
- Source Markdown missing
- Template HTML missing
- PORTAL card anchor cannot be found
- GitHub remote unavailable
- GitHub Pages disabled or not yet deployed

---

## 4. `/close-week` — Sunday Close-Out

### Trigger Phrase
Yaro types `/close-week` or "Sunday close-out".

### Input Expected
- Sunday readiness data
- Sunday recovery/session data if any
- Confirmation that week logging is complete

### Files Read
- `/home/citadel/Documents/wolf-hyrox_Gpt/STATE.md`
- `/home/citadel/Documents/wolf-hyrox_Gpt/state/current_week.md`
- `/home/citadel/Documents/wolf-hyrox_Gpt/state/current_week_plan.md`
- `/home/citadel/Documents/wolf-hyrox_Gpt/state/limiters_now.md`
- `/home/citadel/Documents/wolf-hyrox_Gpt/reference/master_plan.md`
- `/home/citadel/Documents/wolf-hyrox_Gpt/reference/decision_rules.md`
- `/home/citadel/Documents/wolf-hyrox_Gpt/reference/probe_rules.md`
- `/home/citadel/Documents/wolf-hyrox_Gpt/reference/medical.md`
- `/home/citadel/Documents/wolf-hyrox_Gpt/archive/2026/week_NN_report.md` for recent history when present
- `/home/citadel/Documents/wolf-hyrox_Gpt/trackers/*`

### Files Written / Modified
- `/home/citadel/Documents/wolf-hyrox_Gpt/state/current_week.md` — append weekly summary, then move to archive
- `/home/citadel/Documents/wolf-hyrox_Gpt/archive/2026/week_NN_report.md` — new immutable archive file
- `/home/citadel/Documents/wolf-hyrox_Gpt/state/current_week.md` — new live weekly file
- `/home/citadel/Documents/wolf-hyrox_Gpt/archive/2026/week_NN_plan.md` — new plan file
- `/home/citadel/Documents/wolf-hyrox_Gpt/state/current_week_plan.md` — overwrite with new active week plan when adopted
- `/home/citadel/Documents/wolf-hyrox_Gpt/STATE.md` — overwrite with refreshed week boundary state
- `/home/citadel/Documents/wolf-hyrox_Gpt/trackers/readiness_trend.md` — append Sunday row and weekly summary block
- Portal HTML files — optional generated output

### Git Operations
- `git add -A`
- `git commit -m "WNN close-out + WNN+1 plan — <phase context>"`
- `git push origin main`

### Output To Yaro
- TIME ANCHOR block
- Weekly summary
- Files archived and created
- New week phase position
- Next probe target
- Commit hash and push result

### Failure Modes
- Sunday readiness missing
- Current week already archived
- Archive target already exists
- Week number conflicts with time anchor
- Required tracker data missing for lock sync
- Git remote unavailable

---

## 5. `/status` — Read-Only State Check

### Trigger Phrase
Yaro types `/status`.

### Input Expected
- No training data required

### Files Read
- `/home/citadel/Documents/wolf-hyrox_Gpt/STATE.md`
- `/home/citadel/Documents/wolf-hyrox_Gpt/state/current_week.md`
- `/home/citadel/Documents/wolf-hyrox_Gpt/state/current_week_plan.md`
- `/home/citadel/Documents/wolf-hyrox_Gpt/state/limiters_now.md`
- `/home/citadel/Documents/wolf-hyrox_Gpt/trackers/probe_log.md`
- Relevant tracker files when status asks about a station

### Files Written / Modified
- None

### Git Operations
- None

### Output To Yaro
- TIME ANCHOR block
- Current phase and days to race
- Current locks
- Active limiter
- Current week completion state
- Next planned session or next probe
- Data freshness warnings

### Failure Modes
- STATE.md missing
- Time anchor conflicts with state by more than 24 hours
- Referenced current week file missing
- Tracker and STATE lock values conflict

