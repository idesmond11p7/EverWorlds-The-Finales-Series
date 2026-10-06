# Document Map

[ID: DM-02]
[STATUS: ACTIVE / GRAPH ROUTER]
[LAST-UPDATED: 2026-10-06 | TIME: UNKNOWN]
[UPSTREAM: SW-01, SL-03]
[DOWNSTREAM: ALL]

## Function
Maps opaque module IDs to purpose, inputs, outputs, dependencies, update requirements, and contained evidence.

## Required module header
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

## Update propagation
If module A changes a claim consumed by B/C/D, B/C/D become STALE until rechecked. “I updated A” is not completion.

## Obfuscation principle
The stable ID is the primary routing key. Filenames are descriptive aliases. The assistant must use the Schema of Work to discover the module rather than treating filename recognition as sufficient memory.
