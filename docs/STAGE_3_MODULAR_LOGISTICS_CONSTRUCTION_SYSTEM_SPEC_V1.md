# STAGE_3_MODULAR_LOGISTICS_CONSTRUCTION_SYSTEM_SPEC_V1

## 0. Status

```yaml
status:
  public_repo_safe: true
  purpose: design_spec_for_modular_box_logistics_construction_system
  runtime_change_now: false
  code_change_now: false
  source_of_truth: human_design_input
  parent_specs:
    - STAGE_3_RECEPTION_BOX_ECONOMY_PR_WORM_SPEC_V1
    - STAGE_3_STACKABLE_BOX_PHYSICS_CONVEYOR_SPEC_V1
  preserve_current_playable:
    - app_js_v1_8_8
    - Somero_closeable_v1_8_13
    - box_goal_core
    - portal_core
```

This document defines the Stage 3 construction layer where the player builds a modular box distribution and classification system. It is a design contract, not a runtime patch by itself.

---

## 1. Core design intent

```yaml
core_design_intent:
  name: modular_logistics_builder
  player_role:
    - builder_of_box_reception_distribution_system
    - optimizer_of_classification_and_delivery
    - eventual_observer_of_automation_replacing_movement

  gameplay_loop:
    - select_space_blocks
    - place_logistics_modules
    - route_boxes
    - classify_boxes_by_label_level
    - reduce_delivery_time
    - earn_coins_and_productivity_badges
    - discover_that_gizmo_can_replace_the_system
    - confront_result_of_not_moving_and_only_receiving_coins
```

The player should not only move boxes manually. They should construct the system that receives, moves, classifies, accelerates, and delivers boxes.

---

## 2. Buildable space blocks

```yaml
space_blocks:
  purpose: define_buildable_reception_and_processing_area
  player_actions:
    - select_empty_grid_cells
    - assign_cell_function
    - connect_modules
    - reroute_box_flow

  block_types:
    reception_block:
      function: receive_falling_or_incoming_boxes
    conveyor_block:
      function: move_boxes_continuously
    scale_label_register_block:
      function: weigh_label_register_box
    sorting_block:
      function: classify_by_label_level
    output_block:
      function: deliver_or_export_boxes
    storage_stack_block:
      function: hold_stacked_boxes_temporarily
```

The work area should be made of selectable space blocks. The player learns that layout matters.

---

## 3. Buildable logistics modules

```yaml
buildable_modules:
  endless_conveyor:
    label: banda_sin_fin
    purpose: continuous_box_movement
    connection_rules:
      - input_cell
      - output_cell
      - direction

  box_trampoline:
    label: trampolin_de_caja
    purpose: launch_box_across_gap_or_to_higher_path
    constraints:
      - visible_arc
      - safe_landing_cell
      - no_unreadable_launches

  box_chute:
    label: tobogan_de_caja
    purpose: gravity_slide_for_boxes
    constraints:
      - requires_height_difference_or_slope_logic
      - prevents_box_loss

  box_elevator:
    label: elevador_de_caja
    purpose: raise_or_lower_boxes_between_levels
    constraints:
      - one_stack_or_small_stack_at_time
      - visible_state_up_down

  label_level_sorter:
    label: clasificador_por_etiqueta_nivel
    purpose: route_boxes_by_label_or_level
    inputs:
      - label_value
      - level_value
    outputs:
      - route_A
      - route_B
      - route_C
```

Each module should have a visible purpose and readable connection logic.

---

## 4. Player-built distribution system

```yaml
distribution_system:
  player_builds:
    - reception_to_stack_area
    - stack_area_to_scale
    - scale_to_label_register
    - label_register_to_sorter
    - sorter_to_conveyor_or_output
    - conveyor_to_delivery_zone

  success_signals:
    - boxes_flow_without_manual_push_each_time
    - wrong_label_boxes_are_separated
    - delivery_time_decreases
    - coins_increase
    - productivity_badges_unlock

  failure_signals:
    - boxes_jam
    - boxes_stack_too_high
    - sorter_misroutes_boxes
    - conveyor_path_dead_ends
    - player_must_intervene_physically
```

The player should be able to build a complete box delivery and classification system from modular parts.

---

## 5. Optimization and rewards

```yaml
optimization_rewards:
  target: reduce_delivery_and_classification_time
  reward_channels:
    - coins
    - productivity_badges
    - new_module_unlocks
    - new_gizmo_insight

  badge_examples:
    - BADGE_FIRST_CONVEYOR_ROUTE
    - BADGE_TRAMPOLINE_DELIVERY
    - BADGE_CHUTE_FLOW
    - BADGE_ELEVATOR_STACK
    - BADGE_LABEL_SORTER_LEVEL_1
    - BADGE_AUTOMATED_BATCH_20
    - BADGE_MAX_PRODUCTIVITY_NO_WALK
```

The system rewards efficiency, but the rewards should support the narrative question: what happens when productivity removes the player's movement and agency?

---

## 6. Gizmo replacement revelation

```yaml
gizmo_replacement_revelation:
  trigger:
    - player_finishes_modular_logistics_system
    - system_reaches_high_efficiency
    - player_receives_coins_without_moving_much

  realization:
    - everything_built_can_be_replaced_by_gizmo
    - player_movement_becomes_optional
    - coins_continue_arriving
    - player_risks_becoming_passive_operator

  narrative_tension:
    - productivity_success
    - agency_loss
    - embodied_movement_loss
    - ethical_question_about_automation
    - PR_Worm_pressure
```

The player should realize that the same gizmo that helps them can replace the entire logistics construction. The issue is not only that automation works, but that the player stops moving and becomes a passive coin receiver.

---

## 7. Gameplay meaning of not moving

```yaml
not_moving_state:
  visible_result:
    - player_stands_or_sits_near_control_area
    - boxes_move_without_player_intervention
    - coins_tick_up
    - energy_stops_depleting_from_movement
    - attention_pressure_increases

  design_warning:
    - do_not_make_this_only_a_reward
    - show_loss_of_embodied_flow
    - show_reduction_of_direct_agency
    - make_player_choose_intervention_or_passive_income

  possible_choices:
    - keep_automation_running
    - intervene_physically_to_improve_route
    - disable_part_of_system
    - use_gizmo_with_limits
    - rest_and_save
```

Automation should feel powerful and tempting, but also strange: the player receives coins while no longer participating with the body.

---

## 8. First implementation candidate

```yaml
first_implementation_candidate:
  build_candidate: v1_8_15_or_later_modular_logistics_overlay
  type: index_only_or_safe_overlay_first
  allowed_first:
    - show_module_palette
    - show_space_block_grid
    - show_module_labels
    - show_simple_preview_routes
    - show_coin_badge_placeholder
    - show_gizmo_replacement_teaser

  not_yet:
    - full_physics_module_runtime
    - real_continuous_automation
    - complex_pathfinding
    - permanent_passive_income_loop
    - removal_of_player_movement
```

The first implementation should be a visible planning/construction overlay before full automation physics.

---

## 9. Acceptance criteria

```yaml
acceptance_criteria:
  player_understands:
    - blocks_of_space_can_be_selected
    - modules_can_be_placed
    - conveyors_move_boxes
    - trampoline_chute_elevator_change_box_path
    - sorter_classifies_boxes_by_label_level
    - coins_and_badges_reward_productivity
    - high_productivity_reveals_gizmo_replacement_risk
    - passive_coin_receiving_is_not_pure_success

  fail_if:
    - construction_system_is_only_text
    - player_cannot_see_module_flow
    - modules_have_no_clear_function
    - gizmo_replacement_has_no_narrative_consequence
    - automation_removes_gameplay_without_choice
    - app_js_v1_8_8_core_regresses
```
