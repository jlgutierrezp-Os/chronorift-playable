# HUMAN_AVATAR_NEUTRAL_CUSTOMIZATION_SPEC_V1

## 0. Estado

```yaml
packet_status:
  visibility: public_repo_safe
  purpose: design_only_neutral_human_avatar_customization_spec
  runtime_change: false
  code_suggestions: forbidden
  identity_extraction: forbidden
  sensitive_exposure: forbidden
  creator_review_required_before_build: true
  source_of_truth: playable_game_state
```

Este documento extiende la regla visual y semántica de Pos.Aya al avatar humano del jugador. Es diseño conceptual; no implementa código y no usa identidad real del jugador.

---

## 1. Imagen base del avatar humano

```yaml
human_avatar_base:
  identity_policy:
    gender: neutral
    real_identity: none
    nationality: none
    culture_specific_markers: none
    mandatory_skin_or_color_identity: none

  base_visual:
    role: worker_player_avatar
    uniform: company_uniform
    silhouette: neutral_functional_body
    face_detail: minimal_or_masked
    expression: calm_readable_non_specific
    color_policy: grayscale_or_player_selected_later

  design_goal:
    - allow_projection_without_forcing_identity
    - preserve_player_privacy
    - keep_avatar_readable_in_MAP_SIDE_FP_views
    - leave_customization_for_later_unlock
```

El avatar inicial representa función y presencia, no identidad biográfica. La personalización ocurre por elección del jugador, no por inferencia automática.

---

## 2. Badge e identidad de juego

```yaml
badge_system:
  displayed_name:
    source: player_selected_or_randomized
    not_real_name_required: true
    badge_label: somero_id

  random_name_structures:
    one_field:
      example_shape: NounCode
      purpose: minimal_fast_identity

    two_fields:
      example_shape: Adjective_Object
      purpose: memorable_play_identity

    three_fields:
      example_shape: Prefix_Form_Number
      purpose: structured_badge_identity

  constraints:
    - no_real_identity_required
    - no_sensitive_data
    - no_external_account_binding_required
    - player_can_reroll_or_choose
```

El badge funciona como identidad diegética del juego: visible en uniforme, registros internos y STUFFBOX, sin exigir datos personales.

---

## 3. STUFFBOX / locker personal

```yaml
stuffbox_system:
  name: STUFFBOX
  role: personalized_player_locker
  access_condition: appears_when_gizmo_partially_unfolds

  contents:
    - avatar_items
    - uniform_variants
    - patches
    - small_tools
    - self_help_instruments
    - training_objects
    - reflective_items
    - relationship_tokens

  player_choice_rule:
    - player_selects_what_to_share_or_equip
    - personal_stuff_is_chosen_not_extracted
    - equipped_items_change_avatar_character
    - sharing_items_adds_visible_personalization

  privacy_rule:
    - no_real_personal_data_required
    - no_forced_disclosure
    - no_private_ingestion
```

Cada ítem personal elegido por el jugador puede aparecer en el vestuario, carácter visual o gesto del avatar. El sistema no debe asumir identidad real.

---

## 4. Esqueleto base y estados de despliegue

```yaml
avatar_gizmo_skeleton_model:
  human_avatar:
    base_skeleton: neutral_player_skeleton
    customization_layers:
      - uniform
      - badge
      - texture
      - pattern
      - personal_item
      - utility_item
      - rest_or_training_marker

  gizmo:
    states:
      folded:
        meaning: herramienta_cerrada_compacta
      semi_folded:
        meaning: interfaz_parcial_STUFFBOX_y_badge
      unfolded:
        meaning: companion_interface_reader_lens_and_output_surfaces

  relation:
    - human_avatar_and_gizmo_share_visual_language
    - customization_can_affect_both_player_and_gizmo
    - no_customization_should_block_controls_or_readability
```

---

## 5. Customization futura

```yaml
customization_options:
  visual:
    - base_colors
    - grayscale_variants
    - patterns
    - textures
    - fabric_finish
    - brightness_or_luma
    - worn_edges
    - company_patches
    - player_chosen_symbols

  constraints:
    - no_cultural_lock_in
    - no_gender_lock_in
    - no_real_identity_requirement
    - no_sensitive_personal_information
    - no_pay_to_express_identity_requirement
```

La personalización debe abrir expresión sin forzar raza, género, nacionalidad o cultura. Los colores y patrones son elección estética, no identidad obligatoria.

---

## 6. Progresión por entrenamiento y vida cotidiana

```yaml
progression_model:
  attributes:
    - energy
    - resistance
    - damage_tolerance
    - repair_capacity
    - dexterity
    - strength
    - reach_distance
    - agility

  growth_sources:
    work:
      - delivery_tasks
      - organization_tasks
      - puzzle_solving

    training:
      - movement_practice
      - tool_practice
      - controlled_challenge

    recovery:
      - rest
      - meditation
      - reading
      - thinking
      - creating
      - relationship_time

    self_help_instruments:
      - chosen_by_player
      - non_forced
      - framed_as_care_and_skill_building
```

El crecimiento debe equilibrar trabajo, descanso, aprendizaje y relación. No debe empujar al jugador a grind infinito.

---

## 7. Economía narrativa de coins y consecuencias

```yaml
coin_loop_design:
  role: narrative_pressure_system
  player_question: seguir_en_el_loop_o_buscar_otro_modo_de_existir

  coins:
    increase_when:
      - completes_tasks
      - follows_workflow
      - optimizes_routes

  consequences:
    triggered_by:
      - liberties_taken
      - unauthorized_personal_stuff_visible
      - supervisor_random_inspection

  ethics_gate:
    - consequences_must_be_readable
    - avoid_unfair_punishment
    - avoid_dark_patterns
    - allow_player_reflection
    - balance_work_life_theme
```

La cuenta de coins creciente puede representar presión laboral o productividad, pero debe servir a la narrativa de libertad, cuidado y balance vida-trabajo. No debe convertirse en manipulación.

---

## 8. Supervisor e inspección random

```yaml
supervisor_inspection_model:
  role: narrative_system_not_player_surveillance
  event_type: random_or_contextual_inspection

  detects:
    - visible_personal_items
    - non_standard_uniform_mods
    - unauthorized_stuffbox_items
    - work_loop_deviation

  records:
    - consequence_coin
    - narrative_note
    - player_choice_memory

  safety_boundary:
    - no_real_world_surveillance
    - no_sensitive_data
    - no_private_ingestion
    - no_player_real_identity_tracking
```

La inspección es una mecánica narrativa del mundo de juego, no vigilancia real del usuario.

---

## 9. Momento de conciencia

```yaml
awakening_arc:
  early_state:
    - worker_follows_loop
    - earns_coins
    - avoids_penalties
    - hides_or_limits_personal_stuff

  realization:
    - sees_the_loop
    - notices_PosAya_is_more_than_tool
    - realizes_human_avatar_can_also_fold_and_unfold_through_activity
    - questions_work_life_balance
    - wants_to_help_gizmo

  new_desire:
    - personalize_self_by_choice
    - help_PosAya
    - understand_the_system
    - create_other_paths
    - choose_relationship_over_loop_only
```

El avatar no solo progresa en stats. También progresa en conciencia, vínculo, capacidad de plegarse/desplegarse simbólicamente y decisión de personalizarse.

---

## 10. Fold / Unfold humano y minijuego STUFFBOX

```yaml
human_fold_unfold_realization:
  trigger: player_realizes_avatar_can_fold_and_unfold_through_activity
  meaning:
    - adaptacion_corporal_y_funcional
    - agencia_sobre_el_uniforme_y_la_presencia
    - sincronizacion_con_la_logica_foldable_de_PosAya
    - personalizacion_como_despertar_no_como_consumo_obligatorio

  states:
    folded:
      meaning: avatar_en_modo_funcional_de_compania
      visual: uniforme_base_badge_minimo_sin_items_visibles

    semi_folded:
      meaning: avatar_con_acceso_parcial_a_STUFFBOX
      visual: pequenos_items_visibles_y_modificaciones_discretas

    unfolded:
      meaning: avatar_expresa_identidad_de_juego_elegida_y_colabora_con_PosAya
      visual: capas_personales_patrones_texturas_y_herramientas_visibles
```

Cuando el humano comprende que él también puede plegarse y desplegarse mediante actividad, decide personalizarse. La personalización deja de ser adorno y se vuelve decisión narrativa: cuánto del yo de juego entra al uniforme, al cuerpo, al badge y al vínculo con Pos.Aya.

```yaml
stuffbox_minigame:
  name: STUFFBOX_supervision_balance
  role: minigame_narrativo_de_discrecion_y_consecuencia

  player_options:
    equip_discreetly:
      meaning: usar_item_personal_sin_llamar_atencion
      possible_result: item_visible_low_risk

    hide_item:
      meaning: conservar_item_en_STUFFBOX_sin_equipar
      possible_result: no_bonus_no_risk

    declare_item:
      meaning: aceptar_registro_administrativo
      possible_result: administrative_fee_or_rule_note

    pay_administrative_fine:
      meaning: resolver_consecuencia_de_forma_transparente
      possible_result: coin_cost_but_no_secret_penalty

    accept_inspection:
      meaning: someterse_a_revision_narrativa_del_mundo_de_juego
      possible_result: consequence_note_or_clearance

  risk_model:
    visible_personal_item: increases_attention
    non_standard_uniform_mod: increases_attention
    repeated_loop_deviation: increases_attention
    declared_item: reduces_hidden_risk_but_may_cost_coins

  reward_model:
    personal_expression: increases_attachment
    useful_item: may_support_training_or_recovery
    relationship_token: may_support_PosAya_bond
    reflective_item: may_support_awareness_arc
```

La ruta de evasión de supervisión debe entenderse como minijuego diegético de discreción dentro de una compañía ficticia, no como vigilancia real ni como aprendizaje de evasión real. Siempre debe existir una alternativa legible: declarar, pagar multa administrativa, guardar el ítem o aceptar inspección.

```yaml
ethics_and_balance_gate:
  required:
    - consequences_are_clear_before_or_immediately_after_action
    - player_can_choose_compliance_or_discretion
    - no_hidden_real_tracking
    - no_real_personal_data
    - no_unfair_coin_trap
    - no_grind_required_for_self_expression
    - penalties_are_narrative_and_recoverable

  narrative_question:
    - cuanto_de_mi_puedo_llevar_al_trabajo
    - cuanto_cuesta_ocultarme
    - cuanto_cuesta_declararme
    - cuando_el_loop_de_productividad_deja_de_ser_suficiente
    - como_ayudo_a_PosAya_sin_perderme
```

---

## 11. Superconglomerado decisional

```yaml
superconglomerado_decisional:
  option_id: HUMAN_AVATAR_NEUTRAL_CUSTOMIZATION_SPEC_V1
  hashtags:
    - "#avatar"
    - "#stuffbox"
    - "#customization"
    - "#worklife"
    - "#foldunfold"
    - "#supervision"
    - "#posaya"
    - "#populares"

  semantic_desire: crear_avatar_humano_neutro_customizable_con_STUFFBOX_badge_uniforme_fold_unfold_y_progresion_de_balance_vida_trabajo

  creator_question: debe_el_avatar_humano_compartir_la_misma_logica_foldable_customizable_de_PosAya_sin_forzar_identidad_real_y_con_minijuego_de_STUFFBOX_supervision_balance

  branches:
    A_design_only:
      meaning: refinar_modelo_sin_codigo
      risk: low

    B_badge_and_STUFFBOX_spec:
      meaning: detallar_badge_random_names_locker_items_y_reglas_de_privacidad
      risk: low

    C_attribute_progression_spec:
      meaning: separar_stats_entrenamiento_descanso_y_autocuidado
      risk: low_medium

    D_fold_unfold_STUFFBOX_minigame_spec:
      meaning: detallar_minijuego_de_personalizacion_discrecion_multa_administrativa_y_supervision_ficticia
      risk: low_medium

    E_future_runtime_candidate:
      meaning: solo_despues_de_aprobacion_separada_para_build
      risk: medium

  approval_status:
    state: pending_creator_review
```

---

## 12. Gates antes de cualquier build

```yaml
before_build_gates:
  - creator_explicit_approval
  - no_real_identity_required
  - no_sensitive_data
  - no_private_ingestion
  - no_code_from_comments
  - preserve_v1_8_8_box_goal_loop
  - customization_must_be_player_chosen
  - supervisor_system_is_fictional_not_real_surveillance
  - STUFFBOX_consequences_must_be_readable_and_recoverable
```
