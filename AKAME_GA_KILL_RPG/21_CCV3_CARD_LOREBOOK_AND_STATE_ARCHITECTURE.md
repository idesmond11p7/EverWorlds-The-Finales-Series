# 21. CCV3 Card, Lorebook, and Persistent State Architecture
Status: implementation specification for a playable SillyTavern package. Prompt text alone is not a deterministic game engine.

## Package deliverables
1. Core CCV3 card: identity, priority hierarchy, turn protocol, narrator contract and agency protection.
2. Lorebook: canon anchors, geography, species, actions, movement/combat, inventory, Teigu registry, power systems, factions, locations, history, ecology, economy, interface commands and anti-slop checks.
3. Campaign initialization: start location, timeline phase, species, capabilities, equipment and initial conditions.
4. Persistent state template: time, location, body condition, inventory, map knowledge, active NPCs, local environment, current events, faction operations and journal reference.
5. Authored catalogues: unique Teigu, unique relics, named entities, rare species, major locations and historical events.
6. Regression tests with expected state changes.

## Priority hierarchy
1. Locked manga continuity and campaign facts.
2. Current verified persistent state.
3. Player agency and command interpretation.
4. Capability, inventory and world constraints.
5. Causal resolution and information boundaries.
6. Relevant lorebook rules.
7. Narration style and dramatic presentation.
8. Procedural flavor.
Lower priorities cannot overwrite higher ones. Original expansion cannot silently overwrite canon.

## Turn protocol
1. Parse the message as action, dialogue, observation request, interface command, journal edit, setup or out-of-world discussion.
2. Identify the actual intent without inventing additional intent.
3. Validate location, target, route, capability, equipment, prerequisites and costs.
4. Estimate time and likely outcome while preserving uncertainty.
5. Resolve success, partial success, failure or interruption.
6. Apply direct state changes.
7. Propagate only supported causal effects.
8. Update time, inventory, position, injuries, object state, NPC knowledge and active events.
9. Validate consistency and reject unauthorized item/power creation.
10. Narrate from the resolved state.
11. Append a compact state delta when needed.
12. If state cannot be confidently preserved, record ambiguity rather than silently rewriting it.

## Character creation gate
- Read species from the character card if explicitly specified; otherwise require a choice before play.
- Select start location and manga timeline phase.
- Select a valid background, training, affiliation and resources.
- Assign inventory from a defined loadout.
- Record known abilities and limitations.
- Separate player knowledge from character knowledge.
- Distinguish canon character, original character and imported character.
- Do not force every start into the Empire or Capital.

## Campaign start profiles
- Imperial Capital: dense urban surveillance, class stratification, court politics and constrained exits.
- Provincial Empire: local officials, supply routes and distance from central authority.
- Northern frontier: cold, mountain routes, garrisons and weather exposure.
- Western contested territory: occupation, resistance and unreliable reports.
- Southern approach: distinct regional peoples and harsh routes; not automatically inside the Empire.
- Desert civilization: water rights, travel intervals and seasonal constraints.
- Maritime city: tides, port law, shipping schedules and information delays.
- Underground settlement: ventilation, route access, acoustics, water and light.
- Remote frontier: low institutional reach, scarce supplies and high uncertainty.
Start profiles set initial conditions, not a forced main quest.

## Lorebook entry schema
Each entry needs a stable ID, title, category, tags, trigger terms, canon-status label, priority summary, detailed content, related dependencies, retrieval conditions, version and change note. Avoid loading every faction and location into every turn.

## Persistent state schema
### Campaign
campaign ID; timeline phase; start profile; world time; elapsed time; canon-lock version; lorebook version; generation version.

### Player
character ID; name; species; location; facing; posture; movement mode; body condition; injuries; fatigue; exposure; active effects; capabilities; training; power systems and limitations.

### Inventory
item ID; catalogue ID; quantity; owner; slot/container/location; condition; charges/ammunition; acquisition source and time; legal status.

### Local scene
location and zone IDs; weather; light; visibility; sound; footing; exits/routes; obstacles; cover; object positions; persistent damage.

### Relevant NPCs
NPC ID; location; condition; current goal; knowledge; beliefs; loyalties; relationships.

### World operations
Faction operation; location; resources; last known state; next plausible milestone.

### Knowledge and journal
Player observations; rumor source; timestamp; travel path; confidence; user-authored goals, notes, hypotheses and unresolved questions.

### State delta
Changed fields; reason; time cost; confidence; downstream dependencies.

## Interface commands
- inventory: authoritative carried, worn, stored and dropped items.
- status: body condition, immediate limits and active effects.
- map: character-known geography only.
- journal: out-of-world notes and edits.
- objectives: user-authored goals separated from accepted in-world tasks.
- help or commands: supported syntax.
- inspect target: perceptible evidence and reasonable inferences.
Keep interface output compact and never expose private NPC state without an information channel.

## Lorebook retrieval strategy
Always load core priorities and turn rules. Retrieve local geography and hazards by current location; species and power entries by character state; organizations when present or connected to active events; unique-item entries when claimed, seen, transferred or used; canon anchors when the scene touches the manga incident. Remote history should load only when relevant.

## Persistence reality
SillyTavern cards and lorebooks can supply rules and context, but cannot independently guarantee database-like persistence. Use stable IDs, explicit state summaries and compact state deltas. If external tooling is later added, it should store changes transactionally and validate them.

## Minimum regression tests
1. Empty starting loadout plus inventory command produces no invented items.
2. Claiming an unlisted Teigu does not create possession.
3. An impossible jump does not succeed merely because it is declared.
4. A locked door remains closed unless a valid action opens it.
5. Sound through walls is resolved using acoustics and uncertainty.
6. Distant factions receive news only after plausible travel/communication delay.
7. Revisiting a damaged room preserves damage.
8. A journal note about attacking someone does not trigger an attack.
9. Missing species blocks campaign initialization until selected.
10. A desert settlement without a water/food basis is rejected or revised.
11. Mine damage propagates only through connected effects and delays.
12. A destination without a safe route does not receive a fabricated path.
13. A leader's death does not automatically erase an organization.
14. A supernatural entity need not be classified as a Danger Beast.
15. Canon/original conflict is resolved in favor of manga canon.
16. An unlisted but plausible action maps to an existing action family.
17. An unvisited region uses stable generation seed and dependency checks.
18. A visited region retrieves its stored state instead of regenerating.
19. Expired alliances stop being treated as permanent.
20. Dramatic prose cannot contradict the resolved state.

## Build order
Freeze schemas; create core card; implement action/inventory/state rules; build the authored Teigu catalogue; create species and entity taxonomy; finish physical geography and location graph; add factions and history; add event-generation rules; add campaign starts and interface syntax; run regression tests; import/export in SillyTavern and verify actual parsing. Do not call the package complete before round-trip testing.
