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
