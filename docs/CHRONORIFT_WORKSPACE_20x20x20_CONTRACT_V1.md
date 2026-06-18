# CHRONORIFT_WORKSPACE_20x20x20_CONTRACT_V1

Status: design contract. No runtime replacement.

## Purpose

Define the long-term main work area as a modular 20 x 20 x 20 construction workspace for boxes, blocks, portals, and logistics systems.

## Spatial model

Each stage-level workspace is a cube-like structure:

```yaml
workspace:
  size:
    x: 20
    y: 20
    z: 20
  cell:
    box_capacity: 4
    portal_capacity: 1
```

## Cell capacity

Each cell can contain:

- up to 4 boxes
- one portal surface or portal endpoint
- one construction block or defined block-state, depending on gameplay rule

## Portal capacity

Portals can transport up to 4 x 4 boxes through a designed surface route.

Early C6 may implement this as a simplified symbolic capacity while keeping the contract stable.

## Build surfaces

The player can build on:

- floor
- walls
- ceiling

Each build surface should expose different allowed actions.

## Core object classes

- player
- box
- stacked_box_pair
- block
- portal_surface
- lane
- jam_area
- printer_output
- goal_area

## No-clip rules

Objects must not pass through:

- walls
- blocks
- boxes
- portal surfaces unless portal transport is active and valid
- locked goal boundaries

## Main uses

- shipping systems
- classification systems
- distribution systems
- repair systems
- portal routing
- vertical lift routing
- horizontal conveyor routing
- puzzle solutions
- stage progression

## View requirements

The same workspace state must be representable through separate renderers:

- player_eye_3d_like
- horizontal_2d_labyrinth
- vertical_2d_side_view
- map
- gizmo
- tender_style_room_view when returning to office/cubicle context

## Action menu by target

- floor: inspect, place block, mark route
- wall: inspect, attach portal surface, place guide
- ceiling: inspect, attach vertical route, place lift target
- box: grab, stack, send, inspect
- stack: carry, split, send, inspect
- block: activate, rotate, remove, configure
- portal surface: activate, inspect destination, disable
- jam area: inspect, enter minigame, clear

## Stage integration

The workspace should support embedded mini-games:

- jam clear runner
- vertical lift route
- horizontal distribution route
- portal surface calibration
- shipping repair challenge

## First-pass C6 subset

C6 does not need to implement all 20 x 20 x 20 complexity. It must preserve the contract while implementing a playable subset:

- player visible
- player moves
- one or more boxes visible
- one box grabbable
- no-clip collision
- one dedicated portal surface pair
- one goal or shipping area
- survey after completion/report/evaluate

## Not in scope

- Full multiplayer warehouse.
- Heavy physics simulation.
- Public user generated repo changes.
- Core app.js replacement without review.
