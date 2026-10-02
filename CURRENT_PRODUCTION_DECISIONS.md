# EverWorlds — Current Production Decisions

## Decision State
Updated after the prose-rendering research and Chapter 6 structural audit.

### D-001 — World Rendering
**Decision:** EverWorlds uses grounded perceptual realism as its visual prose target.

References:
- Red Dead Redemption / Red Dead Redemption 2
- Kingdom Come: Deliverance / Deliverance II
- grounded realistic horror-game atmosphere
- Eternum as a secondary tonal/environmental reference

**Not the target:** glossy AAA spectacle, constant cinematic adjectives, neon saturation, or “everything is beautiful.”

### D-002 — Beauty / Lighting Separation
**Decision:** Beauty, brightness, darkness, emotional tone, and saturation are separate variables.

Physical conditions establish the visual result.

### D-003 — Prose as Rendering
**Decision:** Environment descriptions prioritize space, light, material, atmosphere, motion, sound, colour, attention, and physical consequence over aesthetic labels.

### D-004 — Chapter 6
**Decision:** Chapter 6 is the habitation/world-grounding chapter.

It must make the new world feel physically lived-in before the story escalates.

### D-005 — Chapter 7
**Decision:** Chapter 7 owns the entrance examination.

Chapter 6 begins on a new day after the Chapter 5 sequence and ends at the 9:00 AM examination bell. The examination itself begins in Chapter 7.

### D-006 — First Plotline
**Decision:** The first actual plotline after the grounded school entry is **the power**.

The exam is a narrative event/threshold, not the first supernatural plotline.

Working sequence:

**Ch.6 — Habitation / Kuoh**
→ **Ch.7 — Entrance examination**
→ **Ch.8 — Power**
→ **Ch.9+ — Consequences / recognition / wider world**

### D-007 — Retired Chapter 6
The previous Chapter 6 draft is quarantined/retired.

Its prose is not to be recycled as active canon unless explicitly requested.

### D-008 — Geography
**Decision:** Do not invent an exact apartment address or exact Kuoh geography yet.

Research confirms Kuoh is a fictional town in Japan and that its exact real-world placement is not firmly established by the accessible sources. Community attempts to place it geographically are inconsistent. citeturn1search1turn1search8

Therefore Chapter 6 can use:
- local neighbourhood;
- station;
- rail journey;
- transfers;
- approach to Kuoh;

without asserting an unsupported real-world address.

### D-009 — Research Standard
Narrative craft decisions are to be grounded in actual research where evidence exists.

Narrative neuroscience/psycholinguistic research supports the use of spatially coherent situation models, protagonist-relative location, and event-boundary changes in reader comprehension. citeturn0search0turn0search1turn0search10

### D-010 — Autonomous Next Action
The next production task is **not another meta-discussion**.

It is:
1. verify Chapter 6's scene dependencies;
2. construct its beat-by-beat sequence;
3. draft only after the sequence passes continuity and rendering checks;
4. then audit Chapter 7's exam boundary;
5. then design Chapter 8's power reveal.

## Current Production Queue

| Priority | Work | State |
|---|---|---|
| 1 | Chapter 6 production control | Complete |
| 2 | Chapter 6 prose reconstruction | Revision Required |
| 3 | Chapter 6 continuity/rendering audit | Complete |
| 4 | Chapter 5 → Chapter 6 chronology/state lock | Complete — live state recorded |
| 5 | Chapter 6 exceptional-function/state reconstruction | Active |
| 4 | Chapter 7 exam architecture | After Ch.6 |
| 5 | Chapter 8 power architecture | After Ch.7 |
| 6 | Wider supernatural ecology | Deferred until earned |

## Hard Rule

Do not skip to the power because it is more exciting.

The power will work better if the reader has first learned what “ordinary” feels like in this world.


### D-011 — Narrative Prose Architecture
**Decision:** EverWorlds now uses a research-backed prose architecture standard covering situation-model construction, spatial coherence, event/attention boundaries, paragraph architecture, sentence cadence, and digital typography.

The standard is stored in `NOVEL_PROSE_ARCHITECTURE_STANDARD.md` and is mandatory for new prose and major revisions.

Key implementation rule: **paragraphs are perceptual/discourse units, not arbitrary readability breaks.** Related observations should accumulate until their perceptual function is complete. Sentence length and punctuation should control attention and processing rhythm. Environmental details must establish spatial/material relationships rather than inventories.

Research basis includes narrative situation-model studies, paragraphing research, eye-tracking/punctuation research, and typographic readability research. Research is used as evidence for constraints and tendencies, not as a claim that experimental psychology dictates literary taste.

### D-012 — Chapter 6 Structural Rewrite
**Decision:** The current Chapter 6 draft is structurally readable but under-dense in paragraph architecture and too fragmentary in environmental rendering. It requires a prose reconstruction pass before lock.

The reconstruction must preserve the existing canon, scene order, chapter boundary, and information budget while changing paragraph grouping, sentence cadence, spatial relationships, and redundant interpretive commentary.

No new plot is to be invented during this pass.


### D-013 — Immersive Prose / Experience-Creation Doctrine
**Decision:** EverWorlds prose must **create the reader's experience of a scene, not report that the protagonist experienced it**.

This is a generative rule, not a paragraph-formatting preference. Changing line breaks, merging sentences, or adding sensory adjectives does not satisfy it if the underlying prose still enumerates information.

#### Core distinction
**Reporting mode:** protagonist encounters X → prose identifies X → protagonist explains X → prose moves to Y.

**Experience mode:** the scene is already in motion → the protagonist acts inside it → the environment reacts → physical/social resistance changes what he does → his attention is redirected by events → each action produces the conditions for the next action.

The reader should be able to maintain a continuous mental model of:
- where the protagonist is;
- where nearby people and objects are relative to him;
- what is moving or changing;
- what he is physically doing;
- what just caused the current action;
- what consequence now requires the next action.

#### Relational rendering
Objects are not introduced as inventory. Their presence should normally be established through **interaction, physical behavior, or consequence**: weight, friction, temperature, texture, sound, obstruction, movement, use, damage, resistance, or effect on the protagonist.

Do not write a room/station/street as a list of objects and then explain what the list means. Make the environment behave while the protagonist moves through it.

#### Persistent scene/camera
Do not repeatedly reset the reader's mental camera with isolated observation → explanation → movement units. Spatial information should accumulate. The reader should feel that the same physical place continues to exist around the protagonist while attention shifts within it.

#### Causality and friction
Ordinary movement must still contain believable resistance where the situation naturally permits it: crowds, timing, unfamiliar procedures, awkward interactions, physical inconvenience, navigation errors, sensory unfamiliarity, objects getting in the way, or small failures. Do not manufacture obstacles merely to satisfy a beat sheet; do not remove friction merely to move efficiently between plot points.

#### Information delivery
Prefer information that arrives through action, perception, dialogue, consequence, and discovery. Do not repeatedly stop the scene to explain why an event matters, what the protagonist should feel, or what the reader should understand.

The protagonist's personality should emerge primarily through choices, reactions, behavior, speech, mistakes, and interaction—not continuous explanatory internal monologue.

#### Prohibited failure pattern
Do not generate prose as:
**observation → explanation → short dramatic sentence → reflection → next object.**

Do not substitute paragraph merging for actual reconstruction. Do not use fragment chains, fake cinematic cadence, lyrical overstatement, object catalogs, or constant filter constructions such as “I looked,” “I saw,” “I noticed,” and “I watched” when direct perception/action can carry the scene.

Single-sentence paragraphs are exceptional emphasis tools, not the default architecture. Normal scene movement should allow several causally related sentences to develop together.

#### Fanfiction immersion requirement
This is a fanfiction/world-entry experience. Mundane scenes are part of the fantasy. The reader must be allowed to **be there** with Jonah: the apartment should feel inhabitable, the commute should feel traversable, the station should feel navigable, and Kuoh should be encountered before it is explained.

The test is not “is this descriptive?” or “is this readable?”

The test is:
**Can the reader construct and continue imagining the physical experience without the prose having to tell them what the experience means?**

If the answer is no, STOP and rewrite the scene-generation approach rather than polishing the same architecture.

This doctrine supersedes any earlier interpretation that treated the Chapter 6 prose problem primarily as paragraph grouping, sensory density, or sentence-length variation.


### D-014 — Sona: Social/Psychic Gravity and Non-Normalization

**Decision:** Sona's Chapter 6 presence must not be normalized through friendliness, warmth, or casual reciprocal interaction.

Hard locks for the Chapter 6 glimpse:
- Sona does **not smile at Jonah**.
- Prefer that Sona does not smile at all during this glimpse unless a later scene explicitly requires it.
- Jonah does not recognize her by name.
- No Tsubaki, Saji, or student-council exposition is required in the glimpse.
- Sona is visibly/socially elevated without being explained as supernatural.
- Her composure, intelligence, beauty, posture, and social gravity should make her feel like she occupies a different social altitude from the applicants.
- Her appearance may use controlled poeticism/hyperbole, including one or two subtly unusual facial characteristics, while remaining physically plausible.
- One restrained visual irregularity may hint that something about her is not entirely ordinary (for example, a shadow behaving slightly incorrectly). Do not stack multiple supernatural tells.
- The effect on Jonah may be **psychic/perceptual rather than consciously social**: an involuntary pressure to become smaller, deferential, silent, or excessively self-conscious; an irrational urge to submit, avoid embarrassment, or even humiliate himself socially can be suggested through bodily impulse and thought.
- This effect must remain ambiguous to Jonah. He should not identify it as psychic manipulation, devil power, aura mechanics, or a supernatural ability.
- Do not turn the effect into mind control, explicit sexual submission, or an explanatory power display. The desired experience is an uncanny involuntary social/psychic pressure produced by Sona's presence and pride, not a lore dump.
- The reader should be able to wonder whether the reaction came from Sona's extraordinary presence, Jonah's own psychology, or something stranger.
- EverWorlds is its own continuity. Do not force Sona back into exact DxD characterization or visual proportions when EverWorlds has deliberately diverged.

This decision refines the older Chapter 6 wording that described Sona as merely "ordinary enough to be explainable." The **world/environment remains grounded**; Sona herself may feel unusually elevated and subtly uncanny.

### D-015 — Typography / Spacing Preservation

**Decision:** Generated Chapter 6 prose must preserve the project's intended novel typography and paragraph architecture.

When passing the chapter to another model for revision:
- do not collapse paragraphs into one dense wall of text;
- do not insert arbitrary one-line paragraphs after every sentence;
- do not convert prose into screenplay/script formatting;
- do not alter dialogue indentation/spacing conventions;
- do not damage blank-line rhythm between scene/paragraph units;
- do not replace normal prose punctuation with decorative formatting;
- do not “clean up” paragraph breaks merely for compactness;
- preserve the established relationship between paragraph length, perceptual unit, dialogue movement, and emphasis;
- any surgical Sona correction must preserve the surrounding chapter's existing typography unless a specific typography correction is requested.

**Typography is part of the prose architecture, not disposable formatting.**
