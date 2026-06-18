# C5B Human Feedback Report - 2026-06-18

## Build

C5_labyrinth_portal_transport_skill

## Result

The human tester could not play.

## Scores

- controls: 1/5
- fun: 1/5
- visual: 1/5
- boxes: 1/5
- portals: 1/5
- global: 1/5

## Access

- link_opened: Parcial
- start_clear: Parcial
- game_started: Si

## Controls and boxes

- walk: No
- controls: No
- grab: No
- visible: No
- viewgrab: No

## Portal and goal

- portal_rule: No
- pad_works: No
- box_state: No
- send: No
- skill: No

## Views

- room3d: No
- map: No
- gizmo: No
- side: No
- fp: No

## Positive observation

There are described areas.

## Main blocker

The player could not move. The player was not visible. Controls did not respond. Only view change responded partially.

## Expected experience

The user expected an office/workstation flow where the player uses a desktop computer to request 3D printed blocks. After selecting a block from a list and pressing print, a short 3 second printing sequence should occur. Then the block appears in a 3D printing area near the desk so the player can pick it up.

Expected block types:

- scaffold block
- xy conveyor block
- yx conveyor block
- elevator cube for minus-z plus-z and plus-z minus-z movement
- piston cube pushing boxes in one of six axes
- angle cube to guide boxes
- slide cube
- trampoline cube
- receiving net cube to prevent boxes from scattering when falling

## Observed

The user could not play.

## Next decision

Return to a stable version and create a C6 structural standalone candidate for human review. Do not patch C5 incrementally.

## Required C6 focus

- Restore player-eye 3D-like view.
- Restore visible player and responsive controls.
- Boxes must be visible, movable, stackable, and usable as jump/transport elements.
- Dedicated portal surfaces must be visible.
- Collision must prevent passing through walls, boxes, and blocks.
- Include office workstation, 3D block printer, and block selection flow.
- Keep survey after completion, evaluation, or report.
