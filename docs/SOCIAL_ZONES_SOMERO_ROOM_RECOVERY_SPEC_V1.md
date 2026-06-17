# SOCIAL_ZONES_SOMERO_ROOM_RECOVERY_SPEC_V1

## 0. Estado

```yaml
packet_status:
  visibility: public_repo_safe
  purpose: design_only_social_zones_somero_room_recovery_spec
  runtime_change: false
  code_suggestions: forbidden
  personal_comment_storage: forbidden
  image_file_sharing: forbidden
  external_assets: forbidden
  private_ingestion: forbidden
  creator_review_required_before_build: true
  source_of_truth: playable_game_state
```

Este documento diseña áreas sociales, minijuegos, descanso, guardado somero y recuperación por nombre + palabras/códigos. No implementa código ni crea una cuenta privada.

---

## 1. Principio de solución óptima

```yaml
optimal_solution:
  product_truth:
    - el_sistema_es_somero
    - no_es_cuenta_privada
    - no_promete_backup_central
    - no_recupera_si_el_jugador_pierde_nombre_palabras_codigo
    - no_guarda_comentarios_personales
    - no_permite_subir_imagenes_archivos_texturas_o_mods

  recovery_truth:
    - jugador_es_responsable_de_guardar_su_nombre_y_palabras
    - el_juego_ofrece_copiar_texto
    - el_juego_ofrece_guardar_archivo_local
    - el_juego_puede_mostrar_QR_local_del_codigo
    - QR_es_conveniencia_de_entrada_no_autenticacion_segura

  minimum_disclosure:
    - mostrar_aviso_antes_de_crear_Somero_ID
    - pedir_confirmacion_de_entendido
    - ofrecer_exportar_antes_de_salir
    - repetir_aviso_si_el_jugador_intenta_continuar_sin_guardar
```

La forma óptima de evitar reclamos es no presentar el sistema como cuenta. Debe presentarse como una identidad somera recuperable por código que el jugador debe guardar.

---

## 2. Aviso obligatorio para jugadores

```yaml
player_notice:
  title: Somero ID no es una cuenta privada
  short_copy: >
    Este juego no guarda tu cuenta personal. Tu avance somero se recupera con tu nombre de badge y tus palabras/códigos. Si los pierdes, no podremos reconstruirlos. Guarda tu texto o QR local antes de salir.

  confirmations:
    - entiendo_que_no_es_cuenta_privada
    - entiendo_que_debo_guardar_mi_nombre_y_palabras
    - entiendo_que_no_debo_escribir_datos_personales_sensibles
    - entiendo_que_no_puedo_subir_imagenes_archivos_texturas_o_mods

  button_labels:
    create: Crear Somero ID
    copy: Copiar código
    save_file: Guardar archivo local
    show_qr: Mostrar QR local
    continue: Continuar
```

---

## 3. Lunch Area / Somero Chat Room

```yaml
lunch_area:
  name: Lunch Room
  type: somero_public_room
  purpose:
    - descanso_social
    - chit_chat_ligero
    - coordinacion_no_sensible
    - sensacion_de_mundo_compartido

  allowed_interaction:
    - preset_phrases
    - multiple_choice_responses
    - emote_text_tokens
    - avatar_gesture_choices
    - table_join_leave
    - water_break_prompt
    - pomodoro_checkin

  forbidden_interaction:
    - images
    - files
    - uploads
    - external_links_by_default
    - free_text_personal_logs
    - personal_sensitive_data
    - private_contact_exchange
    - executable_code
    - mods

  moderation:
    programmable_rules:
      - allowlist_phrases
      - banned_word_filter_if_free_text_later
      - rate_limit
      - no_file_upload
      - no_image_upload
      - no_personal_data_prompt
      - report_button
      - mute_block_later_if_backend_exists

  storage_policy:
    default: no_personal_comment_storage
    if_multiplayer_backend_later:
      store_only_choice_tokens_and_system_events
      avoid_storing_free_text
      creator_review_required: true
```

La Lunch Room debe sentirse pública, pero somera: interacción social ligera mediante opciones, frases seguras y gestos de avatar. Si se quiere chat libre real, requiere backend, moderación, política de datos y aprobación separada.

---

## 4. Bodega / Storage Area

```yaml
warehouse_social_area:
  name: Bodega
  purpose:
    - minijuegos_colaborativos
    - minijuegos_competitivos
    - practica_de_cooperacion
    - practica_de_eficiencia
    - objetos_avatar_como_piezas_de_juego

  collaborative_minigames:
    - mover_caja_entre_dos_players
    - ordenar_paquetes_por_peso_color_patron_interno
    - sincronizar_banda_transportadora
    - abrir_portal_de_carga_con_dos_lecturas
    - balancear_peso_en_bascula_compartida

  competitive_minigames:
    - ruta_mas_eficiente_sin_romper_reglas
    - precision_de_escaneo
    - orden_de_estocado
    - tiempo_de_entrega_con_descanso_obligatorio

  avatar_as_object_interaction:
    - empujar_suavemente_objetos
    - sostener_herramientas
    - cargar_peso_limitado
    - activar_placas
    - ayudar_a_otro_avatar_a_alinear_caja

  constraints:
    - competencia_no_debe_romper_colaboracion
    - no_leaderboard_personal_real
    - no_monetizacion_manipulativa
    - no_castigo_opaco
```

---

## 5. Pasillos / agua / chit chat

```yaml
hallway_area:
  name: Pasillos
  purpose:
    - transicion_entre_trabajo_descanso_y_social
    - tomar_agua
    - conversacion_ligera
    - comentario_personal_no_registrado
    - regular_ritmo_de_juego

  interaction_modes:
    water_break:
      effect: recovery_tick
      storage: choice_event_only

    chit_chat:
      effect: social_presence
      storage: no_personal_comment_storage
      allowed: preset_phrases_or_ephemeral_local_text

    hallway_pause:
      effect: pomodoro_or_recovery_alignment
      storage: timer_state_only

  rule:
    - comentarios_personales_no_se_registran
    - si_hay_texto_libre_debe_ser_efimero_o_local
    - para_exportacion_solo_se_guardan_logros_elecciones_y_descubrimientos
```

---

## 6. Cubículo de recuperación

```yaml
recovery_cubicle:
  name: Cubiculo
  purpose:
    - descanso
    - distraccion_segura
    - entretenimiento_de_oficina
    - recuperacion_de_energia
    - pausa_del_loop

  activities:
    - breathing_timer_light
    - chair_spin_minigame
    - desk_toy_sorting
    - pattern_focus_game
    - short_reading_prompt
    - quiet_reflection_choice
    - PosAya_checkin

  pomodoro_timer:
    configurable_by_user: true
    presets:
      - work_25_break_5
      - work_15_break_3
      - work_45_break_10
      - custom_local_only

  actions:
    - programar_actividad
    - jugar
    - continuar
    - guardar_archivo
    - apagar_equipo
    - salir_de_juego

  storage_policy:
    - guarda_preferencia_de_timer_solo_en_codigo_somero_si_el_jugador_exporta
    - no_guarda_comentarios_personales
    - exporta_logros_y_estado_en_texto
```

---

## 7. Exportación final al salir

```yaml
exit_export_flow:
  trigger:
    - player_clicks_save_file
    - player_clicks_power_off
    - player_clicks_exit_game
    - player_reaches_checkpoint

  export_contains:
    - final_display_name
    - somero_id
    - recovery_words_or_codes
    - config_hash
    - checkpoint_id
    - story_discoveries
    - achievement_tokens
    - avatar_config_ids
    - gizmo_config_ids
    - STUFFBOX_unlocks
    - pomodoro_preferences
    - object_state_summary

  export_does_not_contain:
    - personal_free_text_comments
    - uploaded_images
    - files
    - external_textures
    - private_tokens
    - real_identity_data

  export_formats:
    primary: copyable_text
    secondary: local_txt_file
    optional: local_QR_visual_for_somero_code
```

El archivo exportado debe ser un texto claro, copiables por el jugador. El QR, si existe, codifica el mismo texto o una versión compacta, no datos ocultos.

---

## 8. Login somero por texto, opciones o QR

```yaml
somero_login_flow:
  entry_methods:
    typing:
      - badge_name
      - recovery_words_or_codes

    touch_selection:
      - choose_name_structure
      - choose_word_1
      - choose_word_2
      - choose_word_3_or_number
      - confirm_config_hash

    QR_reading:
      - scan_local_saved_QR
      - parse_somero_payload
      - preview_avatar_gizmo_checkpoint
      - confirm_continue

  QR_use_cases:
    site_access_QR:
      content: public_game_URL_only
      risk: low

    user_resume_QR:
      content: somero_payload_or_compact_recovery_code
      risk: medium
      warning_required: anyone_with_this_QR_may_restore_same_somero_state

  resume_target:
    - last_registered_checkpoint
    - last_registered_player_position_bucket
    - object_state_summary
```

QR puede servir para dos cosas distintas: abrir el sitio o ingresar un código somero. El QR de usuario no debe tratarse como secreto fuerte.

---

## 9. Comentarios personales y registros

```yaml
personal_comment_policy:
  public_room:
    store_personal_comments: false
    allow_free_text_default: false
    allowed_record:
      - multiple_choice_selection
      - emote_token
      - activity_choice
      - achievement_token
      - discovery_token
      - moderation_flag_if_needed

  export_file:
    includes:
      - achievements
      - story_discoveries
      - selected_words
      - config_hash
      - checkpoint
      - chosen_options

    excludes:
      - personal_chat_text
      - private_notes
      - images
      - files
      - sensitive_data
```

Si el jugador puede escribir texto libre para sí mismo, debe quedar como nota local no registrada ni compartida por defecto. Para evitar reclamos, el sistema debe preferir opciones múltiples y tokens.

---

## 10. Nombres y palabras ágiles

```yaml
agile_name_word_builder:
  name_generation:
    modes:
      - random_1_field
      - random_2_fields
      - random_3_fields
      - player_reorder_words
      - player_reroll_one_word
      - player_lock_word

  UI:
    - large_touch_buttons
    - type_to_filter
    - swipe_to_reroll
    - drag_to_reorder
    - preview_badge
    - preview_hash
    - copy_save_QR_buttons

  word_rules:
    - internal_words_only
    - no_sensitive_word_prompt
    - no_real_name_required
    - no_external_dictionary_required
```

---

## 11. Reglas programables de salas

```yaml
programmable_room_rules:
  lunch_room:
    - no_images
    - no_files
    - no_external_links_by_default
    - preset_phrases_first
    - no_personal_data_prompts
    - no_persistent_personal_comments
    - rate_limit
    - report_and_mute_later_if_backend

  bodega:
    - cooperative_mode_default
    - competitive_mode_opt_in
    - no_real_identity_leaderboard
    - no_harassment_tokens
    - fail_state_recoverable

  hallway:
    - water_break_available
    - social_presence_light
    - no_storage_of_personal_chit_chat

  cubicle:
    - rest_is_valid_progress
    - pomodoro_config_local
    - exit_export_prompt_required
```

---

## 12. Reclamo / responsabilidad / consentimiento

```yaml
claim_prevention_policy:
  player_facing_copy:
    before_login: >
      Este juego usa Somero ID. No es una cuenta privada. No guardamos tus comentarios personales ni tus archivos. Tu avance se recupera con el nombre y palabras/código que tú guardes. Si los pierdes, no podemos recuperarlos.

    before_QR: >
      Este QR puede restaurar tu estado somero. Guárdalo como guardarías un código de partida. No contiene cuenta privada, pero quien lo tenga podría cargar la misma configuración.

    before_chat: >
      La Lunch Room usa opciones y frases someras. No compartas datos personales. No se permiten imágenes ni archivos.

    before_exit: >
      Guarda o copia tu Somero ID antes de salir. Sin ese texto no se garantiza recuperación.

  required_buttons:
    - Entiendo
    - Copiar Somero ID
    - Guardar archivo local
    - Mostrar QR local
    - Salir sin guardar

  user_responsibility:
    - guardar_nombre_y_palabras
    - no_usar_datos_sensibles
    - no_compartir_QR_si_no_quiere_que_otros_restauren_estado_somero
```

---

## 13. Fases de implementación futuras

```yaml
future_phases:
  phase_0_design_only:
    status: current
    runtime_change: false

  phase_1_local_only:
    features:
      - Somero_ID_builder
      - export_text
      - save_txt_file
      - QR_local_display
      - local_lunch_room_simulated_or_preset_only
    risk: low_medium

  phase_2_async_public_room:
    features:
      - multiplayer_presence
      - preset_phrases
      - room_rules_backend
      - moderation
    risk: high
    requires:
      - backend_review
      - data_policy
      - moderation_policy
      - creator_explicit_approval

  phase_3_full_social_zones:
    features:
      - collaborative_bodega_minigames
      - public_lunch_presence
      - avatar_object_interactions
    risk: high
    requires_separate_build_review: true
```

---

## 14. Superconglomerado decisional

```yaml
superconglomerado_decisional:
  option_id: SOCIAL_ZONES_SOMERO_ROOM_RECOVERY_SPEC_V1
  hashtags:
    - "#lunchroom"
    - "#someroid"
    - "#bodega"
    - "#pomodoro"
    - "#recovery"
    - "#qr"
    - "#socialzones"
    - "#populares"

  semantic_desire: crear_areas_sociales_someras_y_guardado_exportable_por_nombre_palabras_hash_QR_sin_cuenta_privada_sin_imagenes_archivos_ni_comentarios_personales_persistentes

  creator_question: debe_la_siguiente_etapa_priorizar_Somero_ID_export_y_zonas_sociales_locales_antes_de_chat_publico_real

  recommended_path:
    - phase_1_local_only_first
    - no_real_public_chat_until_backend_review
    - no_personal_comments_storage
    - copy_save_QR_before_exit

  branches:
    A_design_only:
      meaning: refinar_documento_sin_codigo
      risk: low

    B_local_somero_recovery_spec:
      meaning: detallar_export_text_save_file_QR_local_y_login_por_palabras
      risk: low_medium

    C_local_social_zone_simulation_spec:
      meaning: lunch_room_bodega_pasillos_cubiculo_sin_backend_real
      risk: low_medium

    D_public_chat_backend_candidate:
      meaning: solo_con_revision_de_backend_privacidad_y_moderacion
      risk: high

  approval_status:
    state: pending_creator_review
```

---

## 15. Gates antes de cualquier build

```yaml
before_build_gates:
  - creator_explicit_approval
  - no_claim_of_private_account
  - no_personal_comment_storage
  - no_images_or_files_in_chat
  - no_external_assets
  - no_backend_public_chat_without_separate_review
  - QR_warning_required
  - export_prompt_required_before_exit
  - preserve_v1_8_8_box_goal_loop
```
