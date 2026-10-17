# REPOSITORY INDEX — EverWorlds: The Finales Series

## Purpose

This is the file-routing map for the repository.

The repository currently contains several different kinds of material mixed at the same root:
- project/control documentation;
- novel canon;
- chapter production records;
- supernatural/worldbuilding architecture;
- research;
- historical drafts;
- retired OPAQUE system documentation.

This index exists to prevent file-order drift, stale-document drift, and model-memory substitution.

## Critical Rule

Do not treat every Markdown file as equally authoritative.

Use the authority/state classification below before reading or using a file.

### State labels

- LOCKED / CANON — current confirmed continuity or hard production lock.
- CURRENT CONTROL — current process/production authority.
- ACTIVE ARCHITECTURE — current world/system architecture, subject to explicit author revision.
- ACTIVE WORKING — useful current working material; not automatically canon.
- HISTORICAL / SOURCE — preserves source material or past state; useful for recovery, not automatic current truth.
- RETIRED / QUARANTINED — do not use for new generation unless explicitly recovering history.
- RESEARCH — evidence/analysis; never silently becomes canon.
- CONFLICTED / STALE — contains information superseded by later records. Do not use without checking the newer authority.

# 1. START HERE — CONTROL ROUTE

| Priority | File | Role | State | Use |
|---|---|---|---|---|
| 1 | PROJECT_CONTROL_SYSTEM.md | Global control, authority hierarchy, failure protocol | CURRENT CONTROL, partly stale chapter state | Read for process rules; verify chapter-specific state against newer records |
| 2 | NARRATIVE_CANON_AND_WRITING_LOCK.md | Narrative continuity/world/character locks | LOCKED / CANON | Primary narrative authority |
| 3 | CURRENT_PRODUCTION_DECISIONS.md | Current production decisions | CURRENT CONTROL, but contains superseded queue entries | Read latest decisions; do not trust old queue text over later locks |
| 4 | CHAPTER_8_MASTER_STATE.md | Chapter 8 continuity + architecture | CURRENT ACTIVE | Current Chapter 8 routing spine |
| 5 | WORK_LOG.md | Chronological production history | HISTORY / CURRENT STATE SIGNAL | Use latest dated entry to establish what actually happened |
| 6 | PROJECT_BIBLE.md | High-level project definition | PROJECT-LEVEL AUTHORITY | Use for project identity, not detailed novel mechanics |
| 7 | REQUIREMENTS.md | Confirmed requirements | PROJECT-LEVEL | Requirements only |
| 8 | DECISIONS.md | Older/general decisions register | PROJECT-LEVEL / HISTORY | Check against newer explicit decisions |
| 9 | TERMINOLOGY.md | Controlled vocabulary | CONTROLLED VOCABULARY | Use when terminology matters |
| 10 | REPOSITORY_INDEX.md | This routing map | CURRENT CONTROL SUPPORT | Find the correct file before reasoning |

# 2. NOVEL / NARRATIVE SOURCE FILES

## Chapter 5

| File | Role | State | Warning |
|---|---|---|---|
| CHAPTER_5_SOURCE_TEXT.md | Complete author-supplied Chapter 5 manuscript + continuity-critical extraction | SOURCE / CANONICAL SOURCE | Primary Chapter 5 prose source |
| CHAPTER_5_TO_6_LIVE_STATE.md | Transition state from Ch.5 into Ch.6 | HISTORICAL/STATE LOCK | Use for exact handoff; verify against later canon |

## Chapter 6

| File | Role | State | Warning |
|---|---|---|---|
| CHAPTER_6_DRAFT.md | Historical Chapter 6 prose draft | HISTORICAL / DRAFT | Not the released manuscript |
| CHAPTER_6_RESTRUCTURED_DRAFT.md | Restructured Chapter 6 implementation | HISTORICAL / DRAFT | Do not treat as released prose |
| CHAPTER_6_FUNCTION_MAP.md | Scene/function architecture | ACTIVE WORKING / HISTORICAL | Useful for structural recovery |
| CHAPTER_6_SONA_CORRECTION_MODULE.md | Sona-specific correction instructions | ACTIVE WORKING / LOCK SUPPORT | Contains important Sona rendering/epistemic constraints |
| NOVEL_CHAPTER_6_AUDIT.md | Chapter 6 audit | AUDIT RECORD | Historical verification |
| NOVEL_CHAPTER_6_BEAT_SHEET.md | Chapter 6 beat architecture | WORKING PLAN | Not prose canon |
| NOVEL_CHAPTER_6_BLUEPRINT.md | Chapter 6 structural blueprint | WORKING PLAN | Not prose canon |
| NOVEL_CHAPTER_6_DRAFT.md | Separate novel-oriented Chapter 6 draft | HISTORICAL / DRAFT | Do not assume it is released |
| NOVEL_CHAPTER_6_PRODUCTION_CONTROL.md | Chapter 6 production-control stack | CONTROL / HISTORICAL | Important for reconstruction; release state supersedes old queue instructions |

## Chapter 7

There is currently no Chapter 7 manuscript file in main.

Known current state is routed through:
- NARRATIVE_CANON_AND_WRITING_LOCK.md
- latest relevant CURRENT_PRODUCTION_DECISIONS.md entries
- WORK_LOG.md
- CHAPTER_8_MASTER_STATE.md for the Chapter 7 → 8 handoff

Do not invent a Chapter 7 manuscript from file absence.

## Chapter 8

| File | Role | State |
|---|---|---|
| CHAPTER_8_MASTER_STATE.md | Chapter 8 master continuity/architecture spine | CURRENT ACTIVE |

This file is a working state record, not finished Chapter 8 prose.

# 3. NARRATIVE / PROSE STANDARDS

| File | Role | State |
|---|---|---|
| NOVEL_PROSE_ARCHITECTURE_STANDARD.md | Research-backed prose architecture | ACTIVE STANDARD |
| NOVEL_PROSE_RENDERING_STANDARD.md | Rendering/perceptual prose rules | ACTIVE STANDARD |
| RESEARCH_PROSE_RENDERING.md | Research supporting prose/rendering decisions | RESEARCH |
| RESEARCH_SENSUAL_ATTRACTION_PROSE.md | Research-backed attraction, sensuality, fanservice rendering, cadence, attention, synchrony and scene integration | RESEARCH / ACTIVE CRAFT REFERENCE | Use for adult sensual/fanservice prose craft; it does not create narrative canon |
| COMBAT_VISUAL_LANGUAGE.md | Combat visual/experiential grammar | ACTIVE VISUAL CANON / DESIGN |

These control how the novel is rendered. They do not override what happened in canon.

# 4. SUPERNATURAL / WORLD ARCHITECTURE

| File | Role | State | Routing rule |
|---|---|---|---|
| SUPERNATURAL_REALITY_AND_MAGIC_ARCHITECTURE.md | Magic, Work Makes, Aimor, demonic/fallen/angelic architecture | ACTIVE ARCHITECTURE + CANON BOUNDARY | Use, but obey its explicit STOP/recovery boundary |
| EXPERIMENT_001_SPATIAL_REALITY_SYSTEM.md | Spatial/world/realm technical architecture | EXPERIMENT / ARCHITECTURAL SOURCE | Important evidence for realm mechanics; not proof that every prior realm concept is fully recovered |
| EVERWORLD_6_RAW_IDEA_DUMP_001.md | Older broad supernatural ecology/raw ideas | HISTORICAL SOURCE | Critical recovery source; not automatically current canon |
| NARRATIVE_CANON_AND_WRITING_LOCK.md | Narrative continuity/world/character locks | LOCKED / CANON | Highest narrative authority for current novel |
| KUOH_SPIRITUAL_ECOLOGY_AND_COSMOLOGY.md | Canonical layered Kuoh ecology, mythology integration, Rias/Sona territorial coupling | AUTHOR-ACCEPTED CANON / ACTIVE ARCHITECTURE | Primary structural authority for Kuoh's spiritual ecology and territorial model |

### Critical recovery note — resolved for Kuoh territorial ecology

The previously missing Kuoh territory/realm/ecology mechanism has now been explicitly redefined and accepted as canon in `KUOH_SPIRITUAL_ECOLOGY_AND_COSMOLOGY.md`.

That file now governs:
- Kuoh's layered spiritual ecology;
- Rias/Sona's deep territorial coupling;
- the local invisible supernatural hierarchy and politics;
- interlocking mythologies and cultural interpretations;
- blessings, curses, gifts, guardians, ghosts, sleep-paralysis phenomena and related threshold experiences;
- the systemic basis of Kuoh's erotic/"ero-physics" phenomena.

Do not replace this model with generic DxD territory mechanics.

The exact mechanics of unrelated higher realms, Aimor subtypes, or unrecovered historical systems remain subject to their own recovery/authority rules.

**Devil ontology warning remains:** the user's established Devil feeding model is SIN → associated negative energy/emotions → feeding. Do not silently replace it with the later "negative potential" formulation.



# 4A. KUOH TRAVERSAL / REALM ARCHITECTURE

| File | Role | State | Routing rule |
|---|---|---|---|
| KUOH_SPIRITUAL_ECOLOGY_AND_COSMOLOGY.md | Local Kuoh spiritual ecology, Rias/Sona territorial coupling, invisible supernatural ecosystem | AUTHOR-ACCEPTED CANON / ACTIVE ARCHITECTURE | Primary Kuoh ecological authority |
| KUOH_REALM_TRAVERSAL_AND_GATEKEEPING.md | Kuoh subembedded realms, external objective-realm links, traversal methods, gatekeeping, restricted areas and intermythological travel law | AUTHOR-ACCEPTED CANON / ACTIVE ARCHITECTURE | Use for Kuoh travel, realm-access and gatekeeping questions |
| ONTOLOGICAL_SPECTRUM_AND_HIGHER_EXISTENCE.md | Physical→supernatural→spiritual→conceptual→absolute existence spectrum; physics/interface boundary | AUTHOR-ACCEPTED CANON / ACTIVE ARCHITECTURE | Use for ontology, higher-tier interaction and scientific-explanatory-boundary questions |

### Kuoh realm-scope lock

Kuoh's subembedded realms and connected objective realms must never be collapsed into one universal Earth cosmology. External objective realms remain independent territories with their own ontology, politics, inhabitants and traversal systems.

### Ontology-scope lock

Magic and Mystical are distinct but connected categories. The ontological spectrum is not a simple combat-power ladder. Power, ontology, accessibility and causal interface must remain separate.




# 4B. SUPERNATURAL CIVILIZATION ARCHITECTURE

| File | Role | State | Routing rule |
|---|---|---|---|
| SUPERNATURAL_CIVILIZATIONS_AND_NEGATIVE_SPECTRUM.md | Broad civilization ecology, negative-spectrum diversity, human classification limits, hidden/extinct civilizations and inter-civilizational disparity | AUTHOR-ACCEPTED CANON / ACTIVE WORLD ARCHITECTURE | Use for demon/demonic/Nether/Abyss/Inferno/negative-spectrum population and civilization questions |
| SUPERNATURAL_ONTOLOGY_MASTER.md | First-stop invariant map for Demon, Devil, Angel, Fallen Angel, potential polarity, SIN/negative energy, Ender ecology | LOCKED CORE ONTOLOGY / ROUTING AUTHORITY | **Mandatory first read for basic ontology questions.** Routes to detailed files and STOP protocol. |

### Core ontology routing lock

For any basic question about what a Demon, Devil, Angel, or Fallen Angel fundamentally is, retrieve `SUPERNATURAL_ONTOLOGY_MASTER.md` first. Do not answer from model memory. Then retrieve the relevant detailed domain file. If the master and a detailed current file conflict, STOP and resolve the conflict before answering.

This master exists because fragmented supernatural documentation previously caused negative potential, negative energy/SIN, and Devil Ender ecology to be incorrectly treated as competing definitions. That class of maintenance failure is now a repository-level STOP condition.

### Civilization-scope lock

Do not collapse Demon, Demonic Entity, Devils, Nether, Abyss, Rift, Inferno or Hell into one species, civilization or universal realm. Devils are one population among many. Civilization knowledge is incomplete and fragmented; hidden, isolated and extinct populations are legitimate world states.


# 5. PROJECT / CONTROL DOCUMENTS

| File | Role | State |
|---|---|---|
| README.md | Repository landing page | CONTROL HUB |
| PROJECT_BIBLE.md | High-level project identity | PROJECT AUTHORITY |
| PROJECT_CONTROL_SYSTEM.md | Authority, state classes, generation gates, failure protocol | CONTROL AUTHORITY |
| REQUIREMENTS.md | Requirements | REQUIREMENTS AUTHORITY |
| DECISIONS.md | General decision register | DECISION HISTORY |
| CONCEPTS.md | Concept register | CONCEPT REGISTER |
| TERMINOLOGY.md | Controlled vocabulary | TERMINOLOGY AUTHORITY |
| SCHEME_OF_WORK.md | Production framework | PROCESS AUTHORITY |
| WORK_LOG.md | Chronological session/state record | HISTORY / STATE |
| CURRENT_PRODUCTION_DECISIONS.md | Current production decisions | CURRENT DECISION AUTHORITY, with stale queue material requiring reconciliation |

# 6. RESEARCH / ROLEPLAY SYSTEM FILES

| File | Role | State |
|---|---|---|
| ROLEPLAY_RESEARCH_LAB.md | Roleplay/LLM research record | RESEARCH |
| ROLEPLAY_RESEARCH_EPISTEMIC_LEAKAGE.md | Research on epistemic leakage | RESEARCH |

These are not automatically narrative canon.

# 7. RETIRED OPAQUE MATERIAL

archive/opaque-2026-09-25 is a historical archive branch.

Its OPAQUE files are not part of the active narrative source stack.

Do not use them to answer current Apocrypha/novel canon questions unless the task explicitly asks for OPAQUE history or recovery.

The archive contains:
- OPAQUE control/specification/ratification documents;
- OPAQUE Stage VII architecture;
- post-OPAQUE memory/execution protocol;
- shared project-level files preserved at that historical point.

The archive is valuable for historical recovery, but it is deliberately separated from active main.

# 8. MAIN-BRANCH FILE INVENTORY

Current main contains 33 files:

1. CHAPTER_5_SOURCE_TEXT.md
2. CHAPTER_5_TO_6_LIVE_STATE.md
3. CHAPTER_6_DRAFT.md
4. CHAPTER_6_FUNCTION_MAP.md
5. CHAPTER_6_RESTRUCTURED_DRAFT.md
6. CHAPTER_6_SONA_CORRECTION_MODULE.md
7. CHAPTER_8_MASTER_STATE.md
8. COMBAT_VISUAL_LANGUAGE.md
9. CONCEPTS.md
10. CURRENT_PRODUCTION_DECISIONS.md
11. DECISIONS.md
12. EVERWORLD_6_RAW_IDEA_DUMP_001.md
13. EXPERIMENT_001_SPATIAL_REALITY_SYSTEM.md
14. NARRATIVE_CANON_AND_WRITING_LOCK.md
15. NOVEL_CHAPTER_6_AUDIT.md
16. NOVEL_CHAPTER_6_BEAT_SHEET.md
17. NOVEL_CHAPTER_6_BLUEPRINT.md
18. NOVEL_CHAPTER_6_DRAFT.md
19. NOVEL_CHAPTER_6_PRODUCTION_CONTROL.md
20. NOVEL_PROSE_ARCHITECTURE_STANDARD.md
21. NOVEL_PROSE_RENDERING_STANDARD.md
22. OPAQUE_ARCHIVED.md
23. PROJECT_BIBLE.md
24. PROJECT_CONTROL_SYSTEM.md
25. README.md
26. REQUIREMENTS.md
27. RESEARCH_PROSE_RENDERING.md
28. ROLEPLAY_RESEARCH_EPISTEMIC_LEAKAGE.md
29. ROLEPLAY_RESEARCH_LAB.md
30. SCHEME_OF_WORK.md
31. SUPERNATURAL_REALITY_AND_MAGIC_ARCHITECTURE.md
32. TERMINOLOGY.md
33. WORK_LOG.md

# 9. KNOWN INTEGRITY PROBLEMS FOUND DURING AUDIT

## A. Chapter 6 state drift

PROJECT_CONTROL_SYSTEM.md still contains an older statement that Chapter 6 is not ready for prose generation.

WORK_LOG.md records Chapter 6 as released/locked on 2026-10-03.

CURRENT_PRODUCTION_DECISIONS.md contains D-016 explicitly locking Chapter 6 as released.

Resolution: Chapter 6 released state wins. The old control text is stale and should be revised in a controlled cleanup pass.

## B. Chapter 8 state drift

Older production material routes Chapter 8 toward "power" immediately after the examination.

Current author direction has Chapter 8 focused on Ira's internal thought process, grief/mother thread, self-limitation philosophy, voluntary Kuoh exploration, and gradual environmental unease.

Resolution: the older Chapter 8 queue is stale. CHAPTER_8_MASTER_STATE.md is the current Chapter 8 working spine unless the author explicitly changes it.

## C. Chapter 7 manuscript absence

No Chapter 7 manuscript is present on main.

That is not evidence that Chapter 7 does not exist in the author's external/current working state.

Resolution: do not fabricate a manuscript from memory. Use the documented Chapter 7 → 8 handoff and recover the actual manuscript if exact prose is needed.

## D. Released Chapter 6 manuscript absence

The repository records the released Chapter 6 state but explicitly says the exact released manuscript was not committed.

Resolution: do not call any existing Chapter 6 draft "the released manuscript."

## E. Supernatural ontology fragmentation

Devil/supernatural material is split across:
- NARRATIVE_CANON_AND_WRITING_LOCK.md
- SUPERNATURAL_REALITY_AND_MAGIC_ARCHITECTURE.md
- EVERWORLD_6_RAW_IDEA_DUMP_001.md
- EXPERIMENT_001_SPATIAL_REALITY_SYSTEM.md

These are not equivalent sources.

The user's established Devil feeding model (SIN → negative energy/emotions → feeding) must not be overwritten by a later conceptual formulation merely because it appears in a newer architecture document.

## F. Realm / territory mechanic recovery gap

The spatial experiment documents a sophisticated realm/spatial model, but that does not prove it contains the exact previously explained territory/realm mechanic.

The exact prior concept remains UNKNOWN until recovered.

## G. Documentation purpose collision

The repository originally describes EverWorlds as a SillyTavern/LLM extension project, while main now also contains a substantial novel/narrative production system.

That is not automatically wrong, but it means the repository needs an explicit separation between:
- project/control infrastructure;
- novel canon;
- novel production;
- world/supernatural architecture;
- research;
- historical material.

Without that separation, filename semantics become unreliable.

# 10. ROUTING RULE FOR FUTURE SESSIONS

Before answering a lore/continuity question:

1. Identify the domain.
   - chapter;
   - character;
   - supernatural ontology;
   - realm/spatial;
   - prose;
   - production;
   - project architecture;
   - historical recovery.

2. Open the domain authority.

3. Check later explicit decisions / Work Log for supersession.

4. Check historical/source files only if the current authority has a gap.

5. If the gap remains: mark UNKNOWN.

6. Never fill a missing concept from model memory or generic DxD knowledge.

For Chapter 8 specifically:

CHAPTER_8_MASTER_STATE.md
→ NARRATIVE_CANON_AND_WRITING_LOCK.md
→ latest WORK_LOG.md
→ relevant supernatural/spatial documents only when needed.

# 11. THIS INDEX IS A CONTROL DOCUMENT

It does not create new canon.

Its job is to answer:

"Where should I look before I claim I know this?"

If this index conflicts with an explicit later author decision, the later author decision wins and this index must be updated.

Repository integrity comes before convenience.
