# BattleStation Glossary & Naming Convention

| Item | Value |
|------|-------|
| Document | BattleStation Glossary & Naming Convention |
| Version | 0.1 |
| Status | Reviewed |
| Last Updated | 2026-07-08 |

---

# Purpose

This document defines the official terminology, naming conventions, abbreviations, and capitalization used throughout the BattleStation project.

The purpose of this document is to ensure consistency across all documentation, software, hardware, CAD models, wiring diagrams, user interfaces, and future releases.

Whenever terminology conflicts exist, this document shall be considered the authoritative source.

---

# Naming Philosophy

BattleStation terminology should:

- Be professional.
- Be descriptive.
- Be consistent.
- Be easy to understand.
- Support the BattleStation theme without becoming gimmicky.

Where possible, names should reflect real-world command, engineering, and mission control environments.

---

# Official System Names

| Official Name | Description |
|---------------|-------------|
| BattleStation | Complete tournament management system. |
| BattleStation Server | Primary application server running BattleStation software. |
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
| BattleStation Server | BSS |
| BattleStation Core Controller | BSCC |
| BattleStation Bus | BSBus |
| BattleStation Driver Station | BSDS |
| BattleStation Referee Station | BSRS |
| BattleStation Safety Module | BSSM |
| BattleStation Public Display | BSPD |

Future modules shall follow the same naming convention.

---

# Official Software Modules

Software modules shall use descriptive names.

Examples:

- Tournament Manager
- Registration Manager
- Inspection Manager
- Bracket Manager
- Match Engine
- Safety Manager
- Hardware Interface
- Web Server
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

This allows the software to remain role-independent while clearly identifying the purpose of each interface.

---

# Capitalization Standards

The following names shall always be capitalized exactly as shown:

- BattleStation
- Battle Commander
- Mission Control
- BattleStation Server
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
| BSS | BattleStation Server |
| BSCC | BattleStation Core Controller |
| BSBus | BattleStation Bus |
| BSDS | BattleStation Driver Station |
| BSRS | BattleStation Referee Station |
| BSSM | BattleStation Safety Module |
| BSPD | BattleStation Public Display |

Additional abbreviations shall be added to this document as the project evolves.

---

# Naming Guidelines

When naming future hardware, software, or documentation:

- Prefer descriptive names.
- Maintain consistency with existing terminology.
- Avoid unnecessary abbreviations.
- Avoid duplicate terminology.
- Follow the BattleStation theme.
- Favor clarity over creativity.

---

# Design Principle

Consistent terminology improves communication, documentation quality, software readability, hardware labeling, and long-term maintainability.

Every component should have one official name.

Every official name should have one meaning.

---

# Related Documents

- 00_Project_Charter.md
- 01_Mission_Statement.md
- 04_System_Modules.md
- 08_Requirements_Specification.md
- 13_Software_Architecture.md
- 14_Wiring_Architecture.md
- 18_BattleStation_Style_Guide.md (Future)