# Contributing to BattleStation

"Professional tournament management through thoughtful engineering."

## Purpose

This document defines the minimum contribution process for BattleStation.

Contributions shall preserve the approved constitutional architecture, remain traceable to controlled requirements and decisions, and include the verification evidence appropriate to the change.

## Begin with the Constitutional Baseline

Before changing BattleStation, contributors shall review the documents relevant to the proposed work. Begin with `DOCUMENT_INDEX.md`, then follow the role-appropriate reading path.

At minimum, implementation contributors shall understand:

- `00_Project_Charter.md`
- `02_Glossary_and_Naming_Convention.md`
- `09_Requirements_Specification.md`
- `10_Decision_Log.md`
- `14_Software_Architecture.md`
- `15_Wiring_Architecture.md`
- `16_Test_Plan.md`
- `20_Design_Principles.md`
- `21_Coding_Standards.md`
- `22_Interface_Standards.md`
- `23_Release_Process.md`

## Preserve the Existing Architecture

Contributors shall:

- Implement approved responsibilities without unnecessary redesign.
- Preserve the separation between Application Services, the BattleStation Core Controller, BSBus, and distributed modules.
- Use official terminology from the Glossary and Naming Convention.
- Keep interfaces explicit and documented.
- Maintain backward compatibility unless an approved change explicitly authorizes incompatibility.
- Prefer modular Python or C++ implementation consistent with the Coding Standards.

## Change Classification

Before implementation, determine whether the proposed work is:

1. **Implementation within the approved baseline** — proceed under the applicable standards and requirements.
2. **A correction to controlled documentation** — update the affected document with traceable rationale.
3. **An architectural or constitutional change** — record and approve the decision through the Decision Log before implementation.

A contribution shall not silently change constitutional behavior through code, firmware, wiring, or hardware selection.

## Development Expectations

Contributors shall:

- Work from a current repository branch.
- Keep changes focused on one coherent purpose.
- Follow `21_Coding_Standards.md` for software and firmware.
- Follow `22_Interface_Standards.md` for system boundaries and communications.
- Update documentation when behavior, interfaces, configuration, or operating procedures change.
- Add or update tests for changed behavior.
- Preserve a running changelog or equivalent engineering history for significant changes.

## Verification and Evidence

Each contribution shall identify the requirement or architectural responsibility it implements or affects.

Verification shall follow `16_Test_Plan.md`. Evidence should include, as applicable:

- Requirement identifiers
- Verification method
- Test or inspection result
- Software and hardware revisions
- Logs, screenshots, measurements, or observations

A change is not complete merely because it compiles or appears to work.

## Review

Before integration, verify that the contribution:

- Preserves constitutional architecture.
- Uses controlled terminology and interfaces.
- Does not introduce undocumented assumptions.
- Includes required documentation and tests.
- Does not create unresolved Critical or Major defects.
- Remains suitable for the release process defined in `23_Release_Process.md`.

## Release Governance

Only changes that satisfy the applicable requirements, verification obligations, and release criteria may enter a controlled release.

Release approval and versioning shall follow:

- `03_Version_Buckets.md`
- `16_Test_Plan.md`
- `23_Release_Process.md`

## Contribution Principle

Contribute to BattleStation by extending the approved system deliberately, documenting discoveries as they occur, and preserving enough evidence that another engineer can understand what changed and why.
