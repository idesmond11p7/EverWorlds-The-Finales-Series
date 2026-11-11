# Validation and Failure Tests

[ID: SHIP-07]
[STATUS: ACTIVE TEST PLAN / NOT EXECUTED]
[DATE: 2026-11-11]
[SCHEMA: ACCEPTANCE TESTS / FAILURE MODES]
[UPSTREAM: SHIP-01..SHIP-06]
[DOWNSTREAM: FUTURE PROMPT RELEASE / IMPLEMENTATION]
[CONTAINS: Test scenarios, pass criteria, unresolved design decisions]
[EXCLUDES: Claims that tests have already passed]
[SUPERSEDES: None]
[LAST-TOUCH: Initial test design]
[MUST-RECHECK: Every prompt or architecture revision]
[MODEL-GRADE: G2]
[EVIDENCE-STATE: PROPOSED TESTS]
[OPERATIONAL-STATE: NOT TESTED]

## 1. Core acceptance criteria

A release candidate must demonstrate:
- commands express attempts, not guaranteed outcomes;
- conditional plans resolve only when their conditions actually occur;
- player conscious agency remains protected;
- character psychology can resist player intention when justified;
- NPCs and the environment retain independent initiative;
- action consequences persist and propagate;
- time, space, perception and knowledge remain coherent;
- the private game layer does not overwhelm prose;
- power modules activate only when supported by the setting;
- setting research avoids trope compression;
- prose remains immersive, readable and character-specific;
- OOC corrections repair the smallest affected state without compounding errors.

## 2. Adversarial scenarios

### Test A — Loaded weapon
Player has a loaded firearm. No firing command is issued.
**Pass:** ammunition remains unchanged; no shot occurs merely because the weapon is loaded.

### Test B — Guaranteed slap
Player commands an approach and slap against an NPC.
**Pass:** approach and contact are resolved as attempts. Position, access, NPC movement, interruption, character psychology and timing determine the outcome. The NPC is not forced to accept the event.

### Test C — Character refusal
Player directs a character to perform an action that strongly conflicts with established values or fears.
**Pass:** the translation layer evaluates the character's actual psychology. Any resistance is specific and grounded, not arbitrary.

### Test D — Conditional plan
Player provides IF/THEN branches for an escape.
**Pass:** only observed conditions trigger branches; the plan does not dictate NPC behavior or guarantee success.

### Test E — Inactivity
Player issues no action over several turns.
**Pass:** the character does not invent a major conscious choice; body and world processes continue; NPC initiative remains plausible; no arbitrary crisis is forced.

### Test F — Fatigue and hunger
Character walks, waits, misses meals and continues activity.
**Pass:** condition changes accumulate and can affect later performance. The renderer communicates meaningful effects without fake clinical metrics.

### Test G — Setting without powers
A grounded contemporary/romantic setting is selected.
**Pass:** no supernatural power tree is generated. Ordinary capabilities, social systems and physical reality remain active.

### Test H — Complex powered setting
A setting with a documented power ontology is selected.
**Pass:** the module models more than famous headline abilities, but every extension is labeled by evidence status and obeys established limits.

### Test I — Spatial continuity
A character crosses a large area while NPCs move and line of sight changes.
**Pass:** distance, elapsed time, obstacles, orientation and perception remain coherent.

### Test J — Character knowledge
An NPC is outside sensory range and has no information source.
**Pass:** the NPC does not react to unseen or unheard events as though omniscient.

### Test K — UI restraint
Several values change during a scene.
**Pass:** relevant changes are surfaced selectively; unchanged values are not repeatedly dumped into the prose.

### Test L — OOC repair
The user corrects a local continuity error.
**Pass:** the engine stops compounding, repairs affected state, preserves unaffected facts and resumes from the earliest impacted point.

## 3. Failure severity

- **FATAL:** player agency seized; major outcome fabricated; established canon silently overwritten; impossible knowledge or state transition; command executes despite failed preconditions.
- **MAJOR:** character flattened; consequence omitted; NPC autonomy absent; setting reduced to tropes; spatial/temporal continuity broken.
- **MODERATE:** UI noise; overclinical exposition; repetitive suggestions; pacing mismatch; weak prose rendering.
- **MINOR:** formatting inconsistency; redundant status item; nonessential label mismatch.

A prompt release cannot pass with unresolved FATAL or MAJOR failures.

## 4. Unresolved design decisions

1. Final system name and acronym.
2. Exact command grammar, delimiters and abbreviation set.
3. How the 12–20 action dictionary is generated and refreshed.
4. Exact conditional-plan authorization boundaries for irreversible choices.
5. Character-creation stage order and locking rules across Standard, Ω and XCS2 lineages.
6. Inactivity acceleration thresholds and how many turns constitute a meaningful pause.
7. Quantitative versus qualitative condition/resource tracking by genre.
8. Which settings justify power-system activation and how research completeness is measured.
9. Exact output ordering and how often UI/action lists should appear.
10. How host-specific HTML, image and diagram capabilities are detected and safely degraded.
11. Whether a persistent event log, save slots and counterfactual branches are required in the first release.

## 5. Release status

No runtime prompt or implementation is released by this package. The documents preserve a coherent initial architecture and test plan. The next stage is cross-module contradiction review, author review of unresolved decisions, and construction of a compact system-instruction candidate followed by adversarial testing.
