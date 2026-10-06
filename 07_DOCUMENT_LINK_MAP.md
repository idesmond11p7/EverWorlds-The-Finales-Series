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
