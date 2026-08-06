# Release status and roadmap

OpenSpot separates artifacts that are present from claims that have been validated. The current repository is a **public alpha**.

## Current status

| Area | Available now | Required for the next release |
| --- | --- | --- |
| Mechanical | STEP models for compute/LiDAR, auxiliary electronics, radio, and hot-swap plates | Native source CAD, drawings, tolerances, materials, and assembly instructions |
| Electrical | Network/power topology diagram and reference component classes | Schematics, pinouts, harness files, protection strategy, BOM, and measured power/thermal budgets |
| Networking | Reference IP plan and wireless bridge architecture | Reproducible radio configuration and range/throughput/latency/jitter/packet-loss tests |
| Software | Experimental OpenSpot Operator repository | Versioned installation, cross-language protocol tests, packaged Deck build, and hardware smoke tests |
| Validation | Internal prototype and field demonstration media | Published test protocols, raw logs, failure cases, and an independent reproduction |

## Release gates

### Gate 1 — documented alpha

- Inventory every released artifact and mark its maturity.
- Publish project scope, limitations, contribution rules, and scoped licenses.
- Provide an honest system diagram and reference configuration.

### Gate 2 — reproducible hardware

- Release native CAD, fabrication exports, drawings, BOM, schematics, harness documentation, and assembly instructions.
- Record mass, center of mass, power, thermal, and hot-swap repeatability measurements.
- Complete one clean rebuild from released documentation.

### Gate 3 — reproducible software bring-up

- Pin a supported operating-system, ROS 2, Spot SDK, Godot, and Jetson software matrix.
- Provide one-command daemon setup and a versioned Steam Deck build.
- Validate message-protocol compatibility, disconnected/demo operation, diagnostics, logging, and failure-state presentation.
- Resolve and test safe lease handoff before describing Operator as field-ready.

### Gate 4 — measured field validation

- Publish network and end-to-end control measurements with repeatable procedures.
- Run mapping, data-collection, and supervised autonomy scenarios in representative environments.
- Release logs, negative results, recovery procedures, and an independent reproduction report.

No dates are attached to these gates until maintainers have assigned owners and resources. Issues and pull requests should reference the gate they advance.
