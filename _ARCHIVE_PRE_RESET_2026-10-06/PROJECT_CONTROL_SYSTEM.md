# EverWorlds Project Control System

## Purpose

This file is the control layer for EverWorlds: The Finales Series.

Its job is to prevent project drift caused by model memory loss, conflicting documents, stale drafts, accidental invention, or automatic fallback to generic LLM prose.

The project must remain transferable between sessions and between models without requiring the author to verbally reconstruct the project.

---

## 1. Authority Model

When producing or changing project material, use this order of authority:

1. **Explicit author decisions made after earlier documents** — newest confirmed decision wins.
2. **Current production decisions** in `CURRENT_PRODUCTION_DECISIONS.md`.
3. **Narrative canon and writing locks** in `NARRATIVE_CANON_AND_WRITING_LOCK.md`.
4. **Project-level definition/requirements** — `PROJECT_BIBLE.md`, `REQUIREMENTS.md`, `DECISIONS.md`, `TERMINOLOGY.md`.
5. **Active chapter production-control documents.**
6. **Research documents and verified external evidence.**
7. **Blueprints, beat sheets, experiments, and working notes.**
8. **Draft prose.**
9. **Model memory, inference, trope knowledge, or stylistic preference.**

Lower-level material must never silently override higher-level material.

A later explicit author decision may supersede an older document. When this occurs, update the authoritative document instead of allowing two contradictory truths to coexist indefinitely.

---

## 2. State Classes

Every important piece of information belongs to one of these states:

### LOCKED
Confirmed project truth. Generation must preserve it.

### ACTIVE
Currently intended and usable, but still subject to controlled refinement.

### PROVISIONAL
A hypothesis, experiment, research lead, or unresolved possibility. It must not be silently promoted into canon.

### RETIRED
No longer active. It may explain project history but must not guide new generation.

### UNKNOWN
Not established. Do not fill the gap with invention.

### CONFLICTED
Two authoritative-looking sources disagree. Generation is blocked until the conflict is resolved by chronology or explicit author decision.

---

## 3. Generation Gate

Before generating substantial narrative prose, verify:

### Canon
- What chapter/scene is being written?
- What is already established immediately before it?
- What is explicitly unknown to the protagonist?
- What information belongs later and therefore must not leak backward?
- Which characters, locations, mechanics, lore, and psychological states are active?

### Function
- What does this scene accomplish beyond moving the plot?
- What changes in the protagonist?
- What changes in the reader's model of the world?
- What relationships are established or altered?
- What future material is being prepared?
- Which apparently mundane details are actually carrying later structural weight?

### Rendering
Select the rendering/narrative mode appropriate to the scene rather than imposing one permanent style.

Possible modes include:
- immersive RTX-style perceptual rendering;
- storybook-style descriptive narration;
- conventional narrative compression;
- dialogue-forward movement;
- psychological interiority;
- action/event rendering;
- quiet environmental habitation.

Modes may coexist inside one chapter. They must be selected because of scene function, not because one mode is fashionable or easier for the model.

### Continuity
Verify:
- time/date/elapsed time;
- location and physical position;
- character knowledge;
- body/identity state;
- abilities and limitations;
- terminology;
- established relationships;
- world rules;
- chapter ownership of information;
- previously locked visual/rendering language.

### Prose Failure Test

Before accepting prose, test whether it has fallen into:

**observation → explanation → dramatic sentence → reflection → next object**

or:

**inventory → interpretation → summary → transition**

or:

**generic cinematic cadence → sensory adjective stacking → fake immersion**

If yes, STOP. Do not polish the same architecture.

---

## 4. Experience-Creation Requirement

EverWorlds prose must create the reader's experience of the scene rather than report that the protagonist experienced it.

The reader should continuously be able to construct:

- where the protagonist is;
- what surrounds him;
- where nearby people/objects are;
- what is moving;
- what he is physically doing;
- what caused the current action;
- what consequence follows.

Environment should behave independently. Objects should normally become meaningful through interaction, resistance, consequence, use, sound, movement, temperature, texture, obstruction, or change.

The mental camera must persist through the space rather than repeatedly resetting.

This is a generation rule, not merely a paragraph-formatting rule.

---

## 5. Research Rule

When the project requests research:

1. Search multiple credible angles where appropriate.
2. Separate evidence from interpretation.
3. Record durable findings in the repository.
4. Distinguish established fact from hypothesis.
5. Do not let research silently rewrite canon.
6. If evidence conflicts, record the conflict rather than choosing whichever source is convenient.
7. Do not claim verification without actually verifying it.

Research exists to improve the project's decision quality, not to manufacture authority.

---

## 6. Change Control

No substantial project change should happen merely because the model thinks it would be better.

A change requires:

**proposal → evidence/reason → explicit author acceptance → authoritative documentation → implementation**

If the author has not accepted the change, it is not canon.

If a generated draft contains an unapproved change, the draft is non-authoritative.

---

## 7. Failure Protocol

When a failure is detected:

### Level 1 — Local prose failure
Stop generation of the affected passage and repair the underlying scene architecture.

### Level 2 — Continuity/lore failure
Stop the chapter. Reconcile against authoritative documents before continuing.

### Level 3 — Project-state failure
Stop writing. Reconstruct the relevant project state from repository history and authoritative files.

### Level 4 — Repeated model drift
Stop prose production entirely. Audit the control system and source-of-truth hierarchy before another draft is attempted.

**Never continue simply because the user says "next" if a known blocking failure remains unresolved.**

---

## 8. Draft Status

Drafts are not automatically canon.

Use:

- **SOURCE** — author-provided/confirmed material.
- **ACTIVE DRAFT** — current implementation under review.
- **QUARANTINED** — failed or superseded implementation; not a source for new prose.
- **RELEASED** — explicitly accepted final material.

A failed draft must not become an unconscious style template for its replacement.

---

## 9. Chapter Production Pipeline

Every chapter follows:

**SOURCE RECOVERY**
→ **CANON/STATE MAP**
→ **FUNCTION MAP**
→ **SCENE DEPENDENCY MAP**
→ **RENDERING-MODE MAP**
→ **DRAFT**
→ **CONTINUITY AUDIT**
→ **PROSE/IMMERSION AUDIT**
→ **AUTHOR REVIEW**
→ **RELEASE**

A chapter cannot advance past a blocking audit failure.

---

## 10. Current Chapter 6 State

Chapter 6 is **NOT READY FOR ANOTHER PROSE GENERATION PASS**.

The repository currently records Chapter 6 production controls, beat sheets, audits, and multiple drafts. The current production decision says the chapter requires source verification and prose reconstruction, while the project history also contains later author corrections and accumulated context that must be reconciled before generation.

Therefore the next action is not "write Chapter 6."

The next action is a **repository-backed state reconstruction** covering the material Chapter 6 depends on, followed by a conflict report and a locked implementation state.

No new Chapter 6 prose should be generated until that state is verified.

---

## 11. Non-Negotiable Project Principle

EverWorlds must not gradually become a different project because a model forgot, inferred, simplified, optimized, or stylistically substituted something.

When uncertain:

**preserve confirmed state.**

When contradicted:

**STOP and reconcile.**

When missing:

**mark UNKNOWN.**

When proposing:

**mark PROVISIONAL.**

When changing:

**obtain author acceptance and record the change.**

The model is an implementation tool.

It is not the authority over what EverWorlds is.
