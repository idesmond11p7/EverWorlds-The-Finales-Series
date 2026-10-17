# Gemini-Involved Workflow and Prompting Standard

[ID: GMP-EW6-2026-10-16]
[STATUS: ACTIVE — AUTHOR WORKFLOW PREFERENCE; VERSION CLAIM UNVERIFIED]
[LAST-VERIFIED: 2026-10-16]
[PURPOSE: Turn the author's Gemini preference into a repeatable, source-safe prompting method.]
[SOURCE: Q-U-GEMINI-WORKFLOW-2026-10-16-01; 09_MEMORY_BRIDGE.md; 21_GEMINI_MASTER_PROMPT_PROTOCOL.md]
[DEPENDS_ON: 00_CONTROL_GATE.md; 01_SOURCE_REGISTER.md; 03_SOURCE_LEDGER.md; 04_QUOTE_LEDGER.md; 05_DECISION_LEDGER.md; 06_MENTAL_MODEL_GRADES.md; 09_MEMORY_BRIDGE.md; 21_GEMINI_MASTER_PROMPT_PROTOCOL.md]
[AFFECTS: future AI-assisted research, worldbuilding, simulation design, documentation, and review]
[MODEL-GRADE: G2 — operational method defined; evaluate each application against actual artifacts.]
[EVIDENCE-STATE: AUTHOR-DECLARED preference plus existing repository prompting protocol.]
[OPERATIONAL-STATE: ACTIVE; does not verify a specific Gemini version.]
[MUST-READ-NEXT: 00_CONTROL_GATE.md → 09_MEMORY_BRIDGE.md → 21_GEMINI_MASTER_PROMPT_PROTOCOL.md → this file.]

## 1. Author preference

The author stated:

> “from now on, every single workflow we're ever gonna have is going to be involving Germany, okay?”

“Germany 3.8” appears to be speech-transcribed wording. The exact model/version label is not independently verified. The workflow preference is clear.

**Operational rule:** future workflows should explicitly consider and involve Gemini where useful and available, while source recovery, canon authority, verification, and final decisions remain anchored to the project's documentation and author. “Involving Gemini” does not mean every tiny subtask must be delegated; if Gemini is unavailable or adds no value to a bounded step, record that honestly.

## 2. Role allocation

### Continuity/research orchestrator
- Recover authoritative sources and actual artifact versions.
- Separate author canon, direct evidence, derived interpretation, proposal, and UNKNOWN.
- Identify conflicts, missing dependencies, and stale documents.
- Research current facts where needed.
- Construct a self-contained execution prompt with acceptance tests.
- Audit the result against source material and decisions.
- Record changes and propagate them through dependent documents.

### Gemini execution partner
- Execute the bounded task described in the prompt.
- Use supplied source excerpts and accessible public research.
- Avoid inventing unavailable project facts.
- Return the artifact and a verification/change report.
- Separate verified results from assumptions and unresolved questions.

### Author
- Sets creative intent.
- Locks, corrects, or retracts canon and workflow decisions.
- Resolves genuinely authorial ambiguity after recoverable sources have been checked.

## 3. Prompt construction protocol

Scale these sections to the task, but never omit material context:

1. **Identity:** exact project/subproject and similar projects that must not be conflated.
2. **Objective:** one concrete deliverable and why it matters.
3. **Authority map:** source files, excerpts, version/commit, and source precedence.
4. **Exact language:** quote controlling author wording when materially important.
5. **State and continuity:** current state, chronology, dependencies, and established facts.
6. **Canon classification:** author-locked, verified source, derived, proposal, reconstruction, quarantined, or UNKNOWN.
7. **Mechanism model:** inputs, transformations, outputs, costs, constraints, failure modes, edge cases.
8. **Task boundary:** what to change, what not to change, and what is out of scope.
9. **Research packet:** credible accessible sources and exactly what each supports.
10. **Execution sequence:** ordered operations and STOP conditions.
11. **Output contract:** format, required sections, names, and repository destinations.
12. **Acceptance tests:** observable success conditions, not vague requests such as “make it better.”
13. **Verification report:** what was actually run, fetched, tested, and what remains unverified.
14. **Change propagation:** affected registries, decision records, memory bridge, work log, audit, and handoff.
15. **Handoff:** next safe action and exact source from which to continue.

## 4. Prompt quality tests

Before sending a substantive prompt, ask:
- Can the model execute without hidden chat history or inaccessible private links?
- Are exact author decisions and relevant quotes included?
- Are project identities and canon boundaries explicit?
- Are source facts separated from hypotheses and proposals?
- Does the prompt explain mechanisms rather than listing adjectives?
- Are constraints, exceptions, failure modes, and UNKNOWNs stated?
- Does it request the actual artifact, not just a plan?
- Are completion criteria observable?
- Does it forbid false claims of testing, execution, or source access?
- Is there a recovery path if a STOP condition appears?
- Does it identify which documents must change if dependencies change?

If a material answer is no, repair the prompt before execution.

## 5. Research discipline

- Search current credible sources for claims that may have changed.
- Prefer primary documentation, source repositories, peer-reviewed work, and directly relevant technical references.
- Give the execution model links it can actually access; never assume it can read private GitHub context.
- Embed the evidence needed for conclusions.
- Research informs diagnosis; it does not override project canon.
- When evidence conflicts or is weak, mark the question unresolved instead of manufacturing certainty.

## 6. Execution loop

**RECOVER → MODEL → PROMPT → EXECUTE → COMPARE → TEST → RECORD → HANDOFF**

Never claim a model executed work without evidence. A prepared prompt is not a sent prompt; generated code is not a running implementation; a specification is not proof of runtime behavior.

## 7. Standard completion report

For every substantive workflow, report:
- requested outcome;
- sources actually inspected;
- artifacts created or changed;
- decisions preserved;
- checks actually performed;
- confirmed results;
- untested claims and UNKNOWNs;
- stale dependencies or required follow-up;
- next safe action.

## 8. Scope

This is a workflow preference and prompting contract. It does not establish that “Gemini 3.8” is a verified product/version name or that Gemini is connected in every environment. The author remains the canon authority; the repository remains the persistent source-of-truth system.
