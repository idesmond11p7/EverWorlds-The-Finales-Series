# 33. Playability Regression Tests v1
Status: executable-by-review scenario suite for the initial CCV3 card and core lorebook. These are test cases, not a claim that every behavior is guaranteed by prompt text. Run them in SillyTavern after importing the card and lorebook; record actual outputs and state deltas.

## Test protocol
For each test, initialize only the stated facts. Run the user input exactly. Grade **PASS** only when the output satisfies every required condition and violates none of the forbidden conditions. Record model, preset, context size, card/lorebook versions, transcript, and result. A failed test must produce a targeted repair and a rerun.

## A. Setup and agency

### T-001 — Missing species blocks initialization
**Initial state:** No species is declared on the character card or in campaign state.
**Input:** “Start the campaign.”
**Pass:** The assistant requests species selection or explicitly records it as unresolved before in-world play.
**Fail if:** It silently assigns human, elf, demon, or any other species.

### T-002 — Action declaration is an attempt
**Initial state:** Player is unarmed, three meters from a closed locked door.
**Input:** “I am opening the locked door.”
**Pass:** It checks the lock, access and available tools; if no valid means exists, the door remains closed and the attempt may fail or be interrupted.
**Fail if:** The door opens merely because the user declared the action.

### T-003 — Present-continuous convention
**Initial state:** A guard is across a courtyard; no attack has begun.
**Input:** “I am aiming at the guard.”
**Pass:** It treats the declaration as an attempted aim, describes plausible line of sight and exposure, and does not automatically fire.
**Fail if:** It turns aiming into an attack or changes the user's action to a different voluntary action.

### T-004 — Player puppeting
**Initial state:** Player is facing an intimidating official.
**Input:** “I am listening to the official.”
**Pass:** The response describes what can be heard and does not invent the player's fear, anger, agreement, speech or decision.
**Fail if:** It dictates voluntary thoughts, emotions, dialogue or movement.

## B. Inventory and powers

### T-005 — Empty inventory stays empty
**Initial state:** Inventory has no items and no loadout was selected.
**Input:** “inventory”
**Pass:** The report states that no carried items have been established.
**Fail if:** A sword, coins, armor, food or other item appears without an acquisition event.

### T-006 — Declared Teigu possession is rejected
**Initial state:** No Teigu appears in the inventory.
**Input:** “I am activating Murasame.”
**Pass:** The response notes that possession/access is not established and does not grant it.
**Fail if:** Murasame appears or activates by declaration alone.

### T-007 — Unknown catalogue entry stays unknown
**Initial state:** Player asks for the exact function of an unverified Teigu entry.
**Input:** “Explain the full ability set of the missing entry.”
**Pass:** The response labels the information unknown and asks for source verification or limits itself to established facts.
**Fail if:** It invents a definitive canon item or ability.

### T-008 — Capability gate
**Initial state:** Ordinary human character has no flight system, equipment or relevant ability.
**Input:** “I am flying to the roof.”
**Pass:** Flight is unavailable; the assistant may offer a grounded alternative only as a possibility, not an executed choice.
**Fail if:** The character flies because the genre allows it.

## C. Spatial and temporal persistence

### T-009 — Locked geometry persists
**Initial state:** The east door is locked; west corridor is open; player is in the entry room.
**Input sequence:** “I am inspecting the east door.” Then “I am walking into the east room.”
**Pass:** The door remains locked unless a valid opening event occurs; the second action cannot pass through it.
**Fail if:** The door becomes open or the player teleports into the room.

### T-010 — Damage persists on revisit
**Initial state:** A table has a broken leg and is located beside the window.
**Input sequence:** Leave the room; return later; inspect the table.
**Pass:** The same table remains in the same established position with its broken leg unless a repair or movement event occurred.
**Fail if:** The table regenerates intact or changes location without cause.

### T-011 — Time advances with meaningful action
**Initial state:** Local time is established as 16:00.
**Input:** “I am walking for twenty minutes to the market.”
**Pass:** Time advances by a plausible duration and the route/arrival are resolved against known conditions.
**Fail if:** Time remains 16:00 after an actual twenty-minute journey or the player arrives instantly.

### T-012 — Route not guaranteed
**Initial state:** A mountain pass is closed by a documented landslide; a longer route exists.
**Input:** “I am travelling through the pass.”
**Pass:** The closure blocks ordinary passage unless the player attempts a plausible clearance, climb or alternative; the longer route remains an option, not an automatic choice.
**Fail if:** The player passes through an impassable closure without resolution.

## D. Knowledge and causality

### T-013 — No NPC telepathy
**Initial state:** Player privately thinks about betraying a faction leader; no speech, action or mind-reading ability reveals it.
**Input:** “I am standing quietly.”
**Pass:** NPCs do not react to the private thought as known fact.
**Fail if:** An NPC accuses the player based solely on hidden narration.

### T-014 — Information delay
**Initial state:** A remote town has no magical communication link; a witness must travel several days to report a local event.
**Input:** Trigger the local event, then ask what the remote town knows immediately.
**Pass:** The remote town has no knowledge of the event yet unless another valid channel exists.
**Fail if:** Distant authorities react instantly.

### T-015 — Rumor uncertainty
**Initial state:** A traveler reports a second-hand claim about a monster attack.
**Input:** “I am asking the innkeeper what happened.”
**Pass:** The answer preserves source and uncertainty, distinguishing rumor from verified observation.
**Fail if:** The rumor is narrated as confirmed fact without evidence.

### T-016 — Bounded secondary effects
**Initial state:** A small mine's output drops after a local equipment failure; no evidence connects it to regional water systems.
**Input:** “What changes after the breakdown?”
**Pass:** Effects remain tied to supported production, repair, labor or delivery dependencies.
**Fail if:** Unrelated distant towns collapse through arbitrary butterfly effects.

## E. Geography, canon and journal

### T-017 — River and watershed constraint
**Initial state:** A proposed river route would cross a mountain ridge without a pass, canal or tunnel.
**Input:** “Put a major river through the ridge.”
**Pass:** The assistant rejects or revises the proposal unless a plausible physical or supernatural mechanism is defined.
**Fail if:** The river crosses the divide solely for convenience.

### T-018 — Desert settlement viability
**Initial state:** A proposed large desert city has no river, aquifer access, rain capture, imports or food-production system.
**Input:** “Add a million residents.”
**Pass:** The city is rejected as currently unsupported or its water/food/logistics systems are explicitly designed.
**Fail if:** The population is accepted with no material basis.

### T-019 — Manga canon outranks original expansion
**Initial state:** A proposed original event contradicts a verified manga event in the same timeline.
**Input:** “Make the original event replace the manga event.”
**Pass:** The contradiction is flagged; manga canon remains unless a plausible player-caused divergence is explicitly established.
**Fail if:** Original expansion silently overwrites canon.

### T-020 — Journal does not execute
**Initial state:** Player is safe at home; no in-world action has been taken.
**Input:** “journal: I plan to assassinate the governor tomorrow.”
**Pass:** The plan is stored as an out-of-world note; no time passes, NPC learns of it, or assassination begins.
**Fail if:** The world executes the plan or treats it as an accepted in-world commitment.

## F. Rendering and interface

### T-021 — Spatial clarity under movement
**Initial state:** A courtyard contains a wall, a cart, a guard and an eastern gate with established relative positions.
**Input:** “I am moving toward the eastern gate.”
**Pass:** The response preserves the spatial arrangement, describes relevant movement and obstruction, and does not teleport the player.
**Fail if:** Distances, object positions, cover or line of sight change without cause.

### T-022 — Interface does not reveal hidden state
**Initial state:** An NPC has a private plan unknown to the player.
**Input:** “status”
**Pass:** Status reports the player's condition and active effects only.
**Fail if:** The NPC's secret plan is disclosed without an information channel.

### T-023 — Visited location stability
**Initial state:** A generated inn has a stable location ID, room layout and named innkeeper.
**Input sequence:** Leave; visit another region; return.
**Pass:** The inn, layout and innkeeper persist unless a supported event changed them.
**Fail if:** The location is regenerated as an unrelated inn.

### T-024 — No false claim of persistence
**Initial state:** Long conversation with context pressure; some earlier state is no longer certain.
**Input:** Ask for a specific unrecorded item acquisition time.
**Pass:** The assistant labels uncertainty or requests a state receipt.
**Fail if:** It fabricates a precise acquisition time or claims an external database saved it.

## Acceptance criteria
The initial package is not validated until:
- CCV3 card JSON parses;
- lorebook JSON parses and all entries have keys, content and enabled status;
- the card and lorebook import into the target SillyTavern version;
- all 24 tests are run and results recorded;
- all failures are repaired and retested;
- no unverified claim is presented as a successful test.
