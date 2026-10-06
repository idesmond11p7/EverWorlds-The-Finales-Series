# Autonomous Work Loop

STATUS: ACTIVE — EXECUTION PROTOCOL
LAST VERIFIED: 2026-10-06

## Loop
ORIENT → TRACE → VERIFY → PLAN → EXECUTE → AUDIT → RECORD → HANDOFF

### ORIENT
Read 00_CONTROL_GATE.md and 05_SESSION_HANDOFF.md.

### TRACE
Find the authoritative source and every dependency. Never rely on memory when a repository source can be checked.

### VERIFY
Check chronology, provenance, contradictions, and whether the proposed work is actually supported.

### PLAN
Define intent, exact deliverable, dependencies, failure conditions, and stop conditions.

### EXECUTE
Do only the bounded task. Do not silently expand scope.

### AUDIT
Compare output against source, decisions, and exclusions. Test for invented facts and accidental promotion of drafts.

### RECORD
Update the ledger/registers immediately after a meaningful decision or correction.

### HANDOFF
Update 05_SESSION_HANDOFF.md with what was last touched, what was learned, what changed, what remains unknown, and the exact next safe action.

## Anti-amnesia mechanism
The next session must be able to determine the previous session's final action without conversational memory.

## Anti-self-confirmation mechanism
A document cannot validate its own claim. Validation must point outward to a source, author decision, or independent research evidence.

## Anti-drift mechanism
If work changes an assumption, the ledger must record the change before dependent documents are rewritten.

## Anti-compounding mechanism
A failed intermediate result is quarantined before replacement work begins.
