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

## Current cleanup rule
Legacy documents are not assumed clean. Roleplay research, experimental files, raw idea dumps, prose research, and canon masters are each audited for authority leakage, duplicate definitions, unsupported inference, and stale terminology before their information is promoted.

## Dependency propagation
When A changes a fact consumed by B, B becomes STALE. A change is incomplete until affected dependents are either rechecked or explicitly quarantined.

## Quote propagation
When a foundational quote is corrected, every interpretation derived from it is rechecked. The old interpretation is not silently overwritten; it is marked superseded/retracted.

## Graph rule
Do not solve a missing source by creating a better-sounding summary. Create a recovery record pointing to the missing evidence.

## Naming rule
Opaque IDs route. Human-readable filenames describe. Never infer authority from filenames.


## Energy ontology recovery graph entry — 2026-10-12

- TARGET: ENERGY_ONTOLOGY_RECOVERY_GATE_2026-10-12.md
- TARGET ROLE: Recovery/anti-drift gate; not canon specification.
- SOURCE: SRC-ENERGY-RECOVERY-2026-10-12-01
- DECISION: DEC-ENERGY-RECOVERY-2026-10-12-01
- QUOTES: Q-U-ENERGY-RECOVERY-2026-10-12-01; Q-U-ENERGY-ANALOGY-2026-10-12-01; Q-U-ENERGY-PRESERVATION-2026-10-12-01
- DEPENDENCIES: 00_CONTROL_GATE.md; 01_SOURCE_REGISTER.md; 02_DECISION_LEDGER.md; 03_SOURCE_LEDGER.md; 04_QUOTE_LEDGER.md; 05_DECISION_LEDGER.md; 06_MENTAL_MODEL_GRADES.md; 06_RESEARCH_AND_RECOVERY_METHOD.md; 07_DOCUMENT_LINK_MAP.md; 09_MEMORY_BRIDGE.md; archived energy/ontology source files.
- EXCLUDES: Any inferred definition of variable energy or Ether; global definition of Ender beyond source-backed scope; promotion of raw ideation to canon.
- MODEL-GRADE: G1/G2 for exact variable-energy and Ether definitions until source recovery.
- OPERATIONAL-STATE: Recovery in progress; no complete ontology release.

### Existing routing conflict discovered during recovery
The repository currently has duplicate-looking decision/handoff routes: 05_DECISION_LEDGER.md carries opaque ID DEC-05, while 02_DECISION_LEDGER.md contains the longer chronological history and is referenced by other active documents; 15_SESSION_HANDOFF.md carries HND-15, while 05_SESSION_HANDOFF.md is described elsewhere as the active bridge. Do not silently choose one and discard the other. Preserve both, route this recovery through both records, and reconcile their authority as a separate documented maintenance task. This conflict is itself a dependency risk for future continuity work.


## Everworld 6 / Apocrypha integration modules — 2026-10-16

- TARGET: EVERWORLD_6_APOCRYPHA_RELATIONSHIP_AND_CANON_BOUNDARY_2026-10-16.md
- TARGET ROLE: Author-declared project relationship and canon-boundary record; not a complete cosmology.
- SOURCE: SRC-EW6-APOCRYPHA-2026-10-16-01
- DECISION: DEC-EW6-APO-CONNECTION-2026-10-16-01
- QUOTES: Q-U-EW6-APO-CONNECTION-2026-10-16-01
- DEPENDENCIES: CG-00; SRC-03; QTE-04; DEC-05; MMG-06; 09_MEMORY_BRIDGE.md
- MODEL-GRADE: G2
- EVIDENCE-STATE: Author-declared relationship; integration semantics unresolved.
- OPERATIONAL-STATE: Active routing decision.

- TARGET: EVERWORLD_6_AI_SYNCHRONIZATION_BRIEF_2026-10-16.md
- TARGET ROLE: AI continuity/synchronization brief; not a complete world bible and not code-verification evidence.
- SOURCE: Existing README, control/provenance records, historical architecture context, current author decision.
- DEPENDENCIES: relationship record; source/quote/decision ledgers; archive audit; memory bridge.
- MODEL-GRADE: G2 for recorded architecture; G1–G2 for full integrated model.
- EVIDENCE-STATE: Mixed; code implementation not independently verified.
- OPERATIONAL-STATE: Active onboarding record.

- TARGET: GEMINI_WORKFLOW_AND_PROMPTING_STANDARD_2026-10-16.md
- TARGET ROLE: Cross-model prompt construction protocol.
- SOURCE: Q-U-GEMINI-WORKFLOW-2026-10-16-01; existing 21_GEMINI_MASTER_PROMPT_PROTOCOL.md.
- MODEL-GRADE: G2; task-by-task evaluation required.
- OPERATIONAL-STATE: Active workflow preference; version name unverified.
