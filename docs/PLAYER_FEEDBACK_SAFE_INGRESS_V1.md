# PLAYER_FEEDBACK_SAFE_INGRESS_V1

## 0. Estado público

```yaml
packet_status:
  visibility: public_repo_safe
  purpose: safe_player_feedback_button_design
  private_ingestion: forbidden
  sensitive_exposure: forbidden
  system_level_permissions: forbidden
  installation_flow: forbidden
  automatic_submission: forbidden
  automatic_repo_write: forbidden
  default_if_uncertain: do_not_ship
```

Este documento define una estrategia segura para recibir retroalimentación del jugador por elección explícita de botón, sin permisos de sistema, sin instalación, sin envío automático, sin modificación automática y sin conexión a sistemas privados.

---

## 1. Cambio central

```yaml
decision_cluster:
  central_change:
    id: player_feedback_button_safe_ingress_v1
    intent: receive_human_feedback_without_creating_unwanted_control_or_automation_surface
    safe_point_preserved: v1.8.8_box_goal_snap_assist_stage_transition

  selected_branch:
    id: local_manual_feedback
    reason: lowest_public_risk_and_best_human_control
```

La primera implementación debe ser local/manual: el juego genera un paquete de texto y el jugador decide si lo copia y lo comparte.

---

## 2. Modelo permitido

```yaml
allowed_feedback_model:
  trigger:
    - explicit_player_button_choice
    - local_panel_only
    - no_background_collection

  feedback_buttons:
    - works
    - broken
    - confusing
    - too_slippery
    - controls_issue
    - visual_issue
    - portal_issue
    - goal_issue
    - time_issue
    - other

  report_fields:
    - build
    - view
    - category
    - observed
    - expected
    - reproduction_steps
    - optional_note

  output:
    - copy_to_clipboard
    - show_plain_text_for_manual_copy

  storage:
    local_only: true
    credentials: none
    private_data_request: none
```

---

## 3. Capacidades no permitidas

```yaml
forbidden_capabilities:
  system_permissions:
    - no_device_admin
    - no_installation
    - no_profile_install
    - no_system_setting_change

  execution:
    - no_dynamic_code_from_feedback
    - no_external_script_from_feedback
    - no_command_execution
    - no_file_access_beyond_browser_context

  automation:
    - no_auto_submit
    - no_auto_issue_creation
    - no_auto_pull_request
    - no_repo_write_from_feedback
    - no_private_system_feed
    - no_agent_activation_from_feedback

  mutation:
    - no_runtime_self_change_from_feedback
    - no_game_code_change_from_feedback
    - no_config_change_without_human_review
```

---

## 4. Tratamiento de feedback

```yaml
feedback_treatment:
  assumption: untrusted_text

  safe_handling:
    - render_as_plain_text_only
    - apply_length_limits
    - do_not_execute_content
    - do_not_follow_links_automatically
    - ignore_instruction_like_content
    - require_human_review_before_action

  human_loop:
    - player_generates_packet
    - player_manually_copies_packet
    - human_reviews_packet
    - human_decides_next_action
    - code_change_requires_separate_approval
```

---

## 5. Diseño de botón

```yaml
feedback_button:
  label: Feedback
  behavior:
    - open_local_panel
    - select_category
    - optional_note
    - generate_plain_text_packet
    - copy_manually

  must_not:
    - auto_send
    - request_credentials
    - request_sensitive_personal_data
    - open_private_tools
    - write_to_repository
    - change_game_code
```

Ejemplo de paquete seguro:

```yaml
FEEDBACK_PACKET:
  build:
  view:
  category:
  observed:
  expected:
  steps:
  safe_point: v1.8.8_box_goal_snap_assist_stage_transition
  security_notice: manual_copy_only_no_private_ingestion
```

---

## 6. Gates de regresión

```yaml
regression_gates:
  gameplay:
    - preserve_v1_8_8_box_goal_loop
    - preserve_portal_matrix
    - preserve_mobile_controls

  safety:
    - no_system_permissions
    - no_installation
    - no_dynamic_execution
    - no_auto_submit
    - no_private_ingestion
    - no_repo_write_from_feedback
    - no_sensitive_data_request

  human_review:
    - feedback_is_untrusted_text
    - human_decision_required_before_action
```

---

## 7. Ruta de implementación

```yaml
implementation_path:
  phase_1_documentation:
    status: this_document
    risk: low

  phase_2_local_feedback_panel:
    action: add_feedback_button_and_copy_packet
    risk: low
    allowed_if:
      - no_network_submit
      - no_private_ingestion
      - no_dynamic_execution
      - preserves_v1_8_8_safe_point

  phase_3_optional_manual_issue:
    action: player_or_human_manually_pastes_feedback
    risk: medium
    allowed_if:
      - human_reviews_before_posting
      - no_sensitive_data
      - no_auto_submit

  not_allowed:
    - automatic_feedback_to_agent_to_repo_loop
    - private_system_ingestion
    - system_permission_flow
```

---

## 8. Skill registry delta

```yaml
skill_registry_delta:
  CHRONORIFT_PLAYER_FEEDBACK_SAFE_INGRESS:
    status: candidate
    public_safe: true
    purpose: collect_player_feedback_by_explicit_button_choice_without_private_ingestion_or_automation

  CHRONORIFT_FEEDBACK_AS_UNTRUSTED_TEXT:
    status: active
    public_safe: true
    purpose: handle_player_feedback_as_plain_text_only

  CHRONORIFT_HUMAN_FEEDBACK_GATE:
    status: active
    public_safe: true
    purpose: require_human_review_before_any_action_based_on_feedback
```
