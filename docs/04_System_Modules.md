# BattleStation System Modules

## Purpose

This document defines every functional module that makes up the BattleStation System.

A module may consist of hardware, software, or both.

Modules are classified by:

- Version
- Criticality
- Primary User
- Function

---

# Module Classification

## Critical

Failure prevents the tournament from operating safely or correctly.

## Operational

Failure affects tournament efficiency but the event can continue.

## Optional

Failure has little or no impact on tournament operation.

---

# Version Classification

V1 - Required for BattleStation System 1.0

V2 - Enhancement after Version 1.0 is complete

Future - Planned for future releases

---

# Modules

## BattleStation Core

Version:
V1

Classification:
Critical

Description:

Central controller for the entire BattleStation System.

Responsibilities:

- Hosts BattleStation software
- Hosts local Wi-Fi
- Tournament database
- Match control
- Safety monitoring
- Module health monitoring
- Public API
- Web server
- Communications hub

Hardware:

- Raspberry Pi
- Internal power supply
- Touch diagnostics display
- Status LEDs
- Cooling
- Internal storage

---

## Coordinator Station

Version:
V1

Classification:
Critical

Primary User:
Tournament Coordinator

Description:

Primary operator interface.

Responsibilities:

- Event setup
- Registration approval
- Inspection approval
- Bracket generation
- Match control
- Safety overrides
- System health
- Reports

Runs as a local web interface.

---

## Registration Station

Version:
V1

Classification:
Operational

Primary User:
Competitors

Description:

Collects competitor and robot information.

Responsibilities:

- Driver registration
- Robot registration
- Photos
- Weight entry
- Weapon selection
- Check-in

Runs as a local web interface.

---

## Inspection Station

Version:
V1

Classification:
Operational

Primary User:
Inspector

Responsibilities:

- Weight verification
- Safety inspection
- Class verification
- Rule compliance
- Pass/Fail approval

Future capability:

Automatic scale integration.

---

## Driver Station

Version:
V1

Classification:
Critical

Primary User:
Drivers

Hardware module.

Responsibilities:

- Ready button
- Tap Out button
- Status LEDs
- Module health

Connected via BattleStation Bus.

---

## Referee Station

Version:
V1

Classification:
Critical

Primary User:
Referee

Hardware module.

Responsibilities:

- Pause
- Resume
- Unstick
- Arena issue
- Match control requests

---

## Arena Safety Module

Version:
V1

Classification:
Critical

Responsibilities:

- Door sensor
- Safety alarm
- Beacon
- Safety event logging

Future expansion:

Additional arena safety sensors.

---

## Public Display

Version:
V1

Classification:
Operational

Displays:

- Current match
- Next match
- Timer
- Bracket
- Winner
- Event information

Runs as local web interface.

---

## Arena Lighting

Version:
V1

Classification:
Operational

Responsibilities:

- Red corner
- Blue corner
- Pause lighting
- Match intro lighting

Controlled by BattleStation Bus.

---

## Statistics & Reports

Version:
V1

Classification:
Operational

Responsibilities:

- Tournament reports
- Final standings
- Completed brackets
- Event archive

V2:

Career statistics.

---

# Version 2 Modules

## Pit Audio

Wireless announcement system.

---

## Video Interface

Controls external recording system.

---

## Career Statistics

Tracks drivers and robots across multiple events.

---

## Event Recap Generator

Creates post-event reports.

---

# Future Modules

- Multi Arena Controller
- Mobile Referee Interface
- Cloud Synchronization
- League Management
- Live Streaming Integration
- AI Event Analysis