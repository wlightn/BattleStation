## Match States

### Idle
No match is currently active.

### Match Queued
A match has been selected from the bracket and is ready to begin setup.

### Drivers Called
The assigned drivers have been called to the arena.

### Introductions
BattleStation presents the match, drivers, and robots.

### Waiting for Ready
Both drivers must press the Ready button before the match can begin.

### Countdown
BattleStation performs the pre-match countdown.

### Running
The match timer is active and the match is in progress.

### Paused
The match timer is stopped due to an unstick, referee pause, coordinator pause, arena issue, or safety event.

### Safety Stop
The match has been stopped due to an automatic safety trigger such as the arena door opening during an active match.

### Match Complete
The match has ended and is waiting for the result to be confirmed.

### Result Recorded
The winner has been recorded and the bracket has been advanced.

### Arena Reset
A reset timer runs between matches while the arena is cleaned and the next match is prepared.

---

## Normal Match Flow

```text
Idle
  ↓
Match Queued
  ↓
Drivers Called
  ↓
Introductions
  ↓
Waiting for Ready
  ↓
Countdown
  ↓
Running
  ↓
Match Complete
  ↓
Result Recorded
  ↓
Arena Reset
  ↓
Match Queued
```

---

## Pause Flow

```text
Running
   ↓
Paused
   ↓
Countdown (optional)
   ↓
Running
```

A paused match may either resume immediately or restart with a short countdown.

---

## Safety Stop Flow

```text
Running
   ↓
Safety Stop
   ↓
Paused
   ↓
Countdown
   ↓
Running
```

The referee or coordinator determines whether the match resumes or ends.

---

## Match Completion

A match may end by:

- Timer expiration
- Tap Out
- Knockout
- Referee decision
- Coordinator override
- Safety Stop

After completion:

1. Winner is selected.
2. Match result is stored.
3. Bracket advances automatically.
4. Public display updates.
5. Arena Reset begins.

---

## Unstick Tracking

Each competitor is allowed one unstick attempt per match.

BattleStation records:

- Red Driver Unstick Used
- Blue Driver Unstick Used
- Match Time Remaining
- Reason for Pause
- Time of Event

---

## Door Safety

The arena door sensor is only active during:

- Countdown
- Running

The arena door sensor is ignored during:

- Idle
- Match Queued
- Drivers Called
- Introductions
- Waiting for Ready
- Paused
- Match Complete
- Result Recorded
- Arena Reset

If the door opens during an active match:

1. Match timer stops immediately.
2. State changes to Safety Stop.
3. Red beacon begins flashing.
4. Audible alarm sounds.
5. Public display shows a safety warning.
6. Event is written to the system log.
7. Coordinator or Referee must acknowledge before continuing.

---

## Design Principles

- Every match follows the same state machine.
- Hardware buttons and software controls perform identical actions.
- Every state transition is logged.
- The Public Display always reflects the current match state.
- The BattleStation Core display always shows the current state.
- Safety always overrides normal tournament operation.