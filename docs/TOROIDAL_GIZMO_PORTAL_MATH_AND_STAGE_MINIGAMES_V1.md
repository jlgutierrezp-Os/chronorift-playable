# TOROIDAL_GIZMO_PORTAL_MATH_AND_STAGE_MINIGAMES_V1

## 0. Status

```yaml
status:
  public_repo_safe: true
  purpose: translate_human_torus_gizmo_portal_concept_into_original_runtime_math_and_stage_design
  runtime_change_now: false
  code_change_now: false
  source:
    - human_design_note
    - external_reference_reviewed_for_attribution_only
```

The external TeX StackExchange reference is useful for confirming the standard parametric representation of a torus and for the visibility/hidden-stretch problem. This spec does not copy its TikZ implementation. ChronoRift should use an original JavaScript/gameplay math model derived from standard torus geometry.

---

## 1. Design interpretation

```yaml
design_interpretation:
  room_as_cut_through_torus:
    - player_believes_they_are_in_room_sections
    - portals_are_connections_between_nearby_toroidal_points
    - walls_ceiling_floor_are_visible_sections_of_a_toroidal_space
    - entering_portal_can_show_player_entering_and_exiting_simultaneously
    - apparent_multiple_spaces_are_local_slices_of_one_wrapped_manifold

  gizmo_role:
    - toroidal_orientation_calculator
    - thumb_control_panel
    - chooses_surface_or_toroid_patch
    - orients_portals_between_u_v_points
    - helps_player_understand_hidden_external_dimensions
```

---

## 2. Original torus coordinate model for ChronoRift

Use two angular coordinates:

```yaml
torus_coordinates:
  u:
    meaning: major_angle_around_torus_center
    range: 0_to_tau
  v:
    meaning: minor_angle_around_tube_cross_section
    range: 0_to_tau
  R:
    meaning: major_radius
  r:
    meaning: tube_radius
```

Original runtime formula in JS-friendly form:

```text
x = (R + r * cos(v)) * cos(u)
y = (R + r * cos(v)) * sin(u)
z = r * sin(v)
```

Use this as geometry, not as copied TikZ code.

---

## 3. Surface mapping

```yaml
surface_mapping:
  floor_patch:
    v_range: near_bottom_visible_cross_section
    gameplay_view: top_or_room_view
    use:
      - conveyor_floor
      - scale
      - package_drop
      - simple_portal_floor

  wall_patch:
    u_or_v_band: side_slice_of_torus
    gameplay_view: lateral_or_wall_view
    use:
      - wall_to_wall_loop
      - vertical_construction
      - tube_entry_exit

  ceiling_patch:
    v_range: near_top_cross_section
    gameplay_view: vertical_loop_or_ceiling_view
    use:
      - gravity_tube
      - fall_to_jump_conversion
      - ceiling_portal
```

---

## 4. Portal connection model

```yaml
portal_connection:
  portal_A:
    coordinates: [uA, vA]
    surface: floor_wall_or_ceiling
  portal_B:
    coordinates: [uB, vB]
    surface: floor_wall_or_ceiling

  connection:
    - compute_world_position_A
    - compute_world_position_B
    - compute_local_basis_A
    - compute_local_basis_B
    - remap_velocity_from_A_basis_to_B_basis
    - preserve_or_intentionally_scale_speed
    - apply_safe_exit_offset

  visibility_effect:
    - while_entering_A_show_exit_B_simultaneously
    - if_A_and_B_are_close_on_torus_but_far_in_room_show_non_euclidean_shortcut
    - if_A_ceiling_to_B_floor_show_gravity_tube
```

---

## 5. Velocity and gravity remapping

```yaml
physics_model:
  base_gravity:
    value: 9.8
    direction: down_in_current_local_patch

  velocity_mapping:
    input:
      - velocity_vector
      - portal_A_basis
      - portal_B_basis
    output:
      - remapped_velocity_vector
      - exit_impulse
      - predicted_arc

  gravity_tube:
    condition:
      - portal_A_surface_is_ceiling_or_floor
      - portal_B_surface_is_opposite_vertical_patch
    behavior:
      - falling_velocity_stored
      - exit_velocity_becomes_jump_or_upward_impulse
      - gravity_vector_visibly_reorients
      - player_can_chain_loop
```

---

## 6. Control and view rules by minigame row

```yaml
stage_rows_and_minigames:
  floor_area_minigame:
    view_required: map_or_room_view
    controls:
      - normal_movement
      - grab_box
      - place_floor_portal
    modules:
      - scale
      - conveyor
      - package_drop
      - goal_bay

  wall_area_minigame:
    view_required: lateral_wall_view
    controls:
      - horizontal_loop_control
      - place_wall_portal
      - build_side_route
    modules:
      - wall_tube
      - lateral_runner
      - ping_pong_lever
      - piston

  vertical_ceiling_minigame:
    view_required: vertical_or_ceiling_view
    controls:
      - jump
      - jumper_legs
      - stack_boxes
      - gravity_tube
    modules:
      - scaffold_neutral_blocks
      - trampoline_blocks
      - ceiling_portal
      - slide_or_drop_chute

  cubicle_rest_stage:
    view_required: desk_view
    modules:
      - email_notification
      - firmware_update_notice
      - phone_vibration_notice
      - save_point_registry
      - physical_logic_desktop_minigames
```

---

## 7. Logistics package system

```yaml
package_system:
  package_types:
    normal_shipping:
      label: white_shipping_label
      target: shipping_exit
    inspection_warning:
      label: warning
      target: inspection_exit
    return_label:
      label: return
      target: return_exit
    error_shipping:
      consequence: coin_discount_for_wrong_destination

  unlock_loop:
    - receive_box
    - open_box
    - play_assembly_logic_minigame
    - unlock_new_block
    - build_transport_system
    - route_packages_to_correct_exit
    - earn_coins
    - receive_firmware_update_if_threshold_met
```

---

## 8. Required block families

```yaml
block_families:
  movement:
    - trampoline_block
    - jumper_legs_tool
    - speed_incrementer
    - scaffold_neutral_block

  transport:
    - conveyor_block
    - scale_block
    - piston_block
    - slide_block
    - tube_block
    - vacuum_tube
    - receiving_basket

  logic:
    - manual_ping_pong_lever
    - semiautomatic_ping_pong_lever
    - automatic_lever_by_achievement
    - label_sorter
    - inspection_warning_gate
    - return_gate

  gizmo:
    - toroidal_orientation_panel
    - surface_selector
    - portal_alignment_view
    - firmware_update_slot
```

---

## 9. Next implementation boundary

```yaml
next_runtime_boundary:
  do_next:
    - fix_FP_mobility
    - fix_vertical_mobility
    - add_jump_button
    - add_jumper_legs_placeholder
    - add_two_or_more_stackable_boxes
    - add_surface_area_gate_that_forces_correct_view
    - add_basic_package_visual_not_square_only

  do_not_yet:
    - full_torus_renderer
    - full_logistics_factory
    - full_conveyor_network
    - copied_TikZ_code
    - copyrighted_music_or_film_reference_assets
```
