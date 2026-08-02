# Match State Machine

| Item | Value |
|------|-------|
| Document | Match State Machine |
| Version | 1.0 |
| Status | Constitutional Baseline |
| Last Updated | 2026-08-03 |

---

# Purpose

This document defines the official BattleStation match state machine.

The Match State Machine governs the lifecycle of a single tournament match.

Every BattleStation match shall progress through these states using documented transitions.

No implementation may introduce additional operational states without constitutional revision.

---

# State Machine Philosophy

The Match State Machine exists to ensure:

- Safe tournament operation
- Predictable system behavior
- Consistent operator experience
- Repeatable software implementation
- Complete event traceability

Each state has one clearly defined purpose.

Every transition shall occur intentionally and shall be recorded by BattleStation.

---

# Match States

## Idle

No match is currently active.

BattleStation is awaiting selection of the next scheduled match.

---

## Match Queued

A match has been selected from the tournament bracket.

BattleStation prepares the required information and resources before driver notification.

---

## Drivers Called

The assigned competitors have been instructed to report to the arena.

BattleStation monitors progress toward match readiness.

---

## Introductions

BattleStation presents:

- Match information
- Driver names
- Robot names
- Arena presentation information

This state prepares competitors, officials, and spectators for match start.

---

## Waiting for Ready

BattleStation waits for all required Driver Ready confirmations.

The system shall not advance until all required readiness conditions have been satisfied or an authorized override has been performed.

---

## Countdown

BattleStation performs the official pre-match countdown.

Safety monitoring remains active throughout this state.

Successful completion advances the system to Running.

---

## Running

The official match is in progress.

BattleStation manages:

- Match timer
- Match state
- Safety monitoring
- Referee requests
- Driver requests
- System monitoring

---

## Paused

The official match timer is suspended.

Pause may occur because of:

- Referee request
- Battle Commander request
- Unstick
- Arena issue
- Other authorized operational events

---

## Safety Stop

BattleStation has automatically interrupted the match because a monitored safety condition requires immediate action.

Tournament operation remains suspended until the required acknowledgement and recovery procedures have completed.

---

## Match Complete

The official match has ended.

BattleStation awaits confirmation of the official match result.

---

## Result Recorded

The official result has been accepted.

BattleStation records the result and advances the tournament bracket.

---

## Arena Reset

BattleStation prepares for the next scheduled match.

During Arena Reset:

- Arena Crew services the arena.
- Public information is updated.
- Next competitors may be notified.
- Reset timing is displayed where appropriate.

Successful completion returns BattleStation to Match Queued.