# Quote Ledger

[ID: QTE-04]
[STATUS: ACTIVE / EXACT-LANGUAGE MEMORY]
[LAST-UPDATED: 2026-10-06 | TIME: UNKNOWN]
[UPSTREAM: SRC-03]
[DOWNSTREAM: MMG-06, DEC-05, CHR-09, PRO-10]

## Function
Quotes are retrieval anchors and evidence units. They are not decoration.

## Quote classes
Q-U = exact user-authored wording.
Q-A = exact assistant-authored wording that became an important working formulation.
Q-S = exact source/manuscript wording.
Q-R = quoted research/source material.

## Q-U rule
Copy the user's wording exactly. Store date/time/context when available. Never replace it with a cleaner paraphrase.

## Q-A rule
Assistant-retained wording is explicitly marked as assistant-origin. It can guide retrieval but cannot become user canon merely because the assistant remembers it.

## Required quote record
QUOTE-ID
CLASS
EXACT-TEXT
SOURCE-ID
DATE
TIME
CONTEXT
INTENT
WHAT-IT-ESTABLISHES
WHAT-IT-DOES-NOT-ESTABLISH
LINKED-CLAIMS
LINKED-DECISIONS
MODEL-GRADE
STATUS

## Retrieval principle
If a complex idea has a memorable exact formulation, preserve the formulation and link the expanded model to it. The quote is the handle; the model is the structure.
