# Document Link Map

STATUS: ACTIVE — CROSS-DOCUMENT ROUTING
LAST VERIFIED: 2026-10-06

## Mandatory chain
00_CONTROL_GATE → 05_SESSION_HANDOFF → 01_SOURCE_REGISTER → relevant source → 02_DECISION_LEDGER → 03_CHAPTER_REGISTER → task-specific document → 04_WORK_LOOP → 05_SESSION_HANDOFF.

## Document contract
Every active document must contain:
- STATUS
- LAST VERIFIED
- PURPOSE
- CONTAINS
- DOES NOT CONTAIN
- DEPENDS ON
- MUST READ NEXT
- LAST MATERIAL CHANGE

## Pointer rule
A document that creates a durable decision must point to the decision ledger. A chapter document must point to its source record. A research document must point to evidence. A plan must point to the canon it depends on.

## Embed-tag convention
Use literal metadata tags at the top of active documents:
[STATUS: ACTIVE]
[SOURCE: ...]
[DEPENDS_ON: ...]
[AFFECTS: ...]
[SUPERSEDES: ...]
[MUST_READ_NEXT: ...]
[LAST_TOUCH: YYYY-MM-DD HH:MM or UNKNOWN]

These are routing metadata, not prose.

## Failure condition
If a document has no source/decision dependency, it cannot be treated as authoritative simply because it is newer.


## Research checkpoint routing — added 2026-10-09

- `13_PROSE_PERCEPTION_SOUND_WORLD_DEPTH_CHECKPOINT.md` is the central recovery anchor for the open research on perception, sound, textual prosody, visual coherence, and world depth.
- Read it after `00_CONTROL_GATE.md` and `05_SESSION_HANDOFF.md`; read its listed dependencies before promoting claims.
- Current grade: provisional synthesis / research open. Do not treat as story canon or a completed bibliography.
- Decision record: `02_DECISION_LEDGER.md`, “Research buffer-stop decision — 2026-10-09”.
- Source record: `01_SOURCE_REGISTER.md`, “Research checkpoint — RCH-2026-10-09-01”.
- Any future validated upgrade to `10_PROSE_ARCHITECTURE.md` must cite its supporting research source records and include a passage-level verification test.


## Gemini master-prompt workflow routing — added 2026-10-09

- GMP-21: 21_GEMINI_MASTER_PROMPT_PROTOCOL.md is the active operational standard for constructing chapter-specific Gemini production prompts.
- Read it after 00_CONTROL_GATE.md, 05_SESSION_HANDOFF.md, and 09_MEMORY_BRIDGE.md; then trace the target chapter's source, master state, previous-chapter handoff, timeline, decision ledger, canon dependencies, and actual manuscript.
- This is an assistant-side recovery and execution protocol. It does not make the project repository accessible to Gemini. The prompt itself must embed the necessary project context.
- Provenance: SRC-WORKFLOW-2026-10-09-01 and GMP-21. Decision: DEC-WORKFLOW-2026-10-09-01 plus its GMP-21 operationalization entry.
- Acceptance condition: full creative operating brief, actual-draft diagnosis, public/accessible research tied to concrete corrections, correct chapter-specific purpose, and a passed self-containment/continuity audit.
- The user's supplied Chapter 6 prompt is a partial source excerpt; method is author-approved, but the exact complete original artifact has not been recovered.


## Chapter 8 production package — 2026-10-10

- `CHR-08_ADDENDUM_2026-10-10_PSYCHOLOGICAL_NIGHT.md` — current author constraints and developmental corrections.
- `CHR-08_SCENE_ARCHITECTURE_2026-10-10.md` — detailed scene causality and proposed NPC/venue/ending design.
- `CHR-08_GEMINI_MASTER_PROMPT_2026-10-10.md` — self-contained Gemini production brief.
- `LIT-17_SENSORY_COGNITIVE_PROSE_ENGINE.md` — sensory, acoustic, spatial, cognitive prose model.
- `21_GEMINI_MASTER_PROMPT_PROTOCOL.md` — active master-prompt method, based on the documented Chapter 6 workflow.

Authority note: current author corrections and verified manuscript evidence outrank proposed architecture. Archive prompts and the previous contaminated Chapter 8 draft remain quarantined.
