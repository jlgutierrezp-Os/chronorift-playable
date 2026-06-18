# BATCH_NEXT_OPTIMAL_FUN_PHYSICS_CAMERA_ALERTS_V1

## 0. Status

```yaml
status:
  public_repo_safe: true
  purpose: make_core_more_fun_by_prioritizing_physics_portals_and_action_visibility
  runtime_change_now: false
  main_gameplay_change_now: false
  source_issue: 9
  do_not_start_with:
    - cosmetic_avatar_only
    - gizmo_stable_view_only
    - menu_overlay_feedback_only
```

This batch exists because the current game is not fun enough, portals do not yet support satisfying physics play, and visualizations do not show action and movement clearly enough.

---

## 1. Priority

```yaml
priority:
  P1_runtime_core:
    - portal_physics_play
    - movement_action_visibility

  P2_experience:
    - fun_loop
    - alert_cutaway_camera
```

The next runtime work must improve play feel and action readability before adding cosmetic avatar polish, gizmo-only views, or menu-only overlays.

---

## 2. Alert cutaway room camera state machine

```yaml
alert_cutaway_room_camera:
  purpose:
    - show_full_room_context_during_important_events
    - help_player_understand_box_delivery_or_supervision_alert
    - return_player_to_previous_view_without_disorientation

  triggers:
    - box_delivery_alert
    - supervision_alert
    - important_room_event

  state_machine:
    idle:
      description: player_uses_current_view_normally
      on_alert:
        - save_previous_view
        - save_previous_camera_parameters
        - enter_cutaway_intro

    cutaway_intro:
      duration: 0.2_to_0.4_seconds
      action:
        - fade_or_snap_to_external_room_overview
        - freeze_view_mode_switching_if_needed
      next: room_overview_hold

    room_overview_hold:
      duration: 2_to_3_seconds
      camera:
        type: external_room_overview
        shows:
          - player
          - box
          - active_portals
          - goal
          - alert_source
          - relevant_motion_or_route
      next: return_to_previous_view

    return_to_previous_view:
      duration: 0.2_to_0.4_seconds
      action:
        - restore_previous_view
        - restore_previous_camera_parameters
        - resume_normal_control_frame
      next: idle

  constraints:
    - do_not_permanently_reorient_controls
    - do_not_trap_player_in_cutaway
    - do_not_block_box_grab_portal_goal_after_return
```

---

## 3. Minimal portal physics fun model

```yaml
portal_physics_fun_model:
  goal:
    - allow_player_to_experiment_with_motion
    - make_box_and_player_cause_effect_readable
    - make_portals_feel_like_physical_tools_not_symbols

  required_primitives:
    - position
    - velocity
    - portal_normal
    - portal_tangent
    - entry_speed
    - exit_direction
    - safe_exit_point
    - trajectory_preview

  minimum_behavior:
    box:
      - velocity_enters_portal
      - exit_direction_visible
      - speed_preserved_or_intentionally_boosted
      - collision_safe_exit
      - afterimage_or_motion_line_shows_result

    player:
      - player_can_enter_portal_when_close_and_oriented
      - exit_direction_visible
      - no_unreadable_instant_transfer

  fun_tests:
    - player_can_push_or_throw_box_into_portal
    - box_exits_with_readable_motion
    - player_can_predict_where_box_will_go
    - camera_shows_motion_before_and_after_portal
```

---

## 4. Action visibility requirement

```yaml
action_visibility:
  required_visible_entities:
    - player
    - box
    - active_portal_A
    - active_portal_B
    - goal
    - trajectory_or_route
    - alert_source_when_triggered

  visual_distinction:
    player: distinct_avatar_or_marker
    box: distinct_physical_cube_or_crate
    portals: distinct_open_surface_or_ring
    goal: distinct_target_zone
    route: line_or_afterimage_not_confused_with_box

  failure_conditions:
    - player_only_seen_as_ambiguous_triangle
    - box_only_seen_as_line_square_like_portal_marker
    - portals_are_symbols_without_physics_readability
    - movement_is_hidden_by_camera
```

---

## 5. Fun success test

```yaml
fun_success_test:
  human_report_required:
    - more_fun_than_previous_build: yes_no
    - portal_physics_more_playable: yes_no
    - movement_action_visible: yes_no
    - alert_cutaway_helped_understand_scene: yes_no
    - camera_returned_to_previous_view: yes_no
    - core_box_grab_still_works: yes_no
    - green_goal_snap_still_works: yes_no

  target_minimum:
    more_fun_than_previous_build: yes
    portal_physics_more_playable: yes
    movement_action_visible: yes
    camera_returned_to_previous_view: yes
```

---

## 6. Runtime candidate after this design

```yaml
runtime_candidate:
  id: v1_9_0B_fun_physics_alert_cutaway_candidate
  branch: runtime-visual-rebuild-v1-9-0-from-v1-8-8
  base_current: v1_9_0A2

  first_runtime_patch_scope:
    - add_alert_cutaway_camera_state_machine
    - add_room_overview_hold_2_to_3_seconds
    - add_portal_velocity_or_trajectory_visualization
    - improve_entity_distinction_enough_for_test

  not_in_first_patch:
    - full_gizmo_stable_view_delta_B
    - full_conveyor_system
    - full_3d_physics_engine
    - cosmetic_avatar_customizer
```
