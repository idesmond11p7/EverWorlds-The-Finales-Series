# Decision Ledger

[ID: DEC-05]
[STATUS: ACTIVE / CHANGE CONTROL]
[LAST-UPDATED: 2026-10-06 | TIME: UNKNOWN]
[UPSTREAM: QTE-04]
[DOWNSTREAM: CAN-07, IDE-08, CHR-09, PRO-10]

## Function
Chronological change control. Decisions are events, not summaries.

## Required record
DECISION-ID
DATE
TIME
EXACT-MOMENT
USER-INTENT
EXACT-USER-QUOTE
DECISION
SOURCE-IDS
CLASSIFICATION
INVALIDATES
AFFECTS
REQUIRES-UPDATE
LINKED-MEMORY
STATUS

## Status
LOCKED / ACCEPTED / PROVISIONAL / RETRACTED / SUPERSEDED / UNKNOWN

## Correction rule
Never erase an incorrect decision. Mark it RETRACTED or SUPERSEDED, preserve the exact wording, and record the replacement.

## Propagation rule
A decision affecting a foundational model automatically triggers recheck of its dependents.
