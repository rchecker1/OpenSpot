# OpenSpot

**OpenSpot** is a public-alpha, modular payload platform for Boston Dynamics Spot. It brings together field-swappable sensor mounts, onboard compute, power and networking integration, and a forthcoming handheld operator system for field robotics research.

OpenSpot is intended to reduce the repeated mechanical, electrical, and deployment work required before a research team can begin collecting data or testing autonomy on Spot. The current release documents a field-tested prototype; it is not a finished product or a safety-certified system.

![OpenSpot payload system](media/payloads.png)

## System at a glance

| Layer | Reference implementation | Status |
| --- | --- | --- |
| Mechanical | Modular mounts for compute, LiDAR, radio, auxiliary electronics, and hot-swappable sensors | **Available — alpha CAD** |
| Compute and sensing | NVIDIA Jetson Orin, Ouster OS0, IMU/GNSS, and optional camera payloads | **Reference configuration documented** |
| Networking | 2.5 GbE payload network and point-to-point Ubiquiti wireless bridge | **Architecture documented; validation pending** |
| Power and electronics | Spot GXP power distribution, conversion, switching, and passive PoE | **Partially documented** |
| OpenSpot Operator | Steam Deck GUI and Jetson control daemon | **Coming soon — experimental repository** |
| Reproducible release | BOM, wiring package, editable source CAD, assembly guide, calibration, and field test data | **Planned** |

## Repository layout

```text
OpenSpot/
├── hardware/              Mechanical payload designs and inventory
├── docs/                  Architecture, networking, status, and roadmap
├── media/                 Project figures and field media
├── CONTRIBUTING.md        Contribution and validation expectations
└── LICENSES/              Component-specific licenses
```

Start with the [hardware inventory](hardware/README.md), [network architecture](docs/networking.md), and [release status and roadmap](docs/roadmap.md).

## Reference configuration

The current prototype combines:

- Boston Dynamics Spot with a GXP power and network interface;
- an NVIDIA Jetson Orin compute module;
- an Ouster OS0 LiDAR and optional hot-swappable sensor plate;
- a 2.5 GbE payload switch;
- a pair of Ubiquiti Bullet radios configured as a field wireless bridge; and
- an operator-side access point and portable power source.

This is a reference configuration, not a procurement specification. Exact component revisions, cable assemblies, power protection, environmental limits, and substitutions will be frozen with the first reproducible hardware release.

## Current limitations

- Published mechanical files are STEP exports; preferred native CAD source and manufacturing drawings are not yet available.
- The electrical schematic, connector schedule, complete BOM, power budget, and thermal characterization are incomplete.
- Network range, latency, jitter, and packet-loss claims have not yet been released as repeatable tests.
- The payload has not been independently reproduced by another team.
- OpenSpot Operator is experimental and is not represented as a certified emergency-stop or safety controller.

Do not fabricate or operate this system without reviewing Boston Dynamics' payload requirements and performing an independent mechanical, electrical, and operational safety assessment.

## Roadmap

The project is moving through four release gates: documented alpha hardware, reproducible hardware, reproducible software bring-up, and measured field validation. See [docs/roadmap.md](docs/roadmap.md) for the acceptance criteria for each gate.

## Contributing

Issues, corrections, reproduction reports, and new payload adapters are welcome. Please read [CONTRIBUTING.md](CONTRIBUTING.md) before submitting changes. In particular, clearly separate verified behavior from proposed or untested behavior.

## Citation

Until a project paper is available, cite the repository:

```bibtex
@misc{openspot2026,
  author       = {Yash Turkar and Yashom Dighe and Christo Aluckal and Travis Minor},
  title        = {OpenSpot},
  year         = {2026},
  howpublished = {\url{https://github.com/droneslab/OpenSpot}},
  note         = {Public alpha}
}
```

## Licensing and attribution

Licensing is scoped by artifact; see [LICENSES/README.md](LICENSES/README.md). New hardware design releases are provided under CERN-OHL-W-2.0, and original project documentation is provided under CC BY 4.0. Earlier repository revisions were published under GPLv3 and remain available under the terms that applied to them.

OpenSpot is an independent research project of the University at Buffalo Drones Lab. It is not affiliated with, endorsed by, or sponsored by Boston Dynamics. Boston Dynamics and Spot are trademarks of their respective owner. Third-party products, logos, photographs, and trademarks are excluded from OpenSpot's documentation license unless explicitly stated otherwise.
