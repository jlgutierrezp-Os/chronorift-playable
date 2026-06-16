# ChronoRift Assisted Autoupdate Protocol

This protocol simplifies the human feedback loop for voice mode, screen sharing, screenshots, SelfDebug packets, and safe update generation.

## Purpose

Move from fragmented bug reports to one simple loop:

```yaml
human_observes_play:
  - shares screen or screenshots when available
  - describes desired change by voice or text
  - optionally pastes SelfDebug packet

assistant_integrates:
  - visible state
  - human intent
  - system state
  - SelfDebug state
  - roadmap goal
  - safety boundary

assistant_returns:
  - honest diagnosis
  - prioritized improvements
  - safe patch plan
  - exact update batch
  - status terms
```

## Important limitation

The assistant may analyze screenshots, pasted packets, and any screen content that is actually provided in the chat. If live screen visibility is not available in the current client session, the human provides screenshots or describes what is seen. Do not assume unseen screen details.

## One-command human loop

The human can use this command:

```text
/autoupdate-live
```

Then provide any combination of:

```yaml
inputs:
  - screen_cast_or_screenshot
  - voice_description
  - current_url_state
  - SelfDebug_packet
  - desired_feel_or_goal
  - specific frustration
```

## Minimal human phrase

```text
I am showing the screen. Improve what is visible toward the ChronoRift interview goal. Priority: [human request].
```

Spanish version:

```text
Estoy mostrando la pantalla. Mejora lo visible hacia la meta de entrevista de ChronoRift. Prioridad: [solicitud humana].
```

## Assistant integration checklist

Before suggesting or applying an update, classify:

```yaml
visual_layer:
  - canvas_visible
  - HUD_visible
  - buttons_visible
  - target_visible
  - block_visible
  - portals_visible
  - temporal_trace_visible
  - selfdebug_visible

system_layer:
  - build_label
  - viewport
  - device_pixel_ratio
  - fps
  - player_position
  - block_position
  - rift_state
  - echo_count
  - history_length
  - last_events

human_intent_layer:
  - desired_feel
  - frustration
  - target_mechanic
  - priority_area

roadmap_layer:
  - current_batch
  - next_batch
  - blocked_batch
  - whether_update_is_fix_or_feature

security_layer:
  - target_repo_is_chronorift_playable
  - no_ancestor_repo_write
  - no_workflows
  - no_secrets
  - no_dependencies
```

## Evaluation areas

Every response should evaluate all relevant areas, even if the human names only one:

```yaml
evaluation_areas:
  gameplay:
    focus: fun, objective clarity, problem-solution loop
  controls:
    focus: iPhone touch, joystick, button placement, accidental input
  physics:
    focus: smoothness, friction, momentum, block transport, collision
  rifts:
    focus: spatial A/B placement, direction, readability, cooldown
  temporal:
    focus: echoes, trace, temporal portal, collapse, causality
  UX:
    focus: HUD, panels, SelfDebug, copyability, return-to-game
  aesthetics:
    focus: brutalist zen, concrete gray, white light, minimal noise
  performance:
    focus: FPS, lag, canvas size, battery/heat risk
  safety:
    focus: public repo isolation, no secrets, no external dependencies
  roadmap_alignment:
    focus: movement toward interview goal without premature architecture jump
```

## Output format

For each live/voice assisted update, return:

```yaml
ASSISTED_UPDATE_RESULT:
  observed:
    visible:
    reported:
    packet:
  interpretation:
    primary_issue:
    secondary_issues:
    likely_root_cause:
  optimal_improvements:
    P0:
    P1:
    P2:
    P3:
  proposed_patch:
    build_id:
    files_to_change:
    expected_visible_marker:
    expected_gameplay_change:
  safety_gate:
    target_repo:
    forbidden_changes:
    passed: true_or_false
  human_test_after_update:
    - open_url
    - visible_build_marker
    - test_specific_mechanic
    - selfdebug_packet_if_failed
```

## Autoupdate decision rule

```yaml
if_P0_or_P1:
  action: fix_current_build_before_next_batch

if_feedback_is_feel_or_tuning:
  action: small_incremental_patch

if_requested_feature_matches_current_batch:
  action: implement_minimal_feature_version

if_requested_feature_exceeds_architecture:
  action: document_limit_and_offer_architecture_gate

if_update_risks_breaking_playability:
  action: split_into_smaller_patch
```

## Safe status terms

Never skip these:

```yaml
code_complete:
public_preview_updated:
runnable_by_user:
playable_confirmed:
```

## Success condition

```yaml
success:
  - fewer_repeated_errors
  - less_same_error_category
  - faster_human_feedback_to_patch
  - every patch has visible version marker
  - human can test one concrete change at a time
  - project advances toward interview goal
```
