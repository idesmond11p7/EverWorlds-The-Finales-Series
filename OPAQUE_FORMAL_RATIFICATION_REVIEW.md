# OPAQUE — Formal Ratification Review

## Status

**Provisional review framework.** This document governs the review process for the candidate OPAQUE specification. It does not ratify any requirement, invariant, or unresolved governance rule.

## 1. Review Objective

Determine, in a controlled and traceable manner, the disposition of:

- R-001–R-047 candidate requirements;
- I-001 Distinction Preservation;
- U-001–U-012 unresolved specification matters.

The review shall determine whether each item is sufficiently established for formal acceptance, requires controlled amendment or revision, must remain deferred, or should be rejected.

Passing Stage V-E establishes readiness for this review. It does not establish ratification.

## 2. Review Inputs

Primary inputs:

1. OPAQUE_REQUIREMENT_BASELINE.md
2. OPAQUE_DETAILED_SPECIFICATION.md
3. OPAQUE_SPECIFICATION.md
4. OPAQUE_CORE_CONTROL_MODEL.md
5. OPAQUE_RATIFICATION_READINESS.md
6. OPAQUE_UNRESOLVED_MATTERS_VERIFICATION.md
7. OPAQUE_SPECIFICATION_COVERAGE_VERIFICATION.md
8. OPAQUE_SPECIFICATION_CONSISTENCY_VERIFICATION.md
9. OPAQUE_CONTROL_MODEL_CONSISTENCY_VERIFICATION.md

Supporting inputs may be consulted only where required to resolve a traceability or evidence question.

## 3. Ratification Review Principles

The review shall preserve:

- distinction between candidate and ratified state;
- distinction between requirement and implementation;
- distinction between reasoning and authority;
- distinction between unresolved matter and established rule;
- distinction between evidence and interpretation;
- distinction between amendment and silent reinterpretation;
- backward and forward traceability.

No item becomes ratified merely because:

- it is present in the specification;
- it passed verification;
- it appears logically coherent;
- the AI recommends it;
- the user says “next”;
- implementation appears to depend upon it.

## 4. Controlled Dispositions

Each reviewed item shall receive one provisional disposition:

### D-01 — Ratify as Written
The current wording is sufficiently established and requires no material amendment.

### D-02 — Ratify with Amendment
The underlying requirement is accepted, but a specific wording change is required to remove a material ambiguity or defect. The amendment itself must be recorded and authorized.

### D-03 — Defer
The item remains valid as a candidate but cannot yet be ratified because a legitimate unresolved dependency, authority question, or required determination remains open.

### D-04 — Reject
The item is determined not to belong in the ratified OPAQUE specification, with rationale and traceability recorded.

### D-05 — Return for Controlled Revision
A material defect prevents ratification and requires a bounded revision pass. The revision target and completion condition must be explicit.

No other disposition may be invented casually. If another disposition is genuinely required, it must be explicitly defined before use.

## 5. Evidence Standard

A ratification determination shall identify, as applicable:

- the candidate source;
- the detailed specification treatment;
- relevant control-model concepts;
- dependencies;
- unresolved matters;
- verification evidence;
- identified defects or absence of defects;
- authority required for the determination.

Evidence supports a determination; evidence does not itself confer authority.

## 6. Unresolved Matters

U-001–U-012 remain separately governed review objects:

- U-001 Universal Authority Precedence
- U-002 Supersession and Replacement
- U-003 Authority Escalation
- U-004 Validation Authority
- U-005 Controlled Propagation
- U-006 Requirement Granularity
- U-007 Interaction-State Representation
- U-008 Quantification Boundary
- U-009 Exception Authority
- U-010 Closure Semantics
- U-011 OPAQUE/Scheme Operational Interface
- U-012 Termination Governance

An unresolved matter shall not be silently converted into a ratified rule.

Where a requirement depends materially upon an unresolved matter, the requirement may be deferred or otherwise dispositioned only with that dependency explicitly recorded.

An unresolved matter may be resolved during ratification review only through an explicitly authorized determination. If such authority is unavailable or unclear, the matter remains unresolved.

## 7. Candidate Invariant

I-001 Distinction Preservation shall be reviewed separately from ordinary requirements.

The review shall determine:

- whether the invariant is sufficiently defined;
- whether its scope is identifiable;
- whether its exceptions are governed;
- whether it conflicts with any candidate requirement;
- whether it is suitable for ratification as a cross-cutting invariant.

The invariant shall not be treated as ratified merely because it is used consistently throughout the specification.

## 8. Review Matrix

Each item shall be recorded using the following fields:

| Field | Required content |
|---|---|
| Item ID | R-001–R-047 or I-001 |
| Candidate Statement | Current baseline statement |
| Specification Reference | Relevant detailed specification treatment |
| Evidence | Verification and supporting evidence |
| Dependencies | Material dependencies |
| Unresolved Matters | Relevant U-001–U-012 |
| Defect Status | None identified / identified / indeterminate |
| Proposed Disposition | D-01 through D-05 |
| Required Authority | Authority required to finalize disposition |
| Rationale | Concise basis for proposed disposition |
| Resulting Version/State | Result if authorized |
| Traceability | Source → review → disposition → resulting state |

All entries remain **provisional** until authorized.

## 9. Bounded Review Sequence

### Pass 1 — Constitutional Requirements
Review R-001–R-011.

Completion condition: every constitutional requirement has a recorded provisional disposition and every material dependency is identified.

### Pass 2 — Information and Semantic Integrity
Review R-012–R-020.

Completion condition: identification, classification, state, authority, relationship, dependency, conflict, semantic fidelity, and incorporation requirements have dispositions with traceability.

### Pass 3 — Change, Validation, and Operation
Review R-021–R-030.

Completion condition: change, history, validation, conditional operation, outcomes, indeterminacy, failure, exception, and closure requirements have dispositions with unresolved dependencies identified.

### Pass 4 — Traceability, Evolution, and Human–AI Process
Review R-031–R-042.

Completion condition: traceability, feedback, evolution, impact, metacognitive, process, interaction, complexity, momentum, convergence, milestone, and recovery requirements have dispositions.

### Pass 5 — Scheme and Execution Boundary
Review R-043–R-047.

Completion condition: Scheme integrity, work-unit governance, temporal integrity, feasibility, and governance/execution boundary requirements have dispositions.

### Pass 6 — Cross-Cutting Invariant
Review I-001.

Completion condition: invariant scope, interaction with requirements, and required authority are explicitly determined.

### Pass 7 — Unresolved Governance Matters
Review U-001–U-012.

Completion condition: each matter is either explicitly resolved by appropriate authority or explicitly deferred/retained as unresolved with its downstream dependencies recorded.

### Pass 8 — Final Consistency and Traceability Check
Check all provisional dispositions against one another.

Completion condition: no disposition creates an unrecorded contradiction, authority violation, broken dependency, orphaned requirement, or loss of traceability.

## 10. Authority Control

The review process may analyze, compare, identify defects, and propose dispositions.

It may not silently:

- ratify a candidate requirement;
- establish authority precedence;
- create validation authority;
- resolve an unresolved governance question;
- replace a legitimate human decision;
- rewrite the project state;
- convert a proposal into an authoritative rule.

Where authority is unclear, the item is not automatically accepted. It enters controlled deferral/escalation.

## 11. Stop Conditions

The review shall stop a branch when:

- the item has sufficient evidence for its current disposition;
- further analysis produces no materially different information;
- the remaining issue belongs to an explicitly unresolved matter;
- the required authority is absent;
- a material defect requires controlled revision rather than continued analysis;
- continuing would reopen a closed requirement family without demonstrated defect.

This prevents formal review from becoming another open-ended specification loop.

## 12. Completion Condition for Formal Ratification Review

Formal Ratification Review is complete only when:

1. R-001–R-047 each have an explicit recorded disposition;
2. I-001 has an explicit recorded disposition;
3. U-001–U-012 each have an explicit controlled state;
4. every material deferral has its dependency and reason recorded;
5. every proposed amendment has a traceable change record;
6. no material authority ambiguity is silently bypassed;
7. cross-item consistency has been checked;
8. resulting ratified-state changes, if any, are explicitly authorized;
9. all non-ratified items remain distinguishable from ratified state;
10. the final ratification record identifies what was accepted, amended, deferred, rejected, or returned for revision.

## 13. Current Determination

**Formal Ratification Review framework established.**

This is a process milestone, not ratification.

The next work unit is the controlled review of R-001–R-011 against the established evidence and unresolved matters, beginning with the constitutional layer.

