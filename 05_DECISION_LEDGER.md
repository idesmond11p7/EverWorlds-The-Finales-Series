# Decision Ledger

[ID: DEC-05]
[STATUS: ACTIVE / CHANGE CONTROL]
[LAST-UPDATED: 2026-10-06 | TIME: UNKNOWN]
[UPSTREAM: QTE-04]
[DOWNSTREAM: CAN-07, IDE-08, CHR-09, PRO-10]

## Function
Chronological change control. Decisions are events, not summaries.

## Required record
DECISION-ID
DATE
TIME
EXACT-MOMENT
USER-INTENT
EXACT-USER-QUOTE
DECISION
SOURCE-IDS
CLASSIFICATION
INVALIDATES
AFFECTS
REQUIRES-UPDATE
LINKED-MEMORY
STATUS

## Status
LOCKED / ACCEPTED / PROVISIONAL / RETRACTED / SUPERSEDED / UNKNOWN

## Correction rule
Never erase an incorrect decision. Mark it RETRACTED or SUPERSEDED, preserve the exact wording, and record the replacement.

## Propagation rule
A decision affecting a foundational model automatically triggers recheck of its dependents.


## DEC-ENERGY-RECOVERY-2026-10-12-01 — Enforce source-first energy ontology recovery

- DECISION-ID: DEC-ENERGY-RECOVERY-2026-10-12-01
- DATE: 2026-10-12
- TIME: UNKNOWN
- EXACT-MOMENT: User corrected repeated generic reconstructions of existing energy lore and required execution of the documentation system.
- USER-INTENT: Preserve the author's established world and stop asking them to redo documentation work; analogies must live in the relevant document.
- EXACT-USER-QUOTE:
  - “You've created entire systems and documentation to prevent the same problem. Please use those systems.”
  - “When explaining, you're supposed to use the analogy and put it in the document rather than just using bullshit.”
  - “I don't want that. My ideas being forgotten and left in the dust, and being changed to something they were absolutely not.”
- DECISION: Execute CG-00 → SCH-01 → MAP-02 → SRC-03 → QTE-04 → DEC-05 → MMG-06 → target module → AUD-14 → HND-15; recover exact sources and quotations; separate canon from raw ideation and inference; place mechanic + analogy + mapping + boundary + example + provenance in the target document; mark unresolved source claims UNKNOWN; never ask the author to repeat lore already stored; fetch back and verify every changed artifact.
- SOURCE-IDS: SRC-ENERGY-RECOVERY-2026-10-12-01; Q-U-ENERGY-RECOVERY-2026-10-12-01; Q-U-ENERGY-ANALOGY-2026-10-12-01; Q-U-ENERGY-PRESERVATION-2026-10-12-01.
- CLASSIFICATION: LOCKED WORKFLOW DECISION; no new lore canon created.
- INVALIDATES: This session's generic assistant reconstructions of “variable energy” and any chat-only analogy not added to the project artifact.
- AFFECTS: Energy/resource/power-system/ontology/world-lore work and all future continuity recovery.
- REQUIRES-UPDATE: Recovery gate, source register, source ledger, quote ledger, detailed decision history, map/link map, work log, audit record, memory bridge, session handoffs, README.
- LINKED-MEMORY: 09_MEMORY_BRIDGE.md; ENERGY_ONTOLOGY_RECOVERY_GATE_2026-10-12.md.
- STATUS: LOCKED workflow rule; exact energy definitions remain UNKNOWN pending recovery.

### Routing warning attached to this decision
The current repository exposes two decision records (05_DECISION_LEDGER.md / DEC-05 and 02_DECISION_LEDGER.md) and two handoff records (15_SESSION_HANDOFF.md / HND-15 and 05_SESSION_HANDOFF.md). Both paths have been preserved and updated where applicable for this pass. Their precedence is not silently resolved here; reconcile the duplicate control surfaces as a separate maintenance decision.
