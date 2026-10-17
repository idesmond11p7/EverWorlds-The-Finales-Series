# Control Gate — Documentation System V2

[ID: CG-00]
[STATUS: ACTIVE / HARD ENFORCEMENT]
[LAST-UPDATED: 2026-10-06 | TIME: UNKNOWN]
[SCHEMA: META]
[READ-BEFORE: ALL WORK]
[UPSTREAM: SCH-01, MAP-02, SRC-03, QTE-04]
[DOWNSTREAM: ALL]

## Function
This is the execution lock. It does not contain story canon. It prevents the assistant from generating from memory, stale modules, collapsed models, or unverified reconstruction.

## Mandatory route
CONTROL → SCHEMA → MAP → SOURCE → QUOTE → DECISION → MODEL-GRADE → TARGET MODULE → AUDIT → HANDOFF.

## Before touching a module
1. Resolve the target by opaque ID.
2. Read its module contract.
3. Read every upstream dependency.
4. Check STALE flags and supersession.
5. Locate exact source quotes before interpreting claims.
6. Check mental-model grade.
7. Check whether the information is canon, proposal, reconstruction, or unknown.
8. Define the exact operation.
9. Execute only that operation.
10. Recheck dependents after mutation.

## STOP conditions
STOP when:
- source identity is unresolved;
- a required quote cannot be recovered;
- an upstream dependency is stale;
- two authoritative sources conflict;
- model memory is the only evidence;
- reconstruction is being treated as manuscript;
- a G1/G2 model is being used as though it were G3;
- a user correction has not propagated;
- a requested chapter manuscript is absent.

## Hard rule
"Next" never overrides a STOP condition.

## Quote rule
Exact user wording and exact assistant-retained wording are stored separately. A paraphrase is never allowed to replace the source quote.

## Freshness rule
Opening a document does not make it current. Dependency state determines freshness.
