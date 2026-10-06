# Memory Bridge

STATUS: ACTIVE — MODEL LIMITATION CONTROL
LAST VERIFIED: 2026-10-06

## Purpose
Bridge the gap between model context and persistent project state.

## Rule
The assistant must assume its conversational memory is lossy. GitHub is the persistent record; active documents are indexed evidence, not memory substitutes.

## Before claiming knowledge
Ask:
1. Where did this come from?
2. Is the source still authoritative?
3. Was it later corrected?
4. Is it canon, derived, provisional, or reconstruction?
5. What document records the last decision?
6. What other document must be updated if this changes?

## Memory checksum
Every important fact should be recoverable through at least one source pointer and one decision/relationship pointer when applicable.

## Model-memory quarantine
If a fact exists only in the model's recollection, label it UNKNOWN until verified.

## Recovery phrase
When uncertain: SOURCE NOT VERIFIED — STOP.

## Continuity bridge
A new session begins from 05_SESSION_HANDOFF.md, then follows the links in 07_DOCUMENT_LINK_MAP.md. No conversational reconstruction is required.
