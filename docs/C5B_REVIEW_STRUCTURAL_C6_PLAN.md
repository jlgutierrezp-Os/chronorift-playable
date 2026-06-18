# C5B Review and Structural C6 Plan

Status: review/design-only. No core runtime mutation.

## Findings
- Remote C5 play URL could not be opened by the agent browser in this environment because browser navigation is blocked.
- C5 source inspection shows a pseudo-3D/top-down room, walls, pads A/B, goal ENVIO, grab, jump, pad portal, send button, and view cycle.
- The requested lost view is not the top-down pseudo-3D view; it is a player-eye 3D-like view with walls/ceiling, where boxes and portals must also be visible.
- Survey must appear only after completing play, requesting evaluation, or reporting an error.

## Allowed
- Standalone candidate files.
- Review files.
- GitHub issues.
- Non-core test harnesses.
- Human review before app.js/core replacement.

## Not Allowed
- Core/runtime replacement without human review.
- Claiming playable confirmation without human test.
- Auto-sending messages from GitHub Pages to ChatGPT.
- Paid APIs, external credentials, camera login, or QR runtime.
- Placeholder-only build.

## C6 structural target
- Separate modules: state, input, physics, portal surface registry, renderers, survey/debug.
- Renderers: top-down 2D horizontal labyrinth, side 2D vertical Mario-like view, player-eye 3D-like raycast/corridor view.
- Dedicated portal surfaces only; portals visible in every view.
- Boxes and blocks must collide with walls, player and each other. No object should pass through walls or blocks.
- Survey opens after stage complete, Evaluate, or Report.

## Required tests
- controls_movement_boundaries
- collision_player_box_wall
- box_block_no_clip
- portal_surface_only
- portal_box_transport_state_preserved
- view_cycle_visibility
- player_eye_3d_boxes_portals_visible
- side_vertical_mario_like_view
- stage_completion_survey_trigger
- report_generation_plain_text

## Next recommendation
Create a C6 candidate as a standalone structural build for human review, not a patch over C5.
