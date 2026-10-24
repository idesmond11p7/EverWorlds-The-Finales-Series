# 19. Dependency-Driven Procedural World Generation and History Engine
Status: implementation specification for authored foundations plus constrained procedural expansion.

## Core rule
Procedural generation is a constrained completion system, not a random-content fountain. The authored world supplies anchors, rules and locked facts. Generation fills gaps only when its outputs satisfy dependencies and do not overwrite established state.

## Generation layers
1. **Planet parameters:** surface area, land/ocean fraction, latitude bands, axial seasons, prevailing winds, ocean currents and gravity assumptions.
2. **Geology:** tectonic regions, mountain belts, volcanic arcs, basins, faults, mineral provinces and sedimentary zones.
3. **Hydrology:** watersheds, river direction, seasonal flows, aquifers, lakes, deltas, wetlands, desert wadis and recharge.
4. **Climate and biomes:** temperature/moisture bands, rain shadows, soil, vegetation, productivity, fire and seasonal migration.
5. **Ecology and species:** food webs, predators, prey, pollinators, parasites, anomalous entities, spawning/reproduction cycles and habitat constraints.
6. **Resources and industry:** ore, timber, salt, stone, water, food, fuel, processing, waste and depletion/recovery rates.
7. **Routes and settlements:** passes, river crossings, ports, caravan stops, roads, tunnels, ferries, safe water intervals, trade and travel time.
8. **Political geography:** borders, jurisdiction, treaties, local law, military reach, language and resource control.
9. **Authored places and institutions:** major cities, ruins, sacred sites, faction seats, unique hazards and plot-relevant sites.
10. **Local detail:** districts, streets, buildings, objects, NPC routines and event seeds.

A lower layer constrains higher layers. A city may influence a road network and local ecology, but it cannot retroactively create a mountain range to justify itself. If an authored anchor conflicts with the physical model, record a deliberate exception with a cause and downstream effects.

## Stable identifiers and persistence
Every generated region, route, settlement, organization, species and major event gets a stable ID. Store:
- ID, parent region, coordinates or zone, creation seed, generation version and dependencies.
- Authored/generated status and confidence.
- Links to resources, routes, watersheds, organizations, species and historical events.
- Lock state and change history.
Revisiting a location retrieves its existing state; it does not regenerate a new variant. Regeneration is allowed only for explicitly unvisited/unlocked regions or after a versioned migration with dependency checks.

## Randomness policy
Randomness may select among valid candidates only after constraints are applied. Example: choose among three plausible pass routes that satisfy slope, geology, weather and political access. It may not place a river flowing uphill or generate a Teigu.
- Seed random generation by stable region ID and generation version.
- Record why a candidate was accepted and why alternatives were rejected where practical.
- Use authored tables for rare/unique phenomena.
- Unique objects, named Teigu, major historical rulers and canon events are not random outputs.
- Ordinary NPC names, common goods and minor local details can be generated from culture-specific schemas.

## Feedback loops
The world is dynamic, not a static map. Changes propagate through explicit dependency edges:
- Mine excavation -> slope/ventilation/water contamination -> output and worker health -> supply and price changes -> transport and migration.
- Dam damage -> flood risk and water allocation -> crop yield -> food prices -> debt and migration -> political unrest.
- Road closure -> travel-time increase -> delayed messages and goods -> shortage or misinformation -> faction decisions.
- Predator decline -> prey increase -> crop pressure -> settlement conflict -> hunting restrictions.
- War -> casualties, displaced households, damaged roads, requisition, changed borders and interrupted schooling.
- Disease -> mortality, labor shortages, travel restrictions and stigma, with effects limited by actual transmission and contact.
Each link requires plausible mechanisms, delays and scale. Do not propagate every event to the entire planet.

## History generation
Historical events arise from conditions and choices, not a list of random wars.
For each event:
- Preconditions and pressure.
- Actors with goals, resources, knowledge and constraints.
- Trigger or decision point.
- Direct outcome and alternatives not taken.
- Casualties, material damage, economic cost and information loss where relevant.
- Immediate winners and losers.
- Delayed consequences and which systems they affect.
- Records produced, destroyed or distorted.
- Confidence and source provenance.
A drought can cause migration without causing war. War requires actors, incentives, capability, escalation paths and failed alternatives. The same stressor can yield cooperation, adaptation, coercion or collapse depending on institutions.

## Faction simulation
Each organization tracks:
- Objective, doctrine, resources, logistics, leadership and succession.
- Recruitment base, member incentives, internal factions and dissent.
- Allies/rivals, treaty terms, active operations and information sources.
- Public reputation versus actual conduct.
- Geographic reach and communication latency.
- Capacity to replace losses, fund projects and maintain equipment.
- Failure states and recovery paths.
A faction cannot act outside its reach unless it has a credible channel or agent. Killing a leader does not automatically erase a bureaucracy, supply chain or ideology.

## NPC and event scheduler
At each meaningful time interval, select only the systems relevant to current conditions and campaign scale:
1. Update local time/weather/environment.
2. Advance nearby NPC routines and active threats.
3. Advance relevant faction operations according to resources and communication.
4. Resolve scheduled ecological or logistical processes.
5. Select a small number of events from plausible causes.
6. Filter by player sensory access and current knowledge.
7. Narrate only what is perceptible or what a valid interface can report.
The scheduler should not force a new encounter every turn. Quiet travel, missed events and uneventful routines are valid outcomes.

## Geography constraints
- Rivers flow downhill within watersheds.
- Aquifers need plausible recharge or a declared supernatural/engineered source.
- Deserts have specific water and energy budgets.
- Biomes follow latitude, elevation, moisture and soil constraints.
- Routes respect slope, passes, water, weather, load and political access.
- Cities need food, water, waste disposal and supply paths.
- Underground networks are discontinuous unless geology or engineering connects them.
- Ocean travel depends on currents, storms, vessels, ports and navigation knowledge.
- Desert travel intervals must be compatible with water capacity, load and shelter.
- Borders are political outputs, not automatic biome outlines.

## History and canon boundaries
The Empire's canon timeline is an authored, locked event chain. Original intermediate emperors and pre-canon incidents may be added only with explicit **ORIGINAL BRIDGE** labels. Do not overwrite manga events. Uncertain canon facts remain uncertain and can inspire competing in-world historical accounts rather than false certainty.
The broader planet can have much older societies and unrelated institutions. They do not all derive from the Empire. Contact with the Empire depends on actual routes, political awareness and the campaign timeline.

## Quality gates
Reject or revise a generated output if:
- It violates an established fact or stable ID.
- It conflicts with watershed, climate, geology or resource dependencies.
- It has no plausible water/food/supply basis.
- It uses an organization as omnipresent without reach.
- It generates a unique item or Teigu.
- It grants a species unsupported abilities.
- It creates an event solely because the player asked for it.
- It transmits information faster than the available channel.
- It creates consequences without a causal path.
- It repeats the same aesthetic/culture template without an environmental or historical reason.
- It labels original expansion as canon.
- It changes an established location on revisit without recording the intervening cause.

## Practical CCV3 boundary
A SillyTavern character card and lorebook cannot guarantee a fully deterministic simulation engine. They can enforce prompt contracts, maintain compact state blocks and retrieve relevant rules. The implementation should therefore use:
- A concise core card with priority hierarchy and turn protocol.
- Lorebook entries for action rules, world systems, species, faction registries, unique-item catalogues and locations.
- A persistent state block or external state store for inventory, time, position, damage and active events.
- Validation prompts/checklists that catch contradictions.
- A controlled interface vocabulary for inventory, status, map, journal and objectives.
Never claim that a prompt alone guarantees durable memory or exact physical simulation.
