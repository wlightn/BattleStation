# BattleStation Hardware BOM

| Item | Value |
|------|-------|
| Document | Hardware BOM |
| Version | 0.1 |
| Status | Draft |
| Last Updated | 2026-07-08 |

---

# Purpose

This document tracks the hardware components required to build BattleStation.

The Hardware BOM shall include preferred components, acceptable alternatives, purpose, status, and notes.

---

# BOM Status Definitions

## Selected

Component has been chosen for the current design.

## Candidate

Component is being considered but not finalized.

## Open Decision

Component depends on an unresolved design decision.

## Future

Component is planned for a later version.

---

# Core System Components

| Item | Purpose | Preferred | Alternate | Status | Notes |
|------|---------|-----------|-----------|--------|-------|
| BattleStation Server | Runs BattleStation software, database, web server, and reports | Linux Mini PC | Raspberry Pi 5 | Open Decision | Server may remain separate from Core Controller for serviceability. |
| BattleStation Core Controller | Handles field I/O, BSBus, diagnostics, and safety interface | TBD | TBD | Open Decision | May contain microcontroller, CAN interface, power distribution, and diagnostics screen. |
| Core Enclosure | Rugged housing for Core Controller | Aluminum enclosure | 3D printed enclosure | Candidate | Takachi and Hammond are preferred candidates. |
| Internal Power Supply | Provides regulated power to Core Controller electronics | TBD | TBD | Open Decision | Preferred input is standard IEC PC-style power connection. |

---

# Communication Components

| Item | Purpose | Preferred | Alternate | Status | Notes |
|------|---------|-----------|-----------|--------|-------|
| BattleStation Bus Physical Layer | Module communication | CAN Bus | TBD | Candidate | BSBus standard remains independent of physical layer. |
| Communication Cable | Module cabling | CAT6 Ethernet Cable | CAT5e | Candidate | Used as physical cable, not necessarily Ethernet signaling. |
| Module Connector | Standard module connector | RJ45 | Locking circular connector | Candidate | RJ45 preferred for low cost and field replacement. |
| CAN Transceiver | Converts controller logic to CAN bus signaling | TBD | TBD | Open Decision | To be selected during hardware prototyping. |

---

# Operator and Event Interfaces

| Item | Purpose | Preferred | Alternate | Status | Notes |
|------|---------|-----------|-----------|--------|-------|
| Mission Control Laptop | Main operator interface for Battle Commander | Existing laptop | Any modern laptop | Selected | Connects through local BattleStation network. |
| Registration Laptop | Competitor registration interface | Existing laptop | Tablet or second laptop | Selected | Connects through local BattleStation network. |
| Public Display | Shows match and event information | Large HDMI display | Browser client display | Candidate | Can be driven locally or through web interface. |

---

# Hardware Modules

| Item | Purpose | Preferred | Alternate | Status | Notes |
|------|---------|-----------|-----------|--------|-------|
| Driver Station | Ready and Tap Out controls | Custom module | TBD | Candidate | One per driver side. |
| Referee Station | Pause, resume, and match control inputs | Custom module | Mission Control software controls | Candidate | Critical match-control module. |
| Arena Safety Module | Door sensor, alarm, safety beacon | Custom module | TBD | Candidate | Critical module. |
| Arena Lighting Module | Red/blue corner lighting and pause lighting | Custom module | TBD | Candidate | Operational module. |

---

# Inspection Components

| Item | Purpose | Preferred | Alternate | Status | Notes |
|------|---------|-----------|-----------|--------|-------|
| Digital Scale | Official robot weigh-in | TBD | Manual scale entry | Future | Automatic scale input is planned but not required for V1. |

---

# Version 2 / Future Components

| Item | Purpose | Preferred | Alternate | Status | Notes |
|------|---------|-----------|-----------|--------|-------|
| Pit Audio Module | Wireless pit announcements | Wi-Fi audio module | Manual announcements | Future | Version 2 feature. |
| Video Interface | Controls external recording system | Separate recorder | OBS/laptop/action camera | Future | BattleStation logs and controls video, but does not process video in V1. |

---

# Related Documents

- 02_BattleStation_Glossary_and_Naming_Convention.md
- 04_User_Roles.md
- 05_System_Modules.md
- 09_Requirements_Specification.md
- 10_Decision_Log.md
- 14_Software_Architecture.md
- 15_Wiring_Architecture.md
- 20_Design_Principles.md