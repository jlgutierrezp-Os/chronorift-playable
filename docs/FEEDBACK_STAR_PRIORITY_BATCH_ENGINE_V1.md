# FEEDBACK_STAR_PRIORITY_BATCH_ENGINE_V1

## 0. Status

```yaml
status:
  public_repo_safe: true
  purpose: create_regular_player_feedback_loop_for_prioritized_batches
  runtime_gameplay_change_now: false
  main_gameplay_change_now: false
  source: human_request_after_A2_test
```

This is a support/feedback system. It must not be claimed as a gameplay or visual-runtime improvement by itself.

---

## 1. Core intent

```yaml
feedback_engine:
  user_flow:
    - player_keeps_playing
    - player_opens_feedback
    - player_selects_experience_stars
    - player_writes_short_note
    - player_copies_feedback_packet
    - assistant_or_agent_prioritizes_next_batch

  goal:
    - reduce_unstructured_feedback_cost
    - preserve_player_regular_experience
    - turn_player_report_into_batch_priorities
    - avoid_repeating_preventable_errors
```

---

## 2. Star categories

```yaml
star_categories:
  overall_experience:
    scale: 1_to_5
    priority_weight: high

  controls:
    scale: 1_to_5
    priority_weight: critical_if_under_3

  visibility:
    scale: 1_to_5
    priority_weight: critical_if_under_3

  objective_clarity:
    scale: 1_to_5
    priority_weight: high

  physics_feel:
    scale: 1_to_5
    priority_weight: high

  portals:
    scale: 1_to_5
    priority_weight: high

  box_handling:
    scale: 1_to_5
    priority_weight: high

  flow_focus:
    scale: 1_to_5
    priority_weight: medium_high

  aesthetic_readability:
    scale: 1_to_5
    priority_weight: medium
```

---

## 3. Priority compiler

```yaml
priority_compiler:
  P0_blocker:
    triggers:
      - page_does_not_load
      - player_cannot_move
      - game_cannot_be_played
      - controls_score_under_2
      - visual_scene_unreadable

  P1_runtime_core:
    triggers:
      - box_grab_breaks
      - green_goal_snap_breaks
      - portal_A_B_breaks
      - player_avatar_not_visible
      - box_not_distinguishable

  P2_experience:
    triggers:
      - objective_unclear
      - flow_breaks
      - camera_disorienting
      - marker_surface_binding_unclear

  P3_content_next:
    triggers:
      - player_requests_new_modules
      - minigame_request
      - story_or_gizmo_unlock_request
      - polish_without_core_breakage
```

---

## 4. Feedback packet contract

```yaml
feedback_packet_contract:
  packet_name: CHRONORIFT_PLAYER_FEEDBACK_PACKET
  required_fields:
    - build_or_test_url
    - timestamp
    - device_context
    - stars
    - quick_tags
    - what_worked
    - what_failed
    - next_priority_guess
    - free_note

  optional_fields:
    - screenshot_note
    - location_in_game
    - current_view
    - current_objective
    - copied_from_in_game_feedback_overlay
```

---

## 5. Batch decision output

```yaml
batch_decision_output:
  after_feedback_received:
    - parse_star_scores
    - identify_lowest_scoring_category
    - map_to_P0_P1_P2_P3
    - select_next_batch
    - preserve_current_safe_point
    - state_what_will_not_be_done

  expected_assistant_output:
    - feedback_interpretation
    - priority_order
    - next_batch_scope
    - forbidden_scope
    - acceptance_test
```

---

## 6. Runtime gate

```yaml
runtime_gate:
  allowed_as_test_launcher:
    - feedback_overlay
    - copy_packet_button
    - star_rating_UI

  not_allowed_as_claim:
    - calling_feedback_overlay_a_gameplay_update
    - claiming_playable_improvement_from_feedback_UI_only

  before_main_integration:
    - player_confirms_feedback_tool_is_useful
    - copy_packet_works_on_iPhone
    - overlay_closes_and_does_not_block_play
```
