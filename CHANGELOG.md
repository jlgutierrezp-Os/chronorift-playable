# Changelog

## v1.4.1

- Increased goal-fit tolerance so the white block does not need a perfect center fit.
- Added snap-to-goal behavior when the block reaches the green threshold.
- Added block lock on puzzle solve: the block stops moving and stops rotating.
- Updated success message to `PUZZLE RESUELTO · caja encajada en umbral verde`.
- Refined the goal from simple green square to softer `umbral` visual language.
- Slightly darkened and calmed the brutalist-zen palette.
- Still no workflows, dependencies, secrets, npm, or cross-repo access.

## v1.4

- Stage 1 clarity pass: the white block must be moved into the green goal square to solve the puzzle.
- Added explicit success condition and message: `PUZZLE RESUELTO · caja en umbral verde`.
- Player touching the green square no longer counts as solving the stage; block-to-goal is the stage condition.
- Added clearer green goal treatment with pulse, label, and architectural frame.
- Added a first brutalist-zen aesthetic pass: darker concrete palette, calmer surfaces, white-light boundary, less toy-like flat color.
- Added stage label overlay: `STAGE 1 · caja → umbral verde`.
- SelfDebug now frames Stage 1 review around goal clarity, boundary leaks, block transport, HUD intrusion, and aesthetics.
- Secret-area semantics documented in help text but not activated as accidental boundary escape.
- Still no workflows, dependencies, secrets, npm, or cross-repo access.

## v1.3

- Added hard outer-boundary clamp for player, block, echoes, and portal exits.
- Added sub-step movement to reduce high-speed tunneling through walls.
- Added safe portal exit search for spatial and temporal rifts.
- Added block velocity cap to reduce boundary escape risk.
- Added visible outer boundary stroke.
- SelfDebug now classifies boundary crossing as `collision_error` and recommends staying on boundary fix until confirmed.
- Still no workflows, dependencies, secrets, npm, or cross-repo access.

## v1.2

- Added gravitational push assist for the white block.
- Near-contact block movement now responds with progressive acceleration.
- Field button now creates a soft transport/tether behavior.
- Added gentle goal assist when the block is near the green square and the player is nearby.
- Added visible assist halo and tether when block assist is active.
- SelfDebug now includes a broader header for movement feel, block transport, target behavior, and gravitational push feedback.
- Still no workflows, dependencies, secrets, npm, or cross-repo access.

## v1.1

- Promoted Batch 0 as human-runnable based on iPhone feedback.
- Reduced excessive movement with velocity smoothing and lower baseline speed.
- Added surface-material friction fields: slick and grip tiles.
- Block friction now depends on the surface material.
- Rift A/B placement stores direction and draws exit arrows.
- Rift A/B overlap is reduced with separation logic.
- Added first temporal-rift prototype: Lens + Time creates a temporal portal to the touched trace point.
- SelfDebug packets now include SelfFix suggestions and next-batch hints.
- Still no workflows, dependencies, secrets, npm, or cross-repo access.

## v1.0

- Public no-cost GitHub Pages runtime prepared.
- Static ChronoRift HTML/CSS/JS build added.
- SelfDebug panel included with close/return flow.
- Report packet generation included.
- No workflows, dependencies, secrets, or cross-repo access.
