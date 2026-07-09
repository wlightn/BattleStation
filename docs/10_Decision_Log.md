---

# Decision 001

## Title

BattleStation Core Compute Platform

### Status

Open – Under Evaluation

### Date

2026-07-06

### Background

The original BattleStation concept used a Raspberry Pi as both the system controller and application server.

As the project evolved, the responsibilities of the BattleStation Core expanded significantly to include:

- Tournament database
- Local web server
- Coordinator interface
- Registration interface
- Inspection interface
- Public display
- Match engine
- Module communications
- Diagnostics
- Logging
- Report generation
- Local Wi-Fi access point

### Proposal

Evaluate replacing the Raspberry Pi with a Linux-based Mini PC to act as the BattleStation Server.

The server would communicate with the BattleStation Core Controller through a single high-speed connection while dedicated microcontrollers continue handling real-time hardware functions.

### Proposed Architecture

BattleStation Server

- Linux Operating System
- BattleStation Application
- Database
- Web Server
- Reports
- Wi-Fi Access Point
- Local Network Services

↓

Single High-Speed Connection
(Ethernet preferred)

↓

BattleStation Core Controller

- Power Distribution
- BattleStation Bus Interface
- Diagnostics Display
- Safety Electronics
- Module Communications

↓

BattleStation Bus

↓

Driver Stations
Referee Station
Arena Safety Module
Lighting Controller
Future Modules

### Advantages

- Higher processing capability
- Greater memory and storage
- Easier software development
- Easier hardware replacement
- Improved long-term serviceability
- Future expansion without redesign
- Separation of computing hardware from control electronics

### Design Principle

The compute platform shall be replaceable without requiring changes to the BattleStation hardware architecture.

The BattleStation Core Controller and BattleStation Server shall be treated as independent modules.

### Current Leaning

Preferred architecture:

BattleStation Server (Linux Mini PC)

communicating with

BattleStation Core Controller

over a single high-speed connection.

### Decision Deferred

Final selection will be made before software implementation begins after hardware, software, and networking requirements have been fully evaluated.

### Startup Requirement

The BattleStation Server must operate headless in production.

On power-up, the server shall automatically boot Linux and start all required BattleStation services without requiring keyboard, mouse, or monitor input.

The system shall provide maintenance access through SSH, local web interface, or direct keyboard/monitor only when needed.