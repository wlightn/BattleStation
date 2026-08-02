# BattleStation Wiring Architecture

| Item | Value |
|------|-------|
| Document | Wiring Architecture |
| Version | 1.0 |
| Status | Constitutional Baseline |
| Last Updated | 2026-08-03 |

---

# Purpose

This document defines the constitutional hardware communication architecture used by BattleStation.

The Wiring Architecture specifies how the BattleStation Core Controller communicates with distributed BattleStation hardware modules through the BattleStation Bus (BSBus).

This document establishes:

- Hardware communication architecture
- Communication topology
- Module interconnection
- Startup verification
- Module discovery
- Fault handling philosophy
- Wiring design principles

Electrical schematics, PCB layouts, and cable drawings belong within the hardware implementation documentation.

---

# Communication Philosophy

BattleStation communication shall be:

- Modular
- Reliable
- Serviceable
- Replaceable
- Expandable
- Understandable
- Independent of application software whenever practical

The communication architecture shall remain independent of any specific physical communication technology whenever practical.

Communication responsibilities shall remain stable even as implementation technologies evolve.

---

# BattleStation Bus (BSBus)

BattleStation Bus (BSBus) is the constitutional communication standard for BattleStation hardware.

BSBus defines the logical communication architecture connecting the BattleStation Core Controller with distributed hardware modules.

BSBus specifies:

- Communication behavior
- Module identification
- Module discovery
- Health monitoring
- Status reporting
- Fault reporting
- Firmware compatibility

BSBus defines the communication standard.

It does not prescribe a specific physical communication technology.

---

# Architectural Principles

BattleStation Bus shall:

- Support modular hardware.
- Support future hardware expansion.
- Provide deterministic communication.
- Support automatic module discovery.
- Support module health monitoring.
- Isolate communication failures whenever practical.
- Remain independent of the selected physical communication implementation.

# Preferred Physical Implementation

The following implementation represents the approved communication approach for BattleStation Version 1.

Future versions may adopt different physical communication technologies while remaining compliant with the BattleStation Bus (BSBus) architectural standard.

---

# Physical Communication Layer

## Preferred Implementation

Controller Area Network (CAN Bus)

**Status:** Candidate

---

## Engineering Rationale

CAN Bus is currently preferred because it provides:

- Reliable multi-device communication
- Robust error detection
- Deterministic message delivery
- Wide industry adoption
- Excellent electrical noise immunity
- Long cable capability suitable for tournament environments
- Support for distributed embedded controllers

Selection of CAN Bus does not make CAN the BattleStation architecture.

CAN is the preferred physical implementation of the BSBus communication standard.

---

# Communication Cabling

## Preferred Implementation

Category 6 (CAT6) cable

**Status:** Candidate

---

## Engineering Rationale

CAT6 cable is preferred because it is:

- Inexpensive
- Widely available
- Mechanically robust
- Available in standardized lengths
- Easy to replace during tournament operation
- Readily obtainable from commercial suppliers

The cable serves as a standardized multi-conductor communication medium.

Its use does not imply Ethernet communication.

---

# Communication Connectors

## Preferred Implementation

RJ45

**Status:** Candidate

---

## Engineering Rationale

RJ45 connectors are currently preferred because they provide:

- Low cost
- Positive locking
- Commercial availability
- Rapid field replacement
- Familiar installation procedures
- Standardized cable assemblies

Connector selection remains independent of the communication protocol.

Future physical implementations may utilize different connector systems while preserving BSBus compatibility.

---

# Server-to-Core Controller Communication

## Preferred Implementation

Ethernet

**Status:** Candidate

---

## Engineering Rationale

A single high-speed communication link between BattleStation Application Services and the BattleStation Core Controller simplifies system integration while maintaining clear architectural separation.

Alternative implementations may be adopted if they continue to satisfy:

- Required communication performance
- Reliability
- Serviceability
- Architectural independence

The communication interface remains implementation-independent.

---

# Module Power Distribution

Communication wiring and power distribution shall remain separate whenever practical.

Low-power modules may receive power through the communication cable when engineering analysis demonstrates that doing so does not compromise:

- Reliability
- Electrical safety
- Serviceability
- Future expansion

Modules with higher power requirements shall utilize dedicated power distribution while continuing to communicate through BattleStation Bus.

# Network Topology

BattleStation Bus utilizes a distributed communication topology connecting the BattleStation Core Controller with hardware modules deployed throughout the event.

The preferred Version 1 implementation uses a daisy-chain topology.

```text
BattleStation Core Controller
           │
     Driver Station
           │
    Lighting Module
           │
   Arena Safety Module
           │
    Referee Station
           │
       Bus Termination
```

Integrated pass-through connections are preferred whenever practical to reduce installation complexity, cable clutter, and field setup time.

Future topologies may be adopted provided they remain compliant with the BattleStation Bus architectural standard.

---

# Module Discovery

The BattleStation Core Controller shall automatically discover connected BattleStation hardware modules during system startup.

Each module shall provide sufficient information to identify itself and support compatibility verification.

Minimum module information includes:

- Unique module identifier
- Module type
- Firmware version
- Operational status
- Health status
- Fault status

Additional module capabilities may be reported as future versions of BattleStation evolve.

Automatic discovery reduces configuration effort while improving installation, maintenance, and troubleshooting.

---

# Startup Verification

Before BattleStation enters operational service, the BattleStation Core Controller shall perform a complete startup verification sequence.

The purpose of startup verification is to establish confidence that the required hardware communication architecture is operational before tournament activities begin.

Startup verification shall confirm:

- Required modules are present.
- Communication has been established.
- Firmware compatibility requirements are satisfied.
- Required modules report healthy operational status.
- No active critical faults exist.
- Optional modules are identified when present.

Startup verification results shall be communicated to BattleStation Application Services for presentation to the Battle Commander.

Tournament operation shall not begin until startup verification has completed successfully or authorized operational procedures have been followed.

# Module Classification

BattleStation hardware modules are classified according to their impact on tournament operation.

Module classification determines startup requirements, fault handling, and operational behavior.

---

## Critical Modules

Failure of a Critical module prevents safe or dependable tournament operation.

Critical module failures shall prevent tournament operation until the fault has been corrected.

Examples include:

- BattleStation Server
- BattleStation Core Controller
- Driver Stations
- Referee Station
- Arena Safety Module

---

## Operational Modules

Failure of an Operational module affects tournament efficiency but does not necessarily prevent tournament operation.

Operational module failures shall generate warnings and may require manual operating procedures.

Examples include:

- Registration Station
- Inspection Station
- Public Display

---

## Optional Modules

Optional modules provide additional functionality but are not required for normal tournament operation.

Failure of Optional modules shall not prevent tournament operation.

Examples include:

- Pit Audio
- Video Interface
- Future Information Displays
- Future Expansion Modules

---

# Startup Results

Following startup verification, the BattleStation Core Controller shall determine the hardware readiness state.

BattleStation Application Services shall determine the overall operational readiness state using this information.

Three readiness states are defined.

---

## System Ready

All required Critical modules:

- Are present
- Are communicating
- Report compatible firmware
- Report healthy operational status

Tournament operation may begin.

---

## System Ready with Warnings

All Critical modules are operational.

One or more Operational or Optional modules report warnings.

Tournament operation may begin.

Warnings shall be presented to the Battle Commander.

---

## System Not Ready

One or more Critical modules:

- Are missing
- Are not communicating
- Report incompatible firmware
- Report critical faults

Tournament operation shall remain disabled until the condition has been resolved.

---

# Optional Module Management

BattleStation shall allow the Battle Commander to enable or disable monitoring of Optional modules.

Disabled Optional modules shall:

- Not generate active alarms.
- Not prevent tournament operation.
- Continue appearing within System Health.
- Be clearly identified as Disabled.
- Continue to be recorded within operational logs.

This capability allows BattleStation to support events that intentionally deploy only a subset of available hardware modules.

---

# Coordinator Acknowledgements

The Battle Commander may acknowledge selected startup warnings.

Acknowledgements shall:

- Be recorded within the operational log.
- Appear within System Health.
- Be included within the Event Report.

Coordinator acknowledgements shall never override Critical Safety faults.

Examples of acceptable acknowledgements include:

- Public Display unavailable
- Registration Station unavailable after registration closes
- Optional modules intentionally disabled

Examples of non-overridable conditions include:

- Arena Safety Module failure
- Driver Station communication failure
- BattleStation Core Controller failure
- BattleStation Server failure

---

# Fault Philosophy

Every detected hardware fault shall have a defined and intentional system response.

Fault responses are classified as:

- Ignore
- Warning
- Alarm
- Lockout

Critical Safety faults shall always result in Lockout.

Operational module faults shall normally result in Warning.

Optional module faults shall normally result in Warning or Ignore when intentionally disabled.

Fault responses shall remain predictable, documented, and consistent throughout BattleStation.

# Expandability

The BattleStation Wiring Architecture shall support future hardware expansion without requiring redesign of existing hardware modules whenever practical.

Future BattleStation hardware may include, but is not limited to:

- Additional Driver Stations
- Additional Referee Stations
- Video Interface Modules
- Arena Scoreboards
- Wireless Communication Bridges
- Environmental Monitoring Modules
- Additional Safety Devices
- Future BattleStation hardware modules

Expansion shall occur through documented BattleStation Bus interfaces while preserving compatibility with existing architectural responsibilities.

---

# Wiring Architecture Governance

The Wiring Architecture is the constitutional engineering reference for BattleStation hardware communication.

This document defines the architectural rules governing:

- Hardware communication
- Module interconnection
- Startup verification
- Hardware communication topology
- Module discovery
- Fault handling philosophy

Electrical schematics, PCB layouts, wiring harnesses, cable assemblies, connector pinouts, and manufacturing documentation shall conform to this architecture.

Implementation documents may evolve without requiring changes to this architectural baseline provided they continue to satisfy the approved architectural responsibilities.

---

# Design Principles

The BattleStation Wiring Architecture shall:

- Remain modular.
- Support independent hardware modules.
- Use standardized communication interfaces.
- Minimize installation complexity.
- Support rapid field replacement.
- Support efficient troubleshooting.
- Separate communication from application software.
- Separate communication from power distribution whenever practical.
- Support future hardware expansion.
- Remain independent of any specific communication technology.
- Preserve clear architectural boundaries.
- Favor dependable operation over implementation convenience.

---

# Related Documents

- `05_System_Modules.md`
- `08_System_Definition.md`
- `09_Requirements_Specification.md`
- `10_Decision_Log.md`
- `13_Hardware_BOM.md`
- `14_Software_Architecture.md`
- `16_Test_Plan.md`
- `20_Design_Principles.md`