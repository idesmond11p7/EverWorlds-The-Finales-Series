# Source Ledger

[ID: SRC-03]
[STATUS: ACTIVE / ATOMIC PROVENANCE]
[LAST-UPDATED: 2026-10-06 | TIME: UNKNOWN]
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
