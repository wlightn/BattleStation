# Engineering Decision Record 001

| Item | Value |
|------|-------|
| Decision ID | EDR-001 |
| Title | Separation of BattleStation Application Services and Core Controller |
| Version | 1.0 |
| Status | Accepted |
| Date | 2026-08-03 |

---

# Background

Early BattleStation concepts combined tournament management software and field hardware control within a single Raspberry Pi-based system.

As architectural responsibilities became better understood, it became apparent that two fundamentally different responsibilities existed:

- Tournament management
- Real-time hardware coordination

These responsibilities evolved independently during Chapter 1 engineering.

---

# Problem

Combining tournament management and real-time hardware control within one implementation unnecessarily coupled software, infrastructure, and hardware.

This reduced flexibility and limited future deployment options.

---

# Decision

BattleStation shall separate tournament management from field hardware coordination.

The architecture consists of:

- BattleStation Application Services
- BattleStation Core Controller

Application Services coordinate tournament operation.

The Core Controller coordinates field hardware.

Both communicate through documented interfaces.

---

# Infrastructure

BattleStation Application Services consume infrastructure services rather than providing them directly.

Current engineering direction utilizes HomeStation as the infrastructure platform.

The BattleStation architecture remains independent of any specific infrastructure implementation.

---

# Architectural Result

BattleStation architecture becomes:

```text
BattleStation
│
├── Application Services
│
├── Core Controller
│
├── BattleStation Bus
│
└── Distributed Modules
```

Infrastructure hosts Application Services.

Infrastructure is not itself part of the BattleStation architecture.

---

# Consequences

Positive outcomes include:

- Clear separation of responsibilities.
- Independent evolution of software and hardware.
- Simplified hardware replacement.
- Improved deployment flexibility.
- Improved maintainability.
- Improved long-term scalability.
- Greater implementation independence.

---

# Design Principle

Architectural responsibilities shall remain independent of implementation technologies.

Infrastructure may evolve without requiring architectural redesign.

---

# Status

Accepted.

This decision has been incorporated into:

- Project Charter
- Glossary
- System Modules
- System Definition
- Requirements Specification

No further architectural action is required.

This record is retained to preserve engineering history.