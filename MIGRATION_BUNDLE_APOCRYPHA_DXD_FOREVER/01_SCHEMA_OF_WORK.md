# Schema of Work

[ID: SCH-01]
[STATUS: ACTIVE / MASTER ROUTER]
[LAST-UPDATED: 2026-10-07 | TIME: 09:43+01:00]
[UPSTREAM: CG-00]
[DOWNSTREAM: ALL]

## Function
Opaque routing layer. Filenames are aliases. IDs are authority.

## Core modules
CG-00 CONTROL
SCH-01 SCHEMA
MAP-02 DOCUMENT GRAPH
SRC-03 SOURCE LEDGER
QTE-04 QUOTE LEDGER
DEC-05 DECISION LEDGER
MMG-06 MENTAL MODEL GRADES
CAN-07 CANON CLAIM MATRIX
IDE-08 IDEA REGISTRY
CHR-09 CHAPTER REGISTRY
PRO-10 PROSE ARCHITECTURE
MET-11 PROSE MEASUREMENT
WRK-12 WORK LOG
REC-13 RECOVERY / QUARANTINE
AUD-14 AUDIT / RELEASE
HND-15 SESSION HANDOFF
INP-16 INPUT REQUIREMENTS
ARC-17 ARCHIVE INDEX
CLN-18 DOCUMENT CLEANUP / CLASSIFICATION

## Atomicity rule
A module is a reusable information surface, not a topic bucket. One concept may have records across source, quote, model, canon, chapter, and prose modules.

## User-statement integrity rule
For materially meaningful user input:
1. Preserve the exact user wording before interpretation.
2. Split multi-part input into distinct statements/clauses when meaningfully separable.
3. Preserve negations, exceptions, contrasts, corrections, temporal qualifiers and emphasis.
4. Classify each statement before compressing it.
5. Answer each material statement or explicitly state why it is unresolved.
6. Never allow an assistant paraphrase to silently replace the original user statement.
7. If voice/transcription is ambiguous, preserve the raw wording and mark the interpretation UNKNOWN rather than silently normalizing meaning.

Minimum statement classes:
USER-FACT, USER-CONSTRAINT, USER-REQUEST, USER-DECISION, USER-CORRECTION, USER-RETRACTION, USER-QUESTION, USER-HYPOTHESIS, HISTORICAL-STATE, ASSISTANT-INFERENCE, UNKNOWN.

## State hierarchy
Persistence priority:
1. Fundamental project facts, ontology, locked constraints and durable operating rules.
2. Historical decisions, rejected paths and provenance.
3. Current architecture/state.
4. Current drafts and production plans.
5. Temporary ideation.

Lower-level material may be superseded without erasing historical evidence. Recency alone never outranks authority or persistence class.

## Contradiction rule
A contradiction is a state transition problem, not permission to guess.
Record:
- earlier statement;
- later statement;
- exact source/quote;
- chronology;
- whether the later statement corrects, supersedes, qualifies or merely conflicts;
- affected dependents.
Unresolved conflicts remain CONFLICTED/UNKNOWN and block dependent promotion where necessary.

## Memory firewall
Stored, remembered, inferred, current, authoritative and verified are separate states.
A familiar assistant recollection is never evidence by itself.
No generation claim may be promoted from memory-only material.

## Mental-model axis
Every important record receives G1, G2, or G3:
- G1 = one-dimensional / flat / collapsed.
- G2 = partially structured / unique structure exists but information remains collapsed.
- G3 = fully operational mental model: components, relations, boundaries, interactions, exceptions, consequences and usage are understood.

GRADE IS NOT CANONICITY.

## Evidence axis
SOURCE / AUTHOR / VERIFIED / DERIVED / PROVISIONAL / RECONSTRUCTION / RETRACTED / UNKNOWN / CONFLICTED.

## Operational axis
UNUSABLE / REFERENCE-ONLY / OPERATIONAL / VERIFIED-IN-USE.

## Creation rule
No new module without ID, purpose, upstream, downstream, schema, evidence rules, grade rules, and retirement path.
