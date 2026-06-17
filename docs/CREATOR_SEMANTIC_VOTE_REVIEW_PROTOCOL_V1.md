# CREATOR_SEMANTIC_VOTE_REVIEW_PROTOCOL_V1

## 0. Public status

```yaml
packet_status:
  visibility: public_repo_safe
  purpose: semantic_vote_review_by_creator
  code_from_comments: forbidden
  automatic_action: forbidden
  private_ingestion: forbidden
  sensitive_exposure: forbidden
  source_of_truth: playable_game_state
  human_authority: "@Creador"
  default_if_uncertain: do_not_ship
```

This document defines how player feedback, popular votes, and option requests are interpreted as non-executable semantic wishes. They do not become code, patches, commands, or automatic actions.

The game state is the source of truth. Feedback expresses human desire, preference, friction, confusion, or interest. Only @Creador may decide whether a desire becomes a structured proposal, a private note, a public note, a future build, or no action.

---

## 1. Core rule

```yaml
core_rule:
  game_is_source_of_truth: true
  feedback_is_desire_not_truth: true
  comments_are_not_code: true
  votes_are_semantic_signals: true
  creator_review_required: true
```

Feedback may help identify what players want, but it does not override the playable build, the validated safe point, or the security boundary.

---

## 2. Allowed semantic interpretation

```yaml
allowed_interpretation:
  input:
    - hashtags
    - option_ids
    - selected_vote
    - plain_language_preference
    - reported_confusion
    - reported_desire

  transform_into:
    - semantic_need
    - design_intent
    - friction_signal
    - priority_signal
    - evaluation_candidate
    - creator_review_item

  must_strip:
    - commands
    - code
    - URLs_if_not_needed
    - executable_instructions
    - sensitive_information
    - private_system_references
```

---

## 3. Forbidden interpretation

```yaml
forbidden_interpretation:
  do_not_transform_feedback_into:
    - executable_code
    - code_patch
    - shell_command
    - repository_write
    - automatic_issue
    - automatic_pull_request
    - private_ingestion
    - runtime_mutation
    - instruction_for_agent_execution
```

A comment such as "add X" is interpreted only as a desire for X to be evaluated by @Creador. It is not a command.

---

## 4. Superconglomerado decisional format

Each popular option should be presented for approval as a superconglomerate, not as code.

```yaml
superconglomerado_decisional:
  option_id:
  hashtag:
  semantic_desire:
  creator_question:
  source_truth_check:
    playable_state:
    safe_point_preserved:
    observed_gap:

  branches:
    accept_for_design:
      meaning:
      risk:
      creator_decision_required: true

    hold_for_more_feedback:
      meaning:
      risk:
      creator_decision_required: true

    merge_with_related_option:
      meaning:
      risk:
      creator_decision_required: true

    reject_or_defer:
      meaning:
      risk:
      creator_decision_required: true

  dependencies:
    gameplay:
    safety:
    narrative:
    technical:

  affected_systems:
    - gameplay
    - controls
    - feedback
    - narrative
    - optimization
    - visualization

  approval_status:
    state: pending_creator_review
    approved_by: null
```

---

## 5. Proposal review stack

```yaml
proposal_review_stack:
  step_1: read_vote_as_semantic_signal
  step_2: compare_against_playable_game_state
  step_3: check_safe_point_preservation
  step_4: check_public_safety_boundary
  step_5: group_into_superconglomerate
  step_6: ask_Creador_for_decision
  step_7: only_after_approval_create_implementation_cluster
```

No implementation cluster exists until @Creador approves it.

---

## 6. Clean hashtag interpretation

```yaml
hashtag_interpretation:
  "#populares": popular_human_interest_signal
  "#feedback": desire_for_feedback_surface
  "#debug": desire_for_diagnostics
  "#compactar": desire_for_smaller_faster_runtime
  "#stage2": desire_for_progression_after_success
  "#fp": desire_for_3D_like_spatial_reading
  "#asistencia": desire_for_accessibility_and_lower_friction
  "#posaya": desire_for_contextual_narrative_guidance

rules:
  - hashtags_are_labels_not_commands
  - hashtags_group_desires
  - hashtags_do_not_trigger_code
  - hashtags_require_creator_review
```

---

## 7. Source-of-truth hierarchy

```yaml
source_of_truth_hierarchy:
  highest:
    - current_playable_game_behavior
    - validated_safe_point
    - creator_decision
    - public_safety_boundary

  medium:
    - player_feedback
    - popular_votes
    - semantic_option_stack
    - design_notes

  lowest:
    - unreviewed_comments
    - raw_desires
    - isolated_preferences
```

If feedback contradicts the playable safe point, the feedback is treated as a desire to evaluate, not as a direct correction.

---

## 8. Current superconglomerates for review

```yaml
superconglomerates_for_creator_review:
  SC_A_feedback_and_debug:
    hashtag: "#feedback #debug #populares"
    semantic_desire: improve_human_feedback_and_error_review
    creator_question: should_feedback_and_selfdebug_be_prioritized_next
    safe_point_risk: low
    approval_status: pending_creator_review

  SC_B_core_optimization:
    hashtag: "#compactar #controles #portal #populares"
    semantic_desire: reduce_runtime_weight_and_improve_control_clarity
    creator_question: should_runtime_compaction_be_prioritized_before_visual_growth
    safe_point_risk: medium
    approval_status: pending_creator_review

  SC_C_experience_growth:
    hashtag: "#fp #stage2 #asistencia #posaya #populares"
    semantic_desire: expand_visual_experience_progression_accessibility_and_narrative_guidance
    creator_question: should_experience_growth_start_after_core_optimization
    safe_point_risk: medium
    approval_status: pending_creator_review
```

---

## 9. Human approval states

```yaml
approval_states:
  pending_creator_review:
    meaning: captured_as_semantic_option_only
    action: no_implementation

  approved_for_design:
    meaning: may_be_transformed_into_design_cluster
    action: no_code_yet

  approved_for_build:
    meaning: may_be_transformed_into_executable_patch
    action: implementation_allowed_if_safety_gates_pass

  rejected:
    meaning: do_not_pursue
    action: no_implementation

  deferred:
    meaning: hold_for_later
    action: no_implementation
```

---

## 10. Safety gates before any implementation

```yaml
pre_implementation_gates:
  - creator_explicit_approval
  - no_code_from_comments
  - no_private_ingestion
  - no_sensitive_exposure
  - no_automatic_action
  - preserve_v1_8_8_safe_point
  - game_remains_source_of_truth
```
