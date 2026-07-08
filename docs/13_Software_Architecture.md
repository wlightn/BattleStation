# BattleStation Software Architecture

## Purpose

This document defines the software architecture of the BattleStation System.

BattleStation is composed of modular software services that communicate through well-defined interfaces.

The software architecture follows the same modular philosophy as the hardware architecture.

---

# Core Software Modules

## Tournament Manager

Responsibilities

- Create events
- Open/close tournaments
- Tournament state
- Overall workflow

---

## Registration Manager

Responsibilities

- Driver registration
- Robot registration
- Photos
- Check-in

---

## Inspection Manager

Responsibilities

- Inspection status
- Weight
- Rule compliance
- Approval

---

## Bracket Manager

Responsibilities

- Generate brackets
- Advance winners
- Advance losers
- Determine next match

---

## Match Engine

Responsibilities

- Match state machine
- Timer
- Ready state
- Pause
- Resume
- Result recording

---

## Safety Manager

Responsibilities

- Door monitoring
- Emergency stop
- Safety logging
- Safety state

---

## Hardware Interface

Responsibilities

- BattleStation Bus
- Module communications
- Health monitoring
- Device discovery

---

## Web Server

Responsibilities

- Coordinator interface
- Registration interface
- Inspection interface
- Public display
- API

---

## Database Manager

Responsibilities

- Store tournament data
- Drivers
- Robots
- Matches
- Events
- Statistics

---

## Reporting Manager

Responsibilities

- Reports
- Brackets
- Results
- Exports

---

## Configuration Manager

Responsibilities

- Classes
- Arena settings
- Match duration
- System configuration

---

## System Monitor

Responsibilities

- Module health
- CPU usage
- Memory
- Logging
- Diagnostics

---

# Design Principles

Every software module:

- Has a single responsibility.
- Can be tested independently.
- Uses documented interfaces.
- Can be upgraded without affecting unrelated modules.

## Learning Approach

BattleStation will be developed one module at a time.

Each software module should be small enough to understand, test, and maintain independently.

Development will prioritize clarity over cleverness.

No code should be added to the project until its purpose and behavior are understood.

The architecture may be professional, but implementation will be approached in small, teachable steps.

# Core Software Modules

## Tournament Manager

Responsible for overall event flow.

Responsibilities:

- Create and load events
- Track tournament status
- Coordinate registration, inspection, brackets, matches, awards, and reports
- Maintain the high-level tournament workflow

---

## Registration Manager

Responsible for competitor and robot registration.

Responsibilities:

- Create driver records
- Create robot records
- Support multiple robots per driver
- Store robot photos
- Store weapon type and weight information
- Support future returning robot lookup

---

## Inspection Manager

Responsible for event-day approval.

Responsibilities:

- Record official weight
- Warn when weight exceeds class limit
- Record safety inspection status
- Record class-specific inspection status
- Prevent unapproved robots from entering brackets

---

## Bracket Manager

Responsible for tournament bracket logic.

Responsibilities:

- Generate double-elimination brackets
- Randomize initial matchups
- Assign byes when needed
- Advance winners
- Move losers into the correct bracket
- Determine current and next matches

---

## Match Engine

Responsible for match operation.

Responsibilities:

- Enforce the match state machine
- Control match timer
- Track driver ready status
- Handle pause and resume
- Track unsticks
- Handle tap out
- Record match result

---

## Safety Manager

Responsible for safety-related system behavior.

Responsibilities:

- Monitor arena door status
- Trigger Safety Stop
- Activate alarms and beacon outputs
- Log safety events
- Prevent unsafe match operation

---

## Hardware Interface

Responsible for communication with physical BattleStation modules.

Responsibilities:

- Communicate with the BattleStation Core Controller
- Read driver station inputs
- Read referee station inputs
- Monitor module health
- Send lighting, alarm, and status commands
- Abstract hardware details from the rest of the software

---

## Web Server

Responsible for browser-based user interfaces.

Interfaces:

- Coordinator interface
- Registration interface
- Inspection interface
- Public display
- Future maintenance interface

---

## Database Manager

Responsible for persistent data storage.

Responsibilities:

- Store events
- Store drivers
- Store robots
- Store classes
- Store inspections
- Store matches
- Store logs
- Store reports

---

## Reporting Manager

Responsible for generated outputs.

Responsibilities:

- Final standings
- Completed brackets
- Match history
- Event archive
- Future recap packages

---

## Configuration Manager

Responsible for configurable system settings.

Responsibilities:

- Event settings
- Weight classes
- Match duration
- Arena reset timer
- Inspection templates
- Network settings
- Module settings

---

## System Monitor

Responsible for diagnostics and health reporting.

Responsibilities:

- Server health
- Core controller health
- Module health
- Network status
- Error reporting
- Startup checks