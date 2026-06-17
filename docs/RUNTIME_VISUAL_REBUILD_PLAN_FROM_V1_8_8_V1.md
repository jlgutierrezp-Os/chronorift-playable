# RUNTIME_VISUAL_REBUILD_PLAN_FROM_V1_8_8_V1

## 0. Status

```yaml
status:
  public_repo_safe: true
  purpose: satisfy_NEXT_BUILD_GATE_before_any_new_build
  runtime_change_now: false
  code_change_now: false
  source_of_truth:
    - STOP_AT_V1_8_8_RUNTIME_VISUAL_REBUILD_GATE_V1
    - human_gate_message_NEXT_BUILD_GATE
```

This document is a plan only. It does not publish a new build and does not modify runtime.

---

## 1. Rebuild decision

```yaml
rebuild_decision:
  base_safe_point:
    build: v1.8.8_box_goal_snap_assist_stage_transition
    app_js_commit: 0d9c3ce82c9638b07566e13c7a08127fd6110007
    app_js_content_sha: dd6db35c1a91c1af25c3da48344e0a10fd5c0034

  branch_strategy:
    preferred: branch_from_v1_8_8_runtime_core
    branch_name_candidate: runtime-visual-rebuild-v1-9-0-from-v1-8-8

  do_not_use_as_base:
    - v1.8.9_to_v1.8.16_menu_overlay_range
```

The next runtime work should branch from the accepted v1.8.8 core, not from the menu-overlay range.

---

## 2. Playable visual delta definition

```yaml
playable_visual_delta:
  required:
    - actual_game_scene_changes_not_only_menu
    - camera_or_scene_visual_change_visible_during_play
    - map_or_space_representation_inside_canvas_runtime
    - preserve_box_portal_goal_loop

  first_delta_options:
    option_A_rear_aerial_camera:
      description: elevated behind-player view for box mobility and portal path readability
      affects_game_scene: true
      risk: medium

    option_B_gizmo_stable_view:
      description: stable gizmo/scanner camera overlay inside play scene, not a menu panel
      affects_game_scene: true
      risk: medium

    option_C_stage3_reception_canvas_layer:
      description: visible runtime reception area layer with box flow markers and construction zone marker
      affects_game_scene: true
      risk: medium_high

  minimum_acceptable_delta:
    - one_visible_runtime_camera_or_scene_layer
    - player_can_move_after_change
    - box_goal_core_still_works
```

A valid next build must visibly change the playable scene or camera, not only the HTML UI.

---

## 3. Runtime plan phases

```yaml
runtime_visual_rebuild_phases:
  phase_0_restore_and_verify:
    objective: restore v1.8.8 behavior as baseline
    checks:
      - player_moves
      - box_grab_works
      - rift_A_B_works
      - box_crosses_portal
      - green_goal_snap_works
      - puzzle_resolved_or_stage_2_visible

  phase_1_small_visual_delta:
    objective: add exactly one runtime visual delta
    allowed:
      - rear_aerial_camera_label_and_view_transform
      - gizmo_stable_view_inside_canvas
      - stage3_marker_inside_canvas
    not_allowed:
      - new_menu_only_overlay
      - unrelated Somero expansion
      - full Stage 3 physics

  phase_2_regression_check:
    objective: prove v1.8.8 core remains playable
    checks:
      - box_goal_core_same_or_better
      - no_input_blocking
      - no_portal_regression
      - no_goal_snap_regression

  phase_3_human_test:
    objective: human confirms visual runtime change
    required_report:
      - visual_change_seen: yes/no
      - change_inside_play_scene: yes/no
      - core_still_works: yes/no
      - playable_confirmed: yes/no
```

---

## 4. Verification method

```yaml
verification_method:
  machine_check:
    - fetch_runtime_file_and_confirm_version_label
    - inspect_code_for_canvas_or_camera_runtime_delta
    - ensure_app_js_or_new_runtime_file_changed_intentionally
    - ensure_index_only_menu_change_is_not_mislabeled_as_runtime_visual

  human_check:
    - open_new_build_url
    - compare_against_v1_8_8_baseline
    - confirm_visible_change_during_play
    - confirm_box_goal_core_still_works

  visual_indicators_expected:
    - changed_camera_or_scene_while_moving
    - not_only_menu_or_overlay
    - runtime_canvas_affected
```

---

## 5. Rollback plan

```yaml
rollback_plan:
  rollback_anchor:
    build: v1.8.8_box_goal_snap_assist_stage_transition
    app_js_commit: 0d9c3ce82c9638b07566e13c7a08127fd6110007
    app_js_content_sha: dd6db35c1a91c1af25c3da48344e0a10fd5c0034

  rollback_if:
    - box_grab_breaks
    - portal_A_B_breaks
    - green_goal_snap_breaks
    - player_input_breaks
    - visual_delta_is_only_menu
    - user_cannot_run_or_play

  rollback_action:
    - restore_app_js_to_v1_8_8_content
    - restore_index_to_minimal_launcher_if_needed
    - mark_attempt_failed_not_playable
```

---

## 6. Proposed next branch packet

```yaml
NEXT_BRANCH_PACKET:
  branch_name: runtime-visual-rebuild-v1-9-0-from-v1-8-8
  base: v1.8.8_runtime_core
  first_target: one_runtime_visual_delta_only
  recommended_first_delta: rear_aerial_camera_or_gizmo_stable_view
  forbidden:
    - menu_only_overlay_as_success
    - full_stage_3_physics_first
    - claiming_success_before_human_confirmation
```

---

## 7. Acceptance gate for next build

```yaml
next_build_acceptance_gate:
  accept_if:
    - user_can_see_actual_play_visualization_change
    - change_affects_game_scene_or_camera_not_only_menu
    - core_box_portal_goal_still_works
    - user_confirms_runnable_and_playable

  fail_if:
    - only_UI_menu_changes
    - only_text_or_overlay_changes
    - gameplay_scene_remains_effectively_v1_8_8_without_declared_reason
    - assistant_claims_build_success_without_human_confirmation
```
