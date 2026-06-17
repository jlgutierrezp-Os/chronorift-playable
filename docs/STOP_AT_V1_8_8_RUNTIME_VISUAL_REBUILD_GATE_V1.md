# STOP_AT_V1_8_8_RUNTIME_VISUAL_REBUILD_GATE_V1

## 0. Status

```yaml
status:
  public_repo_safe: true
  purpose: stop_menu_only_iterations_and_restore_v1_8_8_as_real_safe_point
  runtime_change_now: false
  code_change_now: false
  source_of_truth: human_feedback_v1_8_16
```

---

## 1. Human directive

```yaml
human_directive:
  stop_at: v1.8.8_box_goal_snap_assist_stage_transition
  reason:
    - versions_after_v1_8_8_are_mostly_index_menu_overlays
    - versions_after_v1_8_8_do_not_really_update_play_visualization_or_3D_experience
    - build_claims_must_not_confuse_menu_changes_with_playable_visual_runtime_changes
```

---

## 2. Current accepted safe point

```yaml
current_real_safe_point:
  build: v1.8.8_box_goal_snap_assist_stage_transition
  accepted_as_playable: true
  accepted_as_resolvable: true
  must_preserve:
    - caja_agarrable
    - caja_menos_resbalosa
    - caja_cruza_portal
    - asistencia_visible_hacia_meta
    - snap_lock_en_meta_verde
    - declaracion_PUZZLE_RESUELTO
    - STAGE_2_DESBLOQUEADO
    - matriz_cardinal_de_portales
```

---

## 3. Non-accepted overlay range

```yaml
non_accepted_as_visual_runtime_update:
  range:
    - v1.8.9
    - v1.8.10
    - v1.8.11
    - v1.8.12
    - v1.8.13
    - v1.8.14
    - v1.8.15
    - v1.8.16
  reason:
    - menu_or_index_overlay_changes
    - insufficient_play_visualization_change
    - no_real_3D_or_runtime_visual_progress_confirmed
```

These versions may contain useful design learnings, Somero improvements, and planning UI ideas, but they are not accepted as real visual gameplay progression.

---

## 4. New gate before any next build

```yaml
next_build_gate:
  forbid:
    - claiming_visual_update_from_menu_only_change
    - publishing_more_index_only_menu_overlays_as_gameplay_progress
    - changing_app_js_without_runtime_rebuild_plan

  require_before_next_build:
    - runtime_visual_rebuild_plan
    - clear_choice_between_restore_v1_8_8_or_branch_from_it
    - playable_visual_delta_definition
    - verification_method_for_visual_change
    - rollback_plan_to_v1_8_8
```

---

## 5. Allowed next work

```yaml
allowed_next_work:
  design_only:
    - consolidate_stage_3_requirements
    - create_runtime_visual_rebuild_plan
    - define_camera_and_map_visual_delta
    - define_box_visual_runtime_delta
    - define_minimal_3D_or_pseudo_3D_target

  implementation_only_after_plan:
    - branch_from_v1_8_8
    - make_small_runtime_visual_delta
    - verify_playable_visual_change
    - confirm_with_human_before_claiming_success
```

---

## 6. Success definition

```yaml
success_definition:
  success_if:
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
