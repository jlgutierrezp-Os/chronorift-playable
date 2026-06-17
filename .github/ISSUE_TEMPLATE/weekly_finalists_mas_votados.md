---
name: Weekly Finalists - #mas_votados
about: Public sanitized weekly finalists for @Creador review
title: "[Weekly Finalists] #mas_votados cycle YYYY-WW"
labels: review, feedback, security
assignees: ""
---

# [Weekly Finalists] #mas_votados cycle YYYY-WW

## 0. Public-safe status

```yaml
issue_status:
  visibility: public_repo_safe
  purpose: weekly_finalists_for_creator_review
  hashtag_source: "#mas_votados #populares"
  code_suggestions: forbidden
  automatic_action: forbidden
  private_ingestion: forbidden
  sensitive_exposure: forbidden
  creator_decision_required: true
  source_of_truth: playable_game_state
  default_if_uncertain: do_not_publish
```

This issue is a public sanitized weekly finalists packet. It does not implement code, does not create automation, does not ingest private information, and does not decide for @Creador.

---

## 1. Cycle window

```yaml
cycle_window:
  cycle_id: YYYY-WW
  date_from: YYYY-MM-DD
  date_to: YYYY-MM-DD
  created_at: YYYY-MM-DD
  prepared_by: human_or_approved_agent
```

---

## 2. Sanitized vote sources summary

```yaml
sanitized_vote_sources_summary:
  source_type:
    - manual_vote_packets
    - public_safe_feedback_summary
    - creator_review_notes

  included:
    - option_ids
    - hashtags
    - semantic_desires
    - non_sensitive_vote_counts
    - non_sensitive_priority_notes

  excluded:
    - personal_sensitive_information
    - private_person_information
    - private_system_information
    - private_repo_links
    - private_file_paths
    - credentials
    - code_or_patch_suggestions
    - executable_instructions
    - raw_unreviewed_private_notes
```

---

## 3. Finalist superconglomerates

```yaml
finalist_superconglomerates:
  finalist_1:
    id:
    hashtags:
    semantic_desire:
    vote_signal:
    creator_question:
    status: pending_creator_review

    branches:
      accept_for_design:
        meaning:
        risk:
      hold_for_more_feedback:
        meaning:
        risk:
      merge_with_related_option:
        meaning:
        risk:
      reject_or_defer:
        meaning:
        risk:

    dependencies:
      gameplay:
      safety:
      narrative:
      technical:

  finalist_2:
    id:
    hashtags:
    semantic_desire:
    vote_signal:
    creator_question:
    status: pending_creator_review

    branches:
      accept_for_design:
        meaning:
        risk:
      hold_for_more_feedback:
        meaning:
        risk:
      merge_with_related_option:
        meaning:
        risk:
      reject_or_defer:
        meaning:
        risk:

    dependencies:
      gameplay:
      safety:
      narrative:
      technical:

  finalist_3:
    id:
    hashtags:
    semantic_desire:
    vote_signal:
    creator_question:
    status: pending_creator_review

    branches:
      accept_for_design:
        meaning:
        risk:
      hold_for_more_feedback:
        meaning:
        risk:
      merge_with_related_option:
        meaning:
        risk:
      reject_or_defer:
        meaning:
        risk:

    dependencies:
      gameplay:
      safety:
      narrative:
      technical:
```

---

## 4. Source truth check

```yaml
source_truth_check:
  game_is_source_of_truth: true
  feedback_is_desire_not_truth: true
  comments_are_not_code: true
  votes_are_semantic_signals: true
  creator_review_required: true

  current_playable_state:
    build: v1.8.8_box_goal_snap_assist_stage_transition
    public_entry_overlay: v1.8.9_entry_vote_notice_local_manual

  observed_gap:
    - weekly_finalist_selection_needs_creator_review
```

---

## 5. Safe point gate

```yaml
safe_point_gate:
  must_preserve:
    - box_grab
    - reduced_sliding
    - portal_transport
    - goal_assist
    - goal_snap
    - success_declaration
    - stage_transition
    - portal_matrix

  reject_if:
    - breaks_box_goal_loop
    - turns_feedback_into_code
    - creates_private_ingestion
    - exposes_sensitive_information
    - creates_automatic_repo_write_from_feedback
```

---

## 6. Creator decision options

```yaml
creator_decision_options:
  A_accept_one_for_design:
    meaning: selected_finalist_may_become_design_cluster
    code_allowed: false

  B_accept_one_for_build:
    meaning: selected_finalist_may_become_executable_patch_after_separate_build_approval
    code_allowed: only_after_separate_creator_approval

  C_merge_finalists:
    meaning: combine_related_semantic_desires_into_one_future_cluster
    code_allowed: false

  D_hold:
    meaning: wait_for_more_feedback
    code_allowed: false

  E_reject_or_defer:
    meaning: do_not_pursue_this_cycle
    code_allowed: false
```

---

## 7. Final creator decision

```yaml
creator_decision:
  selected_option:
  selected_finalist_or_cluster:
  approval_state:
    - pending_creator_review
    - approved_for_design
    - approved_for_build
    - hold
    - rejected
    - deferred
  notes:
```

---

## 8. No automatic action

```yaml
no_automatic_action:
  this_issue_does_not:
    - implement_code
    - accept_feedback_as_instruction
    - create_private_ingestion
    - expose_sensitive_information
    - authorize_repo_write_from_player_feedback
    - replace_creator_decision
```
