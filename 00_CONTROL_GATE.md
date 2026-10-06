# Apocrypha Documentation Control Gate

STATUS: ACTIVE — MANDATORY
LAST VERIFIED: 2026-10-06

This is the first document to consult before changing project state.

## Purpose
Prevent memory drift, provenance loss, accidental canonization, stale-document reuse, and model self-confirmation.

## Mandatory order
1. Read this file.
2. Read 05_SESSION_HANDOFF.md.
3. Read 01_SOURCE_REGISTER.md for the material being touched.
4. Read every linked source marked REQUIRED by the register.
5. Check 02_DECISION_LEDGER.md for superseding decisions.
6. Check 03_CHAPTER_REGISTER.md for chapter status and dependencies.
7. Only then perform work.
8. After work, update 05_SESSION_HANDOFF.md and the relevant ledger/register entries before ending the session.

## Authority
SOURCE > explicit author decision > confirmed derived canon > verified research > active plan > proposal > draft > model memory.

Model memory is never a source.

## STOP gates
STOP if:
- the source is missing;
- two authoritative records conflict;
- a reconstruction is being mistaken for an original;
- a draft is being used as canon without explicit acceptance;
- a fact cannot be traced to a source or decision;
- a requested next step would compound a known error;
- the assistant would have to guess.

## Provenance rule
Every durable claim must have a source pointer, date, status, and relationship to prior knowledge. “I remember” is not provenance.

## Change rule
Do not silently edit history. Corrections create a new dated decision that explicitly invalidates the old claim.

## Session close rule
Before stopping, record: exact task, exact result, files touched, sources consulted, decisions made, unresolved questions, and the first safe next action. Unknown times remain UNKNOWN; never fabricate timestamps.

## Cross-document contract
Every active document must state what it contains, what it does not contain, what it depends on, and what must be read next.
