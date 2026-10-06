# Document Graph

[ID: MAP-02]
[STATUS: ACTIVE / GRAPH CONTROL]
[LAST-UPDATED: 2026-10-06 | TIME: UNKNOWN]
[UPSTREAM: SCH-01, SRC-03]
[DOWNSTREAM: ALL]

## Module contract
Every active module must expose:
[ID]
[STATUS]
[LAST-UPDATED]
[SCHEMA]
[UPSTREAM]
[DOWNSTREAM]
[CONTAINS]
[EXCLUDES]
[SUPERSEDES]
[LAST-TOUCH]
[MUST-RECHECK]
[MODEL-GRADE]
[EVIDENCE-STATE]
[OPERATIONAL-STATE]

## Dependency propagation
When A changes a fact consumed by B, B becomes STALE. A change is incomplete until affected dependents are either rechecked or explicitly quarantined.

## Quote propagation
When a foundational quote is corrected, every interpretation derived from it is rechecked. The old interpretation is not silently overwritten; it is marked superseded/retracted.

## Graph rule
Do not solve a missing source by creating a better-sounding summary. Create a recovery record pointing to the missing evidence.

## Naming rule
Opaque IDs route. Human-readable filenames describe. Never infer authority from filenames.
