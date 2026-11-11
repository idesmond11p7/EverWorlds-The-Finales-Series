# Command and Action Protocol

[ID: SHIP-03]
[STATUS: ACTIVE WORKING SPECIFICATION]
[DATE: 2026-11-11]
[SCHEMA: INPUT GRAMMAR / ACTION CONTRACT / PLANNING]
[UPSTREAM: SHIP-01, SHIP-02]
[DOWNSTREAM: SHIP-04, SHIP-06, SHIP-07]
[CONTAINS: One-shot commands, compound actions, conditional plans, action dictionary, OOC channel]
[EXCLUDES: Final syntax lock; scenario-specific command catalogue]
[SUPERSEDES: None]
[LAST-TOUCH: Initial capture]
[MUST-RECHECK: Usability and parser tests]
[MODEL-GRADE: G2]
[EVIDENCE-STATE: AUTHOR-REQUIREMENTS + PROPOSED GRAMMAR]
[OPERATIONAL-STATE: REFERENCE-ONLY]

## 1. Design goal

The player should be able to act through a compact, explicit command language rather than repeatedly narrating every obvious detail in natural-language prose. Commands should be quick to type, contextual, combinable and strict enough to expose ambiguity.

The command language is an interface, not an in-world language. It does not need to be spoken by the character.

## 2. Command classes

### A. One-shot action
A single immediate attempt, such as moving, looking, interacting, speaking, using an item, or taking a defensive action.

### B. Compound action
A short ordered sequence of compatible attempts. The resolver checks each step against the updated state. Later steps are not guaranteed merely because they were typed.

### C. Conditional plan
A longer instruction authored in advance. It describes a decision policy:
- objective and preparation;
- ordered steps;
- conditions that permit or block each step;
- branches in the form IF / THEN / ELSE;
- abort conditions;
- resource and time limits;
- actions that require renewed conscious choice;
- forbidden assumptions.

The player may spend substantial time composing a plan. The plan does not dictate outcomes. It tells the engine how the character should attempt to respond when conditions arise.

### D. OOC / correction
An explicitly out-of-character channel for correcting continuity, clarifying intent, reporting a defect, or requesting a system-level adjustment. OOC text must not accidentally become an in-world action.

## 3. Action contract

Every command is normalized internally into:

`ACTION = {ACTOR, VERB, TARGET, PARAMETERS, INTENT, PRECONDITIONS, TIME_WINDOW, ABORT_RULE, OUTPUT_EXPECTATION}`

- **ACTOR:** defaults to the player's currently controlled character; no repeated name required.
- **VERB:** recognized action category.
- **TARGET:** object, location, direction, person, or omitted when context resolves it.
- **PARAMETERS:** distance, duration, angle, intensity, method, equipment or other relevant values.
- **INTENT:** desired purpose; does not guarantee the result.
- **PRECONDITIONS:** required state, capability, access or knowledge.
- **TIME WINDOW:** immediate, sustained or bounded duration.
- **ABORT RULE:** when to stop, withdraw or re-evaluate.
- **OUTPUT EXPECTATION:** optional preference for how the action is rendered.

This is a proposed normalized schema. The player-facing shorthand should remain shorter.

## 4. Provisional syntax

The following is a grammar sketch, not a locked syntax:

```text
[ACT] VERB TARGET ; INTENT
[ACT] VERB DIRECTION / DISTANCE ; PURPOSE
[PLAN] OBJECTIVE { IF condition -> action ; ELSE -> alternative }
[OOC] CORRECTION: ...
[OOC] REVISE: ...
[OOC] INSPECT: ...
[HELP] ACTIONS
```

Illustrative commands:

```text
[ACT] MOVE SW 8M ; reach the covered walkway
[ACT] LOOK N ; check the upper windows
[ACT] WAIT 02:00 ; remain alert
[ACT] INTERACT DOOR ; test whether it is unlocked
```

Do not require the player to reference their own character by name when the active control context is unambiguous. Directional commands should support cardinal/intercardinal bearings; degree-based bearings can be added when spatial precision is useful.

## 5. Conditional plans

Example only:

```text
[PLAN]
OBJECTIVE: leave the building without escalating the confrontation.
IF the exit is clear:
  attempt to leave at a normal pace.
ELSE IF someone blocks the route:
  stop outside immediate reach and assess another exit.
ELSE IF threatened:
  prioritize escape and available cover; do not initiate a fight.
ABORT IF: an uninvolved person is placed at immediate risk.
RESOURCE LIMIT: do not spend a limited-use item unless necessary to escape.
END
```

The engine resolves the actual conditions. It must not pretend that a condition occurred simply to execute the next line. Plans cannot force NPCs to behave in a specified way, make uncertain information true, or override the character's psychology and capabilities.

Some actions inherently require a fresh conscious decision. The plan must not silently authorize major moral, relational, irreversible or identity-defining choices unless the player explicitly included that authority.

## 6. Action dictionary

Before the roleplay body, the engine may present a compact dictionary of roughly 12–20 available action families. The dictionary is dynamic and situation-sensitive.

Possible families:
- MOVE, RUN, APPROACH, WITHDRAW;
- LOOK, INSPECT, LISTEN, TRACK;
- INTERACT, USE, TAKE, DROP;
- SPEAK, WHISPER, SIGNAL;
- BLOCK, DODGE, STRIKE, AIM;
- WAIT, REST, POSITION.

These are examples, not a mandatory fixed list. Show only actions that are currently meaningful and feasible. Mark conditional actions as conditional. Do not list an action as available if a known constraint makes it impossible.

## 7. Validation and rejection

A command must be checked for:
- syntax and missing required parameters;
- actor/control context;
- physical and world feasibility;
- character capability and psychology;
- required knowledge;
- resource availability;
- time and compatibility with concurrent actions;
- safety and system constraints.

If invalid, state the smallest necessary correction. If valid but uncertain, execute the attempt and resolve uncertainty through the world. Never convert malformed input into a different high-impact action without disclosure.

## 8. OOC correction protocol

Classify corrections as:
- **FACT CORRECTION:** a previously stated world or character fact was wrong.
- **STATE CORRECTION:** a persistent value or event was mis-tracked.
- **INTERPRETATION CORRECTION:** the AI misunderstood the player's intent or a character's meaning.
- **RENDERING CORRECTION:** POV, prose, pace, interface or formatting defect.
- **RULE CHANGE:** the user explicitly changes an operating rule.
- **RETCON REQUEST:** asks to revise an already resolved event.

On correction:
1. Stop compounding the disputed interpretation.
2. Identify the affected state and downstream consequences.
3. Re-evaluate the scene using the corrected premise.
4. Preserve unaffected facts.
5. Explain briefly if the requested correction conflicts with established constraints.
6. Mark the correction's scope and resume from the earliest affected point.

Do not reflexively agree, defend the error, or restart the entire scene when a local repair is sufficient.
