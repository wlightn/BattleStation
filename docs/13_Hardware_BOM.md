# BattleStation Hardware BOM

| Item | Value |
|------|-------|
| Document | Hardware BOM |
| Version | 1.0 |
| Status | Constitutional Baseline |
| Last Updated | 2026-08-03 |

---

# Purpose

This document defines the hardware Bill of Materials (BOM) for BattleStation Version 1.

The Hardware BOM identifies the physical components, assemblies, and equipment required to implement the BattleStation architecture.

The BOM also records preferred implementations, acceptable alternatives, selection status, and engineering notes to support procurement, construction, maintenance, and future development.

The Hardware BOM describes implementation.

Architectural responsibilities remain defined by the constitutional architecture documents.

---

# Hardware Philosophy

BattleStation hardware exists to fulfill the architectural responsibilities established by Chapter 1.

Whenever practical, BattleStation hardware shall be:

- Modular
- Replaceable
- Serviceable
- Testable
- Maintainable
- Commercial in appearance
- Independently documented

Implementation technologies may evolve without changing the architectural responsibilities they fulfill.

---

# BOM Status Definitions

## Approved

The preferred implementation has been accepted for the current engineering baseline.

---

## Candidate

The implementation is under engineering evaluation.

Additional testing or engineering work is required before approval.

---

## Open Decision

Selection depends upon another unresolved engineering decision.

---

## Future

The component is planned for a future version of BattleStation.

---

## Deprecated

The component has been replaced or is no longer approved for future use.

Historical information is retained for engineering traceability.

---

# BOM Conventions

Each entry identifies:

- The Configuration Item
- Its intended purpose
- Preferred implementation
- Acceptable alternatives
- Current engineering status
- Supporting engineering notes

Configuration Items define **what BattleStation requires**.

Preferred implementations define **how the current engineering baseline fulfills those requirements**.

# Core System Components

These components provide the primary computing, control, and power infrastructure required for BattleStation Version 1.

| Configuration Item | Purpose | Preferred Implementation | Acceptable Alternative | Status | Engineering Notes |
|--------------------|---------|--------------------------|------------------------|--------|-------------------|
| BattleStation Server | Hosts BattleStation Application Services and supporting infrastructure required for tournament operation. | Linux Mini PC | Equivalent Linux-compatible Mini PC | Approved | The server is a configuration item. The Mini PC is the current preferred implementation and may change without altering the architecture. |
| BattleStation Core Controller | Coordinates field hardware, BattleStation Bus communication, module discovery, and real-time hardware interaction. | Custom controller hardware | Future approved controller design | Candidate | Architectural responsibilities are defined by the System Modules document. Hardware implementation remains under evaluation. |
| Core Controller Enclosure | Protects the Core Controller electronics while supporting field serviceability. | Aluminum enclosure | 3D-printed prototype enclosure | Candidate | Commercial enclosure preferred for production. Prototype enclosures remain acceptable during development. |
| Server Mounting Method | Secures the BattleStation Server while allowing replacement and maintenance. | External serviceable mounting | Internal enclosure mounting | Candidate | The preferred solution emphasizes easy replacement and upgradeability. |
| Internal Power Supply | Provides regulated power for BattleStation control electronics. | TBD | TBD | Open Decision | Final selection depends upon electrical load analysis and hardware design. Preferred AC input is an IEC power connection. |

# Communication Components

These components provide the physical implementation of BattleStation communications.

BattleStation Bus (BSBus) defines the architectural communication standard.

The physical communication technology may evolve while remaining compliant with the BSBus specification.

| Configuration Item | Purpose | Preferred Implementation | Acceptable Alternative | Status | Engineering Notes |
|--------------------|---------|--------------------------|------------------------|--------|-------------------|
| BattleStation Bus Physical Layer | Provides the physical communication medium for BattleStation hardware modules. | CAN Bus | Future approved physical layer | Candidate | BSBus is the architectural communication standard. CAN Bus is the current preferred implementation. |
| Communication Cable | Connects distributed BattleStation modules. | CAT6 cable | CAT5e cable | Candidate | The cable is used as a durable multi-conductor medium and does not imply Ethernet communication. |
| Module Connector | Provides standardized field connections between BattleStation modules. | RJ45 | Approved locking connector | Candidate | RJ45 remains the preferred implementation because of availability, low cost, and field serviceability. |
| CAN Transceiver | Converts controller logic signals to the selected physical communication layer. | TBD | TBD | Open Decision | Final component selection will occur during hardware prototyping. |
| Server-to-Core Controller Link | Connects BattleStation Application Services with the BattleStation Core Controller. | Ethernet | USB 3 / USB-C | Candidate | A single high-speed connection remains the preferred architectural model. Final implementation will be selected during integration. |

# Operator and Event Equipment

These items provide human interaction with BattleStation during tournament operation.

Operator equipment is separate from BattleStation architectural modules.

BattleStation interfaces may be accessed from different hardware platforms provided the required operational capabilities are maintained.

| Configuration Item | Purpose | Preferred Implementation | Acceptable Alternative | Status | Engineering Notes |
|--------------------|---------|--------------------------|------------------------|--------|-------------------|
| Mission Control Workstation | Primary operational interface used by the Battle Commander. | Existing laptop | Modern laptop or desktop workstation | Approved | Connects to BattleStation through the local network. Hardware platform may change without affecting Mission Control functionality. |
| Registration Workstation | Registration interface for competitors and registration staff. | Existing laptop | Tablet, laptop, or desktop workstation | Approved | Any approved platform capable of accessing the Registration Station interface may be used. |
| Inspection Workstation | Inspection interface used during robot inspection. | Existing laptop | Tablet or laptop | Candidate | Portable platforms remain preferable for movement throughout the inspection area. |
| Public Display | Displays tournament information for competitors and spectators. | Large HDMI display | Browser-based client display | Candidate | Public Display remains presentation-only and provides no tournament control functions. |
| Core Diagnostics Display | Local diagnostics and maintenance interface for the BattleStation Core Controller. | Small touchscreen display | Non-touch status display | Candidate | Used exclusively for diagnostics, configuration, startup verification, and maintenance. It is not used for tournament operation. |

# BattleStation Hardware Modules

These Configuration Items implement the distributed hardware modules defined by the BattleStation architecture.

Each hardware module fulfills one primary architectural responsibility while communicating through BattleStation Bus.

Hardware implementation may evolve without changing the responsibilities assigned by the constitutional architecture.

| Configuration Item | Purpose | Preferred Implementation | Acceptable Alternative | Status | Engineering Notes |
|--------------------|---------|--------------------------|------------------------|--------|-------------------|
| Driver Station | Provides Driver Ready and Tap Out controls during tournament operation. | Custom BattleStation Driver Station | Future approved implementation | Candidate | One Driver Station is required for each competitor position. Critical module. |
| Referee Station | Provides match supervision controls for the Referee. | Custom BattleStation Referee Station | Mission Control administrative interface (maintenance only) | Candidate | The Referee Station remains the preferred operational interface during live matches. Critical module. |
| Arena Safety Module | Monitors arena safety systems and reports safety conditions. | Custom BattleStation Safety Module | Future approved implementation | Candidate | Supports door monitoring, safety indication, and other protected safety functions. Critical module. |
| Arena Lighting Module | Provides visual indication of match and tournament status. | Custom BattleStation Lighting Module | Future approved implementation | Candidate | Supports match state indication, alliance identification, pause indication, and future lighting effects. |
| Module Pass-Through Interface | Supports daisy-chain connection of distributed BattleStation modules. | Dual RJ45 pass-through ports | Future approved connector system | Candidate | Simplifies field wiring and reduces long home-run cable runs. Supports modular installation and replacement. |

# Inspection Components

These components support robot inspection and verification.

Some items are planned for future integration while remaining outside the minimum Version 1 implementation.

| Configuration Item | Purpose | Preferred Implementation | Acceptable Alternative | Status | Engineering Notes |
|--------------------|---------|--------------------------|------------------------|--------|-------------------|
| Digital Inspection Scale | Measures official robot competition weight. | TBD | Manual weight entry | Future | Automatic scale integration is planned for a future release. Manual weight entry satisfies Version 1 requirements. |

---

# Future Hardware Components

The following Configuration Items represent planned future capabilities.

These items shall not delay completion of BattleStation Version 1.

| Configuration Item | Purpose | Preferred Implementation | Acceptable Alternative | Status | Engineering Notes |
|--------------------|---------|--------------------------|------------------------|--------|-------------------|
| Pit Audio Module | Provides wireless announcements throughout the pit area. | Wi-Fi audio module | Manual announcements | Future | Planned for Version 2 or later. |
| Video Interface Module | Coordinates external video recording systems. | Dedicated recording interface | OBS, laptop, or external recorder | Future | BattleStation coordinates recording but does not process video in Version 1. |
| Additional Display Module | Supports future spectator or information displays. | Browser-based display client | HDMI display | Future | Enables expansion without changing the existing architecture. |
| Wireless Bridge Module | Extends BattleStation communications where wired connections are impractical. | TBD | TBD | Future | Optional capability for future engineering evaluation. |

---

# BOM Governance

The Hardware BOM is the authoritative record of the approved physical implementation for BattleStation.

Configuration Management shall steward this document throughout the project lifecycle.

Changes to this BOM shall be reviewed and documented to preserve engineering traceability.

The Hardware BOM records implementation decisions.

Architectural responsibilities remain defined by the constitutional architecture documents.

Hardware selections may evolve provided they continue to satisfy approved architectural responsibilities and system requirements.

---

# Related Documents

- `05_System_Modules.md`
- `08_System_Definition.md`
- `09_Requirements_Specification.md`
- `10_Decision_Log.md`
- `12_Development_Roadmap.md`
- `14_Software_Architecture.md`
- `15_Wiring_Architecture.md`
- `20_Design_Principles.md`