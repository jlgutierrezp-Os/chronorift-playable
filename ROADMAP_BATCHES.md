# ChronoRift Update Batches

Operational roadmap from the current public static preview toward the interview goal: a minimalist brutalist zen temporal puzzle experience with flow, grace, hyperfocus, spatial rifts, temporal rifts, echoes, Platonic-form avatar fields, and progressive puzzle architecture.

## Non-negotiable delivery rule

Each playable batch must keep the game runnable from the public static GitHub Pages route. Do not call a batch playable until the human confirms it opens and can be played on iPhone.

Status terms:

```yaml
code_complete: false
public_preview_updated: false
runnable_by_user: false
playable_confirmed: false
```

## Batch 0 — Static preview stabilization

Goal: confirm the public route works before adding complexity.

Scope:

- Confirm GitHub Pages branch/root preview opens.
- Confirm iPhone Safari loads canvas.
- Confirm joystick moves avatar.
- Confirm SelfDebug opens and closes.
- Confirm copy/manual-copy of report packet.
- Fix only blockers.

Human feedback required:

- Did the URL open?
- Did the canvas draw?
- Did the joystick move?
- Did SelfDebug return to game?
- Paste SelfDebug packet if anything failed.

Promotion gate:

```yaml
runnable_by_user: true
playable_confirmed: true
selfdebug_closeable: true
```

## Batch 1 — Control feel and iPhone UX

Goal: make the baseline pleasant enough to test repeatedly.

Scope:

- Better joystick dead zone and smoothing.
- Larger edge buttons without blocking view.
- HUD more minimal.
- Touch aim feedback.
- Prevent accidental scroll/zoom issues.
- Add visible safe reset button only if needed.

Human feedback:

- controls_error
- usability_error
- visibility_error
- performance_error

Promotion gate:

```yaml
controls_usable_on_iphone: true
selfdebug_not_blocking: true
fps_stable_enough: true
```

## Batch 2 — Rift Type 1 spatial portals

Goal: make spatial rifts feel intentional and readable.

Scope:

- Stronger Rift A/B placement feedback.
- Better portal entry/exit rules.
- Prevent portal jitter/retrigger loops.
- Add short cooldown visual.
- Add visual connection line between A and B.
- Add simple level objective requiring portal use.

Human feedback:

- rift_error
- collision_error
- gameplay_error
- visibility_error

Promotion gate:

```yaml
rift_pair_usable: true
portal_cooldown_clear: true
at_least_one_portal_solution: true
```

## Batch 3 — Temporal echo baseline

Goal: make Time create a useful future echo.

Scope:

- Clean temporal trace display.
- Echo follows previous path more clearly.
- Echo can press plate.
- Echo can push or nudge block lightly.
- Echo count and path length visible only when useful.
- Collapse if line is cleared or disrupted.

Human feedback:

- temporal_error
- gameplay_error
- visibility_error
- performance_error

Promotion gate:

```yaml
echo_can_solve_plate: true
echo_readable: true
collapse_not_confusing: true
```

## Batch 4 — SelfDebug optimization for /agent-luu

Goal: convert human play feedback into structured update requests.

Scope:

- Better report categories.
- Add one-tap batch status summary.
- Add current build/version in packet.
- Add last action/event list.
- Add human decision field: approve, rollback, fix blocker, optimize.
- Add copy-all fallback instructions for iOS.

Human feedback:

- usability_error
- report_quality_error
- agent_luu_packet_error

Promotion gate:

```yaml
report_packet_copiable: true
report_packet_useful_for_next_update: true
human_can_decide_next_action: true
```

## Batch 5 — Brutalist zen art direction pass

Goal: move from placeholder 2D toward the intended atmosphere while staying lightweight.

Scope:

- Concrete-gray world palette.
- White light accents.
- Subtle black/neon secondary accent.
- Minimal grid/architecture language.
- Portal shimmer and temporal dust.
- Less UI noise.

Human feedback:

- aesthetic_error
- visibility_error
- atmosphere_error

Promotion gate:

```yaml
brutalist_zen_feel: acceptable
ui_less_intrusive: true
readability_preserved: true
```

## Batch 6 — Platonic avatar and field mechanics

Goal: introduce the avatar-as-form concept.

Scope:

- Selectable Platonic hitbox symbols.
- Basic attraction/repulsion field.
- Field affects block and similar forms.
- Simple puzzle requiring field use.
- Keep physics stable and readable.

Human feedback:

- physics_error
- controls_error
- gameplay_error
- visibility_error

Promotion gate:

```yaml
shape_selection_understood: true
field_mechanic_useful: true
physics_not_frustrating: true
```

## Batch 7 — Temporal Rift Type 2 prototype

Goal: select a point on the temporal trace and open a temporal aperture.

Scope:

- Lens mode shows selectable trace points.
- Touch a trace point to mark temporal aperture.
- Time-rift returns player or echo to selected trace point.
- Add cooldown and clear visual feedback.
- No complex non-Euclidean behavior yet.

Human feedback:

- temporal_error
- rift_error
- perspective_error
- gameplay_error

Promotion gate:

```yaml
temporal_trace_selectable: true
time_rift_effect_understood: true
no_major_softlock: true
```

## Batch 8 — Puzzle language expansion

Goal: add small puzzle families without bloating the architecture.

Scope:

- Door/plate refinement.
- Block/field puzzles.
- Light/shadow placeholder puzzle.
- Gravity or impulse placeholder puzzle.
- Optional sacrifice-line puzzle.
- Level select basics.

Human feedback:

- puzzle_clarity_error
- difficulty_error
- gameplay_error

Promotion gate:

```yaml
at_least_three_puzzle_types_work: true
level_select_basic: true
solutions_feel_intentional: true
```

## Batch 9 — Flow, grace, hyperfocus pass

Goal: reduce friction and improve contemplative rhythm.

Scope:

- Smoother movement.
- Better timing windows.
- Less intrusive messages.
- More readable loop setup.
- Short success feedback.
- Calm failure/retry loop.

Human feedback:

- flow_error
- frustration_error
- clarity_error
- performance_error

Promotion gate:

```yaml
repeat_play_not_annoying: true
failure_loop_clear: true
flow_improved: true
```

## Batch 10 — 2.5D / 3D architecture decision gate

Goal: decide if current 2D canvas architecture has reached its limit.

Evaluate:

- Can iPhone run current scope smoothly?
- Are mechanics blocked by 2D representation?
- Does the desired camera system require a new engine?
- Is code size becoming hard to manage?
- Is update risk increasing?

Decision options:

```yaml
continue_2d_canvas:
  when: mechanics still testable and fast

move_to_2_5d_canvas:
  when: visual depth needed but no heavy engine

move_to_lightweight_webgl:
  when: camera/perspective/3d essential

move_to_engine:
  when: physics/world complexity exceeds hand-coded static preview
```

Human feedback:

- architecture_limit
- performance_limit
- visual_limit
- gameplay_limit

Promotion gate:

```yaml
architecture_decision_recorded: true
next_machinery_selected: true
```

## Batch 11 — Minimal 3D brutalist prototype, only after gate

Goal: begin 3D only if Batch 10 says the 2D route reached a real limit.

Scope:

- Minimal brutalist space.
- One avatar form.
- One spatial rift pair.
- One temporal trace mechanic.
- No broad feature port until runnable.

Human feedback:

- perspective_error
- performance_error
- controls_error
- atmosphere_error

Promotion gate:

```yaml
3d_runnable_on_iphone: true
controls_acceptable: true
core_mechanic_survives: true
```

## Batch loop contract

After every batch:

```yaml
human_feedback_required:
  - open_url_result
  - gameplay_result
  - selfdebug_packet_if_error
  - decision:
      - approve_next_batch
      - fix_blocker
      - rollback
      - choose_new_architecture
```

Never advance to a larger batch while a P0/P1 runnable or SelfDebug error remains.
