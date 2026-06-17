# POPULAR_VOTE_STACK_PUBLIC_REVIEW_V1

## 0. Estado público

```yaml
packet_status:
  visibility: public_repo_safe
  purpose: collect_popular_option_votes_for_human_review
  tag: "#populares"
  code_suggestions: forbidden
  automatic_action: forbidden
  private_ingestion: forbidden
  sensitive_exposure: forbidden
  human_decision_required: true
  default_if_uncertain: do_not_publish
```

Este documento crea una lista pública y sanitizada de opciones populares para votación humana. No contiene código sugerido, no ejecuta acciones, no cambia el juego por sí mismo y no alimenta sistemas privados.

---

## 1. Objetivo

```yaml
objective:
  central: organizar_opciones_votables_para_revision_humana
  use_case: alimentar_stack_de_priorizacion_sin_riesgo
  output: decision_humana_sobre_estructura_de_opciones_votadas
```

La intención es permitir que las mejoras se agrupen en opciones claras, comparables y votables antes de decidir qué se implementa.

---

## 2. Regla de seguridad

```yaml
safety_rule:
  allowed:
    - nombres_de_opciones
    - descripcion_general
    - beneficio_esperado
    - riesgo_general_no_tecnico
    - dependencia_de_safe_point
    - criterio_de_revision_humana

  forbidden:
    - codigo
    - parches
    - comandos
    - instrucciones_de_ejecucion
    - automatizacion
    - credenciales
    - informacion_sensible
    - enlaces_privados
    - ingesta_privada
```

---

## 3. Método de voto

```yaml
vote_method:
  type: human_review_stack
  voting_tag: "#populares"
  vote_units:
    - upvote
    - downvote
    - hold
    - needs_review
    - merge_with_other_option

  scoring_suggestion:
    upvote: 2
    hold: 0
    needs_review: -1
    downvote: -2
    merge_with_other_option: 0

  decision_rule:
    - ordenar_por_score
    - revisar_riesgo
    - revisar_dependencias
    - seleccionar_solo_opciones_compatibles_con_safe_point
```

---

## 4. Safe point obligatorio

```yaml
safe_point_gate:
  current_safe_point: v1.8.8_box_goal_snap_assist_stage_transition
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

Ninguna opción votada puede pasar a implementación si rompe el ciclo caja -> portal -> meta verde -> éxito -> Stage 2.

---

## 5. Opciones populares votables

```yaml
popular_options:
  OPT_001_feedback_button_manual:
    tag: "#populares"
    title: Boton_local_de_feedback_manual
    category: feedback
    description: Permitir que el jugador genere un paquete de retroalimentacion copiable manualmente.
    expected_benefit: mejora_recoleccion_de_feedback_humano
    dependency: no_auto_submit_no_private_ingestion
    safe_point_risk: low
    vote_status: open

  OPT_002_compact_runtime:
    tag: "#populares"
    title: Compactar_runtime_sin_romper_v1_8_8
    category: optimization
    description: Reducir duplicacion y peso del runtime preservando caja_portal_meta.
    expected_benefit: mayor_agilidad_menor_peso_mejor_mantenimiento
    dependency: preservar_safe_point_v1_8_8
    safe_point_risk: medium
    vote_status: open

  OPT_003_fp_visual_reintegration:
    tag: "#populares"
    title: Reintegrar_FP_almost_3D_sin_romper_fisica
    category: visualization
    description: Recuperar mejoras visuales 3D-like sin tocar el nucleo de caja y meta.
    expected_benefit: mejor_inmersion_y_lectura_espacial
    dependency: box_goal_gate_passed
    safe_point_risk: medium
    vote_status: open

  OPT_004_stage_2_minimal:
    tag: "#populares"
    title: Crear_Stage_2_minimo_despues_de_exito
    category: progression
    description: Agregar una segunda escena minima tras resolver caja_meta.
    expected_benefit: progreso_real_y_motivacion
    dependency: success_transition_stable
    safe_point_risk: medium
    vote_status: open

  OPT_005_portal_surface_clarity:
    tag: "#populares"
    title: Mejorar_lectura_de_superficies_validas_para_portal
    category: gameplay_clarity
    description: Hacer mas claro donde se puede colocar A/B y que direccion tiene cada portal.
    expected_benefit: menos_confusion_mas_control
    dependency: portal_matrix_preserved
    safe_point_risk: low_medium
    vote_status: open

  OPT_006_assist_modes:
    tag: "#populares"
    title: Modos_de_asistencia_jugable
    category: accessibility
    description: Permitir asistencia alta_media_baja para caja, meta y pistas.
    expected_benefit: accesibilidad_y_menos_frustracion
    dependency: no_break_core_physics
    safe_point_risk: low
    vote_status: open

  OPT_007_pos_aya_guidance:
    tag: "#populares"
    title: Pos_Aya_guia_contextual_minima
    category: narrative_support
    description: Agregar orientacion narrativa breve para objetivos, feedback y descubrimiento.
    expected_benefit: mayor_coherencia_narrativa
    dependency: sanitized_public_content_only
    safe_point_risk: low
    vote_status: open

  OPT_008_self_debug_report_list:
    tag: "#populares"
    title: SelfDebug_local_con_lista_copiable
    category: diagnostics
    description: Panel local para registrar reportes copiables sin envio automatico.
    expected_benefit: mejor_revision_humana_de_errores
    dependency: no_sensitive_data_no_auto_submit
    safe_point_risk: low
    vote_status: open

  OPT_009_mobile_control_polish:
    tag: "#populares"
    title: Pulir_controles_iPhone
    category: controls
    description: Mejorar sensibilidad, agarre de caja, drag y zona de botones.
    expected_benefit: mayor_jugabilidad_movil
    dependency: preserve_grab_and_goal_snap
    safe_point_risk: medium
    vote_status: open

  OPT_010_vote_stack_ui_later:
    tag: "#populares"
    title: UI_de_votacion_local_en_juego_mas_adelante
    category: meta_feedback
    description: En una fase posterior, mostrar opciones votables localmente sin envio automatico.
    expected_benefit: facilitar_priorizacion_humana
    dependency: feedback_safe_ingress_reviewed
    safe_point_risk: medium
    vote_status: hold
```

---

## 6. Stack de revision humana

```yaml
human_review_stack:
  review_order:
    - safety_check
    - safe_point_check
    - value_to_player
    - implementation_risk
    - dependency_conflicts
    - vote_score

  decision_outputs:
    - accept_for_next_cluster
    - hold_for_later
    - merge_with_other_option
    - reject_public_scope
    - move_to_private_human_notes
```

---

## 7. Superconglomerados sugeridos

```yaml
superclusters:
  SC_A_feedback_and_debug:
    options:
      - OPT_001_feedback_button_manual
      - OPT_008_self_debug_report_list
      - OPT_010_vote_stack_ui_later
    central_value: mejorar_feedback_humano_sin_automatizacion
    risk: low_medium

  SC_B_core_optimization:
    options:
      - OPT_002_compact_runtime
      - OPT_005_portal_surface_clarity
      - OPT_009_mobile_control_polish
    central_value: mejorar_estructura_y_control_sin_romper_safe_point
    risk: medium

  SC_C_experience_growth:
    options:
      - OPT_003_fp_visual_reintegration
      - OPT_004_stage_2_minimal
      - OPT_006_assist_modes
      - OPT_007_pos_aya_guidance
    central_value: expandir_jugabilidad_narrativa_y_accesibilidad
    risk: medium
```

---

## 8. Decision humana requerida

```yaml
human_decision_required:
  next_step_options:
    A: votar_opciones_individuales
    B: votar_superconglomerados
    C: elegir_una_opcion_central_y_dos_secundarias
    D: revisar_seguridad_antes_de_votar

  recommended_first_vote:
    - SC_A_feedback_and_debug
    - SC_B_core_optimization
    - SC_C_experience_growth
```

---

## 9. No accion automatica

```yaml
no_automatic_action:
  this_document_does_not:
    - implement_code
    - create_runtime_behavior
    - submit_feedback
    - write_issues_from_player_input
    - connect_to_private_systems
    - decide_for_the_human
```
