# C6 Issue Packet

Title: C6 structural candidate: recover player-eye 3D-like view, collision, portal surfaces, and stage-end survey

## Summary

C5 should not be patched incrementally. The next build should be a standalone C6 structural candidate for human review.

## Human feedback distilled

- The valued 3D-like player-eye view has been lost.
- Current ROOM3D behaves more like top-down or pseudo-isometric view.
- Desired player-eye view should show walls, ceiling, boxes, and portals.
- Portals should exist only on visible dedicated surfaces.
- Need horizontal 2D labyrinth and vertical 2D Mario-like side view.
- Player, boxes, blocks, and walls should not pass through each other.
- Survey should appear after game completion, evaluation, or report.

## Evidence files

- docs/C5B_REVIEW_STRUCTURAL_C6_PLAN.md
- docs/C6_TEST_MATRIX.md
- docs/C6_BOUNDARY_REGISTRY.md
- docs/C6_AGENT_PLAY_REVIEW.md

## Recommended acceptance

- C6 candidate is standalone.
- No core replacement before human approval.
- C6 has separated modules for input, physics, portal surfaces, views, and survey/debug.
- C6 passes the C6 test matrix.
