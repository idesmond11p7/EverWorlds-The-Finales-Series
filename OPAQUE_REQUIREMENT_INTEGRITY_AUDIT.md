# OPAQUE — Requirement Integrity Audit

## Status

**Stage V-A — Requirement Integrity: Complete (working determination).**

This document audits the Stage IV candidate requirement baseline for structural integrity before formal specification. It does not ratify, delete, or silently rewrite requirements.

## 1. Audit Objective

Determine whether the candidate baseline is sufficiently coherent to serve as the input to formal specification, and identify only defects that materially obstruct that work.

The audit does **not** reopen the completed conceptual exploration merely because a requirement can be made more detailed.

## 2. Audit Criteria

Each candidate requirement was examined against:

1. distinctness from neighboring requirements;
2. requirement-versus-principle/capability distinction;
3. semantic clarity;
4. identifiable scope;
5. observable/specifiable behavior;
6. authority implications;
7. dependency direction;
8. overlap or redundancy;
9. unresolved ambiguity;
10. feasibility of later validation.

## 3. Determinations

### 3.1 The baseline is structurally usable

The 47 requirements form a coherent candidate coverage set. No missing requirement family has been demonstrated that would justify reopening Stage IV.

The baseline can therefore proceed into formal specification.

### 3.2 Several requirements require specification refinement

This is expected and is not evidence that the baseline is defective.

The principal refinement areas are:

- **R-001 / R-004:** distinguish OPAQUE's purpose from the mechanisms by which project-state integrity is maintained.
- **R-005 / R-014:** formally separate epistemic classification from multi-dimensional state representation.
- **R-008 / R-009 / R-015:** establish the authority model and precedence rules before attempting detailed authority behavior.
- **R-016 / R-017:** define when a relationship becomes a dependency for governance purposes.
- **R-018:** define operational distinctions among difference, contradiction, conflict, error, uncertainty, and unresolved disagreement.
- **R-019 / R-020:** distinguish preservation of meaning during transformation from the governed transition into controlled state.
- **R-021 / R-025 / R-026:** separate change state, operation state, and outcome state.
- **R-023:** define validation scope and validation authority.
- **R-027 / R-030:** define indeterminacy and closure states without collapsing them into one lifecycle status.
- **R-031 / R-034:** define the minimum material traceability and impact scope required.
- **R-035–R-040:** define process/interactions as governed signals and states without turning every human condition into formal project state.
- **R-041 / R-042:** distinguish milestone/completion control from interruption/recovery.
- **R-043–R-047:** establish the exact OPAQUE/Scheme/execution interface and feasibility boundary.

These are **specification questions**, not new requirements.

## 4. Overlap Findings

Some candidate requirements are closely related but should not be merged automatically.

| Cluster | Reason for preserving distinction |
|---|---|
| R-011 / R-042 | Continuity is a governing property; interruption/recovery is a specific operational condition. |
| R-012 / R-013 / R-014 | Identification, classification, and state representation answer different questions. |
| R-021 / R-025 / R-026 | Change, operation, and outcome have different lifecycle meanings. |
| R-031 / R-034 | Traceability records relationships; impact evaluation determines consequences of proposed change. |
| R-035 / R-036 / R-040 | Audit, process correction, and convergence are related controls but have different purposes. |
| R-041 / R-044 | Milestones govern completion at a higher level; work-unit governance governs individual work units. |

The correct action is to specify the boundaries, not to reduce the count for cosmetic simplicity.

## 5. Requirements That Need Special Caution

### R-039 — Interest-Drop / Momentum Compensation

This requirement must not become a requirement for psychological inference.

The specification should distinguish:

**observable execution signals → hypothesis about cause → permitted procedural response**

rather than:

**observed behavior → assumed internal state → intervention**

Human autonomy remains controlling.

### R-008–R-010 — AI Authority

These requirements should be specified together because the distinction between reasoning agency, human authority, and controlled state modification is constitutional.

The specification must prevent a subtle failure in which the AI is technically permitted to reason independently but its inferred conclusions are nevertheless treated as authoritative merely because the system presents them confidently.

### R-012–R-020 — Information Integrity

These requirements should establish a stable semantic model before detailed workflow rules are written.

Otherwise, later controls may depend on undefined categories.

### R-040 — Convergence Control

Convergence should control unnecessary continuation, not suppress legitimate discovery.

The specification therefore needs a sufficiency criterion rather than a simplistic time or step limit.

## 6. Candidate Invariant Assessment

**I-001 — Distinction Preservation** remains a useful cross-cutting candidate invariant.

It should not be treated as an excuse to preserve every distinction.

Its specification must establish a materiality boundary:

> preserve a distinction when collapsing it could change meaning, authority, state, condition, relationship, consequence, validation, or permitted action relevant to the governed purpose.

This is still a candidate formulation and requires formal specification.

## 7. Non-Requirement Boundary

The Stage IV exclusion of architecture, database design, programming language, AI provider, exact algorithms, and implementation mechanics remains appropriate.

No technical implementation decision is required to close this integrity audit.

## 8. Audit Conclusion

The candidate baseline is **sufficiently coherent to proceed**.

No requirement family is added.

No requirement is deleted.

No requirement is silently ratified.

The principal work remaining is formal semantic specification and dependency resolution.

## 9. Next Milestone

**Stage V-B — Core Control Model**

Objective:

Define the minimum control model required for the candidate requirements to operate coherently.

The model should establish, at minimum:

- governed object;
- controlled state;
- authority;
- condition;
- dependency;
- relationship;
- operation;
- determination;
- validation;
- change;
- outcome;
- closure;
- provenance;
- controlled incorporation.

Completion condition:

A finite conceptual control model exists such that the candidate requirements can be mapped to it without introducing a new uncontrolled conceptual layer.

