# C6 Test Matrix

Status: design only until human review.

## Tests

1. controls_movement_boundaries
   - movement responsive
   - walls block passage
   - no stuck state after collision

2. collision_player_box_wall
   - player cannot pass through boxes
   - boxes cannot pass through walls
   - blocks remain interactable

3. portal_surface_only
   - portals activate only on dedicated visible surfaces
   - non-surface activation is denied
   - surface id is visible

4. portal_box_transport_state_preserved
   - box identity is preserved
   - box state is preserved
   - destination placement does not clip

5. view_cycle_visibility
   - grab persists across views
   - box remains visible
   - portal surfaces remain visible
   - goal remains visible or indicated

6. player_eye_3d_boxes_portals_visible
   - walls visible
   - ceiling visible
   - boxes visible
   - portal surfaces visible

7. side_vertical_mario_like_view
   - vertical route visible
   - player and box visible
   - portal surface visible
   - bottom-to-top reading clear

8. stage_completion_survey_trigger
   - survey hidden at start
   - survey opens after completion
   - survey opens after evaluate
   - survey opens after report

