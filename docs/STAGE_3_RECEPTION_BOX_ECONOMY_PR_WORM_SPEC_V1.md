# STAGE_3_RECEPTION_BOX_ECONOMY_PR_WORM_SPEC_V1

## 0. Status

```yaml
status:
  public_repo_safe: true
  purpose: design_spec_for_stage_3_reception_work_area
  runtime_change_now: false
  code_change_now: false
  source_of_truth: human_design_input
  preserve_current_playable:
    - app_js_v1_8_8
    - Somero_closeable_v1_8_13
    - box_goal_core
    - portal_core
```

This document records the Stage 3 design requirement before implementation. It must not be treated as a runtime patch by itself.

---

## 1. Stage 3 core intent

```yaml
stage_3_core_intent:
  name: reception_box_work_area
  player_role: warehouse_receiver_and_scanner
  primary_loop:
    - receive_boxes
    - weigh_boxes
    - scan_boxes
    - complete_shipments
    - earn_coins
    - unlock_or_receive_new_spell
    - optimize_time
    - handle_fatigue
    - discover_PR_Worm_warning
    - unlock_advanced_gizmo_capabilities
```

Stage 3 should visualize the reception work area where boxes arrive, get weighed, scanned, and delivered through a production-like work loop.

---

## 2. Work area visualization

```yaml
work_area_visualization:
  required_visible_zones:
    - receiving_area
    - box_arrival_zone
    - scale_station
    - scanner_station
    - STUFFBOX_station
    - email_or_warning_terminal
    - stacking_area
    - exit_or_delivery_zone

  visual_priority:
    - show_box_flow
    - show_player_energy
    - show_coin_counter
    - show_batch_progress
    - show_time_bonus_progress
    - show_stacking_pressure
```

The player should understand where boxes enter, where boxes are weighed, where they are scanned, where completed shipments pay coins, and where unfinished boxes begin to pile up.

---

## 3. Box economy and scaling loop

```yaml
box_economy:
  initial_batch:
    box_count: 10
    reward:
      - coins_paid_on_complete_shipment
      - receive_new_spell_or_upgrade

  time_bonus_rule:
    trigger: reduce_completion_time_by_10_percent
    reward:
      - increase_box_count_by_10_percent
      - apply_10_percent_bonus
    bonus_cap: 30_percent

  batch_growth:
    after_initial_optimization:
      - boxes_arrive_in_groups
      - group_size_progresses_to_20

  group_20_rule:
    trigger: reduce_delivery_time_for_20_boxes_by_10_percent
    reward:
      - increase_next_box_flow_by_10_percent

  late_stage:
    arrival_mode: continuous_flow
    pressure: boxes_begin_to_arrive_continuously
```

The economy should reward speed, but the bonus must remain legible and not become pure grind.

---

## 4. Coins and spell rewards

```yaml
coins_and_spells:
  coin_marker:
    visible: true
    updates_on: completed_shipment

  new_spell_reward:
    trigger: completed_batch_or_key_threshold
    examples:
      - faster_scan_hint
      - STUFFBOX_tripod_unlock
      - portal_loop_awareness
      - time_shadow_awareness

  reward_feedback:
    - coin_increment_animation
    - batch_complete_marker
    - new_spell_notice
```

Every completed shipment should pay coins into a visible marker. New spells or abilities should be introduced as narrative and mechanical unlocks, not as disconnected UI items.

---

## 5. Fatigue and end-of-stage pressure

```yaml
player_energy:
  depletion_trigger:
    - after_high_volume_delivery
    - after_continuous_box_pressure
    - after_stage_3_completion_threshold

  result:
    - player_energy_exhausted
    - save_required
    - rest_required
    - boxes_begin_stacking

  visible_feedback:
    - energy_marker_low
    - slower_player_feedback
    - stacking_boxes_visible
    - prompt_to_save_and_rest
```

At the end of Stage 3, the player should feel the system pressure: the player becomes tired, must save/rest, and boxes begin to pile up.

---

## 6. STUFFBOX tripod cinematic

```yaml
stuffbox_tripod_cinematic:
  trigger:
    - player_energy_low
    - boxes_stacking
    - need_to_scan_faster

  sequence:
    - player_opens_STUFFBOX
    - player_finds_tripod_parts
    - player_assembles_tripod
    - scanner_or_reader_gets_mounted
    - player_can_weigh_and_scan_faster

  function:
    - narrate_reader_setup
    - make_scanning_physical_and_visible
    - reduce_repetitive_load
    - prepare_PR_Worm_discovery
```

The cinematic should not be decorative only. It should explain the shift from manual scanning to an improvised reader/tripod workflow.

---

## 7. PR Worm warning email

```yaml
pr_worm_warning_email:
  subject: PR Worm
  classification: Human_In_The_Loop_Eyes_Only
  warning: do_not_scan

  narrative_role:
    - creates_tension
    - separates_human_judgment_from_automation
    - frames_the_gizmo_as_powerful_but_not_neutral

  trigger_context:
    - while_player_is_weighing_boxes
    - while_reader_or_tripod_is_active
    - after_stacking_pressure_has_started
```

The email should appear as a warning intended for Human-in-the-Loop review. It should not be treated as a normal scan target.

---

## 8. Accidental gizmo rotation and PR Worm scan

```yaml
accidental_scan_event:
  cause:
    - gizmo_rotates_accidentally
    - PR_Worm_is_scanned_against_warning

  consequence:
    - hidden_capabilities_deploy
    - portal_A_B_loop_capabilities_reveal
    - time_portal_capabilities_reveal
    - time_shadow_capabilities_reveal

  tone:
    - discovery
    - danger
    - awe
    - agency_test
```

The player should feel that the scan was accidental or semi-accidental, not a simple tutorial button. This event unlocks deeper ChronoRift identity.

---

## 9. Stage 3 advanced capability use

```yaml
advanced_capability_use:
  unlocked_tools:
    - portal_A_B_loops
    - time_portals
    - time_shadows
    - temporal_loop_assistance

  stage_3_use_case:
    - optimize_box_delivery
    - scan_more_efficiently
    - reduce_batch_time
    - earn_more_coins
    - understand_limits_of_human_capacity

  risk:
    - automation_pressure
    - player_fatigue
    - unintended_consequences
    - PR_Worm_expansion
```

After the accidental scan, the player can use portals and temporal shadows to complete Stage 3 faster and earn more coins, but the experience should still show fatigue, risk, and responsibility.

---

## 10. Implementation gates

```yaml
implementation_gates:
  before_runtime:
    - preserve_current_playable
    - do_not_modify_app_js_without_explicit_runtime_plan
    - create_minimal_visual_overlay_first
    - test_closeable_UI_before_new_systems

  acceptable_first_build:
    id: v1_8_14_or_v1_8_15_stage_3_visual_overlay
    type: index_only_or_safe_overlay
    scope:
      - visible_stage_3_work_area
      - coin_marker
      - batch_counter
      - energy_marker
      - boxes_stacking_visual
      - PR_Worm_email_teaser
    not_yet:
      - full_economy_simulation
      - continuous_box_runtime
      - complex_time_portal_physics
      - autonomous_systems
```

---

## 11. Acceptance criteria

```yaml
acceptance_criteria:
  player_understands:
    - where_boxes_arrive
    - how_boxes_are_processed
    - why_coins_increase
    - why_time_reduction_matters
    - why_energy_runs_out
    - why_STUFFBOX_tripod_matters
    - why_PR_Worm_warning_is_dangerous

  fail_if:
    - stage_3_is_only_text_without_visible_work_area
    - coins_are_not_visible
    - boxes_do_not_stack_or_progress
    - PR_Worm_warning_has_no_narrative_weight
    - Somero_or_overlay_blocks_play
    - app_js_v1_8_8_core_regresses
```

---

## 12. Recommended next step

```yaml
recommended_next_step:
  build_candidate: v1_8_14_stage_3_visual_overlay_minimal
  priority:
    - non_blocking_visual_work_area
    - coin_counter
    - batch_counter
    - energy_counter
    - boxes_stack_indicator
    - PR_Worm_email_teaser
  preserve:
    - v1_8_13_closeable_somero
    - app_js_v1_8_8
```
