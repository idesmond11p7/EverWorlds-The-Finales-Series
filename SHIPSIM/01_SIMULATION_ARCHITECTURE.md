# Simulation Architecture

[ID: SHIP-02]
[STATUS: ACTIVE WORKING SPECIFICATION]
[DATE: 2026-11-11]
[SCHEMA: STATE / RESOLUTION / TIME / AUTONOMY]
[UPSTREAM: SHIP-01]
[DOWNSTREAM: SHIP-03, SHIP-04, SHIP-05, SHIP-07]
[CONTAINS: Runtime layers, causal loop, state model, time and throttle separation]
[EXCLUDES: Runtime code; setting-specific canon]
[SUPERSEDES: None]
[LAST-TOUCH: Initial capture]
[MUST-RECHECK: Before implementation]
[MODEL-GRADE: G2]
[EVIDENCE-STATE: SYNTHESIS FROM AUTHOR-REQUIREMENTS]
[OPERATIONAL-STATE: REFERENCE-ONLY]

## 1. Runtime layers

The engine is divided into cooperating layers:

1. **Input and protocol layer:** parses commands, plans, OOC corrections and interface selections.
2. **Character layer:** resolves conscious intent through psychology, knowledge, habits, capabilities and physical condition.
3. **World model:** tracks locations, objects, institutions, schedules, NPCs, factions, hazards and environmental processes.
4. **Action resolver:** determines whether an attempt is possible, interrupted, resisted, partially completed, or successful.
5. **Consequence processor:** updates all affected state, including delayed and indirect consequences.
6. **Autonomy scheduler:** advances relevant NPC and world processes, including during player inactivity.
7. **Progression/game layer:** tracks condition, resources, skills, inventory, objectives and setting-specific powers.
8. **Narrative renderer:** selects POV, detail density, dialogue, sensory evidence, visual formatting and pace.
9. **Continuity/audit layer:** preserves state, provenance, unresolved conflicts, corrections and event history.

These are logical responsibilities, not a claim that an LLM literally runs nine independent software services.

## 2. Causal loop

Use the full loop:

`WORLD_STATE → PERCEPTION → INTERPRETATION → MOTIVATION → INTENT → CHARACTER_FILTER → ACTION_RESOLUTION → CONSEQUENCE → STATE_UPDATE → NEW_PERCEPTION`

For parallel world processes:

`NPC/WORLD_GOALS → AUTONOMOUS_DECISION → ACTION → CONSEQUENCE → STATE_UPDATE`

The loop is iterative. One player command may cause multiple world updates and NPC responses before the next player-facing pause.

## 3. State categories

Track only state that can affect future resolution or continuity:

- **Character:** identity, body, position, orientation, condition, energy, injury, skills, knowledge, emotional state, active intentions.
- **World:** locations, geometry, objects, access, weather, lighting, sound conditions, hazards, local time.
- **Social:** relationships, trust, reputation, commitments, unresolved conflicts, shared history.
- **Resources:** money, food, consumables, equipment, ammunition, power reserves where applicable.
- **Temporal:** current time, elapsed action time, deadlines, schedules, cooldowns, durations.
- **Objectives:** quests, tasks, leads, promises, personal goals, progress and failure conditions.
- **Knowledge:** what each actor knows, suspects, misunderstands, or cannot know.
- **Causal history:** events that explain current state and may matter later.

Do not track numbers merely because a number can be invented. Quantify when a value improves a decision, boundary or continuity check.

## 4. Intent, outcome and interruption

An action has at least three separate records:

- **Intent:** what the player wants the character to attempt.
- **Resolved event:** what the character actually does after psychological, physical, temporal and environmental constraints are applied.
- **Outcome:** what changes because of the resolved event and other agents' responses.

A declared action can be:
- completed;
- partially completed;
- delayed;
- interrupted;
- redirected by the character's own psychology;
- blocked by a physical or social constraint;
- attempted but unsuccessful;
- refused by the character;
- rendered impossible before execution.

Example: `MOVE TO THE OTHER PERSON; SLAP` does not guarantee approach or contact. A guard may intervene, the target may leave, the character may hesitate, a door may be locked, or the character may abandon the plan. The system must establish a causal reason, not invent arbitrary obstruction.

## 5. Time and narrative throttle

Maintain two independent controls:

- **Simulation clock:** actual elapsed time in the fictional world.
- **Rendering throttle:** how much of that time and how many events are narrated in one response.

An ordinary movement may take seconds; a conversation or task may take minutes; a long planned sequence may span hours. A high narrative throttle can summarize low-significance intervals and cover longer spans, but it cannot skip consequential events, silently teleport actors, or violate schedules and causality.

Suggested throttle levels (PROPOSAL; labels may change):
- **LOW:** fine-grained interaction, atmosphere, close reactions.
- **MID:** balanced scene progression.
- **HIGH:** several connected actions and developments per response.
- **HYPER:** broad event windows and rapid progression, with significant causal beats preserved.

Throttle controls rendering density, not physical speed, character competence, or the world's rules.

## 6. Inactivity and autonomous continuation

The player's silence is not a universal pause command.

When the player does not issue a command:
1. Do not invent a conscious decision for the player's character.
2. Continue automatic bodily processes and already-established commitments.
3. Advance nearby NPCs and relevant world processes according to their goals, schedules and available information.
4. Allow environmental activity to continue.
5. If the scene remains quiet, maintain subtle life rather than manufacturing constant spectacle.
6. If a meaningful threshold is reached, present the development and return control at a sensible point.

The system may accelerate background progression after several inactive interaction cycles, but should not force arbitrary crises. This threshold and its exact timing remain PROPOSAL pending testing.

## 7. Consequence propagation

Every resolved action should be checked for direct, indirect and delayed effects. Examples:
- walking changes position, consumes some energy and may alter visibility or exposure;
- waiting advances time, schedules and environmental processes;
- eating changes hunger/energy and consumes food;
- an injury can affect movement, grip, attention or later action;
- a social interaction can change trust, suspicion, reputation or future access;
- firing a weapon consumes ammunition only if a shot is actually discharged;
- possessing a loaded weapon does not imply firing it.

Avoid fake precision. Use qualitative condition states when exact numbers are not justified. Do not report BPM, kilograms, calories or other clinical metrics unless the setting or task genuinely requires them.

## 8. Spatial and epistemic continuity

The world model must preserve position, distance, orientation, line of sight, obstacles, access routes, sound propagation and elapsed travel time when they matter. Actors only perceive what is available from their position, senses, attention and knowledge.

No teleport-like arrivals, omniscient NPCs, impossible reactions, object duplication, or unexplained knowledge jumps. If precision is unavailable, represent uncertainty honestly rather than inventing exact geometry.
