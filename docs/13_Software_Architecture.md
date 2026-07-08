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
