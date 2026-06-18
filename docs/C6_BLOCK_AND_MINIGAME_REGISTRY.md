# C6 Block and Minigame Registry

Status: design registry for C6 standalone candidate.

## Block model goals

Blocks are printed by an in-world 3D printer. They are not arbitrary debug objects. Each block should create a clear gameplay affordance.

## Core block types

1. scaffold_block
   - purpose: temporary climb, bridge, or support
   - views: 3D-like, horizontal 2D, vertical 2D
   - actions: place, rotate, stack, remove

2. conveyor_xy_block
   - purpose: moves boxes along x direction
   - actions: activate, reverse, stop

3. conveyor_yx_block
   - purpose: moves boxes along y direction
   - actions: activate, reverse, stop

4. elevator_up_block
   - purpose: moves boxes from low z to high z
   - actions: call, load, lift

5. elevator_down_block
   - purpose: moves boxes from high z to low z
   - actions: call, load, lower

6. piston_block
   - purpose: pushes boxes along one of six axes
   - actions: select axis, push, reset

7. angle_guide_block
   - purpose: redirects boxes without manual carrying
   - actions: rotate, lock, unlock

8. slide_block
   - purpose: moves boxes by calculated slide path
   - actions: place, rotate, test route

9. trampoline_block
   - purpose: gives boxes or player a calculated jump arc
   - actions: charge, bounce, tune strength

10. receiving_net_block
   - purpose: catches falling or scattered boxes
   - actions: deploy, collect, release

## Stack and carry rules

- Player can carry up to two boxes after ability unlock.
- Stack maximum is two boxes in early C6.
- Stacked boxes should act as a single carried stack until released.
- Stack must not pass through walls, blocks, or portal surfaces.

## Minigame templates

1. jam_clear_runner
   - context: boxes stuck in a shipping lane
   - view: side or horizontal runner representation
   - objective: collect repair blocks and clear jam
   - reward: jammed boxes auto-align and ship

2. vertical_lift_route
   - context: boxes need to move from bottom to top
   - view: vertical 2D side view
   - objective: place elevator, scaffold, or trampoline block
   - reward: unlock vertical transport affordance

3. horizontal_distribution_route
   - context: boxes need sorting to the right lane
   - view: horizontal 2D labyrinth
   - objective: place conveyors and angle guides
   - reward: unlock assisted routing

4. office_printer_request
   - context: player uses desktop computer
   - view: office or tender-style room view
   - objective: choose and print correct block
   - reward: block appears in printer area after 3 seconds

5. portal_surface_calibration
   - context: portal surfaces are dedicated and visible
   - view: player-eye 3D-like plus map
   - objective: connect surface A to B and route box
   - reward: unlock surface transport skill

## Mathematical physics rule

Use calculated effects instead of full simulation where possible:

- conveyors use fixed step movement
- slides use parametric path curves
- trampolines use precomputed arc tables
- elevators use state machines
- pistons use axis-aligned push impulses
- portals use transform from source surface to target surface

## Action menu by target

- floor: inspect, place block, mark route
- wall: inspect, attach portal surface, place guide
- ceiling: inspect, attach vertical route, place lift target
- box: grab, stack, send, inspect
- block: activate, rotate, remove, configure
- portal surface: activate, inspect destination, disable
- printer: select block, print, cancel
- jam area: inspect, enter minigame, clear
