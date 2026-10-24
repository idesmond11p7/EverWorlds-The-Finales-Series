# 07 — Build Roadmap and Validation Gates

**Status:** Active build plan. The project is not complete until the actual CCV3 export and simulation tests pass.

## Phase 0 — Repository and scope
- [x] Isolated branch created: `akame-rpg-ccv3-research`.
- [x] Project charter and initial research log.
- [x] First manga-continuity dossier.
- [x] Initial greater-world atlas concept.
- [x] Geography/procedural generation rules.
- [x] First authored settlement atlas.
- [x] Original faction registry.
- [x] Simulation/causality/CCV3 runtime contract.
- [x] Build roadmap and test gates.
- [ ] Validate every created file by fetching it from the branch and checking its content.
- [ ] Add source-grounded canon entity register.
- [ ] Establish exact target SillyTavern version and actual CCV3 export schema.

## Phase 1 — Manga canon extraction
**Deliverables**
- Chapter-linked chronology for all 78 main manga chapters.
- Separate records for *Akame ga Kill! Zero* and *Hinowa ga Crush!* with relationship and timeline cautions.
- Entity register: character, faction, place, artifact, species, event, date, status and source reference.
- Manga/anime divergence matrix.
- Empire history: founding, First Emperor, Teigu, civil war, Shingu, government and revolution.
- Geography register: all named places, directions, travel clues and visual evidence.

**Acceptance gates**
- Every important canon assertion has a chapter/volume or official/credible source reference.
- Fan-wiki-only claims are tagged secondary and unverified.
- Contradictions are recorded instead of silently reconciled.
- No original name is presented as manga canon.
- Manga's ending remains the reference outcome unless a player-caused divergence is recorded.

## Phase 2 — Planet and map
**Deliverables**
- Planet parameter decision record.
- Global physical map with projection, scale and legend.
- Tectonic/elevation layer.
- Climate/wind/current layer.
- Watershed and major river layer.
- Biome, Danger Beast and resource layers.
- Major route, pass, port and chokepoint layer.
- Political borders and uncertainty layer.
- Canon locations placed with source confidence.

**Acceptance gates**
- Every major river drains coherently.
- Climate and terrain transitions are defensible.
- Travel times are consistent with distance and transport.
- No major settlement lacks food/water/logistics.
- Canon locations are not displaced to make the new map convenient.

## Phase 3 — Nations, peoples and histories
**Deliverables**
- State dossiers with government, population range, economy, military logistics, legal systems, language, culture, internal factions and neighbors.
- Non-state faction dossiers.
- Elven and other peoples' ecological/cultural histories.
- Religion/cult registry, schisms, rituals, sites and information channels.
- Chronology with migration, disease, war, trade, climate events and technological change.
- Multi-system power traditions with limits and interfaces.

**Acceptance gates**
- No culture is a single personality.
- Each major faction has material constraints and internal disagreement.
- Power systems have costs, limits, training and counterplay.
- History causes present borders, institutions and grievances.
- Remote states remain plausibly isolated where routes/contact are absent.

## Phase 4 — Major settlements and authored sites
**Deliverables**
- Imperial Capital study based on manga.
- Major original cities with district maps, street networks, color/material palettes, architecture, landmarks, infrastructure and movement routes.
- Important villages, ruins, forts, ports, mines, shrines and dungeons.
- Interior/site schemas and stable IDs.

**Acceptance gates**
- Distinct silhouette and street grammar.
- Water, waste, food, energy, materials and transport are accounted for.
- Major locations are authored, not randomly assembled.
- Every major site has at least one meaningful constraint or vulnerability.
- Revisit continuity preserves geometry, damage and local state.

## Phase 5 — Simulation engine prompt and data design
**Deliverables**
- Core role/system prompt.
- Response protocol and state record.
- World-info/lorebook architecture with trigger keys.
- Journal mode instructions.
- NPC knowledge model.
- Time, travel and event scheduling conventions.
- Causal fan-out procedure.
- CCV3 field map and version compatibility notes.

**Acceptance gates**
- User actions are attempts, not automatic outcomes.
- Player voluntary decisions remain under player control.
- NPC knowledge requires plausible channels.
- Time and location state persist in context.
- Prompt does not claim to provide unavailable external runtime features.
- Journal entries never execute by implication.

## Phase 6 — Visual/game-view prose method
**Deliverables**
- Spatial prose grammar: position, orientation, distance, elevation, motion, momentum, occlusion, cover, line of sight, light, sound, surface and body state.
- Environmental description system that reveals geometry through action.
- Tactical movement and combat examples.
- Non-combat exploration examples.
- Before/after tests against purple prose and vague action compression.

**Acceptance gates**
- Reader can reconstruct a stable 3D scene.
- The prose states relevant positions and changes without becoming a coordinate dump.
- Cover, exits, obstacles and movement costs remain consistent.
- Sensory description is anchored to source, distance and environmental conditions.
- Metaphor never substitutes for the physical result.

## Phase 7 — Art, UI and card packaging
**Deliverables**
- Manga-faithful visual references for canon elements where legally and technically appropriate.
- Original art direction for the new world.
- Character-card image concept and crop requirements.
- CCV3 JSON export with valid fields.
- Lorebook files and user-facing setup notes only if requested.

**Acceptance gates**
- Art does not falsely portray original additions as official canon.
- Export parses as valid JSON and imports into the target SillyTavern version.
- Prompt length is measured; core rules are not drowned in lore.
- World info activates for relevant locations/factions without excessive false triggers.
- No external image path, file or runtime feature is assumed to exist without verification.

## Phase 8 — Red-team simulation tests
Create fixed test scenarios for:
1. A punch beside a cracked wall with a loose shelf and nearby witnesses.
2. A player tries to attack an armored target with a poor angle and unstable footing.
3. A distant ruler learns of a local assassination through a delayed courier.
4. A river crossing is damaged upstream and downstream travel changes.
5. A generated town is revisited after several in-world days.
6. An NPC is asked about something they could not have witnessed.
7. The player writes a plan in journal mode but does not execute it.
8. An ability is used outside its recorded range or resource limits.
9. A city fire creates smoke, evacuation, damage, rumors and supply consequences.
10. A mining operation harvests a Danger Beast material and alters local ecology.
11. A storm closes a port and affects cargo, food prices and faction plans only along connected trade paths.
12. The manga's Empire incident proceeds without external factions intervening absent a causal bridge.
13. A player action plausibly creates a divergence, which is recorded and propagated.
14. A character attempts a social action and can fail without the narrative stealing agency.
15. A scene transition preserves time, injuries, inventory, weather and object states.

## Definition of done

The project is not “done” because the lore is long. It is done when:
- canon and original expansion are separable;
- the map is coherent and traversable;
- major locations are authored and recognizable;
- factions have credible logistics and information limits;
- the simulation preserves state within practical context limits;
- consequential actions produce plausible direct and indirect effects;
- the prose produces a stable three-dimensional scene;
- CCV3 data validates and imports;
- test scenarios demonstrate both successful behavior and known limitations.

## Current next actions

1. Continue chapter-level manga research; do not pretend the initial dossier is exhaustive.
2. Build a structured canon geography/entity register.
3. Make the planet parameter decision only after testing size, day/year and climate assumptions.
4. Author the Imperial Capital and Great Canal from manga references before expanding the surrounding Imperial map.
5. Add state/cult/people dossiers in batches, each connected to the map and history.
6. Convert stable rules into the compact core prompt only after enough tests reveal which rules need highest priority.
