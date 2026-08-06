# Hardware inventory

The files in this directory capture the current OpenSpot mechanical prototype. They are **alpha artifacts**, not a complete fabrication package. All published models are STEP exports; preferred native CAD sources, dimensioned drawings, tolerances, fastener schedules, print parameters, and assembly procedures remain planned.

## Published designs

| Path | Intended use | Maturity |
| --- | --- | --- |
| `aux_mount/power-network-aux-box-v6.step` | Enclosure/mount for auxiliary power and network hardware | Alpha reference |
| `compute_lidar/compute-lidar-mount-v5.step` | Combined Jetson and LiDAR payload structure | Alpha reference |
| `hot_swap/hot-swap-mount.step` | Base interface for field-swappable sensor payloads | Alpha reference |
| `hot_swap/head-plate-swap-acc-plate-v2.step` | General accessory plate | Alpha reference |
| `hot_swap/head-plate-swap-acc-zed2i-v3.step` | ZED 2i accessory plate | Alpha reference |
| `radio_mount/radio-base-plate-v4.step` | Radio payload base | Alpha reference |
| `radio_mount/radio-bullet-ac-mount-v5.step` | Ubiquiti Bullet mounting structure | Alpha reference |
| `radio_mount/temp.step` | Unclassified working model retained for design-history review | **Experimental; do not fabricate** |

## Before fabrication

1. Confirm the design revision, material, process, fasteners, payload mass, center of mass, and clearance envelope.
2. Review the current Boston Dynamics payload mechanical and electrical requirements.
3. Independently validate structural strength, retention, cable strain relief, thermal behavior, and collision clearance.
4. Treat any file without a released drawing and assembly procedure as experimental.

## Planned reproducibility package

- Native editable CAD and neutral STEP/STL exports.
- Dimensioned drawings and a fastener/insert schedule.
- Manufacturing and print settings with material specifications.
- Assembly photographs and torque guidance.
- Mass and center-of-mass table for each supported configuration.
- Electrical schematic, harness drawings, connector pinouts, fused power budget, and thermal results.
- Calibration transforms and repeatability measurements for each hot-swap plate.

Hardware files released from the public-alpha licensing update onward are licensed under CERN-OHL-W-2.0; see [`../LICENSES/`](../LICENSES/README.md).
