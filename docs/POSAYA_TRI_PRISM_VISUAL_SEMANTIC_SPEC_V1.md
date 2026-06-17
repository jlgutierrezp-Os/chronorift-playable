# POSAYA_TRI_PRISM_VISUAL_SEMANTIC_SPEC_V1

## 0. Estado

```yaml
packet_status:
  visibility: public_repo_safe
  purpose: design_only_visual_semantic_spec
  source_images_published: false
  runtime_change: false
  creator_review_required_before_build: true
  source_of_truth: playable_game_state
```

Este documento convierte las referencias visuales privadas y la descripción de @Creador en una especificación visual y semántica. No publica las imágenes y no implementa cambios en el juego.

---

## 1. Síntesis de diseño

```yaml
posaya_design_synthesis:
  identity: Pos.Aya / WayPoint-O
  form: gizmo_3D_compacto
  posture: robot_pequeno_en_asana
  material_language: gris_normalizado_brutalista_zen
  geometry_language: cuerpo_plegable_toroidal_no_euclidiano
  camera_model: prisma_triangular_de_tres_vistas
  player_relation: interfaz_visible_en_primera_persona
```

Pos.Aya debe sentirse como una herramienta-compañera: un objeto que lee estado del entorno, muestra información y permite seleccionar acciones de juego sin sustituir la decisión del jugador.

---

## 2. Gris normalizado

Las referencias muestran un objeto cálido de barro, piedra o cerámica. Para ChronoRift se traduce a una escala gris neutra, con cuerpo mate y señales luminosas discretas.

```yaml
grayscale_model:
  base_body:
    luma: 0.38
    role: cuerpo_mate_principal

  seams_and_folds:
    luma: 0.24
    role: cortes_pliegues_y_uniones

  raised_surfaces:
    luma: 0.44
    role: lobulos_paneles_y_volumenes_suaves

  worn_edges:
    luma: 0.52
    role: bordes_manipulados_y_superficies_de_uso

  sensor_recesses:
    luma: 0.20
    role: cavidades_de_lectura

  display_surface:
    luma: 0.68
    role: plano_de_estado_visible

  active_highlight:
    luma: 0.82
    role: senal_temporal_de_interaccion
```

Regla visual: cuerpo gris mate, bordes gastados, pliegues suaves, mínima luz de estado. Evitar apariencia de juguete brillante.

---

## 3. Anatomía semántica del gizmo

```yaml
posaya_anatomy:
  shell:
    description: cuerpo_redondeado_compacto_con_lobulos_plegados
    function: hacer_que_el_gizmo_se_sienta_fisico_y_sostenible

  toroidal_core:
    description: logica_visual_de_anillo_o_paso_interior
    function: justificar_aperturas_superficies_y_transiciones

  display_face:
    orientation: 0_degrees
    function:
      - estado
      - objetivo
      - modo_actual
      - ayuda_minima

  folded_body_face:
    orientation: 90_degrees
    function:
      - mostrar_cuerpo_plegado
      - expresar_volumen_no_plano

  sensor_face:
    orientation: 180_degrees
    function:
      - lectura_de_superficie
      - lectura_de_tiempo
      - lectura_de_rotacion

  output_face:
    orientation: 270_degrees
    function:
      - seleccion_de_superficie
      - apertura_visual
      - confirmacion_de_interaccion
```

---

## 4. Cámara como prisma triangular

```yaml
tri_prism_camera:
  face_A_MAP:
    view: laberinto_vista_aerea
    question: donde_estoy_y_como_se_conecta_el_espacio
    player_feel: estrategia_orientacion_mapa

  face_B_SIDE:
    view: laberinto_2D_vista_lateral
    question: como_se_mueve_la_masa_la_gravedad_y_la_caja
    player_feel: razonamiento_mecanico_y_espacial

  face_C_FP:
    view: laberinto_3D_desde_dentro_del_player
    question: que_ve_el_player_y_que_muestra_PosAya
    player_feel: presencia_directa_con_gizmo_visible
```

Cada vista cambia la forma de leer el juego y coordina controles táctiles distintos, pero ninguna debe bloquear movimiento, agarre, portales o meta.

---

## 5. Vista primera persona

```yaml
first_person_modes:
  player_eye:
    meaning: ver_desde_los_ojos_del_player
    interface: mundo_primero_gizmo_como_marco_secundario

  gizmo_reader:
    meaning: ver_desde_el_lector_de_PosAya
    interface: superficies_estado_trazas_y_senales_de_rotacion

  gizmo_lens:
    meaning: ver_a_traves_de_lentes_o_caras_del_gizmo
    interface: botones_tactiles_y_filtros_de_lectura
```

La primera persona debe mostrar el gizmo como una presencia física parcial, no como un menú plano. Sus caras o lentes deben explicar por qué cambian los controles.

---

## 6. Controles táctiles por perspectiva

```yaml
touch_controls_by_view:
  shared:
    - move
    - grab
    - view_switch
    - close_overlay

  MAP_view:
    left_zone: mover_o_recorrer_mapa
    right_zone: seleccionar_superficie_A_B
    center_touch: inspeccionar_superficie
    gizmo_button: resumen_de_lectura

  SIDE_view:
    left_zone: movimiento
    right_zone: agarrar_soltar
    vertical_swipe: intencion_de_altura_o_capa
    gizmo_button: alineacion_caja_meta

  FP_player_eye:
    left_zone: movimiento
    right_zone: mirar_o_apuntar
    gizmo_buttons:
      - lector
      - salida
      - lente
      - vista

  FP_gizmo_reader:
    left_zone: caminar_lento_o_sostener_posicion
    right_zone: leer_superficie
    gizmo_buttons:
      - fijar_lectura
      - comparar_traza_temporal
      - elegir_superficie

  FP_gizmo_lens:
    screen_as_lens: true
    actions:
      - cambiar_lente
      - elegir_superficie
      - confirmar_apertura
      - cancelar_sin_castigo
```

---

## 7. Capa toroidal no euclidiana como modelo de diseño

```yaml
toroidal_design_layer:
  meaning: superficies_que_se_llaman_y_se_conectan_sin_depender_de_distancia_lineal
  visual_metaphor: anillo_plegado_tubo_de_paso_superficie_a_superficie

  conceptual_variables:
    u: eje_alrededor_del_cuerpo_o_superficie
    v: eje_de_paso_o_apertura
    theta: rotacion_de_prisma_camara
    tau: traza_temporal_local
    rho: preparacion_de_superficie

  gizmo_state:
    notation: G_equals_u_v_theta_tau_rho
    purpose: describir_estado_visual_del_gizmo_sin_codigo
```

Esta capa es un modelo de diseño, no una implementación. Cualquier versión jugable requiere aprobación separada.

---

## 8. Integración narrativa

```yaml
narrative_integration:
  first_impression: herramienta_de_trabajo_o_gizmo_corporativo
  later_reading: companero_que_ayuda_a_leer_el_mundo

  themes:
    - identidad
    - nombre
    - percepcion
    - colaboracion
    - realidad_como_interfaz
    - acceso_creado_por_player_y_gizmo

  voice:
    tone: breve_calmo_contextual
    avoids:
      - explicar_demasiado
      - reemplazar_descubrimiento
    prefers:
      - pistas_minimas
      - orientacion_sensorial
      - reflejo_del_estado_del_puzzle
```

---

## 9. Gates antes de build

```yaml
before_build_gates:
  - creator_explicit_approval
  - preserve_v1_8_8_box_goal_loop
  - no_publication_of_reference_images_without_permission
  - keep_as_design_until_next_approval
  - FP_gizmo_visual_must_not_block_controls
```

---

## 10. Opciones siguientes para @Creador

```yaml
creator_review_options:
  A_keep_design_only:
    meaning: refinar_mas_antes_de_visualizar
    risk: low

  B_prepare_minimal_visual_marker_spec:
    meaning: definir_marcador_visual_simple_de_PosAya_en_FP_sin_codigo
    risk: low_medium

  C_split_into_subspecs:
    meaning: separar_en_camara_anatomia_controles_narrativa
    risk: low

  D_defer_until_core_optimization:
    meaning: esperar_a_optimizar_runtime
    risk: low
```
