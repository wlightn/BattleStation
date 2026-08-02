# BattleStation Glossary & Naming Convention

| Item | Value |
|------|-------|
| Document | BattleStation Glossary & Naming Convention |
| Version | 1.0 |
| Status | Constitutional Baseline |
| Last Updated | 2026-08-02 |

---

# Purpose

This document establishes the official terminology, naming conventions, abbreviations, and capitalization standards used throughout the BattleStation project.

Its purpose is to ensure consistent language across documentation, software, hardware, CAD models, wiring diagrams, user interfaces, engineering discussions, and future releases.

When terminology conflicts exist, this document shall be considered the authoritative BattleStation source.

BattleStation shall reference published organizational terminology where applicable while maintaining authority over BattleStation-specific terminology.

---

# Naming Philosophy

BattleStation terminology shall:

- Be professional.
- Be descriptive.
- Be consistent.
- Be easy to understand.
- Support the BattleStation theme without becoming gimmicky.

Where practical, terminology should reflect real-world command, engineering, and mission-control environments.

Every official term should describe a responsibility rather than a specific implementation whenever practical.

---

# Official System Names

| Official Name | Description |
|---------------|-------------|
| BattleStation | Complete tournament management system. |
| BattleStation Application Services | Software services providing BattleStation functionality. |
| BattleStation Core Controller | Hardware controller responsible for field communications and hardware interfaces. |
| BattleStation Bus (BSBus) | Standard communication network connecting BattleStation hardware modules. |
| Mission Control | Primary operational workstation and software interface. |

---

# Official User Roles

| Official Role | Description |
|---------------|-------------|
| Battle Commander | Primary operator responsible for tournament control. |
| Referee | Match official responsible for enforcing rules and match decisions. |
| Inspector | Performs robot inspection and approval. |
| Registration Operator | Assists competitors during registration. |
| Arena Crew | Maintains the arena between matches. |
| Competitor | Individual entering one or more robots. |
| Driver | Person actively controlling a robot during a match. |

---

# Official Hardware Modules

| Official Name | Abbreviation |
|---------------|--------------|
| BattleStation Core Controller | BSCC |
| BattleStation Bus | BSBus |
| BattleStation Driver Station | BSDS |
| BattleStation Referee Station | BSRS |
| BattleStation Safety Module | BSSM |
| BattleStation Public Display | BSPD |

Future modules shall follow the same naming convention.

---

# Official Software Modules

Software modules shall use descriptive names that communicate responsibility.

Examples:

- Tournament Manager
- Registration Manager
- Inspection Manager
- Bracket Manager
- Match Engine
- Safety Manager
- Hardware Interface
- Web Services
- Database Manager
- Reporting Manager
- Configuration Manager
- System Monitor

---

# User Interface Naming

BattleStation user interfaces shall identify the workstation rather than the individual using it.

Examples:

- Mission Control
- Registration Station
- Inspection Station
- Driver Station
- Referee Station
- Public Display

This allows software to remain role-independent while clearly identifying the purpose of each interface.

---

# Capitalization Standards

The following names shall always be capitalized exactly as shown:

- BattleStation
- Battle Commander
- Mission Control
- BattleStation Core Controller
- BattleStation Bus
- Driver Station
- Referee Station
- Registration Station
- Inspection Station
- Public Display

---

# Abbreviations

| Abbreviation | Meaning |
|--------------|---------|
| BS | BattleStation |
| BSCC | BattleStation Core Controller |
| BSBus | BattleStation Bus |
| BSDS | BattleStation Driver Station |
| BSRS | BattleStation Referee Station |
| BSSM | BattleStation Safety Module |
| BSPD | BattleStation Public Display |

Additional abbreviations shall be added to this document as the project evolves.

---

# Naming Guidelines

When naming future hardware, software, documentation, or interfaces:

- Prefer descriptive names.
- Maintain consistency with existing terminology.
- Avoid unnecessary abbreviations.
- Avoid duplicate terminology.
- Prefer responsibility-oriented names over implementation-oriented names.
- Follow the BattleStation theme.
- Favor clarity over creativity.

---

# Design Principle

Consistent terminology improves communication, documentation quality, software readability, hardware labeling, interface consistency, and long-term maintainability.

Every component shall have one official name.

Every official name shall have one meaning.

---

# Related Documents

- `00_Project_Charter.md`
- `01_Mission_Statement.md`
- `05_System_Modules.md`
- `09_Requirements_Specification.md`
- `14_Software_Architecture.md`
- `15_Wiring_Architecture.md`
- `19_BattleStation_Style_Guide.md`