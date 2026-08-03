# BattleStation Project Charter

| Item | Value |
|------|-------|
| Document | Project Charter |
| Version | 1.0 |
| Status | Constitutional Baseline |
| Last Updated | 2026-08-02 |

---

# Purpose

This Project Charter establishes the constitutional foundation of the BattleStation project by defining its purpose, authority, scope, objectives, constraints, governance, and success criteria.

BattleStation is a complete, modular robot combat tournament management and arena-control system.

The project exists to reduce the workload placed on event organizers, improve tournament flow and safety, preserve event information, and provide competitors and spectators with a professional event experience.

This charter is the highest-level engineering definition of the BattleStation project.

All BattleStation requirements, architecture, software, hardware, interfaces, tests, and releases shall remain consistent with this charter.

BattleStation is a project within the **wLIGHTn** organization. Organizational departments publish standards and provide specialist expertise within their respective domains. BattleStation consumes those published standards while remaining responsible for the engineering of the BattleStation system.

---

# Project Vision

BattleStation shall provide a complete operational platform for managing robot combat tournaments from registration through final reporting.

The system shall combine:

- Tournament management
- Competitor and robot registration
- Robot inspection
- Bracket generation
- Match sequencing
- Driver readiness
- Official match timing
- Arena safety monitoring
- Distributed hardware control
- Public event information
- Results and reporting
- System diagnostics

BattleStation shall look, feel, and operate like a commercial event management system rather than a collection of unrelated hobby electronics.

---

# Project Motto

> **BattleStation should look, feel, and operate like a commercial event management system.**

---

# Engineering Motto

> **Professional tournament management through thoughtful engineering.**

---

# Problem Statement

Running a robot combat tournament requires the event organizer to coordinate many activities simultaneously.

These activities include:

- Registration
- Robot inspection
- Bracket management
- Driver staging
- Match introductions
- Match control
- Arena safety
- Results recording
- Public information
- Event reporting

When these functions depend on paper records, spreadsheets, unrelated applications, verbal communication, and manual timing, the tournament organizer must repeatedly switch attention between administrative, technical, and competitive responsibilities.

This creates several risks:

- Registration congestion
- Delayed matches
- Incorrect bracket advancement
- Missed driver calls
- Inconsistent match operation
- Increased coordinator workload
- Incomplete event records
- Reduced spectator engagement
- Safety information being overlooked

BattleStation addresses these problems by combining tournament administration, arena operation, safety monitoring, hardware control, and reporting into one coordinated system.

---

# Primary Project Goal

BattleStation Version 1.0 shall be capable of operating the complete Battle of Bots tournament from registration through awards and final reporting without requiring paper brackets or external spreadsheets.

The system shall reduce manual event-day work while preserving safe, reliable, and understandable tournament operation.

---

# Initial Deployment

The first planned production deployment of BattleStation is the February 2027 Battle of Bots tournament.

BattleStation shall be designed as a reusable platform capable of supporting future arena sizes, event configurations, and tournament requirements without requiring fundamental architectural redesign.

Although Battle of Bots is the first deployment, BattleStation is engineered as a reusable event-management platform rather than a single-event application.

---

# Project Objectives

BattleStation shall:

1. Automate repetitive tournament-management tasks.
2. Reduce the workload of the Battle Commander.
3. Keep the tournament moving at a consistent pace.
4. Improve event safety through active monitoring and controlled match states.
5. Provide clear information to competitors, officials, and spectators.
6. Support multiple competitors, robots, and tournament classes.
7. Preserve event, robot, match, and result data.
8. Operate without requiring Internet access.
9. Use modular, replaceable hardware and software components.
10. Support future expansion without destabilizing Version 1.
11. Provide a professional and consistent user experience.
12. Remain understandable and maintainable through complete repository documentation.

# Scope

## Version 1 Scope

BattleStation Version 1 shall include the functions required to operate a complete tournament safely and reliably.

Version 1 scope includes:

- Event creation and configuration
- Driver registration
- Support for multiple robots per driver
- Robot registration
- Robot photographs
- Weapon-type selection
- Robot check-in
- Weight recording
- Weight-limit warnings
- Robot inspection
- Class-specific inspection requirements
- Approval control before bracket entry
- Randomized double-elimination bracket generation
- Automatic winner advancement
- Automatic loser-bracket placement
- Current-match selection
- Next-match identification
- Driver calls
- Match introductions
- Driver Ready controls
- Match countdown
- Official match timer
- Pause and resume
- Unstick tracking
- Tap Out handling
- Match completion and result recording
- Arena reset timing
- Tournament progression
- Public match information
- Arena door monitoring
- Emergency and safety-stop behavior
- Audible and visual safety alarms
- Module-health monitoring
- Startup verification
- Local web interfaces
- Local BattleStation network
- Event logging
- Final standings
- Completed brackets
- Event reports
- Tournament data archiving

---

## Version 2 Scope

Version 2 shall contain enhancements that improve the event experience but are not required for safe Version 1 tournament operation.

Examples include:

- Pit Audio
- Video-system control
- Event recap generation
- Long-term driver statistics
- Long-term robot statistics
- Enhanced announcements
- Expanded lighting behaviors
- Returning competitor automation
- Additional wireless non-critical modules

Version 2 work shall not delay completion or stabilization of Version 1.

---

## Future Scope

Future development may include:

- Multiple arenas
- League management
- Cloud synchronization
- Remote event dashboards
- Mobile applications
- Live-stream integration
- Advanced statistics
- Additional competition formats
- AI-assisted event analysis
- Expanded tournament networking

Future possibilities may influence extensibility but shall not introduce unnecessary complexity into the Version 1 implementation.

---

# Out of Scope for Chapter 1

Chapter 1 does not include production software or completed physical hardware.

Chapter 1 establishes the engineering foundation required to begin implementation.

The following belong to later Chapters:

- Production application code
- Final database implementation
- Final user interfaces
- Firmware implementation
- Final electronics
- PCB design
- Final enclosure design
- Production wiring harnesses
- Full system integration
- Live tournament validation
- Production release packaging

---

# System Boundaries

BattleStation includes:

- BattleStation Application Services
- BattleStation Core Controller
- Mission Control
- Registration Station
- Inspection Station
- Driver Stations
- Referee Station
- Arena Safety Module
- Arena Lighting Module
- Public Display
- BattleStation Bus
- Tournament data services
- Local web interfaces
- Reporting and archival functions

BattleStation may communicate with external or optional systems but shall not depend on them for core tournament operation.

Examples of external or optional systems include:

- Shared infrastructure services
- Facility Internet
- Video-recording equipment
- Pit Audio equipment
- Additional displays
- Future cloud services

BattleStation consumes external services through documented interfaces. The identity or implementation of those services does not alter BattleStation's architectural responsibilities.

---

# Primary Users

## Battle Commander

The Battle Commander is the primary BattleStation operator.

The Battle Commander oversees:

- Event setup
- Registration approval
- Inspection approval
- Bracket generation
- Match operation
- System status
- Warning acknowledgement
- Permitted operational overrides
- Results
- Reports

---

## Competitors and Drivers

Competitors register one or more robots.

Drivers operate robots during matches and interact with Driver Stations for Ready and Tap Out functions.

---

## Referee

The Referee oversees:

- Match fairness
- Rule enforcement
- Pauses
- Unsticks
- Arena issues
- Match outcomes

---

## Inspector

The Inspector verifies:

- Weight
- Safety
- Class compliance
- Weapon information
- Special construction requirements
- Inspection approval

---

## Registration Operator

The Registration Operator assists competitors with event check-in and registration data.

---

## Arena Crew

Arena Crew members prepare, clean, and reset the arena between matches.

---

## Spectators

Spectators receive event information through the Public Display.

---

## System Administrator

The System Administrator maintains the infrastructure required to support BattleStation operation, including:

- Software deployment
- Hardware configuration
- System configuration
- Backups
- Logs
- Updates
- Diagnostics

Operational infrastructure may be provided by approved organizational platforms without changing BattleStation's architectural responsibilities.

---

One person may perform multiple roles at smaller events.

# Operational Philosophy

BattleStation exists to keep the tournament moving while reducing Battle Commander workload.

The system shall:

- Make the current event state obvious.
- Identify the current and next matches.
- Minimize unnecessary operator input.
- Prevent invalid transitions.
- Provide useful information during arena reset periods.
- Automate bracket progression and reporting.
- Warn only when operator attention is required.
- Allow unused optional modules to be disabled cleanly.
- Preserve manual fallback options for non-critical functions where practical.

---

# Safety Philosophy

Safety has the highest system priority.

Safety behavior shall override normal tournament operation.

Critical safety faults shall not be bypassed through ordinary user controls.

BattleStation shall support:

- Arena door monitoring
- Emergency Stop handling
- Match timer interruption
- Safety Stop state
- Audible alarm activation
- Visual alarm activation
- Safety event logging
- Required acknowledgement
- Safe failure behavior

Convenience, presentation, reporting, and optional features shall never override safety logic.

---

# Reliability Philosophy

BattleStation shall be designed so that failure of a non-critical feature does not unnecessarily stop tournament operation.

Modules shall be classified as:

- Critical
- Operational
- Optional

Critical failures may prevent match operation.

Operational failures may allow manual fallback.

Optional failures shall not prevent tournament operation.

The system shall communicate faults according to their impact:

- Informational
- Warning
- Alarm
- Lockout

Every detected fault shall have an intentional system response.

---

# Offline-First Requirement

BattleStation shall operate entirely on a private local network without requiring Internet access.

Facility Internet may be shared with connected devices when available, but loss of Internet shall not interrupt tournament operation.

Critical safety, timing, and event-control functions shall not depend upon public Internet services.

---

# Modularity and Serviceability

BattleStation shall use modular hardware and software architecture.

Modules shall:

- Have clearly defined responsibilities.
- Communicate through documented interfaces.
- Be independently testable.
- Be replaceable without redesigning unrelated components.
- Report status and faults where applicable.
- Support future upgrades.

The BattleStation Core Controller shall remain architecturally independent of the infrastructure hosting BattleStation services.

Infrastructure may evolve without requiring redesign of:

- BattleStation Core
- BattleStation Bus
- Event modules
- Field wiring
- Event workflows

Likewise, infrastructure evolution shall not require changes to BattleStation's architectural responsibilities.

---

# Technical Direction

The current approved technical direction includes:

- Containerized BattleStation deployment
- Headless automatic startup
- Local browser-based interfaces
- Private local network
- BattleStation Core Controller
- BattleStation Bus (BSBus) for distributed module communication
- CAN as the initial candidate BSBus physical layer
- CAT6 as the preferred candidate field cable
- RJ45 as the preferred candidate field connector
- Pass-through module connections
- Local power for high-current modules
- Modular enclosures
- Field-replaceable cables
- Externalized configuration
- Infrastructure services consumed through documented interfaces

Specific implementation technologies may evolve during future Chapters provided they remain consistent with the approved architecture and responsibilities.

Deployment infrastructure shall satisfy BattleStation's required services without altering the BattleStation architecture.

# Development Philosophy

BattleStation shall follow a documentation-first engineering process.

Engineering work shall progress through disciplined discovery, review, documentation, and implementation rather than implementation-driven design.

The standard engineering workflow is:

1. Discover
2. Discuss
3. Review
4. Decide
5. Document
6. Generate the complete master artifact
7. Review the artifact
8. Commit to the repository
9. Implement
10. Validate
11. Release

The project shall favor:

- Clarity over cleverness
- Reliability over unnecessary complexity
- Maintainability over short-term speed
- Complete master-file revisions over scattered patches
- Documented interfaces over undocumented coupling
- Intentional decisions over accidental behavior
- Architectural consistency over implementation convenience

---

# Repository Authority

The committed BattleStation repository is the authoritative source of project knowledge.

Once information has been reviewed and committed, the repository supersedes:

- Prior conversations
- Informal notes
- Personal memory
- Uncommitted drafts
- Undocumented assumptions

BattleStation shall reference published organizational standards rather than duplicate them.

Architecture shall remain understandable without the original architects being present.

Engineering decisions shall be traceable through the repository and supporting engineering records.

---

# Project Governance

BattleStation is a project within the wLIGHTn organization.

Organizational departments publish standards, provide specialist expertise, and steward their respective disciplines.

BattleStation consumes those standards while remaining responsible for the engineering, implementation, and operation of the BattleStation system.

---

## Chief Systems Architect

**Robert Tucker**

The Chief Systems Architect is responsible for:

- Product vision
- Tournament requirements
- Operational requirements
- Mechanical design
- Fabrication
- System direction
- Final architectural approval

---

## The Engineer

**OpenAI ChatGPT ("The Engineer")**

The Engineer supports:

- Systems engineering
- Architecture development
- Documentation
- Design review
- Technical analysis
- Software planning
- Engineering consistency
- Systems navigation

The Engineer serves as an engineering advisor and reviewer. Final engineering authority remains with the Chief Systems Architect.

---

## Decision Authority

Final project approval rests with the Chief Systems Architect.

Significant technical decisions shall be:

- Discussed
- Documented
- Reviewed
- Recorded in the Decision Log
- Committed to the repository

---

# Constraints

BattleStation development is subject to the following constraints:

- Version 1 must be ready for the February 2027 Battle of Bots tournament.
- Development time is limited.
- The Battle Commander may also be a tournament competitor.
- Event-day operation must minimize dependency on one person.
- The system must operate without Internet access.
- Hardware must be transportable and serviceable.
- Arena debris may affect exposed equipment.
- Modules and wiring must support repeated setup and teardown.
- Component selection should remain cost-conscious.
- Optional features shall not delay completion of core functionality.
- Safety shall never be compromised for schedule or convenience.
- BattleStation shall conform to published organizational standards where applicable.
- Final visual documentation depends upon the publication of official BattleStation branding standards.

# CR-001 Change Summary

## Architectural Changes

None.

## Organizational Changes

- Added relationship to the wLIGHTn organization.
- Clarified organizational standards are referenced rather than duplicated.

## Technical Direction

- Removed implementation-specific infrastructure references.
- Replaced platform-specific wording with responsibility-based wording.

## Governance

- Clarified Engineering advisory role.
- Clarified organizational department relationship.

## Repository

- Strengthened repository authority.

## Result

No architectural intent changed.

Document clarity, maintainability, and organizational consistency improved.

# Assumptions

Chapter 1 is based upon the following assumptions:

- Battle of Bots is currently an annual event.
- The February 2027 event will be the second annual event.
- The initial primary competition class uses a 500 g maximum robot weight.
- Additional classes may be configured.
- A proposed Plastic Ant class may use a 454 g maximum weight and class-specific construction inspection.
- Competitors may enter multiple robots.
- Mission Control and event workstations communicate through the local BattleStation network.
- The system will be assembled, transported, installed, operated, and removed for each event.
- Manual fallback procedures may be used for non-critical functions.
- Final implementation technologies may evolve during prototyping without changing the approved architecture.

---

# Major Risks

Major project risks include:

- Expanding Version 1 scope.
- Insufficient implementation time.
- Hardware integration delays.
- Incomplete safety validation.
- Network instability.
- Inadequate tournament simulation.
- Undocumented architectural changes.
- Overdependence on one operator.
- Uncontrolled hardware substitutions.
- Failure to maintain repository consistency.
- Delaying implementation through unnecessary redesign.

These risks shall be managed through:

- Version Buckets
- Chapter Planning
- Architecture Review
- Decision Logging
- Complete Master Revisions
- Requirements Traceability
- Test Planning
- Regression Testing
- Architecture Freeze
- Controlled Release Procedures

---

# Chapter 1 Objective

Chapter 1 — **Building the Foundation** — establishes the complete engineering baseline required for implementation.

Chapter 1 includes:

- Project definition
- Mission
- Naming
- Roles
- Modules
- Tournament workflow
- Match behavior
- System definition
- Requirements
- Decisions
- Roadmap
- Hardware BOM
- Software architecture
- Wiring architecture
- Test strategy
- Design principles
- Coding standards
- Interface standards
- Release process
- Engineering review
- Blind architecture review

Chapter 1 intentionally defines responsibilities, architecture, interfaces, and engineering process before implementation begins.

---

# Chapter 1 Acceptance

Chapter 1 shall not be considered complete merely because its documents exist.

It shall be considered complete only after successfully passing the established engineering review process.

## ER-1 — Engineering Review

The Engineer shall evaluate the committed repository using complete engineering context to verify:

- Architectural correctness
- Completeness
- Consistency
- Safety
- Testability
- Scope control
- Implementation readiness

---

## CR-1 — Constitutional Revision

Engineering shall evaluate all approved Engineering Refinements discovered during ER-1.

Constitutional Revision shall improve the clarity, consistency, traceability, and maintainability of the repository without changing the approved architecture.

Any proposal that changes architectural intent, responsibilities, or system boundaries shall be deferred for future engineering planning rather than incorporated into Constitutional Revision.

---

## BR-1 — Blind Architecture Review

Junior Engineer #1 shall evaluate only the committed repository with no prior BattleStation or Battle of Bots knowledge.

The Blind Architecture Review shall determine whether an independent engineer can understand:

- What BattleStation is.
- What event it serves.
- Who uses it.
- How it operates.
- How safety works.
- What Version 1 includes.
- How implementation should begin.

Architecture shall remain understandable without the original architects being present.

---

## Final Acceptance

Following successful completion of ER-1, CR-1, and BR-1, Chapter 1 may be formally accepted and frozen as the constitutional engineering baseline for BattleStation Version 1.

---

# Version 1 Success Criteria

BattleStation Version 1.0 is successful when it can:

- Operate a complete tournament from registration through final reports.
- Generate and manage a randomized double-elimination bracket.
- Prevent unapproved robots from entering the bracket.
- Control match states and official timing.
- Manage driver readiness, pauses, unsticks, Tap Out, and results.
- Monitor required arena safety conditions.
- Stop unsafe operation automatically.
- Operate without Internet access.
- Communicate with required hardware modules.
- Display useful event information.
- Preserve complete tournament records.
- Generate final standings and completed brackets.
- Recover safely from expected faults.
- Complete a full tournament simulation.
- Pass all critical acceptance tests.
- Successfully operate the February 2027 Battle of Bots tournament without paper brackets or external spreadsheets.

---

# Project Success

The BattleStation project succeeds when it delivers a professional, reliable, modular, safe, maintainable, and understandable tournament management platform that reduces organizer workload and improves the event experience.

The project shall not be considered successful merely because the system operates.

It shall also be:

- Documented
- Testable
- Serviceable
- Repeatable
- Recoverable
- Expandable
- Understandable by future contributors

BattleStation shall remain understandable, maintainable, and extensible without requiring the continued involvement of its original architects.

---

# Related Documents

- `01_Mission_Statement.md`
- `02_Glossary_and_Naming_Convention.md`
- `03_Version_Buckets.md`
- `04_User_Roles.md`
- `05_System_Modules.md`
- `06_Tournament_Workflow.md`
- `07_Match_State_Machine.md`
- `08_System_Definition.md`
- `09_Requirements_Specification.md`
- `10_Decision_Log.md`
- `11_Project_Journal.md`
- `12_Chapters.md`
- `13_Hardware_BOM.md`
- `14_Software_Architecture.md`
- `15_Wiring_Architecture.md`
- `16_Test_Plan.md`
- `18_Architecture_Review.md`
- `19_BattleStation_Style_Guide.md`
- `20_Design_Principles.md`
- `21_Coding_Standards.md`
- `22_Interface_Standards.md`
- `23_Release_Process.md`
- `CONTRIBUTING.md`