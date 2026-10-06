# Control Gate

[ID: CG-00]
[STATUS: ACTIVE / ENFORCEMENT]
[LAST-UPDATED: 2026-10-06 | TIME: UNKNOWN]
[SCHEMA: SW-00]
[READ-BEFORE: ALL ACTIVE WORK]
[UPSTREAM: 01-SOURCE-LEDGER, 02-DECISION-LEDGER, 03-SCHEMA-OF-WORK]
[DOWNSTREAM: ALL]

## Function
Hard gate between repository knowledge and generation. It is not a summary and does not contain canon.

## Mandatory traversal
CONTROL GATE → SCHEMA OF WORK → DOCUMENT MAP → SOURCE LEDGER → DECISION LEDGER → TARGET MODULE → AUDIT → HANDOFF.

## Required checks before writing/updating anything
1. Identify the target module by ID, not memory or filename.
2. Read its dependency list.
3. Read every required upstream module whose update date is newer than the target.
4. Check supersession/retraction records.
5. Check the last-touch record.
6. Verify source provenance.
7. Define intended change before execution.
8. After execution, update the target's dependency timestamp and affected modules.

## Hard STOP
STOP if source identity is unresolved, dependencies are stale, two authoritative records conflict, a reconstruction is being promoted, or a claim exists only in model memory.

## Precision rule
Unknown means UNKNOWN. Approximate dates/times are not upgraded into exact metadata. Quotes must be copied from source, not reconstructed.

## Enforcement principle
The system is intentionally inconvenient when evidence is weak. That inconvenience is the feature.
