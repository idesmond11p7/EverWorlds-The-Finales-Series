# Experiment 001 — Spatial Reality System

Status: Experimental solution / implementation brief
Date: 2026-09-26
Scope: EverWorlds extension — first executable reality-system experiment
Primary question: Can EverWorlds maintain a coherent model of space independently of prose generation or roleplay?

## 1. The actual problem

The first mistake would be to implement “a DAG spatial system.”

A DAG is a data structure. EverWorlds needs a spatial model.

Research into real spatial systems points to several distinct concerns rather than one universal structure:

- OGC Simple Features separates geometry into points, curves, surfaces, and collections and associates geometry with a spatial reference system.
- OGC topology work treats spatial relations as a separate concern from geometry, including relations based on intersections of interiors, boundaries, and exteriors.
- OGC IndoorGML 2.0 separates a core model for spaces/topological connectivity from navigation networks. It models spaces, subdivision contexts, connectivity, and both logical and metric navigation networks.
- ISO 19164:2024 provides an indoor feature model intended as a common foundation for location-based applications and describes integration with geometric/topological models such as IndoorGML, CityGML, and IFC.
- RDF demonstrates the usefulness of graph-based subject-predicate-object relationships for representing heterogeneous knowledge rather than forcing every relation into a hierarchy.

Conclusion: EverWorlds should not make the DAG the spatial system.

The correct first hypothesis is a hybrid spatial model:

hierarchical containment + arbitrary spatial relations + coordinate frames/transforms + optional geometry + navigation/connectivity + dynamic occupancy/state.

The first experiment should discover which parts are actually necessary, but this gives us a technically grounded starting model instead of inventing a fantasy data structure from scratch.

## 2. What “space” means for EverWorlds

EverWorlds needs to distinguish at least five different questions.

### A. What is the thing?

Examples:
- Earth
- Tokyo
- a school
- classroom 2A
- a person
- a chair
- a door
- a portal

This is entity identity, not geometry.

### B. What spatial container/context is it associated with?

Examples:
- Classroom 2A is inside School A.
- School A is inside Tokyo.
- Tokyo is inside Japan.
- Alice is currently in Classroom 2A.

This is where the DAG-like hierarchy is useful.

### C. What is its geometric position/shape?

Examples:
- Classroom occupies a volume.
- Alice occupies a position inside that volume.
- A wall is a surface.
- A door occupies an opening in the wall.

This is geometry.

### D. How are things spatially related?

Examples:
- north_of
- south_of
- adjacent_to
- connected_to
- inside
- contains
- overlaps
- intersects
- touches
- near
- far
- visible_from
- blocked_from

These are relations.

### E. Can something travel between them?

A classroom can be physically adjacent to another classroom but still be inaccessible because a wall separates them.

Therefore:

physical relationship != navigational relationship.

This distinction is directly consistent with the separation between spatial/topological modelling and navigation modelling in IndoorGML.

## 3. Recommended model

### 3.1 Spatial Entity

Every spatially relevant thing receives a stable identity.

Conceptually:

Entity
  id
  kind
  semantic_type
  spatial_state
  geometry?
  coordinate_frame?
  parent_context?
  relations[]
  knowledge_state?

Do not interpret this as a final TypeScript interface. It is the conceptual model.

A person, building, room, object, planet, portal, or supernatural location can participate in the same spatial system without being forced to have identical geometry.

## 4. The DAG: use it, but only where it belongs

The DAG should represent hierarchical containment/context, not every spatial relationship.

Example:

Earth
  └── Japan
      └── Tokyo
          └── School
              └── Building A
                  └── Floor 2
                      └── Classroom 2A
                          └── Alice

This provides efficient answers to questions such as:
- What contains Alice?
- Which building is Alice in?
- Which city is Alice in?
- Which world/realm contains this location?

A containment graph must reject or explicitly handle cycles.

For example:

Classroom A
  contains Classroom B
    contains Classroom A

is invalid for ordinary physical containment.

But this is NOT enough.

The following should not be encoded by forcing them into the parent-child DAG:

Classroom A --adjacent_to--> Classroom B
Alice --north_of--> Bob
Door A --connects--> Hallway
Portal A --links--> Earth
Building A --above--> Subway Station

Those belong to the relation layer.

## 5. Spatial Relation Graph

EverWorlds therefore needs a second graph.

Conceptually:

subject ── relation ──> object

Examples:

RoomA ── adjacent_to ──> RoomB
RoomA ── above ──> Basement
Alice ── near ──> Bob
Door1 ── connects ──> RoomA
Portal1 ── links ──> Earth

This should be a general property graph, not a DAG.

Relations may be:
- directional;
- symmetric;
- inverse;
- transitive;
- non-transitive;
- conditional;
- dynamic;
- geometry-derived;
- manually asserted.

Examples:

inside(Alice, RoomA) has an inverse:
contains(RoomA, Alice)

north_of(Alice, Bob) has an inverse:
south_of(Bob, Alice)

But near(Alice, Bob) is not necessarily transitive.

Alice near Bob + Bob near Charlie does not imply Alice near Charlie.

The system therefore needs relation semantics rather than treating every edge identically.

## 6. Coordinate frames

This is one of the major pieces missing from a simple location tree.

EverWorlds will eventually contain:
- rooms;
- buildings;
- cities;
- planets;
- dimensions;
- realms;
- pocket spaces;
- moving objects;
- portals;
- potentially non-Euclidean or supernatural spaces.

A single global coordinate system will become brittle.

Instead, spatial entities should be able to define local coordinate frames.

Conceptually:

Earth frame
   ↓
Tokyo frame
   ↓
School frame
   ↓
Building frame
   ↓
Floor frame
   ↓
Classroom frame

An object's local position can then be expressed relative to its current frame.

This is a standard pattern in real spatial systems: geometry exists within a spatial reference system rather than existing as an unexplained universal coordinate.

Why this matters:
- a person can be 2 m from a door;
- a room can be 30 m from another room;
- a building can be located somewhere in a city;
- a ship can move through space;
- a planet can rotate;
- a portal can have a destination that is not physically adjacent.

We do not need all of that in Experiment 001.

We need the representation to not make those futures impossible.

## 7. Geometry should be optional

Do not make every entity require full 3D geometry.

Use levels of spatial precision.

Level 0 — contextual
Alice → Classroom 2A

Level 1 — relational
Alice near Door1
Classroom2A adjacent_to Hallway2

Level 2 — metric
Alice = (x, y, z) within Classroom2A

Level 3 — geometric
Alice has a volume/shape
Classroom has a volume
Door has an opening geometry

Level 4 — advanced
collision
line-of-sight
occlusion
pathfinding
physical simulation

EverWorlds is not trying to become a CAD program.

Real geospatial standards distinguish geometry from semantics and topology; detailed geometry is not the only useful representation.

## 8. Topology before physics

Experiment 001 should test topological reality before physical simulation.

We need to know things such as:
- inside
- contains
- connected
- disconnected
- adjacent
- overlaps
- touches
- intersects

before worrying about realistic collision or continuous movement.

This gives EverWorlds a useful distinction:

“These spaces have a spatial relationship.”

versus:

“A character can physically navigate between these spaces.”

## 9. Navigation is another layer

Suppose:

Classroom A
Classroom B

They share a wall.

They are spatially adjacent.

But there is no door.

Therefore:

adjacent_to(A, B) = true
navigable(A, B) = false

Now add a door:

Door1 connects A ↔ B

and:

navigable(A, B) = true

The navigation graph should be derived from, but not identical to, the spatial graph.

IndoorGML is particularly relevant here because its conceptual model separates spatial contexts/connectivity from navigation networks and supports logical and metric navigation networks.

## 10. Dynamic spatial state

EverWorlds is not a static map.

Things move.
Doors open.
Walls collapse.
Buildings are destroyed.
People enter rooms.
Vehicles move.
Portals appear.
Realms connect/disconnect.

Therefore spatial relationships need temporal state.

A useful conceptual rule is:

The world stores current spatial truth; events explain how that truth changed.

Example:

12:00
Alice → Classroom

12:05
Alice → Hallway

12:08
Alice → Rooftop

The event log is not the spatial state itself.

It explains the transition.

This separation prevents the system from having to reconstruct every spatial query by replaying the entire history.

## 11. Epistemic space

This is essential for EverWorlds.

There are at least three different statements:

1. Alice is physically in Room X.
2. Bob believes Alice is in Room X.
3. The player believes Alice is in Room X.

Those are not necessarily identical.

Therefore the spatial system should eventually distinguish:

world truth

from

known spatial information.

Example:

WORLD:
Alice → hidden basement

PLAYER KNOWLEDGE:
Alice → unknown

Bob KNOWLEDGE:
Alice → probably classroom

Do not implement the complete epistemic layer in Experiment 001.

But the architecture must not make it impossible.

## 12. Supernatural / non-standard space

This is where a normal GIS model eventually becomes insufficient.

EverWorlds may contain:
- pocket dimensions;
- portals;
- folded spaces;
- overlapping realms;
- spaces larger inside than outside;
- locations without ordinary coordinates;
- spaces connected by nonphysical transitions;
- supernatural boundaries;
- spaces whose topology changes;
- locations whose physical and metaphysical positions differ.

Therefore:

coordinate cannot be the definition of space.

Coordinates are one representation of spatial state.

The deeper model is:

entities + spatial contexts + relations + coordinate frames + topology + connectivity + state.

This lets ordinary Euclidean space be one implementation rather than the universal law of the entire system.

## 13. What Experiment 001 actually builds

Do NOT build the full EverWorlds spatial engine.

Build a Spatial Laboratory inside the extension.

It has four pieces.

### A. State

A deterministic in-memory world containing:
- spatial entities;
- containment hierarchy;
- relations;
- coordinate frames;
- optional coordinates;
- current occupancy;
- navigation links.

No LLM.
No roleplay.
No character card.
No prose generation.

### B. Operations

The test harness can execute operations such as:

create_entity
create_space
contain
move
relate
unrelate
connect
disconnect
set_position
destroy
open
close

### C. Queries

The harness asks:

where_is(entity)
containing_spaces(entity)
contents(space)
relation(subject, relation, object)
neighbors(space)
reachable_from(space)
path_between(A, B)
position(entity)
occupants(space)

### D. Inspector

The extension renders the current state visually.

Not a beautiful EverWorlds HUD.

A developer/debug interface.

Example:

WORLD
├─ Earth
│  └─ Japan
│     └─ Tokyo
│        └─ School
│           ├─ Classroom A
│           │  ├─ Alice
│           │  └─ Phone
│           ├─ Hallway
│           └─ Rooftop

And a relation panel:

Classroom A
  adjacent_to → Hallway
  above → Basement
  connected_to → Hallway

This gives us direct visibility into whether the model is behaving.

## 14. The first test fixture

Use an intentionally tiny but spatially nontrivial environment.

World:

Earth
  └── Tokyo
      └── School
          └── Building A
              ├── Floor 1
              │   ├── Classroom A
              │   ├── Hallway A
              │   └── Courtyard
              └── Floor 2
                  ├── Classroom B
                  └── Rooftop

Entities:
Alice
Bob
Phone
Door1
Door2

Relations:
Classroom A adjacent_to Hallway A
Classroom A connected_to Hallway A
Hallway A connected_to Courtyard
Floor 2 above Floor 1
Classroom B connected_to Rooftop

Initial state:
Alice → Classroom A
Bob → Courtyard
Phone → Alice

No story is required.

## 15. Test sequence

### Test 1 — containment

Move Alice:
Classroom A → Hallway A

Verify:
where_is(Alice) = Hallway A

and Alice is no longer in Classroom A.

### Test 2 — nested containment

Ask:
containing_spaces(Alice)

Expected:
Hallway A
Floor 1
Building A
School
Tokyo
Earth

### Test 3 — carried object

Alice carries Phone.

Move Alice to Courtyard.

Expected:
Phone follows Alice.

### Test 4 — dropping

Alice drops Phone.

Move Alice elsewhere.

Expected:
Phone remains at the drop location.

### Test 5 — adjacency vs connectivity

Create two adjacent rooms with no doorway.

Expected:
adjacent = true
connected = false
reachable = false

Add a doorway.

Expected:
connected = true
reachable = true

### Test 6 — path

Create:
Classroom A → Hallway A → Courtyard

Ask for path:
Classroom A → Courtyard

Expected:
Classroom A
Hallway A
Courtyard

### Test 7 — verticality

Ask:
relation(Classroom B, above, Floor 1)

The system should be able to represent vertical relationships independently of parent containment.

### Test 8 — contradiction

Attempt:
Alice → Classroom A
Alice → Rooftop

without a transition.

The system must NOT silently pretend both are ordinary current locations.

The result should be an explicit spatial-state conflict requiring a defined resolution policy.

### Test 9 — deletion

Destroy a doorway.

Expected:
spatial adjacency may remain
connectivity disappears
navigation/path results change

This tests whether spatial truth and navigation truth have been incorrectly fused.

### Test 10 — hidden fact

Create:
Basement X

but expose it to neither the player-facing inspector nor any knowledge layer.

The underlying world should still contain it.

This establishes that the world model can eventually be larger than the player's knowledge.

## 16. The invariants

The experiment is successful only if the system maintains invariants.

### Identity invariant
An entity keeps the same identity when it moves.

### Containment invariant
An entity cannot have contradictory ordinary containment without the system explicitly representing the contradiction.

### Hierarchy invariant
Ordinary containment cannot form illegal cycles.

### Inverse invariant
If:
A inside B
then:
B contains A
must agree.

### Movement invariant
Moving an entity updates all queries that depend on its current location.

### Attachment invariant
If an object is attached/carried by an entity, movement updates the object's effective location.

### Navigation invariant
Navigation cannot exist through a disconnected barrier unless an explicit traversal mechanism exists.

### Relation invariant
Symmetric relations must remain symmetric.
Inverse relations must remain consistent.

### Destruction invariant
Removing a spatial structure must update dependent relationships rather than leaving stale references.

### Determinism invariant
Given identical initial state + identical operations, the spatial result must be identical.

Experiment 001 should be deterministic.

## 17. How the DAG gets tested

The DAG is not the experiment.

The DAG is one candidate mechanism.

We test whether it correctly handles:

Earth
  ↓
Country
  ↓
City
  ↓
Building
  ↓
Floor
  ↓
Room

Then we deliberately introduce cases that a DAG cannot naturally represent:

adjacent
above
below
near
connected
overlaps
portal_to
visible_from

If the DAG starts becoming polluted with hacks to represent those relationships, that is evidence that the DAG belongs only to the containment layer.

That is the result we want.

## 18. Recommended technical architecture

Conceptually:

SpatialWorld
   │
   ├── EntityRegistry
   ├── ContainmentGraph
   ├── RelationGraph
   ├── CoordinateFrames
   ├── NavigationGraph
   ├── SpatialState
   ├── SpatialOperations
   └── SpatialQueries

And separately:

SpatialLab UI
   │
   ├── World Inspector
   ├── Entity Inspector
   ├── Relation Inspector
   ├── Operation Console
   ├── Query Console
   └── Event/Mutation Log

This is intentionally not the final EverWorlds architecture.

It is the smallest architecture that lets us test the hypothesis properly.

## 19. Why we should NOT start with an LLM

The first experiment should be deterministic.

If an LLM is involved, a failure could mean:
- the spatial model is wrong;
- the query interpretation is wrong;
- the model hallucinated;
- the prompt was wrong;
- state serialization was wrong;
- tool calling was wrong;
- memory was wrong.

That destroys experimental clarity.

Instead:

deterministic state
      ↓
deterministic operation
      ↓
deterministic query
      ↓
deterministic answer

Only after this works should an LLM be allowed to interact with the system.

Then the next experiment becomes:

Can an LLM reliably use the spatial system without corrupting spatial truth?

That is a separate hypothesis.

## 20. Why this is the correct first experiment

The objective is NOT:

Build a spatial engine.

The objective is:

Discover whether an externalized spatial state can remain coherent under mutation and querying.

If the answer is yes, we have demonstrated a real foundation for later systems.

If the answer is no, we discover exactly where the model breaks.

More importantly, the experiment exposes which spatial concepts EverWorlds actually needs.

We do not need to prematurely implement:
- planetary coordinates;
- orbital mechanics;
- 3D physics;
- collision;
- portals;
- non-Euclidean geometry;
- supernatural topology;
- full GIS;
- visual mapping;
- LLM reasoning;
- roleplay.

Those become later experiments only when the first system demonstrates a need for them.

## 21. The actual solution

The solution is not a DAG spatial system.

It is:

A graph-based spatial state engine in which a DAG represents hierarchical containment, a general relation graph represents arbitrary spatial relationships, coordinate frames represent metric/transformable position, and a separate navigation graph represents traversability.

Above that sits dynamic state.

Later, an epistemic layer can represent what different entities know or believe about spatial truth.

Geometry is optional and progressive rather than mandatory.

This is much closer to how established spatial modelling separates geometry, topology, semantics, and navigation than trying to collapse all spatial meaning into one graph.

## Research basis

OGC Simple Features — geometry types and spatial reference systems:
https://www.ogc.org/standards/sfa/

OGC topology / DE-9IM:
https://portal.ogc.org/files/47664

OGC IndoorGML:
https://www.ogc.org/standards/indoorgml/

OGC IndoorGML 2.0 announcement:
https://www.ogc.org/announcement/ogc-publishes-indoorgml-2-0-part-1-conceptual-model-standard/

ISO 19164:2024 — Geographic information — Indoor feature model:
https://www.iso.org/obp/ui?_escaped_fragment_=iso:std:iso:19164:ed-1:v1:en

W3C RDF 1.2:
https://www.w3.org/news/2026/w3c-invites-implementations-of-rdf-1-2-concepts-and-abstract-data-model-and-rdf-1-2-semantics/

IFC and indoor navigation survey:
https://doi.org/10.1016/j.autcon.2020.103436

Bottom line: We do not need to invent spatial modelling from nothing. We need to adapt proven distinctions to EverWorlds' much stranger requirement: a persistent fictional reality whose spatial rules can eventually extend beyond ordinary physical space.
