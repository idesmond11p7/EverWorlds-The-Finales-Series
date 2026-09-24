# OPAQUE — Formal Ratification Review — Pass 3

## Status

**Working ratification-review artifact — Pass 3 complete (provisional dispositions).**

This pass reviews **R-021–R-030 — Change, Validation, Operation, Failure, and Closure Requirements** against the current detailed specification, the finite candidate baseline, the established control model, and the unresolved governance matters.

No disposition in this document constitutes ratification.

---

## 1. Review Objective

Determine a controlled provisional disposition for each requirement in R-021–R-030 while preserving:

- requirement identity;
- distinction between ordinary requirements and unresolved governance questions;
- authority boundaries;
- dependency visibility;
- traceability;
- the difference between a requirement being substantively sound and being fully actionable under unresolved governance rules.

### Completion condition

Pass 3 is complete when R-021–R-030 each have:

1. a provisional disposition;
2. relevant evidence;
3. material dependencies identified;
4. unresolved matters identified;
5. defect status recorded;
6. rationale recorded;
7. required authority identified;
8. traceability to the specification and baseline preserved.

That condition has been satisfied.

---

## 2. Review Results

| Item | Provisional disposition | Material unresolved dependency | Defect status |
|---|---|---|---|
| R-021 | D-01 — Ratify as Written | General authority/transition rules remain governing context | No material defect identified |
| R-022 | D-01 — Ratify as Written | None material to the requirement itself | No material defect identified |
| R-023 | D-03 — Defer | U-004 Validation Authority; related authority questions | Governance dependency |
| R-024 | D-01 — Ratify as Written | R-015/U-001 authority framework applies to actual permissions | No material defect identified |
| R-025 | D-01 — Ratify as Written | None material to the distinction itself | No material defect identified |
| R-026 | D-01 — Ratify as Written | Validation/determination may apply downstream | No material defect identified |
| R-027 | D-01 — Ratify as Written | Resolution may depend on authority/validation where applicable | No material defect identified |
| R-028 | D-01 — Ratify as Written | Recovery remains subject to existing authority/validation rules | No material defect identified |
| R-029 | D-03 — Defer | U-009 Exception Authority | Governance dependency |
| R-030 | D-03 — Defer | U-010 Closure Semantics; related authority/termination questions | Governance dependency |

---

## 3. R-021 — Controlled Change

### Candidate / specified meaning

R-021 requires material alterations to controlled state, controlled relationships, governing requirements, or authoritative records to be treated as controlled changes. It distinguishes an authoritative change from a proposal, failed attempt, external observation, or error correction.

### Evidence

The detailed specification establishes the required change dimensions:

- affected object and state;
- proposed alteration;
- authority;
- conditions;
- dependencies;
- validation;
- resulting state.

This directly implements the candidate requirement and aligns with the established control model concepts of Change, State, Authority, Condition, Dependency, Validation, Outcome, and Provenance.

### Dependencies

- R-010 Controlled State Modification;
- R-015 Authority Determination;
- R-017 Dependency Integrity;
- R-023 Validation Integrity where validation is required;
- C-10 Change and related control concepts.

### Unresolved matters

Authority precedence may affect particular change cases, but that does not create a defect in the requirement itself.

### Defect status

**No material defect identified.**

### Proposed disposition

**D-01 — Ratify as Written.**

### Rationale

The requirement establishes a necessary control boundary without attempting to silently define unresolved authority precedence or implementation mechanics.

### Required authority

Formal ratification authority for the requirement as a candidate rule.

### Traceability

Candidate baseline R-021 → detailed specification R-021 → Pass 3 review → D-01 proposed.

---

## 4. R-022 — Change History

### Candidate / specified meaning

R-022 requires preservation of material history sufficient to reconstruct how controlled state was reached and materially changed.

### Evidence

The specification identifies prior state, resulting state, change description, basis, authority, conditions/dependencies, validation result, provenance, and sequence as applicable. It also explicitly prevents later state from erasing material prior state.

This aligns with Provenance, State, Change, Validation, and Traceability in the control model.

### Dependencies

- R-021 Controlled Change;
- R-031 Traceability;
- C-10 Change;
- C-13 Provenance.

### Unresolved matters

No unresolved governance matter currently prevents the requirement from being expressed at this level.

### Defect status

**No material defect identified.**

### Proposed disposition

**D-01 — Ratify as Written.**

### Rationale

The requirement establishes what historical integrity must be preserved while leaving storage and implementation mechanisms downstream.

### Required authority

Formal ratification authority.

### Traceability

Candidate baseline R-022 → detailed specification R-022 → Pass 3 review → D-01 proposed.

---

## 5. R-023 — Validation Integrity

### Candidate / specified meaning

R-023 requires validation to remain distinct from determination, approval, observation, and incorporation, and requires the validation subject, criteria, authority/method, result, evidence, and limitations to remain identifiable.

### Evidence

The detailed specification fully distinguishes validation from adjacent concepts and limits validation to the scope actually covered.

The requirement is internally coherent and supported by C-09 Validation.

### Dependencies

- R-015 Authority Determination;
- R-020 Controlled Incorporation;
- C-09 Validation;
- **U-004 Validation Authority**.

### Unresolved matters

**U-004 — Validation Authority** remains unresolved. The requirement explicitly requires a validation authority or method, but the governance system has not yet finally established who or what may exercise validation authority in every applicable case.

### Defect status

**Governance dependency; not a specification defect.**

### Proposed disposition

**D-03 — Defer.**

### Rationale

Ratifying R-023 now could create the appearance that the validation-authority question has already been settled. The requirement itself is sound, but its authoritative activation depends materially on U-004.

### Required authority

Authority capable of ratifying the requirement while preserving U-004, or authority capable of resolving U-004 where resolution is required.

### Traceability

Candidate baseline R-023 → detailed specification R-023 → U-004 dependency → Pass 3 review → D-03 proposed.

---

## 6. R-024 — Conditional Operation

### Candidate / specified meaning

R-024 requires operations to proceed only when required conditions and dependencies are satisfied, or when explicit conditional operation is permitted.

### Evidence

The requirement clearly identifies:

- operation;
- conditions;
- dependencies;
- satisfaction state;
- consequence;
- permitted/blocked/deferred/conditional disposition.

It directly implements Conditional Operation without specifying implementation architecture.

### Dependencies

- R-015 Authority Determination;
- R-017 Dependency Integrity;
- R-010 Controlled State Modification;
- C-04 Condition;
- C-06 Dependency;
- C-07 Operation.

### Unresolved matters

Authority precedence may affect particular permission conflicts. The requirement does not itself invent a precedence rule; it relies on applicable authority determination.

### Defect status

**No material defect identified.**

### Proposed disposition

**D-01 — Ratify as Written.**

### Rationale

The requirement is a control condition rather than a hidden resolution of authority precedence. Its application remains subject to the authority rules established elsewhere.

### Required authority

Formal ratification authority.

### Traceability

Candidate baseline R-024 → detailed specification R-024 → Pass 3 review → D-01 proposed.

---

## 7. R-025 — Operation-State Integrity

### Candidate / specified meaning

R-025 requires execution state to remain distinct from the controlled state an operation is intended to affect.

### Evidence

The specification explicitly separates proposed, authorized, ready, executing, completed, failed, interrupted, and cancelled operation states from the resulting controlled state.

This preserves the important distinction:

**Execution activity ≠ successful controlled-state transition.**

### Dependencies

- R-021 Controlled Change;
- R-026 Outcome Integrity;
- R-028 Failure and Recovery Governance;
- C-07 Operation;
- C-02 State.

### Unresolved matters

No unresolved governance question materially undermines the requirement itself.

### Defect status

**No material defect identified.**

### Proposed disposition

**D-01 — Ratify as Written.**

### Rationale

The requirement prevents one of the most important control failures in the model: confusing an attempted or completed operation with the state it was intended to produce.

### Required authority

Formal ratification authority.

### Traceability

Candidate baseline R-025 → detailed specification R-025 → Pass 3 review → D-01 proposed.

---

## 8. R-026 — Outcome Integrity

### Candidate / specified meaning

R-026 requires actual outcomes to remain distinct from operations, expectations, interpretations, and resulting controlled state.

### Evidence

The specification requires the actual occurrence, expectation status, affected state, and further validation/determination needs to remain identifiable.

This is consistent with C-11 Outcome and prevents intended results from being substituted for observed results.

### Dependencies

- R-025 Operation-State Integrity;
- R-023 Validation Integrity where validation is required;
- R-027 Controlled Indeterminacy;
- C-11 Outcome;
- C-08 Determination.

### Unresolved matters

No unresolved matter creates a material defect in the requirement itself.

### Defect status

**No material defect identified.**

### Proposed disposition

**D-01 — Ratify as Written.**

### Rationale

The requirement establishes a necessary semantic/control distinction without prematurely deciding how every outcome must be validated or interpreted.

### Required authority

Formal ratification authority.

### Traceability

Candidate baseline R-026 → detailed specification R-026 → Pass 3 review → D-01 proposed.

---

## 9. R-027 — Controlled Indeterminacy

### Candidate / specified meaning

R-027 requires material matters to remain indeterminate where available evidence is insufficient, rather than being silently converted into certainty.

### Evidence

The requirement identifies what is indeterminate, missing/conflicting evidence, dependencies, conditional continuation, and possible resolution evidence.

This directly supports R-006 Controlled Incompleteness, R-007 Explicit Uncertainty, and C-02 State/C-08 Determination/C-09 Validation.

### Dependencies

- R-006 Controlled Incompleteness;
- R-007 Explicit Uncertainty;
- R-018 Controlled Conflict Handling;
- R-023 Validation Integrity;
- C-02 State;
- C-08 Determination;
- C-09 Validation.

### Unresolved matters

Some particular indeterminate matters may depend on unresolved authority or validation rules, but that does not invalidate the requirement to represent indeterminacy.

### Defect status

**No material defect identified.**

### Proposed disposition

**D-01 — Ratify as Written.**

### Rationale

The requirement prevents forced certainty and does not require an indeterminate matter to be resolved merely because the project wants to proceed.

### Required authority

Formal ratification authority.

### Traceability

Candidate baseline R-027 → detailed specification R-027 → Pass 3 review → D-01 proposed.

---

## 10. R-028 — Failure and Recovery Governance

### Candidate / specified meaning

R-028 requires material failures to preserve prior controlled state, record effects, distinguish partial effects, prevent unverified success claims, and govern recovery/rollback/containment/reattempt.

### Evidence

The specification establishes a coherent failure sequence and explicitly subjects recovery to authority, conditions, dependencies, and validation.

This aligns with Operation, State, Change, Outcome, Validation, and Controlled Incorporation.

### Dependencies

- R-021 Controlled Change;
- R-023 Validation Integrity;
- R-025 Operation-State Integrity;
- R-026 Outcome Integrity;
- R-029 Exception Governance where recovery requires exceptional handling;
- R-030 Closure Integrity where failed matters reach closure;
- C-07 Operation;
- C-10 Change;
- C-11 Outcome;
- C-14 Controlled Incorporation.

### Unresolved matters

Specific recovery actions may encounter unresolved authority or exception questions. The requirement explicitly defers those matters to applicable governance rather than inventing a bypass.

### Defect status

**No material defect identified.**

### Proposed disposition

**D-01 — Ratify as Written.**

### Rationale

The requirement is necessary to prevent failure from corrupting controlled state. Its explicit subordination to authority, conditions, dependencies, and validation prevents it from silently resolving those matters.

### Required authority

Formal ratification authority.

### Traceability

Candidate baseline R-028 → detailed specification R-028 → Pass 3 review → D-01 proposed.

---

## 11. R-029 — Exception Governance

### Candidate / specified meaning

R-029 requires exceptional handling to remain distinguishable from ordinary operation and prevents exceptions from becoming uncontrolled bypasses of governing requirements.

### Evidence

The specification identifies the ordinary rule/condition, exceptional circumstance, authority, scope/duration, safeguards, resulting state, and validation/review requirements.

### Dependencies

- R-015 Authority Determination;
- R-018 Controlled Conflict Handling;
- R-021 Controlled Change;
- R-023 Validation Integrity;
- C-03 Authority;
- C-04 Condition;
- C-14 Controlled Incorporation;
- **U-009 Exception Authority**.

### Unresolved matters

**U-009 — Exception Authority** remains unresolved. The requirement correctly says an exception requires authority, but the project has not yet finally established the governance semantics for who/what may authorize exceptional handling.

### Defect status

**Governance dependency; not a specification defect.**

### Proposed disposition

**D-03 — Defer.**

### Rationale

Ratifying R-029 without resolving or explicitly governing U-009 would risk giving the requirement an apparently complete authority path when the authority itself remains open.

### Required authority

Authority capable of ratifying the requirement with the U-009 dependency explicitly preserved, or authority capable of resolving U-009.

### Traceability

Candidate baseline R-029 → detailed specification R-029 → U-009 dependency → Pass 3 review → D-03 proposed.

---

## 12. R-030 — Closure Integrity

### Candidate / specified meaning

R-030 requires closure to remain distinct from completion, success, validation, approval, and termination. Closure must have an identifiable condition/basis and preserve unresolved material and future reopen/continuation semantics.

### Evidence

The detailed specification explicitly prevents closure from being inferred from inactivity, deadline passage, or end of immediate work.

It requires closure condition, state, outstanding unresolved material, authority, and reopen/continue effect to be identifiable.

### Dependencies

- R-023 Validation Integrity;
- R-027 Controlled Indeterminacy;
- R-028 Failure and Recovery Governance;
- R-030 itself interfaces with continuity and termination governance;
- C-12 Closure;
- **U-010 Closure Semantics**;
- U-012 Termination Governance where closure approaches project/matter termination.

### Unresolved matters

**U-010 — Closure Semantics** remains explicitly unresolved.

**U-012 — Termination Governance** may become relevant where closure would have termination consequences, but closure and termination are intentionally distinguished.

### Defect status

**Governance dependency; not a specification defect.**

### Proposed disposition

**D-03 — Defer.**

### Rationale

Closure is a foundational control boundary, but its final semantics cannot be treated as ratified while the project has explicitly retained U-010 as unresolved. The requirement should therefore remain intact while its authoritative disposition is deferred.

### Required authority

Authority capable of resolving or formally preserving U-010, and where applicable U-012.

### Traceability

Candidate baseline R-030 → detailed specification R-030 → U-010/U-012 dependency → Pass 3 review → D-03 proposed.

---

## 13. Cross-Requirement Findings

### 13.1 No new foundational concept identified

R-021–R-030 remain expressible through the existing 14-concept control model.

No missing foundational concept was demonstrated.

### 13.2 Unresolved matters remain bounded

The review does not resolve:

- U-004 Validation Authority;
- U-009 Exception Authority;
- U-010 Closure Semantics;
- U-012 Termination Governance;
- any broader authority-precedence matter.

These remain explicit dependencies.

### 13.3 Important distinction preserved

The following distinctions remain intact:

- change ≠ proposal to change;
- history ≠ current state;
- validation ≠ determination;
- operation ≠ resulting state;
- outcome ≠ intended result;
- indeterminacy ≠ failure;
- failure ≠ closure;
- exception ≠ ordinary operation;
- closure ≠ completion;
- closure ≠ termination.

### 13.4 No implementation decision introduced

No architecture, storage mechanism, database structure, programming language, AI provider, algorithm, or implementation procedure is ratified or required by this pass.

---

## 14. Pass 3 Determination

**PASS — R-021–R-030 have received bounded provisional review.**

Provisional dispositions:

- **D-01:** R-021, R-022, R-024, R-025, R-026, R-027, R-028
- **D-03:** R-023, R-029, R-030

No requirement is ratified by this pass.

The three deferred requirements are deferred because of explicit unresolved governance dependencies, not because a material specification defect was identified.

### Next governed work unit

**Pass 4 — R-031–R-042: Traceability, Evolution, Human–AI Process, and Continuity/Recovery.**

### Stop condition

Pass 3 is closed. Further local analysis of R-021–R-030 is not justified unless a material defect, contradiction, dependency failure, or authority issue is later demonstrated.

