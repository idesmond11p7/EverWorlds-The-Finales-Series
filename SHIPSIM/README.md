# SHIPSIM Successor Workstream

[ID: SHIP-00]
[STATUS: ACTIVE WORKING SPECIFICATION / NOT RELEASED]
[DATE: 2026-11-11]
[SCHEMA: ENGINE WORKSTREAM INDEX]
[UPSTREAM: CG-00, SCH-01, MAP-02, SRC-03, QTE-04, DEC-05, MMG-06]
[DOWNSTREAM: ENGINE MODULES, PROMPT PACKAGES, FUTURE IMPLEMENTATION]
[CONTAINS: System charter, simulation architecture, command protocol, agency model, world/game/power model, narrative/interface model, validation suite]
[EXCLUDES: Novel canon, Apocrypha lore, chapter manuscripts, claims of implemented software]
[SUPERSEDES: None]
[LAST-TOUCH: Initial architecture capture]
[MUST-RECHECK: All modules before operational prompt release]
[MODEL-GRADE: G2]
[EVIDENCE-STATE: AUTHOR-DEFINED REQUIREMENTS + ASSISTANT SYNTHESIS / PROVISIONAL]
[OPERATIONAL-STATE: REFERENCE-ONLY / NOT YET TESTED]

## Purpose

This workstream captures the successor architecture for the user's SHIPSIM family of roleplay and open-world character simulation systems. It is stored in this repository solely because the author explicitly directed this work here. It is **not part of the novel's fictional canon**, does not define the novel's supernatural ontology, and must not be imported into chapter production unless the author separately directs that.

The current label "SHIPSIM successor" is descriptive. No new product/system name has been approved. "MOSAIC" was an assistant proposal and is not locked.

## Read order

1. [00_SYSTEM_CHARTER.md](00_SYSTEM_CHARTER.md)
2. [01_SIMULATION_ARCHITECTURE.md](01_SIMULATION_ARCHITECTURE.md)
3. [02_COMMAND_AND_ACTION_PROTOCOL.md](02_COMMAND_AND_ACTION_PROTOCOL.md)
4. [03_CHARACTER_AGENCY_AND_AUTONOMY.md](03_CHARACTER_AGENCY_AND_AUTONOMY.md)
5. [04_WORLD_GAME_AND_POWER_SYSTEMS.md](04_WORLD_GAME_AND_POWER_SYSTEMS.md)
6. [05_NARRATIVE_AND_INTERFACE_RENDERING.md](05_NARRATIVE_AND_INTERFACE_RENDERING.md)
7. [06_VALIDATION_AND_FAILURE_TESTS.md](06_VALIDATION_AND_FAILURE_TESTS.md)

## Authority labels

- **AUTHOR-REQUIREMENT:** explicitly described by the author in the 2026-11-11 conversation.
- **SYNTHESIS:** architecture inferred to connect multiple author requirements.
- **PROPOSAL:** an implementation choice introduced by the assistant; not locked.
- **UNKNOWN:** unresolved and must not be silently filled.

## Release warning

These documents are an initial architecture package, not a finished system prompt, runtime implementation, tested simulator, or canon release. The next safe stage is to review internal consistency, convert accepted modules into a compact executable system-instruction package, and test against adversarial scenarios. No claim of runtime capability is made.
