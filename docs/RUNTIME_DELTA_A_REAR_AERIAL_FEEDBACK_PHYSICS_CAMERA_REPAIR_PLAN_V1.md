# RUNTIME_DELTA_A_REAR_AERIAL_FEEDBACK_PHYSICS_CAMERA_REPAIR_PLAN_V1

## 0. Status

```yaml
status:
  public_repo_safe: true
  purpose: capture_human_feedback_on_v1_9_0A_and_define_repair_plan_before_next_runtime_patch
  runtime_change_now: false
  code_change_now: false
  source_of_truth: human_feedback_v1_9_0A_rear_aerial_test
```

This document records that v1.9.0A is not accepted as the successful visual runtime delta yet. It should guide the next repair before any delta B work.

---

## 1. Test result summary

```yaml
v1_9_0A_test_result:
  page_loads: true
  accepted:
    - page_loads
    - box_grab_works_or_partially_works

  failed_or_insufficient:
    - rear_aerial_visible_not_accepted
    - actual_canvas_visual_change_not_accepted
    - player_avatar_not_visible_or_not_clear
    - objects_not_visible_or_not_clear
    - movement_controls_fail_during_play
    - portal_A_B_partial_only
    - green_goal_snap_not_confirmed
    - puzzle_resolved_or_stage_2_not_confirmed

  status:
    accepted_as_visual_delta: false
    accepted_as_playable: false
```

---

## 2. Camera/control problem

```yaml
camera_control_problem:
  observed:
    - aerial_over_top_x_axis_to_floor_is_interesting_but_not_correct
    - controls_are_reoriented_wrong_during_play
    - player_avatar_and_objects_are_not_clear_enough

  reported_axis_issue:
    up: north_x_plus
    down: south_x_minus
    right: y_plus
    left: y_minus

  repair_need:
    - camera_transform_must_not_invert_expected_player_controls
    - visual_camera_rotation_must_not_redefine_input_space_without_clear_rule
    - player_avatar_box_portals_goal_must_remain_visible
```

The visual transform can rotate the camera, but the control frame must remain predictable for the player.

---

## 3. Portal physics and math requirement

```yaml
portal_physics_requirement:
  human_note: ask_for_math_and_physics_help_if_needed

  required_model:
    - portal_opening_requires_orientation_basis
    - portal_transport_preserves_or_transforms_velocity_by_basis_mapping
    - box_entry_exit_should_have_readable_arc_or_line
    - player_needs_instruction_before_using_advanced_portal_systems

  math_primitives:
    - vector_position
    - velocity_vector
    - portal_normal
    - portal_tangent
    - basis_transform
    - conservation_or_intentional_remap_of_speed
    - collision_safe_exit_point
```

Portal use should be physically and mathematically legible, not only represented by circular symbols.

---

## 4. Gizmo instruction gate

```yaml
gizmo_instruction_gate:
  before_advanced_portal_use:
    - player_opens_gizmo_box
    - player_reads_instruction
    - player_registers_labels
    - player_places_label_on_box
    - box_label_contains_QR_smiley_donut_marker

  purpose:
    - avoid_unexplained_portal_power
    - connect_box_logistics_to_gizmo_interface
    - make_scanning_and_registration_part_of_world_logic
```

Advanced portal functions should unlock through gizmo instruction and label registration, not appear as unexplained free powers.

---

## 5. Conveyor and logistics route requirements

```yaml
conveyor_route_requirements:
  start_process:
    - box_moves_to_first_conveyor_block
    - conveyor_first_block_starts_processing
    - box_moves_to_end_of_belt_or_route

  later_modules:
    - corner_bands
    - corner_blocks
    - ramps
    - elevators
    - slides
    - vacuum_tubes
    - nets
    - ducts
    - reception_baskets
    - reception_areas

  routing_goal:
    - transmit_boxes_to_reception_or_processing_area
    - preserve_visible_box_path
    - avoid_unreadable_instant_transfer
```

Boxes should move through visible machinery and physical paths: conveyors, ramps, elevators, ducts, tubes, nets, and baskets.

---

## 6. Vertical construction and jumper legs

```yaml
vertical_construction:
  requires:
    - active_side_view
    - vertical_build_mode
    - jumper_legs_tool

  jumper_legs_tool:
    description: work_tool_leg_attachment_for_jumps
    enables:
      - player_jumps_over_two_boxes
      - player_carries_up_to_two_boxes_if_strength_and_energy_sufficient
      - vertical_logistics_construction

  constraints:
    - depends_on_strength
    - depends_on_energy
    - should_not_break_box_goal_core
```

Building upward requires a side view and a tool-based mobility upgrade, not only a top-down or rear aerial view.

---

## 7. Repair plan before next runtime patch

```yaml
repair_plan_before_next_patch:
  block_delta_B_until:
    - camera_A_repaired_or_formally_rejected
    - control_mapping_is_defined
    - avatar_box_goal_visibility_is_defined
    - portal_physics_minimal_model_is_defined

  next_A_repair_candidate:
    id: v1_9_0A2_rear_aerial_control_visibility_repair
    scope:
      - keep_runtime_branch
      - keep_v1_8_8_core
      - no_menu_overlay_success_claim
      - fix_control_frame_or make rear_aerial_visual_only
      - increase_player_box_goal_visibility
      - add portal path/velocity markers

  not_yet:
    - gizmo_stable_view_delta_B
    - full_conveyor_runtime
    - jumper_legs_runtime
    - vacuum_tube_runtime
```

---

## 8. Acceptance criteria for A repair

```yaml
acceptance_criteria_A_repair:
  accept_if:
    - rear_or_aerial_view_is_visibly_different_inside_canvas
    - controls_feel_predictable
    - player_avatar_is_visible
    - box_is_visible
    - goal_is_visible
    - portal_entry_exit_are_legible
    - box_grab_still_works
    - portal_A_B_still_works_or_clear_reason_if_not
    - green_goal_snap_still_works

  fail_if:
    - view_is_interesting_but_disorienting
    - control_axes_fail_during_play
    - no_player_avatar_or_objects_visible
    - portals_are_only_symbols_without_useful_transport_model
    - assistant_claims_success_without_human_confirmation
```
