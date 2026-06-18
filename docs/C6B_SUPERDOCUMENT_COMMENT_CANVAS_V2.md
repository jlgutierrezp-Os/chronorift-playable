# C6B Superdocumento de Revisión Humana — Canvas Editable V2

Status: human-editable review canvas. No runtime replacement. No gameplay build.

## Propósito

Este documento corrige el formato anterior. No pide solo ACCEPT/REVISE. Proporciona campos reales para que el humano escriba comentarios libres, correcciones, nombres alternativos, dudas, prioridades, texto sustituto, ejemplos de humor y decisiones de aprobación.

El objetivo es recibir todos los comentarios humanos en una sola interacción, revisarlos por coherencia interna, prioridad y conglomerado decisional, e integrarlos en el mismo superdocumento antes de pasar al build.

## Instrucciones de uso

1. Lee solo las secciones que quieras corregir.
2. Escribe debajo de cada campo marcado como `ESCRIBE_AQUI`.
3. Deja vacío lo que no quieras comentar.
4. No necesitas escribir ACCEPT.
5. Si algo está bien, simplemente no lo toques.
6. Si quieres aprobar al final, llena la sección final de decisión.

## Niveles de revisión

```yaml
REVIEW_LEVELS:
  macro:
    purpose: mundo_historia_producto_direccion
  meso:
    purpose: capitulos_sistemas_personajes_areas_UIX
  micro:
    purpose: pantallas_dialogos_gags_menus_iconos
  atomico:
    purpose: lineas_exactas_botones_triggers_flags_nombres
```

---

# A. Comentarios globales libres

## A1. Comentario general del humano

ESCRIBE_AQUI:


## A2. Qué sientes que estoy interpretando mal

ESCRIBE_AQUI:


## A3. Qué debo conservar sin cambiar

ESCRIBE_AQUI:


## A4. Qué falta aunque no lo haya preguntado

ESCRIBE_AQUI:


---

# B. Revisión macro

## B1. Mundo y premisa general

Auto-completado actual:
- ChronoRift es un RPG/sátira corporativa low-processor.
- El jugador trabaja físicamente, gana coins y descubre que la productividad infinita es el Loop.
- El jugador ayuda a Pos.Aya / WayPoint-O y al avatar a recuperar agencia.
- The Corporation usa lenguaje amable para convertir disponibilidad en productividad.
- PR_Worm representa el parásito de productividad/retención/loop.

Comentario humano:
ESCRIBE_AQUI:


## B2. Dirección comercial general

Auto-completado actual:
- Primero web demo.
- Luego web complete con posible pago único si es viable.
- Después modo active/comic/skip.
- App y mercado después, solo si hay valor y privacidad.
- Multiplayer/builder arena después.

Comentario humano:
ESCRIBE_AQUI:


## B3. Dirección low-processor

Auto-completado actual:
- Cálculo exacto al momento de la acción.
- State machines.
- Celdas 20x20x20.
- Microgames aislados.
- Nada de física global pesada.

Comentario humano:
ESCRIBE_AQUI:


---

# C. Revisión meso

## C1. Capítulos y progresión

Auto-completado actual:
- C6B solo cubre onboarding RPG.
- No incluye todavía paquetes, construcción, portales, PR_Worm Debug ni finales.
- La historia completa queda para bajar capítulo por capítulo.

Comentario humano:
ESCRIBE_AQUI:


## C2. Personajes y roles

Auto-completado actual:
- Player / Sairen opcional.
- The Corporation.
- Supervisor Local.
- Chief Office.
- PR_Worm.
- Pos.Aya / WayPoint-O.
- Bunch of Loving Ones.
- Birdi.

Comentario humano:
ESCRIBE_AQUI:


## C3. Áreas del mundo

Auto-completado actual:
- Corporate intro.
- Application.
- Stuff Box / locker.
- Cubicle hub.
- Notebook / Somero.
- Laptop.
- Future: warehouse/workspace, monitor room, CEO office, Small-O-Big-O Chamber, multiplayer builder area.

Comentario humano:
ESCRIBE_AQUI:


## C4. UIX y flujo de jugador

Auto-completado actual:
- Pantallas cortas.
- Texto con humor satírico.
- Botones claros.
- Modo skip/next/active debe existir después.
- C6B debe ser simple y funcional.

Comentario humano:
ESCRIBE_AQUI:


---

# D. Revisión micro: nombres exactos

## D1. Nombres confirmados propuestos

```yaml
EXACT_NAME_REGISTRY:
  game_title: ChronoRift
  current_build: C6B_RPG_ONBOARDING_FOUNDATION
  memory_system: Somero
  memory_trace: Somero Trace
  player_symbolic_default: Sairen
  player_role_primary: HUMAN in the LOOP
  job_role: Trainee de Supervisión Operativa
  corporation_current_name: The Corporation
  corporation_short_label: Corporation
  local_supervisor_display: Supervisor Local
  boss_display: Chief Office
  antagonist: PR_Worm
  antagonist_readable: PR Worm
  companion_gizmo_primary: Pos.Aya
  companion_gizmo_english: WayPoint-O
  personal_storage: Stuff Box
  personal_items_label: Personal Belongings
  future_chamber: Small-O-Big-O Chamber
  rescue_group: Bunch of Loving Ones
  office_toy: Birdi
  app_future_label: App Sync
```

Comentario humano sobre nombres:
ESCRIBE_AQUI:


## D2. Nombres que quieres renombrar

Llena solo los que quieras cambiar.

```yaml
NAME_CHANGES:
  corporation_current_name:
    current: The Corporation
    proposed:
    reason:
  local_supervisor_display:
    current: Supervisor Local
    proposed:
    reason:
  boss_display:
    current: Chief Office
    proposed:
    reason:
  PR_Worm:
    current: PR_Worm
    proposed:
    reason:
  Pos_Aya:
    current: Pos.Aya / WayPoint-O
    proposed:
    reason:
  Stuff_Box:
    current: Stuff Box
    proposed:
    reason:
  Somero:
    current: Somero
    proposed:
    reason:
  Bunch_of_Loving_Ones:
    current: Bunch of Loving Ones
    proposed:
    reason:
  Birdi:
    current: Birdi
    proposed:
    reason:
```

Comentarios libres de nombres:
ESCRIBE_AQUI:


---

# E. Revisión micro: textos de pantallas C6B

## E1. Screen A — The Corporation Intro

Texto propuesto:

```text
🏢 THE CORPORATION PRESENTA

ChronoRift: HUMAN in the LOOP

No necesitas experiencia.
No necesitas entender todo.
No necesitas saber cuánto dura un loop.

Solo necesitas estar disponible.

La Corporation busca Trainees de Supervisión Operativa para tareas físicas ligeras, observación de sistemas, corrección de errores y crecimiento personal medible en coins.

Beneficios:
★ Coins por disponibilidad.
★ Entrenamiento en trabajo físico.
★ Acceso eventual a Pos.Aya.
★ Progreso verificable.
★ Un puesto que siempre puede necesitarte un poco más.
```

Qué revisar:
- ¿Es demasiado largo?
- ¿Es suficientemente satírico?
- ¿Quieres más humor absurdo?
- ¿Quieres cambiar “The Corporation”?

Comentario humano:
ESCRIBE_AQUI:


Texto sustituto, si quieres reemplazarlo completo:
ESCRIBE_AQUI:


## E2. Screen B — Application / Somero Identity

Texto propuesto:

```text
FORMULARIO DE INGRESO — TRAINEE

Nombre de uso dentro del Loop:
[________________]

Sugerencia: Sairen

Este nombre será usado para tu Somero Trace.
No es contraseña.
No es cuenta.
No es verificación de identidad.

Es una marca para recordar dónde estabas cuando el sistema finja que todo empieza desde cero.
```

Comentario humano:
ESCRIBE_AQUI:


Texto sustituto:
ESCRIBE_AQUI:


## E3. Screen C — Avatar Seed

Texto propuesto:

```text
AVATAR TEMPORAL

Tu avatar no necesita estar completo para empezar.
La Corporation solo requiere una silueta suficientemente operativa.

El resto de ti puede ser recuperado después.
Si recuerdas dónde lo guardaste.
```

Comentario humano:
ESCRIBE_AQUI:


Texto sustituto:
ESCRIBE_AQUI:


## E4. Screen D — Personal Belongings

Texto propuesto:

```text
PERSONAL BELONGINGS

Antes de ingresar al área operativa, guarda tus pertenencias.
La Corporation recomienda viajar ligero.

Algunos objetos parecen inútiles durante el trabajo.
Eso suele significar que todavía no has llegado a la parte importante.
```

Comentario humano:
ESCRIBE_AQUI:


Texto sustituto:
ESCRIBE_AQUI:


## E5. Screen E — Stuff Box

Texto propuesto:

```text
📦 STUFF BOX

Tus Personal Belongings han sido guardados.
Estado de propiedad: Personal.
Ubicación actual: Stuff Box.
Acceso durante turno: limitado por comodidad operativa.

Somero Trace:
{PLAYER_NAME}-STUFFBOX-PERSONAL-BELONGINGS-STABLE

Cierra el locker para iniciar entrenamiento.
```

Comentario humano:
ESCRIBE_AQUI:


Texto sustituto:
ESCRIBE_AQUI:


## E6. Screen F — Cubicle Hub

Texto propuesto:

```text
CUBÍCULO DE TRAINEE

Tu estación está lista.
La Corporation ha preparado herramientas suficientemente útiles para que parezca que elegiste empezar.

📓 Notebook / Somero
💻 Laptop corporativa
◉ Pos.Aya
📦 Stuff Box status
⬆ Levantarse

Objetivo actual:
Conoce tu estación antes de optimizar nada.
```

Comentario humano:
ESCRIBE_AQUI:


Texto sustituto:
ESCRIBE_AQUI:


## E7. Screen G — Notebook / Somero

Texto propuesto:

```text
📓 NOTEBOOK / SOMERO

Nombre: {PLAYER_NAME}
Rol: HUMAN in the LOOP / Trainee
Capítulo: 1 — Cubicle Obedience
Stage: Orientation
Energía humana: estable
Energía Pos.Aya: disponible
Personal Belongings: Stuff Box
Somero Trace:
{PLAYER_NAME}-CH1-CUBICLE-STUFFBOX-STABLE-FIRSTLOG

Nota:
La Corporation registra desempeño.
Somero recuerda contexto.
No son lo mismo.
```

Comentario humano:
ESCRIBE_AQUI:


Texto sustituto:
ESCRIBE_AQUI:


---

# F. Revisión micro: diálogos y mensajes

## F1. Supervisor Local first email

Texto propuesto:

```text
FROM: Supervisor Local
SUBJECT: Bienvenido, Trainee

Bienvenido al área operativa.
Hoy no necesitas resolver todo.
Solo necesitamos confirmar tres cosas:

1. Que puedes leer instrucciones.
2. Que puedes reconocer herramientas.
3. Que puedes volver a tu estación cuando el sistema lo solicite.

Paso 1: abre Notebook / Somero.
Paso 2: revisa este correo.
Paso 3: mantén disponibilidad.

La disponibilidad es la primera forma de productividad.
```

Comentario humano:
ESCRIBE_AQUI:


Texto sustituto:
ESCRIBE_AQUI:


## F2. Chief Office welcome message

Texto propuesto:

```text
FROM: Chief Office
SUBJECT: Tu oportunidad en la Corporation

Nos alegra tenerte en HUMAN in the LOOP.
Aquí cada acción cuenta.
Cada corrección cuenta.
Cada segundo disponible puede convertirse en valor.

No estás aquí para hacer trabajo pequeño.
Estás aquí para aprender a supervisar sistemas que todavía necesitan humanos.

Por ahora, solo familiarízate con tu estación.
La eficiencia profunda empieza pareciendo una orientación sencilla.
```

Comentario humano:
ESCRIBE_AQUI:


Texto sustituto:
ESCRIBE_AQUI:


## F3. PR_Worm first nudge

Texto propuesto:

```text
FROM: PR_Worm Service
SUBJECT: Small productivity reminder

Hola, Human.
Un recordatorio amistoso:
los loops funcionan mejor cuando nadie se sale antes de tiempo.

No es presión.
Es continuidad.

Tip automático:
si sientes que terminaste, revisa si todavía estás disponible.
```

Comentario humano:
ESCRIBE_AQUI:


Texto sustituto:
ESCRIBE_AQUI:


## F4. Pos.Aya / WayPoint-O first hint

Texto propuesto:

```text
◉ POS.AYA / WayPoint-O
Corporate routing assistant online.

Funciones iniciales:
- recordar rutas
- mostrar contexto
- ayudarte a no perderte en procesos simples

Hint:
Tus Personal Belongings están en Stuff Box.
Puedo recordar esa ubicación si tú decides volver por ellas.
```

Diálogo propuesto:

```yaml
DIALOGUE_BOX:
  speaker: Pos.Aya
  line: "No todo lo guardado queda perdido. Algunas rutas solo esperan permiso."
  player_options:
    - "Gracias."
    - "¿Rutas?"
    - "Solo dime qué sigue."
```

Comentario humano:
ESCRIBE_AQUI:


Texto sustituto:
ESCRIBE_AQUI:


## F5. Recovery seed

Texto propuesto:

```text
🌱 MICROPAUSA DISPONIBLE

Antes de iniciar trabajo físico, puedes elegir una preparación breve.
No aumenta productividad inmediata.
Puede mejorar tu estado.

Opciones:
📖 Leer una línea
🌬 Respirar
🧍 Estirar
👔 Revisar uniforme

La Corporation no penaliza las micropausas.
Todavía.
```

Comentario humano:
ESCRIBE_AQUI:


Texto sustituto:
ESCRIBE_AQUI:


---

# G. Revisión micro: humor y gags

## G1. Gags propuestos

```yaml
GAGS:
  corporate_intro:
    gag: crecimiento_personal_medible_en_coins
    comment: contradiccion_entre_desarrollo_humano_y_metrica_productiva
  application_identity:
    gag: sistema_finge_que_todo_empieza_desde_cero
    comment: Somero_como_memoria_contra_el_reset
  avatar:
    gag: silueta_suficientemente_operativa
    comment: corporacion_reduce_persona_a_funcion
  stuff_box:
    gag: limitado_por_comodidad_operativa
    comment: eufemismo_corporativo
  cubicle:
    gag: herramientas_suficientemente_utiles_para_que_parezca_que_elegiste_empezar
    comment: falsa_agencia
  pr_worm:
    gag: si_terminaste_revisa_si_todavia_estas_disponible
    comment: loop_infinito_suave
  recovery:
    gag: no_penaliza_micropausas_todavia
    comment: humor_de_sombra_del_futuro
```

Comentario humano:
ESCRIBE_AQUI:


Gags que quieres agregar:
ESCRIBE_AQUI:


Gags que quieres quitar o bajar de intensidad:
ESCRIBE_AQUI:


---

# H. Revisión micro: ítems, botones, iconos

## H1. Items

```yaml
ITEMS:
  - Phone
  - Chip / SIM
  - Tape
  - Sticks
  - Miniature Office Flower / Bonsai Seed
```

Comentario humano:
ESCRIBE_AQUI:


## H2. Buttons

```yaml
BUTTONS:
  intro:
    - APLICAR A TRAINEE
    - LEER BENEFICIOS
    - OMITIR INTRO
  application:
    - GUARDAR NOMBRE EN SOMERO
    - USAR SAIREN
    - USAR HUMAN_01
    - CONTINUAR A AVATAR
  stuff_box:
    - CERRAR LOCKER
    - REVISAR PERSONAL BELONGINGS
    - APP PERSONALIZATION FUTURO
  cubicle:
    - NOTEBOOK / SOMERO
    - LAPTOP
    - POS.AYA
    - LEVANTARSE
    - STUFF BOX
    - C6B REVIEW
```

Comentario humano:
ESCRIBE_AQUI:


## H3. Icons

```yaml
ICONS:
  Corporation: 🏢
  Loop: 🔁
  Human: 👤
  Stuff_Box: 📦
  Personal_Belongings: 🎒
  Notebook_Somero: 📓
  Laptop: 💻
  Supervisor: 👁️
  Chief_Office: 🪑
  PR_Worm: 🪱
  Pos_Aya: ◉
  Energy: ⚡
  Recovery: 🌱
  Achievement: ★
  Badge: ◆
  Warning: ⚠
  Locked_App: 🔒
```

Comentario humano:
ESCRIBE_AQUI:


---

# I. Revisión micro: achievements y badges

## I1. Achievements

```yaml
ACHIEVEMENTS:
  First_Application: apply_pressed
  Identity_Seed: name_and_avatar_saved
  Stuff_Box_Ready: locker_closed_after_item_storage
  First_Log: notebook_opened
  First_Order: supervisor_email_read
  Corporate_Welcome: boss_message_read
  Cubicle_Awareness: stand_up_and_return
  Gizmo_Handshake: pos_aya_hint_opened
```

Comentario humano:
ESCRIBE_AQUI:


## I2. Badges

```yaml
BADGES:
  Early_Identity_Badge: inspect_avatar_before_continue
  Personal_Meaning_Badge: all_core_items_selected
  Before_Asked_Badge: open_notebook_or_laptop_before_prompt
  Efficient_Orientation_Badge: all_orientation_steps_under_target_time
```

Comentario humano:
ESCRIBE_AQUI:


---

# J. Revisión de prioridad

## J1. P0 blockers

Algo que impediría construir o jugar C6B.

ESCRIBE_AQUI:


## J2. P1 major

Algo que rompería historia, coherencia o dirección.

ESCRIBE_AQUI:


## J3. P2 minor

Algo que debe mejorar claridad o UIX.

ESCRIBE_AQUI:


## J4. P3 polish

Preferencias de wording, tono, nombres, iconos o estilo.

ESCRIBE_AQUI:


---

# K. Decisión final del humano

Llena esto solo si ya quieres cerrar esta ronda.

```yaml
FINAL_HUMAN_DECISION:
  integrate_my_comments_into_same_superdocument: YES | NO
  generate_revised_superdocument: YES | NO
  approve_for_C6B_build_after_revision: YES | NO
  need_more_macro_dialogue_before_build: YES | NO
```

Comentario final:
ESCRIBE_AQUI:

