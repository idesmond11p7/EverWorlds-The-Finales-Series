# SHIPSIM Successor Workstream

[ID: SHIP-00]
[STATUS: ACTIVE WORKING SPECIFICATION / NOT RELEASED]
[DATE: 2026-11-11]
[SCHEMA: ENGINE WORKSTREAM INDEX]
[UPSTREAM: CG-00, SCH-01, MAP-02, SRC-03, QTE-04, DEC-05, MMG-06]
[DOWNSTREAM: ENGINE MODULES, PROMPT PACKAGES, FUTURE IMPLEMENTATION]
[CONTAINS: System charter, simulation architecture, command protocol, agency model, world/game/power model, narrative/interface model, validation suite, executable prompt candidate]
[EXCLUDES: Novel canon, Apocrypha lore, chapter manuscripts, claims of implemented software]
[SUPERSEDES: None]
[LAST-TOUCH: Executable prompt candidate v0.1]
[MUST-RECHECK: All modules before operational prompt release]
[MODEL-GRADE: G2]
[EVIDENCE-STATE: AUTHOR-DEFINED REQUIREMENTS + ASSISTANT SYNTHESIS / PROVISIONAL]
[OPERATIONAL-STATE: REFERENCE-ONLY / PROMPT CANDIDATE UNTESTED]

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
8. [07_EXECUTABLE_SYSTEM_PROMPT.md](07_EXECUTABLE_SYSTEM_PROMPT.md) — consolidated operating prompt candidate v0.1; untested and not released.

## Authority labels

- **AUTHOR-REQUIREMENT:** explicitly described by the author.
- **SYNTHESIS:** architecture inferred to connect multiple author requirements.
- **PROPOSAL:** an implementation choice introduced by the assistant; not locked.
- **UNKNOWN:** unresolved and must not be silently filled.

## Release warning

The architecture modules are reference specifications. The executable prompt in 07_EXECUTABLE_SYSTEM_PROMPT.md is the first consolidated candidate, not a validated release or runtime implementation. It makes conservative defaults explicit where the architecture left decisions open. The next stage is adversarial testing against 06_VALIDATION_AND_FAILURE_TESTS.md, followed by revision of observed failures. No claim of runtime capability is made.
