# Mental Model Grade Matrix

[ID: MMG-06]
[STATUS: ACTIVE / GRADE CONTROL]
[LAST-UPDATED: 2026-10-06 | TIME: UNKNOWN]
[UPSTREAM: SRC-03, QTE-04, DEC-05]
[DOWNSTREAM: CAN-07, IDE-08, CHR-09, PRO-10, PRO-10]

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
