# C6 Full Review Recovery Blueprint

Status: review and planning. No core runtime replacement.

## Human request

Run secure semiautomated development for ChronoRift through /agent-luu and /agent-apply. Recover every recognized function and star-rewarded direction before building the next candidate.

## Current failure state

The current C5/C6 direction failed human playability. Current visible state has map-like views only, no usable player/avatar, no visible gizmo, no usable boxes, and no working interaction loop.

## Recognized functions to recover

- RPG-style interactive storytelling.
- Sequential dialogue boxes after achievements.
- Coin counter and objective counter.
- Clear areas and zones.
- Goal completion and stage progression.
- Player position visualization.
- 3D-like map/world representation.
- A prior player-eye 3D-like view with walls and ceiling.
- Mathematical 3D-like rendering derived from formulas.
- Assistive indicators that improve playability and control.
- Better controlability aids.
- Stuff Box, office, desk, door, and stage-start flow.
- Portal/rift identity as original ChronoRift mechanic.

## Missing or failed functions

- Player/avatar visibility.
- Usable movement.
- Usable controls.
- Visible and grabbable boxes.
- Stack up to two boxes.
- Carry up to two boxes.
- Visible gizmo.
- Real action menus by area, surface, object, and block.
- Portal surfaces dedicated to transport.
- Horizontal and vertical mini-games used as gameplay, not placeholder views.

## View recovery plan

C6 should separate views as renderers instead of treating them as one patched camera.

Required renderers:

1. player_eye_3d_like
   - from player eyes
   - walls visible
   - ceiling visible
   - boxes visible
   - portal surfaces visible
   - interaction prompts visible

2. horizontal_2d_labyrinth
   - top-down or map-like horizontal logistics route
   - visible lanes and surfaces
   - clear box routes

3. vertical_2d_side_view
   - side view similar to Mario-style bottom-to-top movement
   - vertical routes and falling boxes readable

4. tender_style_room_view
   - office/cubicle/cafeteria/storytelling room view
   - interaction nodes and RPG dialogue

5. gizmo_view
   - Pos.Aya state, hints, route diagnostics, and action menu context

## Physics approach

Do not prioritize heavy simulation. Use deterministic mathematical physics effects:

- scripted acceleration curves
- snap zones
- discrete object states
- fixed collision checks
- finite-state box movement
- calculated arcs and slides
- portal transforms between named surfaces
- stack state machine up to two boxes

The goal is agile predictable gameplay, not full physical realism.

## Interaction model

Areas, surfaces, objects, boxes, and blocks should open context menus.

Menu context sources:

- floor
- wall
- ceiling
- portal surface
- printer desk
- box
- stack
- block
- jammed area
- shipping lane
- service area

Each menu should expose only relevant actions.

## Required C6 first-pass loop

1. Start in office/desk area.
2. Player visible and movable.
3. Player opens 3D printer computer.
4. Player selects one block type.
5. Print sequence runs for three seconds.
6. Block appears near printer.
7. Player grabs box or block.
8. Player uses view switching without losing state.
9. Player uses dedicated portal surface.
10. Player sends at least one box.
11. Survey opens after completion/evaluate/report.

## Safety and governance

C6 is a standalone candidate. It must not replace app.js without explicit human review and approval.
