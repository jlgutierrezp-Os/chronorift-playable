# STAGE_3_ACTIVE_BUILD_AREAS_CAMERA_CHECKPOINT_SPEC_V1

## 0. Status

```yaml
status:
  public_repo_safe: true
  purpose: integrate_v1_8_15_feedback_into_playable_stage_3_requirements
  runtime_change_now: false
  code_change_now: false
  source_of_truth: human_feedback_v1_8_15
  parent_specs:
    - STAGE_3_RECEPTION_BOX_ECONOMY_PR_WORM_SPEC_V1
    - STAGE_3_STACKABLE_BOX_PHYSICS_CONVEYOR_SPEC_V1
    - STAGE_3_MODULAR_LOGISTICS_CONSTRUCTION_SYSTEM_SPEC_V1
  preserve_current_playable:
    - app_js_v1_8_8
    - Somero_closeable_v1_8_13
    - box_goal_core
    - portal_core
```

The v1.8.15 overlay was useful as a menu prototype, but it did not yet change the game state or represent the play environment. This document defines the next integration requirements.

---

## 1. Human feedback summary

```yaml
v1_8_15_feedback:
  accepted:
    - menus_function
    - Somero_closes
    - core_still_works

  insufficient:
    - build_menu_does_not_affect_game
    - grid_does_not_represent_the_play_environment
    - route_preview_does_not_work_as_game_route
    - coins_preview_does_not_behave_as_game_feedback
    - gizmo_teaser_not_visible_enough
    - build_close_to_game_not_confirmed

  priority:
    - integrated_playable_map
    - construction_areas_only
    - stable_camera_modes
    - saveable_solutions
    - deadline_alerts
```

---

## 2. Build menu activation rule

```yaml
build_activation:
  allowed_only_in:
    - construction_area
    - workbench_area
    - desk_area
    - stage_3_reception_planning_zone

  not_allowed_when:
    - player_is_in_active_delivery_motion
    - player_is_mid_portal_transfer
    - player_is_carrying_unstable_box_stack
    - deadline_alert_is_resolving

  feedback_if_not_allowed:
    - show_message: Build available only in construction zones
    - show_marker_to_nearest_construction_area
```

The construction menu should not be a global abstract menu. It must feel like a tool used in the correct physical work area.

---

## 3. Map/environment representation

```yaml
build_grid_requirements:
  must_represent:
    - visible_play_area
    - current_reception_area
    - stack_zone
    - scale_station
    - label_station
    - registry_station
    - conveyor_path
    - output_doors
    - blocked_cells
    - active_buildable_cells

  fail_if:
    - grid_is_empty_abstract_buttons
    - grid_does_not_show_environment
    - module_placement_has_no_visible_route_effect
```

The grid must represent the actual playable map around the player, not a detached UI diagram.

---

## 4. Camera requirements

```yaml
camera_modes:
  first_person:
    status: core_experience
    need: keep_playable_when_available

  stable_gizmo_view:
    purpose: second_first_person_mode_from_gizmo
    requirements:
      - more_stable_than_player_camera
      - useful_for_scanning_and_routing
      - shows_box_flow_and_labels
      - no_motion_sickness_or_visual_jitter

  rear_aerial_player_view:
    purpose: visualize_player_box_mobility
    requirements:
      - camera_behind_player
      - elevated_angle
      - shows_box_stack_and_path
      - helps_dragging_and_routing_boxes

  top_down_build_view:
    purpose: construction_planning
    requirements:
      - shows_buildable_area
      - shows_modules
      - shows_route_preview
      - returns_to_play_without_blocking
```

Stage 3 needs camera modes that make box movement legible, especially a stable gizmo view and a rear aerial player view.

---

## 5. Construction as data processing metaphor

```yaml
construction_semantics:
  meaning:
    - package_routes_are_data_routes
    - boxes_are_physical_packets
    - labels_are_metadata
    - sorters_are_routing_rules
    - priorities_are_scheduling_rules
    - deadlines_are_service_level_constraints

  gameplay_translation:
    - player_creates_package_routes
    - player_defines_label_outputs
    - player_assigns_priorities
    - player_handles_deadline_alerts
```

The construction process should assimilate data processing: boxes are packets, routes are flows, labels are metadata, deadlines are constraints.

---

## 6. Classification minigames

```yaml
classification_minigames:
  later_modules:
    - classify_by_label
    - classify_by_output_door
    - classify_by_priority
    - classify_by_deadline

  mechanics:
    - choose_output_lane
    - correct_misrouted_box
    - handle_high_priority_alert
    - prevent_deadline_failure

  rewards:
    - coins
    - productivity_badges
    - route_stability
    - lower_error_rate
```

Later minigames should make classification meaningful: different labels, different exits, different priority, different deadlines.

---

## 7. Deadline alerts

```yaml
deadline_system:
  warning_channels:
    - wall_panel_alert
    - sound_alert
    - vibration_alert_when_available
    - visual_priority_marker

  fail_condition:
    deadline_missed: restart_level

  design_requirements:
    - warning_must_be_clear
    - player_must_understand_why_restart_happened
    - warning_should_not_feel_random
    - alert_should_not_block_controls
```

Deadlines should produce a physical and sensory warning: wall panel, sound, vibration if available, and then restart if missed.

---

## 8. Save and checkpoint rules

```yaml
checkpoint_system:
  manual_save_allowed:
    - any_time_from_menu
    - desk_area
    - construction_area

  save_contents:
    - player_position
    - box_state_summary
    - module_layout
    - route_rules
    - active_checkpoint
    - current_stage_goal
    - coins_and_badges
    - saved_solution

  reentry_behavior:
    - restore_checkpoint
    - show_summary_of_saved_solution
    - allow_replay_solution
    - allow_continue_editing_route
```

The player should be able to save checkpoints at any moment from menu or desk/construction area. The solution should be saved so it can replay or be restored on reentry.

---

## 9. Next implementation candidate

```yaml
next_safe_build_candidate:
  build: v1_8_16_or_later_integrated_build_area_overlay
  type: index_only_or_runtime_plan_first

  allowed_first:
    - show_build_only_near_construction_area_marker
    - replace_abstract_grid_with_visible_map_preview
    - show_module_route_on_map_preview
    - show_camera_mode_labels
    - add_checkpoint_export_for_build_layout
    - add_deadline_alert_placeholder

  requires_runtime_plan_before:
    - real_module_physics
    - actual_player_camera_switching
    - vibration_api_use
    - level_restart_logic
    - persistent_solution_replay
```

---

## 10. Acceptance criteria

```yaml
acceptance_criteria:
  accept_if:
    - build_menu_is_contextual_to_construction_area
    - map_preview_represents_environment
    - route_preview_visibly_changes_map
    - player_can_return_to_game
    - save_packet_contains_build_layout
    - deadline_alert_is_visible_and_understandable

  fail_if:
    - build_is_only_menu
    - route_preview_does_not_map_to_game_area
    - camera_mode_labels_confuse_player
    - checkpoint_save_does_not_include_solution
    - overlay_blocks_play
    - app_js_v1_8_8_core_regresses
```
