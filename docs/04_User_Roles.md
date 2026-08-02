# BattleStation User Roles

| Item | Value |
|------|-------|
| Document | BattleStation User Roles |
| Version | 1.0 |
| Status | Constitutional Baseline |
| Last Updated | 2026-08-02 |

---

# Purpose

This document defines the official user roles within the BattleStation system.

Each role represents a set of operational responsibilities rather than a specific individual. One person may perform multiple roles during smaller events.

---

# Battle Commander

The Battle Commander is the primary operator of BattleStation.

Responsibilities include:

- Creating and configuring events
- Approving robot registrations
- Generating tournament brackets
- Controlling match operation
- Recording match results
- Managing operational overrides
- Monitoring overall system health
- Supervising tournament progression

---

# Competitor / Driver

The Competitor registers one or more robots for the event.

The Driver operates a robot during competition.

Responsibilities include:

- Registering robots
- Checking in at the event
- Confirming robot information
- Competing in scheduled matches
- Indicating Driver Ready
- Initiating Tap Out when appropriate

One individual may perform both roles.

---

# Referee

The Referee is responsible for safe and fair match operation.

Responsibilities include:

- Monitoring match fairness
- Responding to arena issues
- Pausing and resuming matches
- Requesting unsticks
- Confirming match outcomes
- Supporting safe event operation

---

# Inspector

The Inspector verifies that each robot satisfies competition requirements.

Responsibilities include:

- Weight verification
- Safety inspection
- Class compliance
- Weapon classification
- Special class requirements
- Inspection approval

---

# Spectator

Spectators receive publicly available event information only.

Information may include:

- Current match
- Next match
- Match timer
- Results
- Tournament bracket
- Event status

Spectators do not interact with BattleStation operational controls.

---

# Pit Area Participant

Participants within the pit area receive operational event information.

Examples include:

- Upcoming matches
- Driver staging
- Event announcements
- Schedule delays
- General event status

---

# System Administrator

The System Administrator maintains the infrastructure supporting BattleStation.

Responsibilities include:

- Software deployment
- Infrastructure configuration
- Backups
- Updates
- Log management
- Diagnostics
- System recovery
- Troubleshooting

Infrastructure may be provided by approved organizational platforms without changing BattleStation's architectural responsibilities.

---

# Design Principle

Roles define responsibilities.

BattleStation interfaces, permissions, and workflows shall be organized around responsibilities rather than individual people.

---

# Related Documents

- `00_Project_Charter.md`
- `02_Glossary_and_Naming_Convention.md`
- `05_System_Modules.md`
- `09_Requirements_Specification.md`