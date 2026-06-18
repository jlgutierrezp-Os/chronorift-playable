# ChronoRift Star Recovery and Block Model Review

Status: full review seed for secure semiautomated development.

## Purpose

Recover every recognized achievement and star direction before creating the next playable candidate.

## Recognized achievements to preserve

- RPG dialogue and sequential storytelling after achievements.
- Interactive RPG-like environmental solutions.
- Coins counter.
- Objective completion and stage progression.
- Player position was visible in earlier builds.
- A 3D-like map/render view existed and should be recovered.
- Areas were described and understandable.
- Assistance systems improved control and playability.
- Physics-like behavior can be represented through calculated mathematical effects instead of heavy simulation.

## Current failures

- Current version has no visible player/avatar.
- Current version has no visible gizmo.
- Current version mostly shows map-like vertical and horizontal representations.
- Vertical and horizontal loop views are present but not yet used as gameplay.
- Boxes are absent or not usable.
- C5 failed: no movement, no visible player, no grab, no usable boxes, no useful views.
- C6 sandbox/local external-file failed because buttons did not function on the user device.

## View recovery priority

1. Restore player-eye 3D-like view first.
2. Keep top-down 2D horizontal labyrinth as a functional planning view.
3. Keep side 2D vertical view for bottom-to-top logistics.
4. Keep map/gizmo views only if they support gameplay and do not distract.
5. Do not replace working view logic with placeholders.

## Mathematical effect model

ChronoRift should not depend on expensive or complex physics simulation for the next playable stage. Use deterministic calculated effects:

- position updates by grid/cell or axis vectors
- gravity as fixed step per tick in side view
- conveyors as fixed displacement per tick
- elevators as bounded vertical interpolation
- pistons as one-step impulse along selected axis
- trampolines as calculated arc impulse
- slides as guided vector displacement
- nets as capture zones that absorb falling boxes
- portal surfaces as deterministic remap from source zone to destination zone

## Carry and stack rules

- Player can carry one box by default.
- Unlock allows carrying up to two boxes.
- Boxes can stack up to height 2.
- Stack height above 2 is blocked.
- Stacks should be stable enough for jumping or transport.
- No object may pass through walls, boxes, or blocks.

## Block model catalog

### Scaffold block

Purpose: create temporary platform or step.

Modes:
- horizontal 2D: bridge over short gap
- vertical 2D: step ladder or landing
- player-eye 3D-like: visible low platform
- tender/RPG office: modular work scaffold

### Conveyor XY block

Purpose: move box along X axis.

Effect: box displacement vector positive or negative X based on orientation.

### Conveyor YX block

Purpose: move box along Y axis.

Effect: box displacement vector positive or negative Y based on orientation.

### Elevator up/down block

Purpose: move box or player between vertical layers.

Effect: deterministic interpolation from lower zone to upper zone.

### Piston block

Purpose: push box out of the surface it is on.

Effect: single-axis impulse in one of six directions.

### Angle guide block

Purpose: redirect moving boxes.

Effect: transforms incoming vector into a diagonal or orthogonal output vector.

### Slide block

Purpose: guide a box downward without random scatter.

Effect: controlled descent vector.

### Trampoline block

Purpose: bounce player or box upward.

Effect: calculated parabolic arc impulse.

### Receiving net block

Purpose: catch falling boxes.

Effect: capture zone that sets velocity to zero and snaps box into safe cell.

### Portal pad block

Purpose: create visible dedicated surface for portal transport.

Effect: source/destination remap while preserving identity and state.

## Mini-game models

### Horizontal 2D logistics

Core challenge: move boxes across maze lanes using conveyors, scaffold and portal pads.

### Vertical 2D Mario-like logistics

Core challenge: move boxes bottom-to-top using elevators, trampolines, slides and nets.

### Player-eye 3D-like office/labyrinth

Core challenge: navigate corridor walls and visible ceiling while using boxes and portal surfaces.

### Tender/RPG office mode

Core challenge: interact with desk, terminal, printer, locker, dialogue, and stage goals.

## Next build recommendation

Create a stable C6 candidate only after delivery pipeline passes. Start with:

1. player visible
2. controls responsive
3. player-eye 3D-like view recovered
4. one box visible and grabbable
5. no-clip collision
6. 3D printer creates one scaffold block
7. survey appears after Evaluate or Report

Do not add full block catalog until the first six items pass.
