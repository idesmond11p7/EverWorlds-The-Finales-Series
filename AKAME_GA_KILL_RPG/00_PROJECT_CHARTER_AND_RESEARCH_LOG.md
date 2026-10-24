# Akame ga Kill! RPG CCV3 — Project Charter & Research Log

**Status:** Active research; no final architecture locked beyond explicit author decisions below.  
**Workspace branch:** `akame-rpg-ccv3-research`  
**Project scope:** Design and eventually author a high-fidelity SillyTavern Character Card V3 (`chara_card_v3`) for an expanded, manga-continuity Akame ga Kill! dark-fantasy RPG.  
**Hard exclusion:** Do not use The Ledger. Do not treat this branch or these notes as completed implementation.

## 1. Author-locked direction

- **Primary continuity:** the *Akame ga Kill!* manga, not the anime-original ending. The manga's later arcs, including Wild Hunt, and manga-specific character outcomes remain relevant. Do not silently merge anime-only events into the continuity.
- **World scale:** deliberately expand the known setting to feel roughly an order of magnitude larger than the narrow world impression of the original story. “Ten times larger” is an authorial scale direction, not a canon measurement or a claim about the original map's exact dimensions.
- **Political center:** the Empire is the largest / dominant major power, but it is only one nation. It is unusually enclosed and self-reliant, with limited contact with other regions and realms. It is not the whole world, nor a unique separate dimension.
- **Geography first:** establish landmasses, seas, coasts, climate bands, mountain systems, watersheds, rivers, lakes, forests, deserts, tundra, islands, passes, resource regions and travel corridors before filling the world with detailed settlements.
- **Authored places first:** major regions, nations, cities, towns and signature locations receive deliberate designs. Their district layouts, street structures, architecture, materials, silhouettes, colors, landmarks, infrastructure and environmental character are not left to unconstrained procedural generation.
- **Bounded procedural expansion:** procedural generation is rule-based, layered and spatially connected. It expands between and beyond authored places without replacing them. Generated features must satisfy terrain, hydrology, climate, geology, ecology, transport, settlement, resource and political constraints. Randomness may select among valid outcomes; it must not override dependency rules.
- **Dark-fantasy game feel:** draw high-level experiential inspiration from Elden Ring's environmental scale and discovery, Gotham Knights / modern third-person action games' urban readability, and the spatial/tactical awareness of third-person shooters. Do not copy their prose, art, maps, UI, or signature assets.
- **Not just one power system:** multiple nations, cultures, technologies, magic traditions, energy ontologies, species, Danger Beasts, mining/extraction, crafting, building, equipment, and potentially other realms. Do not collapse everything into Teigu or one universal mana bar. Each system must have its own rules and compatibility boundaries.
- **Simulation before narration:** world state, causal continuity, embodied action, autonomous NPC behavior, information propagation, and consequences govern what the prose can truthfully describe.
- **Third-person game imagination:** “TPP” means a spatially embodied third-person playable view, not third-person literary narration. The prose must help the reader mentally construct position, scale, direction, movement, occlusion, cover, verticality, distance, momentum, and changing tactical relationships.
- **Persistent information:** time, sunlight, weather, location geometry, nearby entities, travel, sound, visibility, damage, resources, and world events must persist consistently between turns. The player should not have to repeatedly ask for basic environmental facts.
- **Player agency and embodiment:** the player controls their character's voluntary locomotion and attempted speech/actions, not guaranteed outcomes. The world can move, injure, displace, frighten, exhaust, restrain or otherwise affect the character. Wind affects clothing and exposed body parts according to the environment; impacts transfer force and cause plausible reactions. Never assume the character remains perfectly still or unaffected.
- **Cognitive and knowledge limits:** no mind-reading by NPCs. Separate objective world state, the player's character's knowledge, each NPC's knowledge, rumors, inference, and unknowns. IQ or intelligence labels do not grant unsupported foresight; conclusions require available evidence and plausible inference.
- **Information propagation:** information travels through concrete channels—sight, sound, witnesses, messages, records, travel, institutions, delay, distortion, secrecy and misinformation. NPCs do not instantly know distant events. Rumors can mutate. Reports can be late, incomplete, biased or false.
- **Journal mode:** a distinct non-roleplay mode for recording the user's intentions, objectives, observations, plans, unresolved questions and character notes. Recording an intention does not make it an in-world action or guarantee that it becomes a subconscious motive. The user can discuss an OC in journal mode without the simulation executing the discussion as a scene.
- **Multiple starting scenarios:** allow different entry routes, including traveling toward the Empire and starting in other regions. Do not force every campaign through the Imperial Capital.
- **Canon vs expansion:** clearly distinguish manga-established facts, sourced interpretation, deliberate authorial expansion, generated content, and unresolved questions.

## 2. Research findings — first pass

### 2.1 Manga continuity

The manga and anime diverge substantially in the later story. Secondary guides place the major divergence around the end of anime episode 19 / manga chapter 38, with the manga continuing into the Wild Hunt arc and later manga-specific events. The project therefore uses the manga's events as its continuity spine and must not use the anime's ending as the default resolution.

Sources:
- Yen Press official series page: https://yenpress.com/series/akame-ga-kill?format=Digital
- Manga/anime divergence overview (secondary): https://wheredoestheanimeleaveoff.com/where-does-the-akame-ga-kill-anime-leave-off-in-the-manga/
- Chapter/volume reference (secondary): https://en.wikipedia.org/wiki/List_of_Akame_ga_Kill%21_chapters

**Verification note:** chapter-level chronology and individual world facts must be checked against the manga itself or reliable primary material before being marked as canon. Online wikis are discovery indexes, not final authority.

### 2.2 Canon geography is broader than the Empire

A first-pass geography index identifies a variety of regions and places inside and beyond the Empire, including:
- Northern, Western, Southern and Eastern countries / regions.
- The Empire's central, northern, eastern, western, southern and northwest regions.
- A coastline and great ocean on the Empire's eastern side.
- Arid Putra, mountains, rivers, forests, lakes, islands, a major canal system, rural settlements and cities.
- Wakoku, including the Soukai and Tenrou nations, indicating a distinct eastern geopolitical/cultural context.
- Multiple Danger Beast habitats and regions with unusual environmental conditions.

Source for discovery and cross-checking:
- Geography index (secondary fan-maintained source): https://akamegakill.fandom.com/wiki/Geography
- Empire overview (secondary fan-maintained source): https://akamegakill.fandom.com/wiki/The_Empire

**Caution:** the manga does not establish every region's complete map, borders, dimensions, population, or political structure. Unknown details remain unknown until sourced. The RPG's additional continents, nations, realms, settlements and ecosystems must be labeled as expansion rather than attributed to canon.

### 2.3 Worldbuilding implication

The original setting provides anchors, not a complete global atlas. The expansion should preserve recognizable canon geography while building a coherent larger planet/setting around it. It should not merely scale up the Empire, nor make every outside culture a variation of the Empire.

The authored atlas should establish:
1. Global orientation and scale assumptions.
2. Landmasses, seas, coastlines and major ocean currents where relevant.
3. Elevation and geological structure.
4. Climate, prevailing winds, precipitation and biome distribution.
5. Watersheds, river sources, tributaries, floodplains, deltas, lakes and wetlands.
6. Danger Beast ecology and migration corridors.
7. Mineral/biological resources and extraction zones.
8. Routes, ports, passes, navigable rivers, barriers and realistic travel times.
9. Nation borders, disputed zones, frontier belts and maritime claims.
10. Settlement placement and the political/economic consequences of geography.

These are dependencies, not ten independent decoration lists. For example, settlements must have plausible water, food, transport and economic reasons to exist.

## 3. Procedural world-generation principle

**Procedural does not mean random.** Use a layered dependency model:

`World frame → landforms/geology → climate/water → biomes/ecology → resources → routes → settlements → districts/streets → local sites → events`

The arrows indicate dependency, not a one-way pipeline that forbids feedback. Cities can reshape rivers, roads can redirect trade, mining can damage watersheds, wars can depopulate regions, and infrastructure can alter settlement growth. Such changes must update dependent systems.

Generation should be constrained by:
- Topology and adjacency: generated locations must connect to real neighboring locations.
- Hydrology: rivers flow downhill and join coherent watersheds; they do not begin and end arbitrarily.
- Climate and ecology: species, crops, materials and hazards must fit the local environment unless an explicit mechanism explains otherwise.
- Logistics: roads, ports, passes, mines and settlements need plausible access and supply relationships.
- Political causality: borders, claims, forts and patrols relate to resources, terrain, history and current power.
- Cultural distinction: architecture, street plans, clothing, food, naming, public spaces and institutions vary for grounded historical and environmental reasons.
- Persistent identity: once a generated location enters play, it receives a stable identity and does not regenerate on re-entry.
- Validation: reject or repair outputs that violate established constraints; preserve the prior state when a generation attempt fails.

Most major cities and signature towns should be hand-authored. Procedural generation should fill the spaces between them, provide peripheral detail, and support controlled expansion.

## 4. Prose and game-view research target

The target is a mentally navigable, embodied third-person view—not a camera label, not a static panorama, and not three paragraphs of generic sensory adjectives.

Prose should continuously communicate, when relevant:
- Where the viewpoint is located and what it faces.
- Relative position, distance, elevation and orientation of important entities.
- Motion trajectories, acceleration, stopping distance, momentum and bodily recovery.
- Occlusion, cover, sightlines, blind spots and exposure.
- Surface texture, traction, slope, obstacles, clearances and footing.
- Light sources, shadow direction, glare, reflected light and visibility.
- Sound source, distance, direction, obstruction, masking and plausible listeners.
- Environmental change and the physical consequences of interaction.
- What the character notices versus what remains outside their attention or knowledge.

Use controlled literary techniques—spatial anchoring, action-linked sensory details, selective metaphor, rhythmic variation, sentence-level motion cues, contrast, negative space, anticipation, and consequence-focused description. The method must produce a stable scene model in the reader's imagination. Poetic language is useful only when it sharpens perception rather than obscuring mechanics.

## 5. Anti-slop and failure catalogue — initial hypotheses to test

This list is a research agenda, not a claim that every model always makes every error.

- **Spatial amnesia:** doors, distances, elevations, room layouts, weather or object positions change without cause.
- **Temporal amnesia:** the sun, clock, travel duration, wounds, patrols and ongoing events reset or contradict each other.
- **Outcome theft:** the narrator treats the player's declared attempt as a guaranteed success.
- **Player puppeting:** the narrator invents voluntary thoughts, decisions, emotions, dialogue or actions for the player's character.
- **NPC telepathy:** characters react to private thoughts or know events without an information path.
- **Information teleportation:** rumors, alarms, orders and discoveries spread instantly or perfectly.
- **Competence inflation:** characters infer highly specific conclusions from weak evidence or act as if their IQ score grants omniscience.
- **Power inflation:** new abilities acquire extra capabilities, range, precision or immunity that were never established.
- **Fake physics:** precise-sounding numbers are invented without a usable model or source.
- **Threat inflation:** every new enemy, faction or location is stronger or more important than the last.
- **Culture homogenization:** every nation shares the same institutions, architecture, moral assumptions, military structure and naming logic.
- **Procedural soup:** generated content has names and adjectives but no geography, logistics, causal history or stable identity.
- **Lore dumping:** huge blocks of setting text arrive without regard to viewpoint, relevance, discovery or usable information.
- **Purple-prose fog:** elaborate metaphors obscure positions, actions, timing or consequences.
- **Action compression:** complex movement or combat is summarized into one result without intermediate physical changes.
- **Reactionless embodiment:** the character is struck, pushed, chilled, soaked, exhausted or startled without appropriate physical response.
- **Mood locking:** a stated mood prevents plausible reactions to changing circumstances.
- **NPC cardboard behavior:** NPCs exist only to deliver exposition, praise the player, attack on cue or wait for the player.
- **False choice:** options are presented as meaningful while the world resolves them identically.
- **Continuity laundering:** a contradiction is silently treated as true rather than flagged and repaired.
- **Interface clutter:** every turn repeats huge status blocks, or the player cannot find essential state because information is poorly prioritized.

Next research must collect concrete examples, identify the mechanism behind each failure, and derive specific prevention and validation rules rather than relying on a generic “avoid AI slop” instruction.

## 6. Decisions still open

- Exact world map projection, planet dimensions and scale calibration.
- How many continents and major oceans are authored initially.
- Which canonical regions are placed precisely on the expanded map, and which remain unresolved pending manga verification.
- How the eastern nations / Wakoku / Hinowa ga Crush continuity will be incorporated, and what sources govern that decision.
- Whether other realms are physically connected, ocean-separated, or accessible only through defined mechanisms.
- Which power/energy traditions exist, and how their interfaces and incompatibilities are represented without collapsing them into one system.
- The exact simulation state format and how much state can be reliably maintained within SillyTavern context.
- How journal mode is invoked and how it is kept separate from in-world actions.
- Starting-scenario selection and campaign-time placement relative to manga events.
- The visual/UI format that can be reliably expressed by the final CCV3 card in SillyTavern.

Do not silently resolve these open questions through model inference.

## 7. Next research steps

1. Build a manga-continuity evidence matrix: geography, nations, places, Danger Beasts, technologies, Teigu/Shingu, known realms, and timeline.
2. Verify source claims against manga chapters/volumes wherever possible; label fan-wiki claims as secondary until verified.
3. Build the global physical geography before inventing new nation names or city lists.
4. Develop the visual design grammar for terrain, settlement silhouettes, street structures, materials, colors, and regional architecture.
5. Research model-generated roleplay failure patterns and convert them into testable rules.
6. Design the prose method for persistent third-person game-space imagination.
7. Design journal mode, information propagation, player embodiment, and action-resolution procedures.
8. Only after these layers are coherent, compile the long lore book and final CCV3 JSON incrementally.

## 8. Change discipline

- Author-locked decisions outrank assistant proposals.
- Manga canon, secondary-source interpretation, authorial expansion, generated details and unknowns must remain distinguishable.
- Do not claim a feature works merely because a prompt says it should work.
- Do not call the card production-ready until it has passed scenario tests for continuity, spatial/temporal persistence, information propagation, agency, procedural consistency, and SillyTavern CCV3 structure.
- Keep work incremental. This file is the initial charter and research log, not the completed lore book or final card.
