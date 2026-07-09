# BattleStation Wiring Architecture

| Item | Value |
|------|-------|
| Document | Wiring Architecture |
| Version | 0.2 |
| Status | Reviewed |
| Last Updated | 2026-07-08 |

---

# Purpose

This document defines the physical communication architecture of the BattleStation System.

The objective is to provide a clean, modular, reliable wiring system that is easy to assemble, troubleshoot, transport, maintain, and expand.

The wiring architecture supports the BattleStation design philosophy of creating a professional, commercial-quality event management system.

---

# Design Philosophy

BattleStation wiring shall:

- Minimize cable clutter.
- Support modular installation.
- Allow rapid module replacement.
- Support multiple arena sizes.
- Use standardized connectors and cables.
- Be easy to troubleshoot.
- Separate communication from high-current power whenever practical.

---

# BattleStation Bus (BSBus)

The BattleStation Bus (BSBus) is the primary communication network connecting the BattleStation Core Controller to distributed BattleStation hardware modules.

The BSBus standard defines:

- Communication protocol
- Module addressing
- Device discovery
- Health monitoring
- Status reporting
- Firmware compatibility

The BattleStation Bus standard is independent of the physical communication layer.

---

# Physical Layer

Initial implementation:

- CAN Bus

Future versions may utilize alternative communication technologies while maintaining BattleStation Bus compatibility.

---

# Cabling

Preferred communication cable:

- CAT6 Ethernet Cable

Reasons:

- Widely available
- Inexpensive
- Multiple standard lengths
- Rugged
- Easy field replacement
- Locking connectors
- Supports modular installation

Multiple cable lengths may be used to accommodate different arena sizes.

---

# Connectors

Preferred connector:

- RJ45

Advantages:

- Low cost
- Locking mechanism
- Easy replacement
- Industry standard
- Readily available

---

# Network Topology

BattleStation Bus utilizes a daisy-chain topology.

```
BattleStation Core Controller
        │
Driver Station
        │
Lighting Module
        │
Safety Module
        │
Referee Station
        │
Termination
```

Modules may include integrated pass-through connectors to reduce cable clutter and simplify installation.

---

# Module Power

Communication wiring shall remain independent of module power whenever practical.

Low-power modules may receive power through the communication cable.

High-current modules shall use local power while remaining connected to the BattleStation Bus for communication.

Examples include:

- Arena Lighting
- Audible Alarm
- Future high-power devices

---

# Module Discovery

Each module shall:

- Possess a unique address.
- Identify its module type.
- Report firmware version.
- Report health status.
- Report fault conditions.

The BattleStation Core Controller shall automatically discover connected modules during startup.

---

# Startup Verification

Before tournament operation begins, BattleStation shall perform a complete startup verification sequence.

The verification process ensures that all required hardware and software components are operating correctly before allowing tournament operation.

The system shall verify:

- Required modules are present.
- Communication has been established with required modules.
- Module firmware is compatible with the installed BattleStation software.
- No critical faults are active.
- Optional modules are detected when available.

---

# Module Classification

Every BattleStation module shall be assigned one of three classifications.

## Critical

Failure prevents safe or reliable tournament operation.

Examples:

- BattleStation Server
- BattleStation Core Controller
- Driver Stations
- Referee Station
- Arena Safety Module

Critical module failures prevent match operation.

---

## Operational

Failure impacts tournament efficiency, but tournament operation may continue using manual procedures.

Examples:

- Registration Station
- Inspection Station
- Public Display

Operational failures generate coordinator warnings but do not prevent tournament operation.

---

## Optional

Failure has little or no impact on tournament operation.

Examples:

- Pit Audio
- Video Interface
- Future Wireless Displays
- Future Statistics Modules

Optional module failures shall never prevent tournament operation.

---

# Startup Results

Following startup verification, BattleStation shall report one of the following system states.

## System Ready

All Critical modules are:

- Present
- Communicating
- Firmware compatible
- Free of critical faults

Tournament operation may begin.

---

## System Ready with Warnings

All Critical modules are operational.

One or more Operational or Optional modules report warnings.

Tournament operation may begin.

Warnings shall be displayed to the coordinator.

---

## System Not Ready

One or more Critical modules are:

- Missing
- Offline
- Running incompatible firmware
- Reporting critical faults

Tournament operation shall remain disabled until the issue is resolved.

---

# Optional Module Alarm Control

The coordinator shall be able to enable or disable monitoring of Optional modules.

Disabled Optional modules shall:

- Not generate active alarms.
- Not appear as active faults.
- Continue to appear on the System Health page.
- Be clearly identified as Disabled.
- Continue to be recorded in the system log.

This allows BattleStation to support tournaments that choose not to deploy every available hardware module.

Examples:

- Pit Audio disabled
- Video Interface disabled
- Wireless Display disabled
- Future expansion modules disabled

---

# Coordinator Override

BattleStation shall allow the coordinator to acknowledge selected startup warnings.

Coordinator acknowledgements shall:

- Be recorded in the system log.
- Be displayed on the System Health page.
- Be included within the Event Report.

Critical Safety faults shall never be overridable.

Examples of acceptable acknowledgements:

- Public Display unavailable
- Registration laptop unavailable after registration closes
- Optional modules intentionally disabled

Examples of non-overridable faults:

- Arena Door Safety fault
- Driver Station communication failure
- BattleStation Core Controller failure
- BattleStation Server failure

---

# Expandability

The BattleStation Bus shall support future hardware modules without requiring changes to existing modules.

Future modules may include:

- Additional Driver Stations
- Video Controller
- Scoreboards
- Wireless Bridges
- Environmental Sensors
- Future Arena Systems

---

# Fault Philosophy

Every detected fault shall have an intentional system response.

Fault responses shall be classified as one of the following:

- Ignore
- Warning
- Alarm
- Lockout

Critical Safety faults shall always result in Lockout.

Optional module faults shall normally generate Warnings or be Ignored when disabled by the coordinator.

---

# Design Principles

The BattleStation wiring architecture shall:

- Remain modular.
- Use standardized connectors.
- Minimize installation time.
- Support rapid troubleshooting.
- Support future expansion.
- Separate hardware communication from application software.
- Remain independent of the BattleStation Server computing platform.

---

# Related Documents

- 04_System_Modules.md
- 07_System_Definition.md
- 08_Requirements_Specification.md
- 09_Decision_Log.md
- 12_Hardware_BOM.md
- 13_Software_Architecture.md
- 17_Design_Principles.md