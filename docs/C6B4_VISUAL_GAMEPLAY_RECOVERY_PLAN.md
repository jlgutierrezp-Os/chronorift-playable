# CHRONORIFT C6B4 — Visual Gameplay Recovery Plan

**Artifact ID:** `C6B4_VISUAL_GAMEPLAY_RECOVERY_PLAN`  
**Stage:** C6B recovery, post-C6B3 review  
**Status:** Plan and build contract only. **No playable build in this artifact.**  
**Current default player alias:** `Human_01` / `PLAYER_ALIAS`  
**Removed from project context as operational player name:** previously used symbolic name removed by user instruction.  
**Primary issue:** C6B3 works as logic/state prototype, but still feels like webpage + low quality drawings rather than a game scene.

---

## 0. Operating instruction

```yaml
AGENT_LUU_APPLY:
  artifact: C6B4_VISUAL_GAMEPLAY_RECOVERY_PLAN
  no_build_until:
    - goals_are_clear
    - acceptance_tests_are_clear
    - human_accepts_or_requests_C6B4_build
  current_action: document_plan_only
  next_allowed_action_after_human_decision:
    - build_C6B4_visual_gameplay_candidate
    - revise_plan
    - ask_missing_visual_direction_question
```

**AUTO_NOTE:** This plan must prevent another web-page mockup. It must define what a minimum acceptable C6B4 is before any code is built.

**HUMAN_COMMENT_WRITE_HERE:**

---

## 1. Honest review of C6B3

### 1.1 What worked

```yaml
C6B3_WORKED:
  - opens_on_iPhone_web: true
  - basic_navigation_exists: true
  - state_machine_exists: true
  - required_items_exist:
      - Phone
      - Chip/SIM
      - Tape
      - Sticks
      - Miniature Office Flower
  - Pos_Aya_concept_is_present: true
  - Somero_trace_exists: true
  - package_goal_exists: true
```

### 1.2 What failed

```yaml
C6B3_FAILED:
  P1_major:
    - page_like_interface_dominates
    - low_quality_drawings
    - weak_game_feel
    - weak_first_person_embodiment
    - Pos_Aya_still_feels_like_buttons_and_panel
    - no_satisfying_physical_action
    - not_fun_enough
  P2_minor:
    - logic_is_clearer_than_before
    - text_and_panels_still_too_visible
```

### 1.3 Honest description

C6B3 is a useful **logic and state prototype**. It is not yet a satisfying minimal game. It lets the player move between named locations, collect items, trigger actions and complete objectives. However, the visual layer still reads as an HTML page with canvas drawings. It does not yet create the feeling of being in a first-person room using Pos.Ayá as an embodied tool.

**HUMAN_COMMENT_WRITE_HERE:**

---

## 2. C6B4 minimum goals

### 2.1 Non-negotiable minimum goals

```yaml
C6B4_MINIMUM_GOALS:
  visual_first_frame:
    requirement: first_screen_must_read_as_game_scene_not_webpage
    pass_condition: human_sees_room_or_first_person_view_before_explanatory_panels

  reduced_webpage_feel:
    requirement: panels_must_not_dominate_default_view
    pass_condition: default_view_is_at_least_70_percent_game_scene

  Pos_Aya_embodied:
    requirement: Pos_Aya_visible_as_in_world_held_object_or_object_on_desk
    pass_condition: player_uses_Pos_Aya_by_touching_object_parts_not_reading_UI_taxonomy

  physical_action:
    requirement: at_least_one_action_must_feel_physical
    candidates:
      - grab_package
      - repair_conveyor_with_Tape
      - place_Sticks_as_bridge
      - scan_route_with_Pos_Aya
      - send_package_with_visible_motion
    pass_condition: player_can_describe_what_physical_action_happened

  challenge:
    requirement: victory_must_require_decision_or_sequence_not_button_mashing
    pass_condition: player_must_complete_repair_bridge_route_send_sequence

  essential_item_continuity:
    requirement: all_story_required_items_exist_and_have_a_use
    items:
      Phone: signal_test_or_later_outside_contact_seed
      Chip_SIM: required_for_signal_test
      Tape: repairs_conveyor
      Sticks: bridges_gap
      Miniature_Office_Flower: recovery_or_anti_productivity_seed
      Stuff_Box: item_storage_and_retrieval_anchor
      Notebook_Somero: memory_trace_anchor
      Laptop: corporate_messages_and_PR_Worm_seed
      Pos_Aya: guide_object_tool_companion_menu

  win_feedback:
    requirement: win_must_be_unambiguous_and_rewarding
    pass_condition: player_reports_seeing_clear_win_and_understanding_why
```

**HUMAN_COMMENT_WRITE_HERE:**

---

## 3. Optimal restructure

### 3.1 Preserve

```yaml
PRESERVE_FROM_C6B3:
  - iPhone_web_access
  - static_single_HTML_direction
  - no_accounts_no_payments
  - local_state
  - Somero_trace
  - item_continuity
  - Phone_Chip_Tape_Sticks_Flower
  - Stuff_Box
  - Notebook_Somero
  - Laptop_messages
  - PR_Worm_seed
  - Pos_Aya_core_role
  - clear_win_goal_from_C6B2
```

### 3.2 Remove or demote

```yaml
REMOVE_OR_DEMOTE:
  - webpage_panel_dominance
  - visible_UI_design_taxonomy
  - generic_explanatory_panels
  - low_quality_symbol_only_room
  - button_spam_as_primary_gameplay
  - logic_board_as_main_scene
  - empty_modes_without_distinct_function
```

### 3.3 Add for C6B4

```yaml
ADD_FOR_C6B4:
  visual_scene:
    - first_person_room_composition
    - desk_foreground
    - conveyor_midground
    - output_zone
    - Stuff_Box_as_visible_storage
    - Pos_Aya_as_held_object_or_desk_object
    - package_as_visible_object

  interaction_layer:
    - tap_or_drag_package
    - hold_Pos_Aya_to_choose_intention
    - inspect_target_with_Pos_Aya_eyes
    - talk_with_Pos_Aya_mouth
    - use_with_Pos_Aya_hands
    - move_with_Pos_Aya_feet
    - repair_with_Tape
    - bridge_with_Sticks
    - send_package_with_animation

  feedback_layer:
    - object_highlight
    - package_motion
    - repair_flash
    - route_glow
    - energy_change_animation
    - PR_Worm_intrusion_effect
    - win_effect
```

**HUMAN_COMMENT_WRITE_HERE:**

---

## 4. Pos.Ayá C6B4 design contract

### 4.1 Player-facing version

Pos.Ayá is not described to the player as a UI model. It appears as a physical object/tool. The player learns its function by using it.

```yaml
POS_AYA_PLAYER_FACING:
  what_player_sees:
    - object_in_hand_or_on_desk
    - eyes
    - mouth
    - hands
    - feet
    - repair_marking
    - build_marking

  what_player_does:
    eyes: mirar
    mouth: hablar
    hands: usar_tomar
    feet: ir_a
    repair_marking: reparar
    build_marking: construir

  what_player_should_feel:
    - holding_a_tool
    - choosing_intention
    - being_guided_by_companion
    - interacting_with_the_room
```

### 4.2 Internal implementation notes

These terms are valid only for internal design and must not appear as game text unless deliberately used in dev/debug view.

```yaml
POS_AYA_INTERNAL_ONLY:
  - diegetic_UI
  - skeuomorphic_UI
  - action_selector
  - radial_menu_alternative
  - interactive_hotspots
  - contextual_gateway
```

**HUMAN_COMMENT_WRITE_HERE:**

---

## 5. C6B4 proposed core loop

```yaml
C6B4_CORE_LOOP:
  1_enter_room:
    visible: first_person_room
    player_action: look_around
    Pos_Aya_support: optional_hint

  2_recover_items:
    visible: Stuff_Box
    player_action: open_and_choose_items
    required_items:
      - Phone
      - Chip/SIM
      - Tape
      - Sticks
      - Miniature Office Flower

  3_check_Somero:
    visible: Notebook_on_desk
    player_action: open_or_scan
    outcome: memory_trace_created

  4_use_Pos_Aya:
    visible: object_in_hand
    player_action: select_intention_by_body_part
    outcome: target_highlight_or_hint

  5_fix_route:
    visible: broken_conveyor_and_gap
    player_action:
      - apply_Tape
      - place_Sticks
      - scan_route
    outcome: route_glows

  6_send_package:
    visible: package_moves_to_output
    player_action: send_or_push
    outcome:
      - package_count_increases
      - coins_reward
      - energy_cost

  7_win:
    condition: 3_packages_sent
    visible: room_reacts_and_win_message
    outcome: C6B4_orientation_complete
```

**HUMAN_COMMENT_WRITE_HERE:**

---

## 6. Acceptance tests

### 6.1 Human acceptance tests

```yaml
HUMAN_ACCEPTANCE_TESTS:
  H1_visual_first_impression:
    question: "Does it look like a game scene before it looks like a webpage?"
    pass: yes_or_partial_yes

  H2_Pos_Aya_feeling:
    question: "Does Pos.Ayá feel like a tool/object/companion rather than a menu card?"
    pass: yes_or_partial_yes

  H3_action_satisfaction:
    question: "Was at least one action physically satisfying?"
    pass: yes_or_partial_yes

  H4_fun:
    question: "Is it more fun than C6B3?"
    pass: yes_or_partial_yes

  H5_clear_win:
    question: "Did you know when you won and why?"
    pass: yes

  H6_story_items:
    question: "Did any required item feel missing or unused?"
    pass: no_missing_required_item
```

### 6.2 Automated/self-debug acceptance tests

```yaml
SELFDEBUG_ACCEPTANCE_TESTS:
  code:
    - no_external_script_src
    - no_missing_core_items
    - no_removed_player_name
    - report_export_exists
    - win_condition_locks_after_3_packages

  gameplay_state:
    - can_open_room
    - can_retrieve_items
    - can_open_somero
    - can_use_Pos_Aya
    - can_apply_Tape
    - can_place_Sticks
    - can_send_package
    - can_win

  visual_state:
    - canvas_or_scene_exists
    - Pos_Aya_visible
    - package_visible
    - route_feedback_visible
    - UI_does_not_cover_scene_by_default
```

**HUMAN_COMMENT_WRITE_HERE:**

---

## 7. Build contract for next interaction

```yaml
C6B4_BUILD_CONTRACT:
  build_id: C6B4_VISUAL_GAMEPLAY_RECOVERY
  allowed_after:
    - this_plan_accepted_or_no_major_objection
    - acceptance_tests_clear

  must_be:
    - static_single_HTML
    - iPhone_first
    - low_processor
    - no_external_dependencies
    - no_accounts
    - no_payments
    - no_removed_player_name
    - not_called_playable_confirmed_until_human_confirms

  must_include:
    - first_person_room_scene
    - Pos_Aya_as_in_world_object
    - required_story_items
    - one_satisfying_physical_action
    - package_motion
    - win_feedback
    - selfdebug
    - copyable_report

  must_not_include:
    - UI_design_jargon_visible_to_player
    - webpage_dominant_layout
    - placeholder_only_drawings_without_feedback
    - disconnected_modes
```

**HUMAN_COMMENT_WRITE_HERE:**

---

## 8. Expected next commit and issue behavior

```yaml
EXPECTED_PROJECT_ACTIONS_AFTER_APPROVAL:
  next_commit:
    type: create_or_update_HTML_build
    file: tests/chronorift_C6B4_visual_gameplay_recovery.html
    commit_message: "Add C6B4 visual gameplay recovery build"

  issue_update:
    issue: "#18 C6B4 visual/fun gameplay recovery"
    expected_action:
      - add_comment_with_plan_link
      - mark_acceptance_tests
      - later_update_with_human_review

  self_debug_loop:
    before_human_link:
      - check_file_exists
      - check_no_external_deps
      - check_core_items_present
      - check_win_condition_exists
      - check_report_export_exists
      - check_visual_first_frame_if_possible
```

**HUMAN_COMMENT_WRITE_HERE:**

---

## 9. Final human decision field

```yaml
FINAL_HUMAN_DECISION:
  approve_C6B4_plan: YES | NO | REVISE
  proceed_to_C6B4_build_next: YES | NO
  most_important_change_before_build:
    - visual_scene
    - Pos_Aya_object
    - physical_action
    - fun_feedback
    - narrative_clarity
    - other: 
```

**HUMAN_COMMENT_WRITE_HERE:**
