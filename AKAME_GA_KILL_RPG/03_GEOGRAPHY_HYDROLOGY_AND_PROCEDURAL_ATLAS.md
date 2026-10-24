# 03 — Geography, Hydrology and Procedural Atlas Rules

**Status:** Original design specification. Canon placements remain provisional until manga-source verification.

## 1. Non-negotiable model

The map is not a collage of biomes. It is a causal physical model. Every authored place and every generated place must fit its surrounding terrain, water, climate, ecology, transport, resources and history.

Dependency chain:

`planet parameters → tectonics → elevation/geology → winds and ocean currents → climate → watersheds → biomes → species/resources → routes → settlement sites → districts/infrastructure → events`

Feedback is permitted when it has a mechanism: dams change floodplains; mines contaminate streams; deforestation increases erosion; roads create markets; war destroys bridges; irrigation salinizes soil; ports redirect settlement growth.

## 2. Map coordinate and scale protocol

Do not commit a final planetary radius or map projection before the world-scale decision is validated. Start with a layered atlas:
- **Global layer:** landmasses, oceans, major currents, climate belts, tectonic boundaries.
- **Continental layer:** elevation, watersheds, biomes, major species ranges, resource provinces.
- **Regional layer:** roads, rivers, passes, ports, borders, settlements, migration corridors.
- **Settlement layer:** district boundaries, street networks, walls, gates, markets, water systems, landmarks.
- **Site layer:** buildings, interiors, local objects, cover, entrances, exits, elevation and sightlines.
- **Live-state layer:** temporary conditions and changes: weather, damage, fire, crowds, patrols, blocked roads, water levels, construction, disease, political control.

Every location needs a stable identifier, parent region, coordinate or explicit relative location, source/provenance label, scale, neighboring features and known routes. Never rely on name alone to establish identity.

## 3. Physical geography rules

### Tectonics and landforms
- Long mountain chains require a plausible uplift history. Volcanic arcs follow suitable plate boundaries or established local mechanisms.
- Plateaus, basins and escarpments alter rainfall, routes, settlement density and military movement.
- Mineral deposits have geological contexts. Do not put every rare ore in every mountain.
- Karst caves require soluble rock and groundwater pathways; lava tubes require volcanic history; deep caves are not one universal underground continent.

### Climate
- Use latitude, elevation, prevailing winds, ocean currents, continentality and rain shadows to determine climate.
- A wet windward slope and dry leeward basin should be connected by the mountain system that creates the contrast.
- Seasonal monsoon, snowmelt, drought, freeze-thaw and storm seasons influence farming, travel, disease and military campaigns.
- Magic may create a local anomaly only when its extent, energy/material cost, maintenance and side effects are defined.

### Hydrology
- Every river belongs to a watershed. Trace source, tributaries, gradient, floodplain, seasonal flow and final sink or outlet.
- Lakes need inflows, outflows or a plausible closed basin; wetlands need persistent water and sediment conditions.
- Deltas require sediment and low-gradient outlets; estuaries require a coastal setting where tides and freshwater interact.
- Canals connect feasible water levels. Locks, aqueducts, cuttings, labor, maintenance, dredging and political control are part of the design.
- Bridges, ferries and fords are strategic nodes. Destroying one must alter routes and travel times.
- Floods propagate downstream; upstream actions may create delayed and uneven consequences.

### Ecology and Danger Beasts
Each species dossier must define: habitat, range, food, predators, prey, reproduction, seasonal movement, territory, sensory capabilities, social behavior, body materials, hazards, and evidence that reveals its presence. A rare beast cannot sustain a large harvesting industry unless its reproduction and population support that extraction.
Danger Beast behavior may reshape human geography: abandoned routes, fortified settlements, seasonal closures, bounty economies, protected breeding grounds and contested carcass rights.

## 4. Rule-driven procedural expansion

Procedural generation is a constrained choice system, not a dice roll that gets to ignore geography.

For each generated feature:
1. Identify its parent region and local terrain.
2. Gather hard constraints from geology, climate, hydrology, ecology, existing routes, politics and neighboring authored landmarks.
3. Generate a small candidate set satisfying those constraints.
4. Score candidates for coherence, novelty, resource balance and narrative utility.
5. Select one candidate using a stable seed derived from world/region/location IDs.
6. Save the result as persistent state.
7. Validate neighboring connections and downstream consequences.
8. Reject or repair candidates that violate hard constraints.

Randomness may select among valid alternatives; it cannot decide that a river flows uphill or a desert has a wetland climate without an explanation.

### Authored core / procedural frontier
- **Authored:** canon locations, major cities, major landmarks, faction headquarters, critical routes, unique dungeons, important historical sites.
- **Rule-generated:** secondary villages, road stops, local ruins, minor mines, small shrines, patrol posts, minor caves, local events and ecological encounters.
- **Hybrid:** large forests, mountain chains, frontier regions, city outskirts and contested borders. Macro-shape and key landmarks are authored; subordinate details can be generated under constraints.
- Generated sites become stable once discovered or recorded. Revisiting a place must not silently replace it with a different settlement.

### Generation rejection examples
- A large port with no navigable water or viable trade hinterland.
- A major city without a reliable water/food/waste plan.
- A river crossing with no ford, bridge, ferry or engineered crossing.
- A settlement placed in a floodway without defenses, seasonal abandonment or flood-adapted design.
- A metal mine without a deposit or geological explanation.
- A Danger Beast appearing outside its range without migration, escape, introduction or anomaly.
- A secret organization whose members know every event across the planet without communication infrastructure.

## 5. Travel and scale

Travel estimates depend on terrain, season, transport, load, health, road quality, weather, checkpoints, danger and rest. Do not state exact travel duration unless enough inputs exist; otherwise provide a defensible range and state the main uncertainty.

Track:
- origin and destination;
- route and alternative routes;
- distance and elevation changes;
- transport and movement pace;
- rest, supplies and injuries;
- weather and seasonal constraints;
- tolls, permits, patrols, hazards and closures;
- time elapsed and arrival state.

A long-distance message has its own route and delay. The person sending it, the carrier, the recipient and the wider world do not share one instantaneous information state.

## 6. Settlement viability check

Every permanent settlement must answer:
- Why here rather than nearby?
- Freshwater source and drought/flood strategy?
- Food source, storage and supply route?
- Waste, drainage and disease management?
- Building materials and energy?
- Population size and labor base?
- Trade role or strategic function?
- How do people enter, leave and move within it?
- What can cut it off?
- Who controls essential infrastructure?
- What happened historically that made this settlement grow?
- What visible design choices express climate, resources, politics, religion and class?

If the answer is “because fantasy,” it needs a more specific mechanism.

## 7. Palette and visual identity as geography

Color must emerge from physical and cultural sources, not arbitrary region-wide filters. Record:
- dominant ground/stone/soil colors;
- water color and seasonal variation;
- vegetation and canopy tones;
- local sky, haze and weather;
- construction materials and patina;
- dyes, heraldry, paint and light sources;
- contrast conditions at dawn, midday, dusk and night;
- how soot, salt, mud, rain, smoke, age and conflict change the palette.

A city should remain recognizable in silhouette, street plan, materials and lighting even when its color palette is removed.

## 8. Atlas validation tests

- **Drainage test:** trace every major river from source to outlet.
- **Pass test:** every overland crossing of a major range has a named pass, engineered crossing or explicit impassability.
- **Climate test:** no unexplained sharp biome transitions.
- **Supply test:** every major city can feed itself or has a credible import network.
- **Route test:** roads connect actual destinations and avoid impossible gradients unless engineered.
- **Population test:** settlement density matches water, food, disease, safety and transport.
- **Extraction test:** mining and harvesting have labor, logistics, waste and ecological effects.
- **Persistence test:** a generated location remains the same after departure and return.
- **Causal test:** infrastructure damage affects connected systems without triggering arbitrary global consequences.
- **Canon test:** manga-established geography is not moved to suit the expansion map without explicit justification and provenance.

## 9. Current lock status

Locked: dependency-first generation, stable IDs, authored major locations, persistent discovered locations, causal geography, source labels and rejection of unconstrained randomness.

Not locked: planet size, map projection, continents' final outlines, exact coordinates, climate numbers, global calendar and total settlement counts.
