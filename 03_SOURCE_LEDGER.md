# Source Ledger

[ID: SRC-03]
[STATUS: ACTIVE / ATOMIC PROVENANCE]
[LAST-UPDATED: 2026-10-09]
[UPSTREAM: ARC-17, CG-00]
[DOWNSTREAM: QTE-04, DEC-05, MMG-06, CAN-07, IDE-08, CHR-09, PRO-10]

## Function
Convert historical material into atomic evidence records. Do not copy archives into new documents.

## Source classes
ORIGINAL_MANUSCRIPT
AUTHOR_STATEMENT
AUTHOR_DECISION
VERIFIED_RESEARCH
DERIVED
PROPOSAL
RECONSTRUCTION
RETRACTED
UNKNOWN

## Record schema
SOURCE-ID
ORIGINAL-FILE
ARCHIVE-PATH
GIT-COMMIT(S)
DATE
TIME
CONTEXT
EXACT-QUOTE(S)
LINE/SECTION
CLAIM
CONTAINS
DOES-NOT-CONTAIN
AUTHORITY
MODEL-GRADE
EVIDENCE-STATE
DEPENDENTS
SUPERSEDES
STATUS

## Critical distinction
A source may be highly authoritative while the assistant's mental model of that source is only G1/G2.

## Recovery rule
A source identity remains UNKNOWN until the actual artifact, Git history, publication evidence, or explicit author confirmation resolves it.

## SRC-WORKFLOW-2026-10-09-01 — Chapter 6 master Gemini prompt / workflow correction

- SOURCE-ID: SRC-WORKFLOW-2026-10-09-01
- ORIGINAL-FILE: User-pasted “EVERWORLDS: THE FINALES — CHAPTER 6 — MASTER GEMINI PRODUCTION PROMPT”
- ARCHIVE-PATH: Not independently established; source was pasted into the conversation on 2026-10-09 with its internal header “Paste October 02, 2026 - 1:54PM”
- DATE: Original prompt date indicated by user: 2026-10-02; received in this conversation: 2026-10-09
- TIME: Original header says 1:54PM; timezone not independently established
- CONTEXT: The author explicitly identified this as the prompt that made Chapter 6 a “master peice” and corrected the assistant's Chapter 8 prompting methodology.
- EXACT-QUOTE(S): “THIS was the prompt that made chap 6 a master peice”; “You keep forgeting THAT YOUR JOB is to PROMPT gemini ...Gemini can't access locked LINKS like github only research papers and other surface things YOU didn't and you keep leading gemini astray your supposed to be a master prompter”
- CLAIM: Future chapter prompting must preserve the full creative-operating-brief method, with the assistant responsible for sourcing/reconstructing project context and embedding it in the prompt Gemini receives.
- CONTAINS: A visible excerpt of the Chapter 6 production prompt; the user's explicit assessment of its success; the user's correction that Gemini cannot access the project's locked GitHub links in their current workflow.
- DOES-NOT-CONTAIN: A verified complete copy of every line of the original prompt in the repository; proof that every stylistic instruction alone caused Chapter 6's success; permission to transfer Chapter 6-specific plot decisions to other chapters.
- AUTHORITY: AUTHOR_STATEMENT / ORIGINAL_SOURCE excerpt
- MODEL-GRADE: G2 pending recovery of complete original artifact and application to another actual prompt
- EVIDENCE-STATE: AUTHOR-CONFIRMED for the benchmark assessment and role split; partial artifact capture for exact source text
- DEPENDENTS: 09_MEMORY_BRIDGE.md; 02_DECISION_LEDGER.md; 04_QUOTE_LEDGER.md; 05_SESSION_HANDOFF.md; future chapter-specific Gemini production prompts
- SUPERSEDES: The assistant's previous tendency to produce generic editorial checklists instead of a full production prompt; the assumption that pointing Gemini to a private GitHub source is sufficient context transfer
- STATUS: LOCKED WORKFLOW RULE; source artifact itself remains PARTIAL until a complete copy is durably recovered

## Research checkpoint — RCH-2026-10-09-01

- SOURCE-ID: RCH-2026-10-09-01
- ORIGINAL PATH/NAME: 13_PROSE_PERCEPTION_SOUND_WORLD_DEPTH_CHECKPOINT.md
- SOURCE TYPE: WORKING_PLAN / DERIVED SYNTHESIS (not VERIFIED_RESEARCH and not story canon)
- DATE/TIME: 2026-10-09 11:15+01:00
- EXACT PROVENANCE: Built from the author's current-session assessment of the published final Chapter 6 and the research synthesis already discussed in-session. It is a pause/recovery record, not a replacement for original research sources.
- WHAT IT ESTABLISHES: Current research questions, provisional perception/sound/world-depth models, implementation hypotheses, failure conditions, verification tests, and the required continuation method.
- WHAT IT DOES NOT ESTABLISH: A final theory, completed bibliography, locked fictional canon, validated universal prose rules, or an update to a separate TypeShift destination.
- DEPENDENT DOCUMENTS: 05_SESSION_HANDOFF.md; 02_DECISION_LEDGER.md; 10_PROSE_ARCHITECTURE.md when findings are later validated and promoted.
- SUPERSEDED CLAIMS: The prior handoff's Chapter 6 manuscript-identity uncertainty is superseded by the author's direct confirmation in this session. Earlier historical record is retained as history.
- CONFIDENCE: Author's Chapter 6 status statement = CONFIRMED; research framework = PROVISIONAL.
- VERIFICATION STATUS: Checkpoint file and handoff/decision updates fetched back from GitHub successfully; bibliography still incomplete.
