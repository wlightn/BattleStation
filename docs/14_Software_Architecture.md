# BattleStation Software Architecture

| Item | Value |
|------|-------|
| Document | Software Architecture |
| Version | 0.2 |
| Status | Reviewed |
| Last Updated | 2026-07-07 |

---

# Purpose

This document defines the software architecture of the BattleStation System.

BattleStation is composed of modular software services that communicate through well-defined interfaces.

The software architecture follows the same modular philosophy as the hardware architecture.

---

# Learning Approach

BattleStation will be developed one module at a time.

Each software module should be small enough to understand, test, and maintain independently.

Development will prioritize clarity over cleverness.

No code should be added to the project until its purpose and behavior are understood.

The architecture may be professional, but implementation will be approached in small, teachable steps.

---

# Core Software Modules

## Tournament Manager

Responsible for overall event flow.

Responsibilities:

- Create and load events
- Open and close tournaments
- Track tournament status
- Coordinate registration, inspection, brackets, matches, awards, and reports
- Maintain the overall tournament workflow

---

## Registration Manager

Responsible for competitor and robot registration.

Responsibilities:

- Create driver records
- Create robot records
- Support multiple robots per driver
- Store robot photographs
- Store weapon type information
- Store robot weight
- Support future returning competitor and robot lookup

---

## Inspection Manager

Responsible for robot inspection and approval.

Responsibilities:

- Record official weight
- Warn when weight exceeds class limits
- Record inspection status
- Record class-specific inspection requirements
- Prevent unapproved robots from entering tournament brackets

---

## Bracket Manager

Responsible for tournament bracket management.

Responsibilities:

- Generate double-elimination brackets
- Randomize initial matchups
- Assign byes when required
- Advance winners
- Advance losers
- Determine current and next matches

---

## Match Engine

Responsible for match operation.

Responsibilities:

- Execute the Match State Machine
- Control the official match timer
- Track driver ready status
- Handle pause and resume
- Track unstick usage
- Process Tap Out events
- Record match results

---

## Safety Manager

Responsible for all safety-related system behavior.

Responsibilities:

- Monitor arena door status
- Process Emergency Stop events
- Trigger Safety Stop
- Activate alarms and warning beacons
- Log safety events
- Prevent unsafe match operation

---

## Hardware Interface

Responsible for communication with BattleStation hardware modules.

Responsibilities:

- Communicate with the BattleStation Core Controller
- Interface with the BattleStation Bus
- Read Driver Station inputs
- Read Referee Station inputs
- Monitor module health
- Send commands to lighting, alarms, and status indicators
- Abstract hardware communication from higher-level software

---

## Web Server

Provides the browser-based user interfaces.

Provides the following interfaces:

- Coordinator Station
- Registration Station
- Inspection Station
- Public Display
- Future Maintenance Interface
- Future Administrative Interface

---

## Database Manager

Responsible for persistent data storage.

Responsibilities:

- Events
- Drivers
- Robots
- Tournament Classes
- Inspections
- Matches
- Tournament Results
- System Logs
- Reports
- Future Career Statistics

---

## Reporting Manager

Responsible for generating tournament output.

Responsibilities:

- Final standings
- Completed brackets
- Match history
- Event archive
- Tournament reports
- Future recap packages

---

## Configuration Manager

Responsible for system configuration.

Responsibilities:

- Event settings
- Tournament classes
- Match duration
- Arena reset timer
- Inspection templates
- Network configuration
- Module configuration
- System preferences

---

## System Monitor

Responsible for diagnostics and system health.

Responsibilities:

- BattleStation Server health
- BattleStation Core Controller health
- Module health
- Network status
- CPU usage
- Memory usage
- Error reporting
- Startup diagnostics
- System logging

---

# Design Principles

Every software module shall:

- Have a single responsibility.
- Be independently testable.
- Use documented interfaces.
- Be replaceable without affecting unrelated modules.
- Support future expansion.
- Maintain separation between business logic and hardware communication.

---

# Related Documents

- 04_System_Modules.md
- 05_Tournament_Workflow.md
- 06_Match_State_Machine.md
- 07_System_Definition.md
- 08_Requirements_Specification.md
- 09_Decision_Log.md
- 17_Design_Principles.md