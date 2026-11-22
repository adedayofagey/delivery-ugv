# Dvx_UGV_v2.0 — Final Demo Release (3D Printing + URDF/Simulation Meshes)

`v2.0` is the print-ready, merged variant of `v1.0`, following the exact repository layout. Every file is **GitHub-safe (`< 35 MB`)**, oriented **`+X` front, `+Y` left, `+Z` up** (`Z = 0` at wheel/caster ground contact), with **zero overlapping parts** and **1-to-1 sync** between the assembly, printable parts, and URDF meshes.

---

## Folder Structure

| Folder / File | Who Uses It | Units & Orientation |
|---|---|---|
| `step/Dvx_UGV_v2.0.step` (`33.7 MB`) | Everyone (Fusion 360 / CAD) | **mm**, `+Z` up, `+X` front, colored assembly with original black/blue kit wheels |
| `step/printable_parts/` (`14` colored `.step` files) | Facilitator / CAD edits | **mm**, exact same colors & names as `Dvx_UGV_v2.0.step` |
| `stl/printable_parts/` (`14` `.stl` files) | **Facilitator (3D Printing)** | **mm**, rotated flat on `Z = 0` print bed, ready to slice |
| `urdf_meshes/collision/` (`11` `.stl` files) | **ROS / Gazebo Team (Collision)** | **metres (m)**, `+X` front, `+Y` left, `+Z` up, `Z = 0` ground |
| `urdf_meshes/visual/` (`11` `.dae` files) | **ROS / Gazebo Team (Visual)** | **metres (m)**, colored Collada (`Z_UP`), ready for RViz/Gazebo |

---

## Printable Parts List (`14` Unique Files — Everything Printable Together Is Merged!)

| # | Part File (`step/printable_parts/` & `stl/printable_parts/`) | Qty to Print | PETG Color | Integrated Features Included |
|---|---|---|---|---|
| 1 | `tub_front` | 1 | **Black** | Integrated front support posts, 3S2P battery cradle, L298N bracket & 5V buck bracket |
| 2 | `tub_rear` | 1 | **Black** | Integrated rear support posts, Arduino/breadboard cradle, Raspberry Pi 4B bracket & IMU bay |
| 3 | `deck_plate_1` | 1 | **White** | Integrated front cargo dock locating peg |
| 4 | `deck_plate_2` | 1 | **White** | Ribbed center deck section |
| 5 | `deck_plate_3` | 1 | **White** | Integrated rear cargo dock locating peg |
| 6 | `deck_splice_strap` | **2** | **White** | Bridges front & rear deck plate seams underneath |
| 7 | `cargo_bay_front` | 1 | **Royal Blue** | Integrated 4× door snap-fit latches *(rotate `15°–45°` on a `200×200` bed)* |
| 8 | `cargo_bay_rear` | 1 | **Royal Blue** | Rear cargo bay shell |
| 9–12 | `door_lower_left/right`, `door_upper_left/right` | 1 each | **Royal Blue** | Integrated printed hinge pins on every door |
| 13 | `lidar_mount` | 1 | **Royal Blue** | Hollow tapered box-section column with `Ø15 mm` cable conduit |
| 14 | `printed_quarter_turn_cam_lock` | **4** | **White** | Tool-free hand-operated cargo dock corner locks |

- **Minimal Hardware Needed:** One small pack of `M3` screws (`24× M3×10`, `8× M3×8`) + `20× M3` hex nuts, `4× M2.5×8` screws (for RPLIDAR), and `2–4` zip ties for the battery.

---

## Notes for the ROS / URDF Team (`urdf_meshes/`)
- **Units:** **Metres (`1.0 m`)**, ROS REP-103 frame (`+X` forward, `+Y` left, `+Z` up, ground at `Z = 0.000 m`).
- **Included Links (`urdf_meshes/collision/*.stl` & `urdf_meshes/visual/*.dae`):**
  - `mobile_base`, `cargo_bay`, `door_lower_left`, `door_lower_right`, `door_upper_left`, `door_upper_right`, `wheel_left`, `wheel_right`, `castor_wheel`, `lidar`, plus `Dvx_UGV_v2.0_full`.
- **Key Kinematic Dimensions (in metres):**
  - Wheel diameter: `0.065 m` (`radius = 0.0325 m`), Wheel separation: `0.2364 m` (`Y = ±0.1182 m`)
  - Front drive axle: `X = +0.1100 m, Z = +0.0325 m`
  - Rear ball caster contact: `X = -0.1500 m, Y = 0.0000 m, Z = 0.0000 m`
  - LiDAR scan plane center: `X = +0.1450 m, Y = 0.0000 m, Z = +0.3482 m`
  - Door hinge axes (vertical `Z`): `X = +0.1170 m, Y = ±0.0948 m` (`0°` to `115°` outward swing)
