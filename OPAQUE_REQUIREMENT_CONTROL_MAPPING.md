# OPAQUE — Stage V-C Requirement-to-Control Mapping

## Status

**Working determination — Stage V-C.**

This mapping tests whether the 14-concept core control model can account for all 47 candidate requirements. It is not ratification.

## Control Legend

- C-01 Governed Object
- C-02 State
- C-03 Authority
- C-04 Condition
- C-05 Relationship
- C-06 Dependency
- C-07 Operation
- C-08 Determination
- C-09 Validation
- C-10 Change
- C-11 Outcome
- C-12 Closure
- C-13 Provenance
- C-14 Controlled Incorporation
- I-001 Distinction Preservation

## Mapping

| Requirement | Primary | Supporting | Main dependency / note |
|---|---|---|---|
| R-001 OPAQUE Purpose | C-01 | C-02, C-12, I-001 | Defines what OPAQUE governs and its disposition boundary |
| R-002 OPAQUE Boundary | C-01 | C-03, C-05, C-14, I-001 | Requires distinct governed domains and authority |
| R-003 Scheme Boundary | C-01 | C-05, C-06, C-03, I-001 | OPAQUE/Scheme relationship and dependency must remain distinct |
| R-004 Project-State Integrity | C-02 | C-01, C-14, C-13, I-001 | Controlled state cannot be silently redefined |
| R-005 Epistemic Integrity | C-02 | C-08, C-09, C-13, I-001 | Epistemic dimensions require state distinctions |
| R-006 Controlled Incompleteness | C-02 | C-04, C-06, C-08, C-12 | Unknowns become controlled state rather than hidden certainty |
| R-007 Explicit Uncertainty | C-02 | C-08, C-09, C-13, I-001 | Uncertainty is a relevant state distinction |
| R-008 AI Authority Boundary | C-03 | C-08, C-14, I-001 | Reasoning output must remain distinct from authority |
| R-009 Human Decision Authority | C-03 | C-08, C-10, C-14 | Authority governs standing of decisions and state changes |
| R-010 Controlled State Modification | C-14 | C-03, C-04, C-07, C-10, C-02, I-001 | Incorporation is the boundary before authoritative state changes |
| R-011 Continuity | C-12 | C-02, C-13, C-07, C-10 | Resume requires preserved state/history |
| R-012 Identification | C-01 | C-02, C-13, C-05, C-06 | Object identity is the foundation |
| R-013 Classification | C-02 | C-01, C-08, C-13, I-001 | Classification affects treatment and state |
| R-014 State-Dimension Integrity | C-02 | I-001, C-12, C-03, C-09 | Explicitly protects separate state dimensions |
| R-015 Authority Determination | C-03 | C-01, C-04, C-05, C-13 | Authority is scoped to governed matter |
| R-016 Relationship Integrity | C-05 | C-01, C-06, I-001 | Preserves association without falsely creating dependency |
| R-017 Dependency Integrity | C-06 | C-05, C-04, C-02, C-10 | Dependencies drive eligibility, propagation, and impact |
| R-018 Controlled Conflict Handling | C-08 | C-02, C-03, C-05, C-13, I-001 | Difference/contradiction/conflict must not collapse |
| R-019 Semantic Containment and Fidelity | C-13 | C-01, C-02, C-05, C-08, C-14, I-001 | Meaning survives interpretation and transformation |
| R-020 Controlled Incorporation | C-14 | C-03, C-04, C-06, C-08, C-09, C-13 | Governs acquisition of controlled standing |
| R-021 Controlled Change | C-10 | C-03, C-04, C-07, C-11, C-09, C-13 | Change lifecycle requires controlled transition |
| R-022 Change History | C-13 | C-10, C-02, C-14 | History is provenance of material change |
| R-023 Validation Integrity | C-09 | C-03, C-04, C-08, C-13 | Validation requires criteria, scope, and authority |
| R-024 Conditional Operation | C-04 | C-03, C-06, C-07, C-02 | Operation eligibility depends on conditions/dependencies |
| R-025 Operation-State Integrity | C-07 | C-02, C-03, C-04, C-10, C-12 | Separates possible/eligible/authorized/executed states |
| R-026 Outcome Integrity | C-11 | C-07, C-10, C-02, C-08, I-001 | Separates execution, result, determination, consequence |
| R-027 Controlled Indeterminacy | C-02 | C-08, C-09, C-12, I-001 | Unresolved determination is controlled rather than forced |
| R-028 Failure and Recovery Governance | C-11 | C-02, C-07, C-10, C-12, C-13 | Failure is an outcome with resulting state/history |
| R-029 Exception Governance | C-04 | C-03, C-07, C-02, C-12 | Exceptions are conditional deviations with authority |
| R-030 Closure Integrity | C-12 | C-02, C-10, C-11, C-13, I-001 | Closure states have distinct consequences |
| R-031 Traceability | C-13 | C-01, C-05, C-06, C-08, C-10, C-11, C-14 | Provenance connects transformations |
| R-032 Feedback Incorporation | C-14 | C-11, C-08, C-10, C-02, C-13 | Feedback becomes controlled only through incorporation |
| R-033 Controlled Evolution | C-10 | C-03, C-14, C-13, C-12 | Change between governance layers must remain distinct |
| R-034 Impact Evaluation | C-10 | C-06, C-03, C-09, C-02, C-13 | Change assessment depends on relationships/dependencies |
| R-035 Metacognitive Audit | C-08 | C-02, C-10, C-11, C-13, I-001 | Audit produces determinations about current/project/process state |
| R-036 Process Self-Correction | C-10 | C-08, C-07, C-03, C-12 | Process defect becomes controlled change, not automatic rule change |
| R-037 Interaction Control | C-04 | C-02, C-03, C-07, C-08, I-001 | Interaction conditions affect permitted procedure without inventing psychology |
| R-038 User-Facing Complexity Control | C-04 | C-08, C-13, I-001 | Controls presentation conditions without changing internal state |
| R-039 Interest-Drop / Momentum Compensation | C-04 | C-02, C-07, C-08, C-12, I-001 | Observable signals guide procedural adaptation; cause remains uncertain |
| R-040 Convergence Control | C-12 | C-04, C-08, C-10, C-01 | Closure condition prevents unnecessary continued exploration |
| R-041 Milestone and Completion Control | C-12 | C-01, C-02, C-04, C-07, C-10, C-13 | Completion conditions and next milestone require controlled disposition |
| R-042 Interruption and Recovery | C-12 | C-02, C-13, C-10, C-07 | Resume depends on preserved state/history |
| R-043 Scheme Integrity | C-01 | C-02, C-05, C-06, C-10, C-12, I-001 | Scheme remains a distinct governed domain |
| R-044 Work-Unit Governance | C-01 | C-02, C-03, C-04, C-06, C-07, C-12 | Work units are governed objects with state/conditions/dependencies |
| R-045 Temporal Integrity | C-02 | C-04, C-06, C-07, C-10, C-13, I-001 | Time is represented as a relevant state/condition/dependency dimension |
| R-046 Execution Feasibility | C-04 | C-06, C-07, C-02, C-03, C-10 | Feasibility is conditional on resources, dependencies, technology, time, complexity |
| R-047 Governance/Execution Boundary | C-03 | C-07, C-02, C-10, C-11, C-14, I-001 | Governance standing must remain distinct from execution |

## Findings

### 1. Coverage

All 47 candidate requirements have a placement in the 14-concept model.

No requirement currently demonstrates the necessity of a fifteenth core concept.

### 2. Strongest cross-cutting concept

**I-001 Distinction Preservation** is not a substitute for the core model. It protects the relationships between the concepts and prevents their accidental collapse.

### 3. Most important control cluster

The most tightly coupled concepts are:

**C-03 Authority + C-04 Condition + C-09 Validation + C-10 Change + C-14 Controlled Incorporation + C-02 State**

This cluster governs the critical question:

> Can this material legitimately change controlled state?

### 4. Secondary control cluster

**C-01 Object + C-02 State + C-05 Relationship + C-06 Dependency**

This cluster answers:

> What is this, what condition is it in, and what does it depend on?

### 5. Execution cluster

**C-07 Operation + C-10 Change + C-11 Outcome + C-12 Closure**

This cluster answers:

> What was attempted, what changed, what resulted, and where does the matter stand now?

### 6. Evidence cluster

**C-08 Determination + C-09 Validation + C-13 Provenance**

This cluster answers:

> What do we conclude, how was it established, and where did the supporting material come from?

## Specification Gaps Remaining

The mapping exposes no core-model defect.

The remaining work is refinement of rules, especially:

- exact authority precedence;
- exact validation authority;
- exact state-transition conditions;
- supersession/replacement;
- propagation;
- closure semantics;
- OPAQUE/Scheme interface;
- termination governance.

These are downstream specification matters, not reasons to expand the core model.

## Stage V-C Completion Condition

Stage V-C can be considered complete when this mapping is accepted as the working placement of all candidate requirements and the remaining matters are explicitly carried into detailed requirement specification.

## Determination

**Working determination: the 14-concept control model is sufficient to represent the current candidate requirement baseline.**

The project should now stop expanding the foundational ontology and move into detailed requirement specification.
