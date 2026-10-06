# Source Ledger

[ID: SL-03]
[STATUS: ACTIVE / PROVENANCE]
[LAST-UPDATED: 2026-10-06 | TIME: UNKNOWN]
[UPSTREAM: CG-00, ARCHIVE]
[DOWNSTREAM: CM-05, IR-06, CR-07, PR-08]

## Function
Atomic source records. This is where the old archive is converted rather than merely summarized.

## Source classes
ORIGINAL_MANUSCRIPT / AUTHOR_QUOTE / AUTHOR_DECISION / RESEARCH / DERIVED / PROPOSAL / RECONSTRUCTION / RETRACTED.

## Required source record
SOURCE-ID
ORIGINAL-FILE
ARCHIVE-PATH
GIT-COMMIT(S)
DATE/TIME
EXACT-QUOTE(S)
LINES / SECTION
CLAIM(S)
CONTAINS
DOES-NOT-CONTAIN
AUTHORITY
DEPENDENCIES
SUPERSEDED-BY
STATUS

## Conversion rule
Archive documents remain immutable evidence. Their useful information is atomized into source records and routed into the appropriate canonical, decision, idea, chapter, prose, or research modules.

## No dumping
Do not copy an entire old document into a new document simply to preserve it. Preserve the source in archive; extract reusable claims into atomic records.
