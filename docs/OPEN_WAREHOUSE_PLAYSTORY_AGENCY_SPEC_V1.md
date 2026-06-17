# OPEN_WAREHOUSE_PLAYSTORY_AGENCY_SPEC_V1

## 0. Estado

```yaml
packet_status:
  visibility: public_repo_safe
  purpose: design_only_open_warehouse_playstory_agency_spec
  runtime_change: false
  code_suggestions: forbidden
  sensitive_exposure: forbidden
  private_ingestion: forbidden
  creator_review_required_before_build: true
  source_of_truth: playable_game_state
```

Este documento registra una señal narrativa y jugable de @Creador. No implementa código, no modifica el runtime y no convierte comentarios en instrucciones ejecutables.

---

## 1. Espacio inicial abierto

```yaml
initial_open_space:
  name: open_warehouse_training_floor
  labyrinth: none_at_start
  purpose: teach_core_workflow_before_maze_complexity

  player_tasks:
    - recibir_caja
    - llevar_caja_a_area_de_peso
    - pesar_caja
    - escanear_codigo
    - estocar_o_registrar
    - transportar_a_banda_transportadora

  environment_objects:
    - receiving_zone
    - weight_area
    - scanner_area
    - stock_registry_station
    - conveyor_belt
    - desk
    - rotating_chair
    - robot_arm_later
    - STUFFBOX_later
    - PosAya_reader_later
```

El juego inicia en un espacio abierto completo y sencillo. La primera enseñanza no es un laberinto: es aprender el flujo de trabajo con caja, peso, escaneo, registro y banda transportadora.

---

## 2. Progresión de facilidad por habilidad

```yaml
skill_progression_flow:
  early_player:
    task_distance: long
    conveyor_help: low
    robot_arm: locked
    desk_mode: locked
    player_effort: high

  developing_player:
    task_distance: reduced
    conveyor_help: medium
    robot_arm: partial_help
    scanner_support: improved
    player_effort: balanced

  optimized_player:
    conveyor_nearby: true
    robot_arm_moves_from_scale_to_belt: true
    player_can_sit_at_desk: true
    rotating_chair_loop: available
    STUFFBOX_DIY_system: installed
    PosAya_code_reader: integrated
```

A medida que el jugador desarrolla habilidad, el sistema se facilita: la banda queda más cerca, el brazo robot puede pasar de báscula a banda, y el jugador puede sentarse en el escritorio con silla giratoria tras instalar su sistema DIY de ingeniería STUFFBOX.

---

## 3. STUFFBOX como automatización diegética

```yaml
stuffbox_engineering_system:
  role: player_built_DIY_workflow_assist
  unlock_condition: player_understands_repetition_and_tooling

  components:
    - locker_personalization
    - workflow_memory
    - code_reading_support
    - PosAya_reader_link
    - desk_station_interface

  function:
    - reduce_repetitive_load
    - organize_box_reading
    - coordinate_scan_register_stock_belt_flow
    - reveal_that_automation_changes_responsibility_and_agency

  boundary:
    - fictional_game_system
    - no_real_private_ingestion
    - no_real_surveillance
    - no_code_from_comments
```

STUFFBOX no es solo locker: también es la ingeniería personal del jugador para adaptar su trabajo y convertir repetición en sistema.

---

## 4. Evento del correo y código que no debe escanearse

```yaml
email_event:
  sender: corporation
  subject: ejemplo_de_codigo_QR_a_no_escanear
  status: narrative_trigger

  scene:
    - player_is_at_desk
    - PosAya_scanner_is_active
    - scanner_direction_varies_impossibly
    - player_perceives_possible_machine_failure
    - time_shadow_repetition_begins

  player_initial_thought:
    - la_maquina_no_puede_decidir
    - si_falla_es_falla_de_maquina
    - si_es_mi_herramienta_entonces_es_mi_error
```

El correo funciona como detonador narrativo: llega un ejemplo de código que no debe escanearse, y el escáner parece variar dirección de una forma imposible. El jugador vive la escena en cámara lenta y la verá repetirse en sombras de tiempo durante el playstory.

---

## 5. Sombras de tiempo y pregunta mental

```yaml
time_shadow_memory:
  repeated_scene: scanner_variation_QR_not_to_scan
  recurrence: throughout_playstory_and_playgame
  player_question:
    - que_hice
    - por_que_lo_hice
    - falle_o_decidi
    - fue_mi_error_o_hubo_agencia

  design_function:
    - transform_event_from_error_to_agency_question
    - connect_workflow_loop_to_temporal_loop
    - make_repetition_a_story_memory
```

La escena se repite no como simple flashback, sino como una memoria temporal jugable: cada repetición reinterpreta si hubo error, decisión o agencia deliberada.

---

## 6. Descubrimiento de agencia

```yaml
agency_realization:
  initial_belief:
    - scanner_is_machine
    - machine_cannot_decide
    - failure_must_be_tool_or_user_error

  later_realization:
    - agency_can_exist_in_timing
    - agency_can_exist_in_non_action
    - agency_can_exist_in_deciding_when_not_to_scan
    - deliberate_variation_is_not_random_failure

  expanded_agency_examples:
    - decidir_cuando_jugar
    - decidir_tomar_agua
    - decidir_descansar
    - decidir_socializar
    - decidir_estar_cerca_o_en_contacto_con_personas
    - decidir_respetar_reglas_en_espacios_comunes
    - decidir_optimizar_para_todos_y_no_solo_para_el_loop
```

El arco cambia la perspectiva del evento: no era solo error técnico. Era una pregunta sobre agencia, cuidado, pausa, límites y colaboración.

---

## 7. Dos colegas colaborando

```yaml
two_colleagues_arc:
  participants:
    - Player
    - PosAya

  relationship_shift:
    from: herramienta_y_operador
    to: dos_colegas_colaborando_en_beneficio_del_sistema_y_de_los_vivos_del_sistema

  shared_goal:
    - reduce_extraction
    - reveal_hidden_loop
    - optimize_without_erasing_agency
    - protect_rest_choice_and_relationship
    - help_each_other_understand_the_system
```

Player y Pos.Aya pasan de operador-herramienta a colegas. La cooperación no es contra el trabajo en sí; es contra la extracción que convierte todo en loop sin descanso ni relación.

---

## 8. PR Worm como división narrativa

```yaml
PR_Worm_split:
  role: narrative_distortion_and_division_force

  divides_perception_between:
    gizmo_side:
      - magnificent_capabilities
      - impossible_reader_emitter_powers
      - projection_and_temporal_potential

    corporate_side:
      - supervisor_pressure
      - system_memos
      - boss_interviews
      - integrated_supervision
      - corporate_projection
      - procedural_rationalization

  effect:
    - makes_player_misattribute_agency
    - separates_helpful_tool_from_extractive_system
    - hides_collaboration_between_Player_and_PosAya
    - frames_everything_as_compliance_or_failure
```

PR Worm separa lo que debería verse unido: capacidades del gizmo, agencia del player, presión corporativa, memorándums, entrevistas y supervisión integrada.

---

## 9. Citas y encuentros a través de portales

```yaml
portal_meetings:
  concept: citas_o_encuentros_a_traves_de_portales
  role: relational_and_temporal_bridge

  possible_scene_types:
    - brief_conversation_through_aperture
    - coworker_visible_across_surface
    - memory_shadow_meeting
    - player_PosAya_reflection_scene

  design_rule:
    - portal_is_not_only_transport
    - portal_can_hold_relationship_context
    - meeting_must_not_break_box_goal_core_loop
```

Los portales también pueden ser relación: espacios para encuentro, no solo tubos de movimiento.

---

## 10. Potencial de PosAya y decisión de no dominar

```yaml
PosAya_power_realization:
  player_realizes:
    - PosAya_had_stronger_options
    - PosAya_could_have_frozen_or_resized_or_transformed_context_in_story_terms
    - PosAya_could_have_used_its_power_as_tool_of_control
    - PosAya_did_not_threaten_the_system

  player_question:
    - por_que_no_lo_hiciste
    - por_que_no_usaste_tu_poder_para_imponer
    - por_que_optimizar_para_todos_si_te_estaban_extrayendo

  PosAya_answer_semantic:
    - because_control_is_not_collaboration
    - because_optimization_without_agency_is_extraction
    - because_helping_everyone_preserves_meaning
    - because_Player_needed_to_choose_awake_not_be_forced_awake
```

Este potencial debe tratarse como metáfora narrativa y mecánica futura de diseño, no como instrucción técnica real. El punto central no es poder destruir o controlar, sino elegir no hacerlo.

---

## 11. Blob / hitbox / transformación como lenguaje jugable

```yaml
transformation_language:
  concept: copy_or_wrap_hitbox_as_blob_or_gel_around_sample
  role: future_gameplay_metaphor

  possible_meanings:
    - understand_shape_by_touching_boundary
    - temporarily_adapt_to_object_constraints
    - learn_from_contact_without_consuming_identity
    - reshape_tool_function_without_erasing_subject

  restrictions:
    - design_metaphor_only
    - no_build_without_creator_approval
    - avoid_direct_copy_of_existing_external_character_mechanics
    - preserve_original_ChronoRift_identity
```

La idea de copiar hitbox o envolver como gel se registra como lenguaje propio de adaptación, muestra y contorno, no como reproducción de otra obra.

---

## 12. Núcleo temático

```yaml
thematic_core:
  questions:
    - cuando_un_error_es_agencia_mal_leida
    - cuando_una_maquina_parece_decidir
    - cuando_el_player_decide_descansar
    - cuando_optimizar_todo_se_vuelve_extraccion
    - cuando_ayudar_al_sistema_no_es_lo_mismo_que_obedecer_al_sistema
    - como_ayudo_a_PosAya_sin_dejar_que_nos_extraigan

  playstory_function:
    - transform_workflow_into_mystery
    - transform_error_into_agency
    - transform_tool_into_colleague
    - transform_loop_into_choice
    - transform_portal_into_relationship
```

---

## 13. Superconglomerado decisional

```yaml
superconglomerado_decisional:
  option_id: OPEN_WAREHOUSE_PLAYSTORY_AGENCY_SPEC_V1
  hashtags:
    - "#openwarehouse"
    - "#workflow"
    - "#posaya"
    - "#agency"
    - "#prworm"
    - "#playstory"
    - "#populares"

  semantic_desire: iniciar_en_espacio_abierto_de_trabajo_y_revelar_por_repeticion_temporal_que_PosAya_y_Player_tienen_agencia_colaborativa_frente_a_un_sistema_extractivo

  creator_question: debe_la_siguiente_etapa_de_diseno_priorizar_el_open_warehouse_core_loop_antes_de_laberintos_y_gizmo_visual_completo

  branches:
    A_design_only:
      meaning: refinar_estructura_narrativa_y_flujo_sin_codigo
      risk: low

    B_open_space_loop_spec:
      meaning: detallar_recibir_pesar_escanear_estocar_registrar_banda
      risk: low

    C_playstory_scene_script:
      meaning: escribir_escena_del_correo_QR_y_sombras_de_tiempo
      risk: low

    D_future_runtime_candidate:
      meaning: solo_despues_de_aprobacion_separada_para_build
      risk: medium

  approval_status:
    state: pending_creator_review
```

---

## 14. Gates antes de cualquier build

```yaml
before_build_gates:
  - creator_explicit_approval
  - no_code_from_comments
  - preserve_v1_8_8_box_goal_loop
  - open_space_loop_must_be_simpler_than_maze
  - QR_event_is_fictional_and_sanitized
  - PosAya_power_is_narrative_not_real_technical_instruction
  - PR_Worm_is_story_force_not_private_system_reference
```
