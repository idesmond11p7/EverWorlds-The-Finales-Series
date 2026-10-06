# Document Cleanup and Contamination Audit

[ID: CLN-18]
[STATUS: ACTIVE / LEGACY AUDIT]
[LAST-UPDATED: 2026-10-06 | TIME: UNKNOWN]
[UPSTREAM: ARC-17, SRC-03, QTE-04, DEC-05]
[DOWNSTREAM: CAN-07, IDE-08, CHR-09, PRO-10]

## Purpose
Audit historical documents for useful information AND contamination. A document can contain both.

## Audit dimensions
1. INFORMATION-DENSITY — how much recoverable evidence exists.
2. AUTHORITY — whether the document can establish truth.
3. MODEL-GRADE — how completely its subject is understood.
4. CANON-LEAKAGE — research/experiment/speculation presented as story truth.
5. DUPLICATION — competing definitions of the same concept.
6. TERMINOLOGY-DRIFT — renamed concepts that silently change meaning.
7. PROVENANCE — whether claims have exact source/quote support.
8. AGE — whether later decisions supersede it.
9. SAFETY/BOUNDARY — whether content research crosses narrative constraints.
10. REUSABILITY — which atomic modules should receive extracted information.

## First audited targets

### ROLEPLAY_RESEARCH_LAB.md
CLASS: EXPERIMENTAL RESEARCH
AUTHORITY: NOT STORY CANON
USEFUL: research methodology, state-tracking hypotheses, epistemic leakage taxonomy, experimental design.
CONTAMINATION RISK: high if research abstractions are mistaken for fictional ontology or proven claims about model internals.
ROUTE: extract atomic research claims → SRC-03 / PRO-10 where craft-relevant / separate research records.
STATUS: QUARANTINE-BY-DEFAULT.

### ROLEPLAY_RESEARCH_EPISTEMIC_LEAKAGE.md
CLASS: EXPERIMENTAL CASE STUDY
AUTHORITY: observation-specific, not universal law.
USEFUL: epistemic-boundary failure taxonomy and case evidence.
CONTAMINATION RISK: converting one observed model behavior into a universal claim.
ROUTE: atomic experiment/case records.
STATUS: QUARANTINE-BY-DEFAULT.

### EVERWORLD_6_RAW_IDEA_DUMP_001.md
CLASS: RAW IDEATION
AUTHORITY: NONE until individual ideas are promoted.
USEFUL: exact idea provenance.
ROUTE: IDE-08, one idea per atomic record.
STATUS: INGESTION SOURCE ONLY.

### EXPERIMENT_001_SPATIAL_REALITY_SYSTEM.md
CLASS: EXPERIMENT
AUTHORITY: experimental only.
CONTAMINATION RISK: experimental mechanics becoming world canon.
ROUTE: REC-13 + IDE-08 where ideas survive.
STATUS: QUARANTINE-BY-DEFAULT.

### NOVEL_PROSE_ARCHITECTURE_STANDARD.md
CLASS: CRAFT STANDARD / RESEARCH DERIVATION
AUTHORITY: craft guidance, not plot canon.
ROUTE: PRO-10 / PRO-11.
STATUS: ACTIVE ONLY AFTER RECONCILIATION.

### NOVEL_PROSE_RENDERING_STANDARD.md
CLASS: CRAFT STANDARD
AUTHORITY: craft guidance.
ROUTE: PRO-10 / PRO-11.
STATUS: RECONCILE WITH ACTUAL FINAL CHAPTER TEXT.

### RESEARCH_PROSE_RENDERING.md
CLASS: RESEARCH EVIDENCE
AUTHORITY: external/craft evidence.
ROUTE: SRC-03 → PRO-10.
STATUS: EVIDENCE, NOT COMMAND.

### NARRATIVE_CANON_AND_WRITING_LOCK.md
CLASS: AUTHOR-DEFINED NARRATIVE CONTROL
AUTHORITY: potentially high, but claim-level verification required.
ROUTE: SRC-03 → DEC-05 / CAN-07.
STATUS: RECHECK AGAINST DIRECT MANUSCRIPTS.

### SUPERNATURAL_ONTOLOGY_MASTER.md
CLASS: AUTHOR-DEFINED FOUNDATIONAL WORLD ARCHITECTURE
AUTHORITY: high where explicitly locked.
ROUTE: claim-level extraction → CAN-07.
STATUS: PROTECTED SOURCE; no competing definitions may be created casually.

## Cleanup rule
Do not rewrite historical documents merely to make them prettier. Extract their information into the new graph. Preserve the original so the reasoning history remains auditable.

## Nonsense rule
When a historical statement is wrong, stale, speculative, duplicated, or unsupported:
PRESERVE → CLASSIFY → LINK → RETRACT/QUARANTINE → PREVENT REUSE.

Deletion destroys the evidence needed to understand how the error occurred.

## Audit Pass 1 — Archive inventory completed
**Verified:** 2026-10-06
**Archive size:** 41 Markdown files
**Archive tree SHA:** 7d7de2221bfe289bda643651e63c83e0d05b8d37

All 41 archived files were retrieved from the preserved archive tree and reviewed for document role, authority, chapter/prose contamination, stale production state, terminology drift, and recovery value. The raw archive remains untouched.

### Critical findings
1. The archive is **not safe as a generation source**. It contains manuscripts, drafts, plans, audits, research, experiments, canon architecture, obsolete control layers, and contradictory production states.
2. Chapter 6 has multiple prose artifacts. None is to be silently treated as the released manuscript merely because its filename says DRAFT.
3. CHAPTER_5_SOURCE_TEXT.md is a strong direct manuscript source, but its statement that the examination is “tomorrow” conflicts with the later accepted Chapter 6 production chronology. That conflict must remain explicit until the authoritative chronology event is linked.
4. NOVEL_CHAPTER_6_PRODUCTION_CONTROL.md, CURRENT_PRODUCTION_DECISIONS.md, WORK_LOG.md, and older control material contain different temporal states. They must be treated as event history, not merged into one timeless statement.
5. NARRATIVE_CANON_AND_WRITING_LOCK.md contains later supersession language and should be treated as a high-authority narrative control source, while its individual claims still require quote-level provenance.
6. ROLEPLAY_RESEARCH_LAB.md, ROLEPLAY_RESEARCH_EPISTEMIC_LEAKAGE.md, and the research files are evidence/research surfaces, not story canon.
7. EVERWORLD_6_RAW_IDEA_DUMP_001.md is a historical ingestion source. Its individual propositions must be classified before reuse.
8. EXPERIMENT_001_SPATIAL_REALITY_SYSTEM.md is experimental implementation architecture and must not silently become fictional spatial canon.
9. SUPERNATURAL_ONTOLOGY_MASTER.md, DEVIL_DEMON_NEGATIVE_POTENTIAL_ARCHITECTURE.md, SUPERNATURAL_REALITY_AND_MAGIC_ARCHITECTURE.md, KUOH_SPIRITUAL_ECOLOGY_AND_COSMOLOGY.md, KUOH_REALM_TRAVERSAL_AND_GATEKEEPING.md, ONTOLOGICAL_SPECTRUM_AND_HIGHER_EXISTENCE.md, and SUPERNATURAL_CIVILIZATIONS_AND_NEGATIVE_SPECTRUM.md contain valuable author-defined architecture but must be consumed through claim/quote records rather than copied wholesale into new summaries.
10. OPAQUE_ARCHIVED.md explicitly marks OPAQUE as historical. It is not an active narrative requirement source.

### Contamination rule
RAW ARCHIVE → RECOVERY → ATOMIC RECORD → VERIFICATION → PROMOTION.
Never RAW ARCHIVE → GENERATION.

If an archived statement is needed again, the assistant must retrieve its promoted atomic record or perform a fresh recovery operation. This prevents stale archive wording from becoming a hidden second canon.

### Hole-closure rule
Every archived file must appear in 19_ARCHIVE_MANIFEST.md. A file without a manifest record is a documentation integrity failure.
