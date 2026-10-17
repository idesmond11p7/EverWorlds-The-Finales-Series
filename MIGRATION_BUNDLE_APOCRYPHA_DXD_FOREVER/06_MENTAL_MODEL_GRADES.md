# Mental Model Grade Matrix

[ID: MMG-06]
[STATUS: ACTIVE / GRADE CONTROL]
[LAST-UPDATED: 2026-10-07 | TIME: 09:43+01:00]
[UPSTREAM: SRC-03, QTE-04, DEC-05, SCH-01]
[DOWNSTREAM: CAN-07, IDE-08, CHR-09, PRO-10]

## Purpose
Measure whether the assistant actually possesses a structured mental model rather than merely a fluent description.

## G1 — FLAT
One-dimensional. Surface description. Generalized/collapsed. Can name the thing but cannot reliably model its internal behavior.

Typical signs:
- components collapsed into one label;
- relationships absent;
- boundaries absent;
- exceptions absent;
- consequences guessed;
- requires improvisation to operate.

## G2 — FORMING
Unique structure exists. Some components, relationships, constraints, or interactions are known, but the model still contains collapsed dimensions or unresolved causal links.

Typical signs:
- can explain more than the label;
- can distinguish some cases;
- some interactions are operational;
- important edge cases or dependencies remain unresolved.

## G3 — FULLY MODELED
Operationally understood. Components, relationships, boundaries, dependencies, interactions, exceptions, consequences and failure conditions can be stated and applied without inventing missing structure.

Required tests:
1. Define it.
2. Define what it is not.
3. Decompose it.
4. Trace interactions.
5. State limits/boundaries.
6. Explain consequences.
7. Handle a changed condition.
8. Identify failure modes.
9. Apply it to an actual artifact.
10. Recover it in a later session from the record.

## Anti-inflation rule
Detailed prose does not equal G3. A long document can remain G1.

## Grade transitions
G1 → G2 requires structural distinctions.
G2 → G3 requires operational completeness and artifact-level verification.
G3 → lower grade occurs when a contradiction, missing dependency, or failed application is discovered.

## Grade is independent of truth
G3/PROVISIONAL means "well understood, not yet canon."
G1/LOCKED means "canonically fixed, poorly understood."

## Retrieval-grade rule
A record cannot be treated as fully operational merely because it is stored.
For G3, the system must be able to recover the exact source/quote, explain the model, distinguish it from adjacent concepts, and apply it without importing unsupported assumptions.


## Everworld 6 / Apocrypha integration — 2026-10-16

- TARGET: Everworld 6 ↔ Apocrypha relationship.
- GRADE: G2 — the author's relationship decision is explicit and recoverable, but the complete setting/integration model is not yet structurally resolved.
- EVIDENCE: Current-session author statement preserved in the relationship record, source ledger, quote ledger, and decision ledger.
- KNOWN LIMITS: Exact setting equivalence, world/engine mapping, and full lore integration remain unresolved. Do not infer these from project names.
- UPGRADE REQUIREMENTS: Recover authoritative lore sources; define boundaries and relationships; trace world rules into intended simulation contracts; test changed conditions and failure modes; fetch back artifacts in a later session.

- TARGET: Gemini-involved prompting standard.
- GRADE: G2 — a structured prompt protocol exists and is linked to the existing GMP-21 protocol; performance remains task-dependent and requires artifact-level audit.
- LIMIT: The speech-transcribed “Germany 3.8” label is unverified.
