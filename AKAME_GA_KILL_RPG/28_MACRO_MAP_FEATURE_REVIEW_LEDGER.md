# 28. Macro-Map Feature Review Ledger
Status: active review ledger, version 1. No exact coordinates are committed. This ledger tracks proposed physical-map features and their dependencies so revisions propagate instead of silently breaking downstream geography.

## 1. Ledger rules

Every map feature receives a stable ID. Names may change; IDs should not be reused for unrelated features. Record whether a feature is a canon claim, authorial constraint, original authored proposal, or unresolved hypothesis.

**Evidence classes**
- **C1 — Primary canon verified:** directly checked against manga panels or an official primary source.
- **C2 — Secondary report:** a fan reference or other secondary source; not yet panel-verified.
- **A — Authorial lock:** a setting constraint explicitly established by the author.
- **O — Original proposal:** new geography created for this project.
- **U — Unresolved:** insufficient evidence or dependent on a decision not yet made.

**Status**
- **Proposed:** plausible idea, not yet checked against all dependencies.
- **Conditional:** can be retained only if named prerequisites are satisfied.
- **Accepted-topology:** relative placement and causal logic accepted; no exact coordinates implied.
- **Locked:** an explicit authorial decision or a validated feature not to be changed casually.
- **Rejected:** fails a dependency or contradicts a higher-priority constraint.
- **Needs-source-check:** requires direct evidence before it can be treated as canon.

A feature may be accepted-topology without having a final coordinate. Do not use “locked” to disguise an untested guess.

## 2. Current planetary and macro-geography entries

| ID | Feature | Class | Status | Rationale / dependency | Open validation |
|---|---|---|---|---|---|
| MAP-001 | Planetary surface area = 12.3 Earth surface areas | A | Locked | User-defined scale constraint; impacts eventual map scale and planetary parameter model | Resolve radius/gravity consistency without changing surface-area lock |
| MAP-002 | Gravity somewhat stronger than Earth | A | Conditional | User-defined qualitative constraint, but no numerical value exists | Select radius, density and gravity model coherently |
| MAP-003 | Six macro-geographic systems | O | Proposed | Provides distinct geography without implying equal-sized continents | Test silhouettes, land/ocean fraction and continuity |
| MAP-004 | Imperial Heartland and Inner Marches | O + canon-adjacent | Conditional | Main location system for Empire and adjacent territories | Separate manga-supported footprint from original expansion |
| MAP-005 | Great Arid Belt | O | Proposed | Supports multiple desert types, civilizations and water regimes | Establish latitudes, wind/moisture mechanisms and rain shadows |
| MAP-006 | Monsoon Rim and Green Basins | O | Proposed | Wet windward slopes, seasonal rivers and floodplain settlement | Check ocean configuration, seasonal circulation and basin outlet |
| MAP-007 | Northern Shield and Cold Interior | O | Proposed | Cold forests, uplands, lakes, snowmelt and seasonal routes | Define latitude/elevation and snowmelt basins |
| MAP-008 | Broken Western Lands | O | Proposed | Fragmented terrain, multiple watersheds, passes and straits | Decide rift/tectonic hypothesis and coherent coastlines |
| MAP-009 | Outer Maritime and Deepwater Systems | O | Proposed | Shelf seas, island arcs, deep basins and distinct maritime routes | Check plate-boundary hypothesis, currents and marine ecology |
| MAP-010 | Main mountain wall between wet region and interior drylands | O | Proposed | Provides a physical rain-shadow mechanism | Confirm prevailing moisture direction before fixing the dry side |
| MAP-011 | Older uplands in the Imperial Heartland | O | Proposed | Divides drainage and creates mineral/route variation | Define elevation and river source regions |
| MAP-012 | Rift or fragmented geological province in western region | O | Proposed | Explains broken basins, lakes and possible geothermal zones | Align volcanism and mineralization with the tectonic sketch |
| MAP-013 | Island arc in outer maritime region | O | Conditional | Supports deep trenches, volcanic islands and navigational chokepoints | Establish plausible plate boundary and regional hazard pattern |
| MAP-014 | Northern snowmelt river system | O | Proposed | Connects cold uplands to lower river corridors | Mark source elevations, tributaries, outlet and freeze/thaw effects |
| MAP-015 | Imperial Heartland major river basin | O + canon-adjacent | Proposed | Supports dense settlement and strategic transport | Keep original river separate from any unverified canon river placement |
| MAP-016 | Monsoon-driven seasonal river system | O | Proposed | Supports floodplain agriculture and seasonal access constraints | Check rainfall, watershed area, outlet and flood season |
| MAP-017 | Inland endorheic basin within arid belt | O | Proposed | Supports salt pan, terminal lake or seasonal playa | Calculate plausible inflow, evaporation and sediment accumulation |
| MAP-018 | Multiple episodic desert wadis | O | Proposed | Creates temporary flood hazards and seasonal water access | Map catchments and identify downstream flash-flood paths |
| MAP-019 | Major delta or estuary | O | Proposed | Creates productive, contested settlement and shipping corridor | Confirm sediment supply, gradient, tides and coastal geometry |
| MAP-020 | Broad agricultural floodplain | O | Proposed | Supports dense population but carries flood and disease risks | Check river regime, levees, flood storage and upstream dependencies |
| MAP-021 | Desert aquifer recharge and discharge zones | O | Conditional | Makes oasis locations and water politics causal | Distinguish renewable recharge from fossil/slow-recharge water |
| MAP-022 | Strategic mountain passes | O | Proposed | Connects otherwise separated basins and creates chokepoints | Identify elevation, slope, weather closure and bypass costs |
| MAP-023 | Major sea straits | O | Proposed | Constrain maritime trade and naval movement | Confirm coastline and navigable depth assumptions |
| MAP-024 | Coastal shelves and reef zones | O | Conditional | Support fisheries, ports and marine ecologies | Match shelf depth and reef temperature/salinity requirements |
| MAP-025 | Manga-era Empire footprint | C/U | Needs-source-check | Canon must remain intact; secondary reports are not sufficient for exact borders | Panel-verify each named location and relationship before drawing a precise outline |
| MAP-026 | Great Canal and reported dimensions | C2/U | Needs-source-check | Secondary summaries report a very long canal; measure and meaning need verification | Locate the reference, verify translation/context, do not use it to infer whole-map scale |
| MAP-027 | Imperial Capital reported area | C2/U | Needs-source-check | Fan references report a large area; measurement definition may be unclear | Verify manga/source context and distinguish city, administrative area and surrounding region |
| MAP-028 | Original atlas PL-001 to PL-060 | O | Conditional | Place seeds only after landforms, water and climate exist | Assign macro-region, watershed/coast, route graph and settlement basis |
| MAP-029 | Twelve desert civilization concepts | O | Conditional | Must occupy different desert types and water regimes | Audit environmental and cultural redundancy before placement |
| MAP-030 | Final coordinates for cities and borders | U | Blocked | No scaled schematic or physical parameter model exists yet | Do not assign until macro-map topology and scale review pass |

## 3. Dependency graph

Use this order for changes. If a parent feature changes, inspect every dependent feature before accepting the revision.

1. **Planetary model** (MAP-001 to MAP-002, plus unresolved rotation/tilt/land-ocean fraction).
2. **Coastline and macro-system silhouettes** (MAP-003 to MAP-009).
3. **Tectonic and relief hypotheses** (MAP-010 to MAP-013).
4. **Watershed and coastal hydrology** (MAP-014 to MAP-020).
5. **Groundwater and resource distribution** (MAP-021 and relevant resource overlays).
6. **Passes, straits and route graph** (MAP-022 to MAP-024).
7. **Canon placement verification** (MAP-025 to MAP-027).
8. **Original atlas and civilization placement** (MAP-028 to MAP-029).
9. **Scale, coordinates and regional maps** (MAP-030).

A downstream feature cannot be used as proof that its upstream cause exists. For example, a city requiring a river does not justify bending the river to reach it; the city must move or its water infrastructure must be explicitly designed and paid for.

## 4. Change-impact rules

When a feature changes, record:
- changed feature ID and old/new proposal;
- reason and evidence;
- dependent IDs inspected;
- whether any accepted feature was invalidated;
- consequences for routes, settlements, ecology, politics, campaign starts and canon boundaries;
- review status and unresolved questions.

Examples:
- Moving a mountain axis triggers a review of windward/leeward climate, river sources, mineral provinces, passes, rain shadows, settlement viability and desert margins.
- Moving a watershed divide triggers a review of river direction, aquifer recharge assumptions, floodplains, irrigation, water rights, pollution and city water supply.
- Closing a strait triggers a review of sea routes, port economies, naval power, migration and information delay.
- Moving an atlas settlement triggers a review of its economic niche, nearest route nodes, jurisdiction, climate and dependency hooks.
- Changing the planetary scale model triggers a review of distance ranges, travel estimates, communication delays and the physical plausibility of gravity-dependent assumptions.

## 5. Review decisions that remain open

Do not silently resolve these by inventing numbers:
- planetary radius and density;
- numerical gravity and how it remains slightly stronger than Earth;
- rotation period, axial tilt, orbital eccentricity and calendar;
- land/ocean fraction and final coastlines;
- exact latitude bands and prevailing circulation;
- tectonic plates, mountain ages and active hazards;
- map projection and scale;
- verified manga geography placements and exact borders;
- final atlas coordinates and travel distances.

## 6. Schematic-map acceptance gate

The map can move from topology draft to provisional placement only when:
- all six macro-systems have distinct silhouettes and clear physical identities;
- mountain axes and ocean moisture sources produce plausible climate contrasts;
- major watersheds are visible and river direction is coherent;
- the Great Arid Belt contains multiple desert types, not one continuous generic sand field;
- the northern system has a credible cold-season and snowmelt model;
- strategic passes and straits connect actual landforms rather than serving as arbitrary plot doors;
- the Empire's verified canon footprint is visually distinct from original proposals;
- original locations remain movable until their physical and economic dependencies pass review;
- unresolved claims are visibly marked;
- no exact coordinates or travel times are presented as facts without a defined scale.

## 7. Immediate next action

Produce a schematic map draft from documents 26 and 27, then use this ledger to review each macro-feature. The first draft should be judged for topology, relief, hydrology and climate logic, not polish. Once the macro-map passes, add the atlas locations and desert civilizations as a separate placement layer. Do not begin street-level maps yet.
