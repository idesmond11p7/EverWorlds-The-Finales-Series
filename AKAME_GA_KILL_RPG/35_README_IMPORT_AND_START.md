# Akame ga Kill! RPG CCV3 — Core Package

## Primary import
Import **30_AKAME_GA_KILL_RPG_CCV3_CORE_CARD.json** directly into SillyTavern as a character card. The card embeds all 160 core lorebook entries, so it is sufficient for a first campaign.

## Optional standalone World Info
Import **34_AKAME_RPG_WORLD_INFO_IMPORT.json** as a SillyTavern World Info/Lorebook file if you want to manage the entries separately. Do not bind both the embedded book and this standalone copy to the same character unless duplicate prompt injection is intentional.

## Other files
- **31_AKAME_RPG_CORE_LOREBOOK.json** — canonical source representation for all 160 entries.
- **32_CAMPAIGN_STATE_TEMPLATE.json** — blank campaign state. Null/empty values mean unknown or uninitialized, not permission to invent.
- **33_PLAYABILITY_REGRESSION_TESTS_V1.md** — 24 scenario tests covering agency, inventory, time, geometry, canon, causality, and state persistence.
- Numbered research files — world geography, factions, powers, ecology, canon, procedural generation, and simulation contracts.

## Start
1. Import the CCV3 JSON card.
2. Start a new chat. The first message asks you to establish character identity/species, start region, timeline relationship, background/training, and valid starting equipment.
3. Establish initial campaign state before in-world actions.
4. Use `help`, `inventory`, `status`, `map`, `journal`, `objectives`, or `inspect: target`.
5. Use present-continuous declarations where practical: `I am walking north`, `I am trying to open the gate`. These are attempts, not guaranteed outcomes.
6. Keep concise state receipts for important changes.

## Core rules
- Akame ga Kill! manga continuity outranks anime-only continuity.
- The 48 Teigu are a closed catalogue; possession and availability must be established.
- The player controls voluntary actions, not guaranteed outcomes.
- Journal notes are out-of-world and do not execute.
- NPC knowledge requires a plausible information path.
- Visited locations and consequential state should persist as far as the active conversation context allows.
- The card/lorebook is a prompt and data package, not a deterministic simulation engine or external database.

## Verification
- CCV3 card JSON: parsed; fetched back from GitHub; 160 embedded entries; 113 unique entry IDs; trigger keys are arrays of discrete strings.
- Standalone World Info JSON: generated from the same 160-entry source and uses SillyTavern-style World Info entry fields.
- State template: valid JSON.
- Regression suite: 24 cases written; they have not been executed in a live SillyTavern session here. Do not treat them as passed.
- Live import/round-trip into the target SillyTavern installation remains the final external UI acceptance check.

## Format references
- SillyTavern Character Design: https://docs.sillytavern.app/usage/core-concepts/characterdesign/
- SillyTavern World Info: https://docs.sillytavern.app/usage/core-concepts/worldinfo/
- Character Card V3 specification: https://github.com/kwaroran/character-card-spec-v3
