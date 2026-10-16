# Everworld 6 — AI Synchronization Briefing

[ID: EW6-AI-SYNC-2026-10-16]
[STATUS: ACTIVE — INITIAL CONTINUITY BRIEF; NOT A COMPLETE WORLD BIBLE]
[LAST-VERIFIED: 2026-10-16]
[PURPOSE: Give future AI sessions a source-aware starting point for Everworld 6 and its connection to Apocrypha.]
[SOURCE: EW6-APO-REL-2026-10-16; README.md; 09_MEMORY_BRIDGE.md; 10_ARCHIVE_AUDIT_PASS_1.md; 12_WORK_LOG.md]
[DEPENDS_ON: 00_CONTROL_GATE.md; 01_SOURCE_REGISTER.md; 02_DOCUMENT_MAP.md; 03_SOURCE_LEDGER.md; 04_QUOTE_LEDGER.md; 05_DECISION_LEDGER.md; 06_MENTAL_MODEL_GRADES.md]
[AFFECTS: future Everworld 6 lore records, engine-contract mapping, Apocrypha worldbuilding, session handoffs]
[SUPERSEDES: starting from conversational memory alone or treating Everworld 6 as unrelated to Apocrypha]
[MODEL-GRADE: G2 for the recorded architecture; G1–G2 for the full integrated world model.]
[EVIDENCE-STATE: mixed — author-declared relationship plus repository-recorded architecture; implementation requires code verification.]
[OPERATIONAL-STATE: ACTIVE AS AN ONBOARDING BRIEF; not a complete canon bible.]
[MUST-READ-NEXT: 00_CONTROL_GATE.md → 05_SESSION_HANDOFF.md → 09_MEMORY_BRIDGE.md → EVERWORLD_6_APOCRYPHA_RELATIONSHIP_AND_CANON_BOUNDARY_2026-10-16.md → this file → relevant source records.]

## 1. Repository identity

- Canonical repository: idesmond11p7/EverWorlds-The-Finales-Series
- URL: https://github.com/idesmond11p7/EverWorlds-The-Finales-Series
- Default branch observed during this pass: main
- The current README identifies the active control surface as “Apocrypha — Documentation Control Surface V2.”
- This repository is the persistent documentation record. Model memory and chat summaries are lossy and cannot replace source recovery.

## 2. Project relationship

Everworld 6 is now explicitly connected to Apocrypha. Apocrypha is the active worldbuilding focus for this workstream. Preserve the connection without collapsing distinct project roles or claiming that every file belongs to both. See the relationship-and-boundary record for the exact author decision and unresolved boundaries.

## 3. Architecture described by prior project records

Prior project context describes the intended or claimed Everworld 6 architecture as including:

- An authoritative deterministic world-state engine.
- Immutable snapshots and gated atomic state transitions.
- Seven modeled domains: Entity Lineage, Somatics, Topology, Items, Epistemics, Processes (Φ), and Causal Ledger.
- Continuous processes, epistemic horizons, and an immutable causal DAG/ledger.
- A frontend runtime with a dynamic comic-panel presentation, inspectors, controls, and a ledger viewer.
- A testbed scenario featuring Ignis-Vorax and Kaelen at the Obsidian Sanctum.
- Previously named implementation modules: StateStore.ts, AuthorityRegistry.ts, CouplingEngine.ts, ContinuousEngine.ts, and CausalLedgerDag.ts.

**Verification boundary:** these details were recovered from prior project context and existing documentation references, not independently verified against the current source tree in this pass. Inspect actual files, build scripts, tests, and current commits before marking any implementation as present, compiling, or tested.

## 4. Specification families and known audit signals

Existing project records identify specification families covering behavioral/epistemic contracts, minimum computational substrate, conceptual structure, field-level entity schemas, state-transition semantics, event lifecycle, causal DAGs and omission causality, attribution, causal ledger semantics, continuous processes, counterfactual branching/sandboxing, constitutive domain-engine contracts, and epistemic horizons.

Historical audit material has raised potential risks including missing abort semantics when targets are destroyed, nondeterministic floating-point/PRNG behavior, unbounded belief growth, event ordering, bounded cascade depth, process-abort semantics, determinism standards, and epistemic boundedness. Treat each as a historical finding to recheck against current specifications and code; do not assume it is still open or already fixed.

## 5. Worldbuilding-to-engine trace

Where a lore rule is intended to affect simulation, preserve the chain:

**source claim → canon/decision record → schema or domain contract → transition/process/causal semantics → runtime implementation → test evidence**

Not every lore fact needs a mechanic. Appearance or a historical relationship may be narrative data; a metaphysical law may affect action legality, entity properties, causality, traversal, or perception. Do not force every fact into code, and do not leave a mechanically consequential rule prose-only if the author intends it to govern simulation.

For each integrated rule, identify source wording, canon status, model grade, affected entities/domains, preconditions, legal transitions, observable consequences, constraints/costs, failure cases, causal representation, tests, and unresolved details.

## 6. Current Apocrypha/worldbuilding anchors

The repository README identifies:
- LORE_COSMOLOGY_WORKING_RECORD_2026-10-12.md as a provisional conversational-context reconstruction, not source-verified canon.
- ENERGY_ONTOLOGY_RECOVERY_GATE_2026-10-12.md as an anti-drift/recovery gate, not a completed energy ontology.

Use these as routing anchors, not as permission to fill gaps. The wider universe remains under construction. Exact author-defined “variable energy” and Ether concepts were marked unrecovered in the 2026-10-12 pass. Do not replace missing definitions with generic fantasy or generic DxD assumptions. Kuoh-specific architecture is local and must not be generalized to every realm.

## 7. Mandatory documentation protocol

Follow the repository's active process:

1. Read 00_CONTROL_GATE.md.
2. Read 05_SESSION_HANDOFF.md and 09_MEMORY_BRIDGE.md.
3. Read 01_SOURCE_REGISTER.md and relevant original sources.
4. Preserve materially important exact wording in 04_QUOTE_LEDGER.md.
5. Record decisions in 02_DECISION_LEDGER.md and/or 05_DECISION_LEDGER.md according to existing routing; do not erase old decisions.
6. Record provenance and claim boundaries in 03_SOURCE_LEDGER.md.
7. Update 06_MENTAL_MODEL_GRADES.md when the grade changes.
8. Update 02_DOCUMENT_MAP.md and 07_DOCUMENT_LINK_MAP.md for new modules and dependencies.
9. Audit with 14_AUDIT_RELEASE.md.
10. Record actual changes and checks in 12_WORK_LOG.md.
11. Update README.md and 05_SESSION_HANDOFF.md.
12. Fetch back each changed file. A successful write alone is not verification.

The repository has two decision-related files and multiple handoff conventions. Preserve both existing paths; do not silently consolidate or delete them.

## 8. Gemini-involved workflow preference

The author wants future workflows to involve Gemini. The phrase “Germany 3.8” appears to be speech-transcribed; its exact model/version identity is unverified. Record the workflow preference without asserting product availability or pretending Gemini was used.

The orchestrating assistant should recover sources, preserve continuity/provenance, research where needed, build a self-contained prompt, and audit the result. Gemini is a preferred execution partner where useful and available. The author remains the authority on canon.

A useful prompt must include project identity, objective, authoritative excerpts, exact author decisions, continuity, canon classifications, mechanism details, constraints, unknowns, accessible research links where relevant, concrete output format, acceptance tests, and reporting requirements. Do not expect another model to access private GitHub context or inherit hidden chat history. Do not treat fluent output as canon without verification.

## 9. Verified versus unverified

### Verified during the repository pass
- The repository exists at the URL above and its default branch is main.
- The README and core control/provenance/decision/handoff/audit documents were fetched from GitHub.
- The README calls the active system Apocrypha Documentation Control Surface V2.
- The control gate requires source-first routing, exact quotes, stale-dependency checks, and STOP conditions.
- The author explicitly declared the Everworld 6–Apocrypha connection in the current session.

### Not verified during this pass
- Presence, contents, build status, or test status of the named TypeScript modules.
- Whether the frontend and seed scenario currently run.
- Whether every specification named in prior summaries exists at its expected path.
- The complete Everworld 6 canon and exact integration boundaries.
- The finalized cosmology and energy ontology.
- The exact product/version identity behind “Germany 3.8.”

## 10. Safe next actions

1. Recover actual Everworld 6 specifications and implementation files from the repository and preserved archives.
2. Build a file-level inventory with source authority, freshness, model grade, and project assignment.
3. Recover relevant Apocrypha lore sources and map each to Everworld 6 entities/rules only where evidence supports the mapping.
4. Verify implementation claims against source files, build scripts, and tests.
5. Create an integration map and domain-by-domain lore records after source recovery.
6. Audit and fetch back the updated documents before declaring the onboarding package complete.

**Continuity rule:** do not make the author repeat recoverable information; do not invent unrecoverable information. Recover what exists, mark what is missing, and proceed only as far as the evidence permits.
