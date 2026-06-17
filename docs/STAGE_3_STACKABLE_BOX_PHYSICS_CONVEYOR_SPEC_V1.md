# STAGE_3_STACKABLE_BOX_PHYSICS_CONVEYOR_SPEC_V1

## 0. Status

```yaml
status:
  public_repo_safe: true
  purpose: design_spec_for_stage_3_stackable_boxes_and_conveyor_workflow
  runtime_change_now: false
  code_change_now: false
  source_of_truth: human_design_input
  parent_spec: STAGE_3_RECEPTION_BOX_ECONOMY_PR_WORM_SPEC_V1
  preserve_current_playable:
    - app_js_v1_8_8
    - Somero_closeable_v1_8_13
    - box_goal_core
    - portal_core
```

This document refines Stage 3 physical box behavior. It is a design contract, not a runtime patch by itself.

---

## 1. Camera and reception view

```yaml
stage_3_camera:
  primary_view: top_down_reception_area
  required_visual:
    - boxes_fall_from_above_or_arrival_chute
    - boxes_land_inside_reception_area
    - boxes_stack_visibly
    - player_can_read_work_area_from_above
    - conveyor_scale_label_register_station_visible
```

The reception area must be readable from above. The player should see where boxes enter, how they pile up, and how to move them toward the scale and conveyor workflow.

---

## 2. Stackable box behavior

```yaml
stackable_boxes:
  properties:
    stackable: true
    fragile_breaking: false
    can_be_used_as_steps: true
    grid_snap: true
    maintain_position_inside_cell: true

  behavior:
    - boxes_snap_or_settle_into_square_cells
    - boxes_keep_position_when_stacked
    - boxes_can_form_stairs
    - player_can_climb_boxes_without_breaking_them
    - boxes_can_be_pulled_or_dragged_when_accessible
```

Boxes should tend to become stable stacks, not chaotic loose objects. They should preserve position in a square/cell so the player can plan movement.

---

## 3. Containment wall/net and front exit

```yaml
containment_area:
  structure:
    - retaining_wall_or_mesh
    - prevents_boxes_from_spilling_out
    - keeps_boxes_collected
    - leaves_front_exit_available

  front_exit:
    purpose: extract_boxes_toward_processing_line
    allowed_extraction:
      - one_box
      - two_boxes_stacked_max
```

A wall/net keeps the receiving pile contained so boxes do not overflow into the whole map. A front opening lets the player pull boxes out of the pile in controlled order.

---

## 4. Dragging stacked boxes

```yaml
stack_dragging:
  max_drag_stack_height: 2
  allowed:
    - drag_single_box
    - drag_two_boxes_stacked_vertically
  not_allowed_initially:
    - drag_three_or_more_boxes_stacked
    - unstable_bulk_dragging

  use_cases:
    - move_two_box_stack_to_scale_area
    - use_two_box_stack_as_step
    - clear_front_exit
```

The player can drag up to two boxes stacked one on top of the other. This creates useful work puzzles without making the physics unstable.

---

## 5. Boxes as staircase

```yaml
box_stair_system:
  player_can_climb: true
  stair_units:
    - one_box_step
    - two_box_step
  design_use:
    - reach_higher_boxes
    - cross_over_small_pile
    - access_STUFFBOX_or_reader_setup
    - create_shortcuts_in_reception_area

  fail_if:
    - boxes_break_when_player_steps_on_them
    - boxes_slide_uncontrollably
    - player_gets_trapped_without_exit
```

Stacked boxes are part of spatial puzzle design. They are not only cargo; they become temporary architecture.

---

## 6. Conveyor, scale, label, and registry station

```yaml
processing_line:
  required_stations:
    - conveyor_belt
    - scale_station
    - label_station
    - registry_station
    - piston_or_pusher

  layout:
    conveyor_next_to_scale: true
    label_and_registry_near_scale: true
    piston_pushes_box_after_registration: true

  workflow:
    - place_box_on_scale
    - read_or_scan_label
    - register_box
    - piston_pushes_box_to_conveyor
    - conveyor_moves_box_to_shipping_or_exit
```

The work loop should become physical and visible: weigh, label, register, then piston pushes the box onward.

---

## 7. Productivity, coins, and badges

```yaml
productivity_rewards:
  objective:
    - reduce_processing_time
    - maximize_coins
    - earn_productivity_badges

  reward_signals:
    - coin_counter_increases
    - time_reduction_marker
    - batch_complete_marker
    - productivity_badge_unlock

  badge_examples:
    - BADGE_10_BOX_START
    - BADGE_STACK_CONTROL
    - BADGE_TWO_BOX_DRAG
    - BADGE_FAST_SCALE_LABEL_REGISTER
    - BADGE_MAX_TIME_REDUCTION
    - BADGE_PRODUCTIVITY_30_CAP
```

The goal is to reduce processing time to a maximum efficiency point and earn coins/badges without hiding the human cost and fatigue introduced in the parent Stage 3 spec.

---

## 8. First implementation candidate

```yaml
first_implementation_candidate:
  build_candidate: v1_8_14_or_v1_8_15_stage_3_stack_visual_overlay
  type: index_only_or_safe_overlay
  allowed_first:
    - draw_top_down_reception_area
    - draw_containment_mesh
    - draw_front_exit
    - show_box_stack_cells
    - show_scale_conveyor_piston_labels
    - show_coin_counter_placeholder
    - show_badge_placeholder
  not_yet:
    - full_physics_runtime
    - continuous_box_spawn_runtime
    - climb_collision_runtime
    - advanced_stack_drag_physics
```

First build should be a visible non-blocking work-area overlay or safe simplified interaction, not full physics immediately.

---

## 9. Acceptance criteria

```yaml
acceptance_criteria:
  player_understands:
    - boxes_arrive_from_above
    - boxes_stack_in_contained_area
    - wall_or_mesh_prevents_spillover
    - front_exit_is_for_extracting_boxes
    - boxes_can_be_used_as_steps
    - two_box_stack_can_be_dragged
    - scale_conveyor_label_register_piston_line_is_the_processing_path
    - coins_and_badges_reward_productivity

  fail_if:
    - boxes_spread_uncontrollably
    - stack_visual_is_unreadable
    - player_cannot_see_reception_area_from_above
    - conveyor_scale_piston_path_is_not_visible
    - overlay_blocks_play
    - app_js_v1_8_8_core_regresses
```
