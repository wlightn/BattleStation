# BattleStation Coding Standards

| Item | Value |
|------|-------|
| Document | Coding Standards |
| Version | 0.1 |
| Status | Reviewed |
| Last Updated | 2026-07-13 |

---

# Purpose

This document defines the coding standards for the BattleStation project.

These standards are intended to keep the codebase understandable, reliable, modular, testable, and maintainable throughout the life of the project.

The BattleStation codebase shall favor clarity, maintainability, and reliability over cleverness or unnecessary optimization.

---

# Scope

These standards apply to:

- BattleStation Server software
- Mission Control
- Browser-based interfaces
- Database code
- Hardware communication software
- Module firmware
- Testing tools
- Maintenance utilities
- Supporting scripts

Language-specific standards may be added later, but they shall remain consistent with the principles defined in this document.

---

# Core Principles

## Clarity First

Code shall be easy to read and understand.

A straightforward implementation is preferred over a shorter or more complicated solution.

Code should communicate its purpose without requiring extensive interpretation.

---

## One Responsibility per Module

Each software module shall have one clearly defined responsibility.

Examples:

- Registration Manager handles registration.
- Match Engine handles match operation.
- Safety Manager handles safety behavior.
- Hardware Interface handles communication with physical modules.

A module shall not take responsibility for unrelated system behavior.

---

## Small, Focused Functions

Functions should perform one logical task.

Large functions should be divided into smaller functions when doing so improves:

- Readability
- Testing
- Reuse
- Error handling
- Maintenance

Function names shall describe the action they perform.

Examples:

```python
start_match()
pause_match()
record_robot_weight()
generate_bracket()
check_module_health()
```

Avoid vague names such as:

```python
do_work()
handle_stuff()
process_data()
run_thing()
```

---

# Naming Standards

Names shall be descriptive and consistent with:

- `02_Glossary_and_Naming_Convention.md`
- `14_Software_Architecture.md`
- `20_Design_Principles.md`

## Variables

Variable names shall describe the information they contain.

Preferred:

```python
match_time_remaining
red_driver_ready
official_robot_weight
arena_door_closed
```

Avoid:

```python
x
temp
data1
thing
flag2
```

Short variable names may be used only where their meaning is immediately obvious, such as a small loop index.

---

## Functions

Function names should use action-oriented language.

Examples:

```python
create_event()
load_robot_profile()
approve_inspection()
send_module_command()
```

---

## Classes

Class names shall represent the object or responsibility they model.

Examples:

```python
TournamentManager
MatchEngine
SafetyManager
ModuleHealthMonitor
```

---

## Constants

Named constants shall be used instead of unexplained values.

Preferred:

```python
MAX_MATCH_DURATION_SECONDS = 180
DEFAULT_ARENA_RESET_SECONDS = 60
MAX_UNSTICKS_PER_DRIVER = 1
```

Avoid:

```python
if match_time > 180:
```

Unexplained literal values are commonly called magic numbers and should be avoided.

---

# Modularity

BattleStation software shall be organized into independent packages and modules.

Modules shall communicate through defined interfaces rather than directly modifying each other's internal data.

A change within one module should not require unrelated modules to be rewritten.

Shared functionality shall be placed in an appropriate shared package rather than duplicated.

---

# Separation of Responsibilities

The following concerns shall remain separated whenever practical:

- Tournament rules
- User-interface presentation
- Database storage
- Hardware communication
- Safety logic
- Configuration
- Reporting
- System diagnostics

For example, the Match Engine may request that a light be activated, but it should not contain the low-level CAN or BSBus implementation used to activate that light.

---

# Hardware Abstraction

Higher-level software shall not depend directly on specific hardware models.

The Hardware Interface shall translate application commands into hardware communication.

Preferred:

```python
hardware_interface.set_red_corner_light(True)
```

Avoid placing hardware-specific communication throughout the Match Engine or user-interface code.

This allows hardware to change without requiring major application rewrites.

---

# Configuration

Values that may vary by event or installation shall be configurable.

Examples include:

- Match duration
- Arena reset time
- Weight limits
- Weight tolerance
- Enabled modules
- Network settings
- Inspection templates

Configurable values shall not be hard-coded throughout the application.

Safe default values may be provided.

---

# Error Handling

Errors shall be handled intentionally.

The software shall not silently ignore unexpected failures.

Errors should be classified according to their operational effect:

- Informational
- Warning
- Alarm
- Lockout

Critical safety failures shall use safe default behavior.

Error messages shall explain:

- What failed
- Why it matters
- What action may resolve it

Where practical, errors shall be written to the system log.

---

# Safety-Critical Code

Safety-related behavior shall be simple, explicit, and independently testable.

Safety code shall:

- Fail safely.
- Avoid unnecessary dependencies.
- Use clearly defined states.
- Log safety events.
- Prevent unsafe operation.
- Remain separate from presentation-only features.

Convenience features shall never override safety logic.

Critical safety faults shall not be bypassed through ordinary user-interface controls.

---

# State Management

Tournament and match behavior shall follow documented state machines.

State transitions shall occur through defined commands.

Hardware buttons, Mission Control controls, and automated safety triggers shall use the same internal state-management system.

Code shall not directly alter match state from unrelated modules.

Every significant state transition shall be logged.

---

# Database Standards

Database access shall occur through the Database Manager or a defined data-access layer.

Application modules shall not contain scattered database queries when a shared interface can be used.

Database operations shall:

- Validate input.
- Preserve referential integrity.
- Handle failures.
- Avoid partial updates.
- Support backup and recovery.
- Record timestamps where appropriate.

Schema changes shall be documented and version-controlled.

---

# User Interface Standards

User-interface code shall remain separate from tournament business logic.

Interfaces shall call defined application services rather than reproducing logic independently.

For example, Mission Control and a hardware Pause button shall both call the same match pause command.

User interfaces shall display clear states and actionable errors.

Detailed visual requirements will be defined in:

- `19_Style_Guide.md`
- `22_Interface_Standards.md`

---

# Comments and Documentation

Comments shall explain why code exists or why an unusual decision was made.

Avoid comments that merely repeat the code.

Poor example:

```python
# Add one to match number
match_number += 1
```

Better example:

```python
# Match numbers are one-based because they are displayed directly to competitors.
match_number += 1
```

Public functions, classes, and modules should include concise documentation describing:

- Purpose
- Inputs
- Outputs
- Important side effects
- Exceptions or failure behavior

---

# Type Information

Python code should use type hints where practical.

Example:

```python
def calculate_remaining_time(
    match_duration_seconds: int,
    elapsed_seconds: int,
) -> int:
    return max(0, match_duration_seconds - elapsed_seconds)
```

Type hints improve readability, editor assistance, testing, and maintenance.

Firmware written in C or C++ shall use explicit and appropriate data types.

---

# Testing Requirements

Every meaningful software module shall be independently testable.

New behavior should include tests where practical.

Tests shall cover:

- Expected operation
- Invalid input
- Boundary conditions
- Fault conditions
- Safety behavior
- Recovery behavior

A bug fix should include a regression test when practical.

All tests shall remain traceable to the Test Plan and applicable requirements.

---

# Dependencies

External dependencies shall be kept to a reasonable minimum.

A dependency should be added only when it provides a clear benefit over implementing the required behavior internally.

Before adding a dependency, consider:

- Maintenance status
- License
- Security history
- Linux compatibility
- Offline availability
- Long-term support
- Project stability

Dependency versions shall be recorded and controlled.

---

# Security

Even though BattleStation operates primarily on a local network, security shall be considered throughout development.

The software shall:

- Validate user input.
- Protect administrative functions.
- Avoid exposing unnecessary network services.
- Store credentials securely.
- Avoid embedding passwords or secrets in source code.
- Log authentication and permission failures where appropriate.

Safety-critical functions shall not depend on public Internet services.

---

# Logging

The system shall use structured and consistent logging.

Logs should include:

- Timestamp
- Severity
- Software module
- Event description
- Relevant event, match, robot, or module identifier

Logs shall help diagnose faults without requiring the system to be reproduced immediately.

Sensitive information shall not be written to logs unnecessarily.

---

# Complete Master File Workflow

Meaningful revisions shall be delivered as complete, internally consistent master files whenever practical.

Partial code patches should be avoided when replacing the complete file reduces the chance of:

- Pasting code into the wrong location
- Duplicate logic
- Missing imports
- Inconsistent naming
- Formatting mistakes
- Documentation drift

The workflow for a meaningful source-file revision is:

1. Discuss the change.
2. Confirm expected behavior.
3. Generate the complete master file.
4. Review the file.
5. Run applicable tests.
6. Commit the revision.
7. Update related documentation and changelog entries when required.

Small corrections may be made directly when replacing an entire file would create unnecessary risk.

---

# Backward Compatibility

Existing documented interfaces shall remain compatible whenever practical.

Changes that may break compatibility shall:

- Be intentional.
- Be documented.
- Include a migration plan when needed.
- Update affected tests.
- Update the Decision Log when architecturally significant.

Version 1 behavior shall not be changed casually after the Chapter 1 architecture freeze.

---

# Code Review Checklist

Before committing meaningful code, verify:

- The purpose of the change is understood.
- The code follows the documented architecture.
- Names follow the project glossary.
- Functions and modules have focused responsibilities.
- No unnecessary duplication was introduced.
- Errors are handled intentionally.
- Safety behavior remains correct.
- Tests pass.
- Documentation is updated where required.
- The application remains in a working state.

---

# Git Standards

Commits should represent one logical unit of work.

Commit messages shall clearly describe what changed.

Preferred examples:

```text
Implemented match pause state transitions
Added registration data validation
Created BattleStation database schema
Added Core Controller health monitoring
Fixed bracket advancement after a bye
```

Avoid messages such as:

```text
Update
Changes
Fix stuff
Work
Test
```

Every commit should leave the repository in a coherent and usable state whenever practical.

---

# Language-Specific Standards

## Python

Python shall be the primary language for the BattleStation Server unless an approved decision changes the architecture.

Python code should generally follow:

- PEP 8 formatting
- Type hints
- Clear package boundaries
- Automated formatting and linting when selected
- Virtual environments for dependency isolation

Exact tools will be selected during Chapter 2.

---

## C and C++

C or C++ may be used for embedded firmware and hardware modules.

Firmware code shall:

- Remain modular.
- Avoid blocking behavior where it could interfere with safety or communication.
- Use named constants.
- Validate incoming messages.
- Handle communication loss safely.
- Include hardware-level tests where practical.

---

# Definition of Acceptable Code

BattleStation code is acceptable when it is:

- Correct
- Understandable
- Testable
- Maintainable
- Documented
- Consistent with the architecture
- Safe for its intended responsibility

Code is not considered complete merely because it runs.

---

# Related Documents

- `02_Glossary_and_Naming_Convention.md`
- `07_Match_State_Machine.md`
- `09_Requirements_Specification.md`
- `10_Decision_Log.md`
- `12_Chapters.md`
- `14_Software_Architecture.md`
- `16_Test_Plan.md`
- `20_Design_Principles.md`
- `22_Interface_Standards.md`
- `23_Release_Process.md`