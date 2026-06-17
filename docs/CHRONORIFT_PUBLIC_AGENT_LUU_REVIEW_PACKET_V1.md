# CHRONORIFT_PUBLIC_AGENT_LUU_REVIEW_PACKET_V1

## 0. Public safety status

```yaml
packet_status:
  visibility: public_repo_safe
  repository_scope: chronorift_playable_only
  private_ingestion: forbidden
  automatic_feed_to_private_systems: forbidden
  credentials: none
  private_repo_links: none
  private_file_links: none
  external_runtime_activation: none
  intended_use: human_review_then_private_notes_if_approved
```

This packet is designed for public review of ChronoRift development direction. It must not be treated as an ingestion source for any private Aid OS, LUU, Atlas, agentic, or production repository.

The public repository is used only as the visible playable prototype and sanitized public documentation surface. Any private production planning must be performed by the human through private methods, private repositories, or private review workflows.

---

## 1. Purpose

```yaml
purpose:
  primary: provide_a_sanitized_review_packet_for_agent_luu_analysis
  secondary: preserve_chronorift_playability_and_design_trace
  tertiary: support_human_decision_after_security_evaluation
```

This deliverable summarizes the operational contract, development constraints, safety boundaries, and decision format for ChronoRift. It is intentionally public-safe and does not expose private system internals.

---

## 2. Public/private boundary

```yaml
boundary:
  public_allowed:
    - gameplay_safe_points
    - public_build_status
    - sanitized_design_intent
    - public_testing_notes
    - non_sensitive_decision_framework
    - generic_agent_luu_review_packet

  public_forbidden:
    - private_repo_urls
    - private_file_paths
    - credentials
    - private_Atlas_kernel_contents
    - private_Aid_OS_runtime_designs
    - personal_sensitive_data
    - automatic_ingestion_instructions
    - deployment_secrets
    - paid_api_keys

  transfer_rule:
    - public_repo_may_contain_notes
    - human_may_manually_review_notes
    - private_systems_must_not_auto_ingest_public_repo
    - private_production_requires_separate_human_approved_flow
```

---

## 3. Current safe point

```yaml
current_safe_point:
  build: v1.8.8_box_goal_snap_assist_stage_transition
  human_validation:
    grab_works: true
    box_less_slippery: true
    box_crosses_portal: true
    goal_assist_visible: true
    box_snaps_to_goal: true
    success_declared: true
    stage_2_visible: true

  must_preserve:
    - box_grab
    - reduced_sliding
    - portal_transport
    - goal_assist
    - goal_snap
    - success_declaration
    - stage_transition
    - portal_matrix
```

No future visual, narrative, mathematical, or architectural improvement should be accepted if it breaks the validated box -> portal -> green goal loop.

---

## 4. Execution framework

Every meaningful ChronoRift change should map to:

```yaml
execution_framework:
  goal: define_desired_result
  plan: define_how_to_reach_result
  process: perform_verifiable_steps
  success_criteria: define_acceptance_conditions
  testing: validate_function_and_coherence
  feedback_loop: learn_and_improve_iteratively
```

Required traceability questions:

- What goal does the change serve?
- What is the implementation plan?
- What process will execute it?
- How is success measured?
- How is it tested?
- What feedback does it generate?

---

## 5. Decision cluster format

```yaml
decision_cluster:
  central_change:
    id:
    intent:
    safe_point_preserved:

  branches:
    minimal_patch:
      effect:
      risk:
      byte_cost:
      rollback:

    structural_refactor:
      effect:
      risk:
      byte_cost:
      rollback:

    alternate_route:
      effect:
      risk:
      byte_cost:
      rollback:

  dependencies:
    required:
    optional:
    forbidden:

  interconnections:
    affects:
    preserves:
    must_not_touch:

  executable_fix:
    file:
    patch_type:
    expected_result:

  regression_gates:
    - box_goal_resolvable
    - portal_matrix_ok
    - stage_transition_ok
    - mobile_controls_ok
    - time_system_preserved
    - fp_view_not_blocking

  self_debug_update:
    learned_error:
    prevention_rule:
    test_added:

  skill_registry_delta:
    added:
    updated:
    deprecated:
```

---

## 6. Optimization policy

```yaml
optimization_policy:
  goal: maximum_effect_with_minimum_runtime_weight

  prefer:
    - compact_data_tables
    - vector_functions_for_portals
    - parameterized_friction
    - single_goal_gate
    - unified_render_loop
    - short_internal_identifiers
    - semantic_UI_labels_only_where_needed
    - no_duplicate_runtime_paths

  avoid:
    - visual_changes_that_break_gameplay
    - redundant_helpers
    - verbose_runtime_comments
    - public_private_coupling
    - automatic_private_ingestion
    - excessive_HTML_patches_when_native_runtime_patch_is_safer

  alternate_route:
    use_when:
      - compaction_would_reduce_quality
      - refactor_risks_breaking_safe_point
      - public_repo_constraints_block_safe_private_design
    action:
      - keep_public_runtime_stable
      - create_private_human_notes_separately
      - test_in_isolated_mode_before_integration
```

---

## 7. ChronoRift playable constraints

```yaml
playable_constraints:
  must_remain:
    - iPhone_first
    - no_external_runtime_dependencies
    - no_paid_api_dependency
    - public_safe
    - human_tested
    - rollbackable

  core_loop:
    - move_player
    - grab_box
    - transport_box
    - portal_A_B
    - green_goal_snap
    - success_declaration
    - stage_transition

  secondary_systems:
    - MAP_view
    - SIDE_view
    - FP_3D_like_view
    - TithiTra_time_shift
    - Lens_time_trails
    - portal_matrix
```

---

## 8. Self-debug heuristic

```yaml
self_debug_heuristic:
  observe:
    - human_report
    - failed_expectation
    - repeated_error_category
    - safe_point_regression

  classify:
    - P0_playability
    - P1_controls
    - P2_physics
    - P3_visualization
    - P4_narrative
    - P5_optimization

  fix:
    - smallest_executable_patch_first
    - preserve_validated_safe_point
    - add_test_for_same_error_category
    - avoid_same_failed_route

  learn:
    - record_error_category
    - record_preventive_rule
    - update_skill_registry
    - define_next_regression_gate
```

---

## 9. Skill registry delta

```yaml
public_skill_registry_delta:
  CHRONORIFT_SAFE_POINT_PRESERVATION:
    status: active
    public_safe: true
    purpose: preserve_last_validated_playable_build

  CHRONORIFT_BOX_PORTAL_GOAL_GATE:
    status: active
    public_safe: true
    purpose: validate_box_to_portal_to_green_goal_loop

  CHRONORIFT_DECISION_CLUSTERING:
    status: active
    public_safe: true
    purpose: structure_each_change_as_central_change_branches_dependencies_and_patch

  CHRONORIFT_COMPACT_RUNTIME_REFACTOR:
    status: candidate
    public_safe: true
    purpose: reduce_bytes_and_duplication_without_breaking_gameplay

  CHRONORIFT_SELF_DEBUG_LEARNING:
    status: active
    public_safe: true
    purpose: record_errors_fixes_preventive_rules_and_tests

  CHRONORIFT_FP_MATH_SMOOTHING:
    status: candidate
    public_safe: true
    purpose: optimize_3D_like_view_without_breaking_physics
```

---

## 10. Security recommendation for human decision

```yaml
security_recommendation:
  public_repo_integration: approved_if_sanitized
  private_system_ingestion: not_approved
  human_review_required: true
  recommended_private_action:
    - read_public_packet_manually
    - extract_notes_by_human_decision
    - create_private_derivative_only_in_private_workspace
    - do_not_link_public_repo_as_private_source
```

The public packet may be used as a visible reference for discussion. It must not become an automatic source of truth for private Aid OS / LUU / Atlas systems.

---

## 11. Recommended next decision

```yaml
recommended_next_decision:
  id: v1.8.9_compact_runtime_without_breaking_v1.8.8
  central_change: compact_runtime_after_safe_point
  required_gate: preserve_box_portal_goal_loop

  branches:
    A_minimal:
      action: compact_only_repeated_small_helpers
      risk: low

    B_structural:
      action: unify_physics_portal_goal_functions
      risk: medium

    C_alternate:
      action: create_private_production_notes_after_human_security_review
      risk: low
```
