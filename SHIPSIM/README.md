# SHIPSIM Successor Workstream

[ID: SHIP-00]
[STATUS: ACTIVE WORKING SPECIFICATION / NOT RELEASED]
[DATE: 2026-11-11]
[SCHEMA: ENGINE WORKSTREAM INDEX]
[DOWNSTREAM: ENGINE MODULES, PROMPT PACKAGES, FUTURE IMPLEMENTATION]
[EXCLUDES: Novel canon, chapter manuscripts, claims of implemented software]
[LAST-TOUCH: v0.2 prompt and targeted regression suite]
[MODEL-GRADE: G2]
[OPERATIONAL-STATE: REFERENCE-ONLY / PROMPT CANDIDATE UNTESTED]

## Purpose

This workstream captures the successor architecture for the user's SHIPSIM family of roleplay and open-world character simulation systems. It is stored here solely because the author explicitly directed this work here. It is not part of the novel's fictional canon and must not be imported into chapter production unless separately directed.

No new product/system name has been approved. "MOSAIC" was an assistant proposal and is not locked.

## Current canonical prompt candidate

**[08_EXECUTABLE_SYSTEM_PROMPT_V0.2.md](08_EXECUTABLE_SYSTEM_PROMPT_V0.2.md)** — current candidate v0.2. It supersedes v0.1 as the active draft, but remains untested and unreleased.

[07_EXECUTABLE_SYSTEM_PROMPT.md](07_EXECUTABLE_SYSTEM_PROMPT.md) — previous v0.1 candidate retained for comparison and history.

## Architecture references

1. [00_SYSTEM_CHARTER.md](00_SYSTEM_CHARTER.md)
2. [01_SIMULATION_ARCHITECTURE.md](01_SIMULATION_ARCHITECTURE.md)
3. [02_COMMAND_AND_ACTION_PROTOCOL.md](02_COMMAND_AND_ACTION_PROTOCOL.md)
4. [03_CHARACTER_AGENCY_AND_AUTONOMY.md](03_CHARACTER_AGENCY_AND_AUTONOMY.md)
5. [04_WORLD_GAME_AND_POWER_SYSTEMS.md](04_WORLD_GAME_AND_POWER_SYSTEMS.md)
6. [05_NARRATIVE_AND_INTERFACE_RENDERING.md](05_NARRATIVE_AND_INTERFACE_RENDERING.md)
7. [06_VALIDATION_AND_FAILURE_TESTS.md](06_VALIDATION_AND_FAILURE_TESTS.md)
8. [09_V0.2_VALIDATION_ADDENDUM.md](09_V0.2_VALIDATION_ADDENDUM.md) — targeted regression tests for world compression, mystery, suggestions and UI.

## Authority labels

- **AUTHOR-REQUIREMENT:** explicitly described by the author.
- **SYNTHESIS:** architecture inferred to connect multiple author requirements.
- **PROPOSAL:** an implementation choice introduced by the assistant; not locked.
- **UNKNOWN:** unresolved and must not be silently filled.

## Release warning

The architecture modules are reference specifications. v0.2 is the current consolidated prompt candidate. It adds strict operating contracts for mystery/information asymmetry, world modeling, option-space diversity, mandatory Unicode/emoji interface rendering, staged character construction and response validation. The targeted regression suite is written but has not been executed in the target model. No runtime capability or release readiness is claimed.
