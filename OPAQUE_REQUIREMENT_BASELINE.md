# OPAQUE — Candidate Requirement Baseline

## Status

**Candidate baseline — Stage IV consolidation output.**

This document consolidates the OPAQUE requirement material developed during the specification process. It is a working baseline, not a ratified specification and not an implementation plan.

No item in this document becomes authoritative merely because it appears here. Ratification, authority, versioning, and controlled change remain part of OPAQUE's governance problem.

## 1. Purpose of the Baseline

The purpose of this baseline is to establish a finite, coherent set of candidate requirements from the previously examined OPAQUE material without reopening completed conceptual branches.

The baseline deliberately separates:

- requirements;
- cross-cutting invariants;
- constraints;
- capabilities;
- unresolved questions;
- implementation decisions.

## 2. Candidate Requirements

### A. Constitutional Requirements

**R-001 — OPAQUE Purpose**  
OPAQUE shall provide meta-level control that helps keep EverWorlds governable and executable under complexity, incompleteness, uncertainty, change, disruption, and human–AI interaction problems.

**R-002 — OPAQUE Boundary**  
OPAQUE shall remain distinct from the substantive EverWorlds product, the Scheme of Work, individual work execution, and legitimate human project authority.

**R-003 — Scheme Boundary**  
OPAQUE shall govern the conditions and integrity of the Scheme of Work without silently becoming the Scheme of Work itself.

**R-004 — Project-State Integrity**  
OPAQUE shall preserve the integrity of controlled project state and shall not allow uncontrolled information, interpretation, or activity to redefine it.

**R-005 — Epistemic Integrity**  
OPAQUE shall preserve distinctions between what is known, observed, inferred, proposed, assumed, questioned, unresolved, validated, rejected, and otherwise epistemically relevant.

**R-006 — Controlled Incompleteness**  
OPAQUE shall permit project and specification work to proceed under incomplete knowledge while making materially relevant unknowns, dependencies, and unresolved conditions explicit and controlled.

**R-007 — Explicit Uncertainty**  
OPAQUE shall represent materially relevant uncertainty rather than silently converting uncertainty into certainty.

**R-008 — AI Authority Boundary**  
OPAQUE shall distinguish AI reasoning agency from AI project authority.

**R-009 — Human Decision Authority**  
OPAQUE shall preserve legitimate human authority over project decisions and shall not silently replace or override it.

**R-010 — Controlled State Modification**  
OPAQUE shall prevent AI reasoning, conversational momentum, inference, preference, or temporary interaction state from silently modifying authoritative project state.

**R-011 — Continuity**  
OPAQUE shall preserve project continuity across interruption, temporary loss of momentum, changes in interaction state, and other ordinary execution disruptions.

### B. Information and Semantic Integrity

**R-012 — Identification**  
OPAQUE shall provide sufficient identification of governed information and governed objects to determine their relevant meaning, scope, status, provenance, relationships, and applicability.

**R-013 — Classification**  
OPAQUE shall support controlled classification of information according to the distinctions required for its governance and use.

**R-014 — State-Dimension Integrity**  
OPAQUE shall distinguish materially different state dimensions rather than collapsing epistemic, governance, authority, lifecycle, execution, or other states into an ambiguous single state.

**R-015 — Authority Determination**  
OPAQUE shall identify the applicable authority of governed information and shall not assume universal precedence where such precedence has not been established.

**R-016 — Relationship Integrity**  
OPAQUE shall preserve materially relevant relationships between governed objects and shall distinguish general relationships from dependencies where that distinction matters.

**R-017 — Dependency Integrity**  
OPAQUE shall identify and preserve materially relevant dependencies, including dependency conditions and potential propagation effects.

**R-018 — Controlled Conflict Handling**  
OPAQUE shall distinguish difference, contradiction, conflict, error, uncertainty, and unresolved disagreement where materially relevant, and shall not silently merge or erase conflicting information.

**R-019 — Semantic Containment and Fidelity**  
OPAQUE shall preserve materially relevant meaning, context, conditions, scope, uncertainty, authority, and relationships when information is interpreted, transformed, transmitted, or incorporated.

**R-020 — Controlled Incorporation**  
OPAQUE shall govern the transition by which relevant information from conversation, research, execution, AI reasoning, or other permitted sources becomes controlled project state.

### C. Change, Validation, and Operation

**R-021 — Controlled Change**  
OPAQUE shall distinguish proposed, authorized, executed, observed, validated, and recorded change states.

**R-022 — Change History**  
OPAQUE shall preserve sufficient history and traceability for material changes to governed state.

**R-023 — Validation Integrity**  
OPAQUE shall define and preserve the conditions by which a determination can be evaluated and accepted as validated for its intended scope.

**R-024 — Conditional Operation**  
OPAQUE shall permit operations only when their applicable conditions, prerequisites, dependencies, authority, and permissions are satisfied.

**R-025 — Operation-State Integrity**  
OPAQUE shall distinguish an operation being possible, eligible, permitted, authorized, executable, attempted, completed, failed, or otherwise materially different in status.

**R-026 — Outcome Integrity**  
OPAQUE shall distinguish execution, observed result, determined outcome, and downstream consequence where those distinctions materially affect governance.

**R-027 — Controlled Indeterminacy**  
OPAQUE shall provide a controlled state for cases in which a determination cannot yet be established sufficiently for the intended purpose.

**R-028 — Failure and Recovery Governance**  
OPAQUE shall preserve the identity, cause/status where known, impact, containment, recovery, and resulting state of material failures.

**R-029 — Exception Governance**  
OPAQUE shall distinguish governed exceptions from ordinary operation and shall define the conditions under which an exception may be introduced, maintained, resolved, or rejected.

**R-030 — Closure Integrity**  
OPAQUE shall distinguish completed, paused, deferred, blocked, abandoned, superseded, invalidated, and otherwise materially different closure states.

### D. Traceability and Evolution

**R-031 — Traceability**  
OPAQUE shall support forward and backward traceability across relevant transformations such as source material, interpretation, requirement, design, implementation, test, result, and subsequent governance state.

**R-032 — Feedback Incorporation**  
OPAQUE shall incorporate relevant observations and execution outcomes into subsequent governance evaluation where they may affect project state, requirements, dependencies, validation, continuity, or process integrity.

**R-033 — Controlled Evolution**  
OPAQUE shall support controlled evolution of project governance without conflating changes to EverWorlds, the Scheme of Work, OPAQUE requirements, OPAQUE specification, and OPAQUE implementation.

**R-034 — Impact Evaluation**  
Material proposed changes shall be evaluated for effects on relevant requirements, invariants, boundaries, dependencies, authority, validation, continuity, and existing controlled state before becoming authoritative.

### E. Human–AI Interaction and Process Control

**R-035 — Metacognitive Audit**  
OPAQUE shall support recurring audit of project state, process/workflow state, interaction state, efficiency/cognitive load, and epistemic state before and after substantive operations.

**R-036 — Process Self-Correction**  
OPAQUE shall detect material process drift or defective working methods and support corrective action without confusing detection with authorization to modify governing rules.

**R-037 — Interaction Control**  
OPAQUE shall account for human–AI interaction conditions that materially affect project integrity, including misunderstanding, over-compliance, insufficient challenge, excessive explanation, cognitive overload, emotional disruption, and loss of progress visibility.

**R-038 — User-Facing Complexity Control**  
OPAQUE shall permit the complexity of internal reasoning and governance representation to differ from the complexity required in the human-facing operational explanation.

**R-039 — Interest-Drop / Momentum Compensation**  
OPAQUE shall support controlled adaptation when execution momentum, attention, or engagement degrades, while distinguishing observable signals from assumptions about their cause and preserving human autonomy.

**R-040 — Convergence Control**  
OPAQUE shall constrain exploratory specification work so that local examination does not continue indefinitely after sufficient information has been obtained for the current milestone.

**R-041 — Milestone and Completion Control**  
OPAQUE shall maintain explicit current objectives, completion conditions, remaining work, and next justified milestones for controlled specification and execution processes.

**R-042 — Interruption and Recovery**  
OPAQUE shall preserve sufficient state to resume controlled work after interruption without treating interruption itself as destruction or automatic invalidation of prior work.

### F. Scheme and Execution Governance

**R-043 — Scheme Integrity**  
OPAQUE shall preserve the integrity of the Scheme of Work and its relationship to project objectives, phases, tasks, timelines, dependencies, and execution.

**R-044 — Work-Unit Governance**  
OPAQUE shall support controlled definition, dependency handling, status, completion, carry-forward, blocking, and revision of meaningful work units.

**R-045 — Temporal Integrity**  
OPAQUE shall preserve materially relevant dates, durations, deadlines, sequencing, and temporal dependencies without inventing missing temporal information.

**R-046 — Execution Feasibility**  
OPAQUE shall distinguish an intended action from an action that is currently feasible given requirements, dependencies, resources, technology, time, complexity, and other relevant constraints.

**R-047 — Governance/Execution Boundary**  
OPAQUE shall distinguish governance decisions and permissions from the external or operational execution of those decisions and shall preserve the resulting execution state.

## 3. Candidate Cross-Cutting Invariant

### I-001 — Distinction Preservation

OPAQUE should preserve materially relevant distinctions between governed information, states, meanings, authorities, conditions, relationships, events, and determinations unless a governed transformation explicitly establishes a different state or relationship.

This invariant is cross-cutting rather than a substitute for the requirements above.

A corresponding anti-pattern is **distinction collapse**: treating materially different things as equivalent merely because they are related, convenient to represent together, or similar in ordinary language.

Distinction preservation must remain compatible with controlled equivalence; the goal is not to accumulate distinctions without purpose.

## 4. Items Explicitly Not Classified as Requirements

The following remain outside the requirement set unless later established otherwise:

- specific software architecture;
- specific database or data-model implementation;
- specific programming language/library decisions;
- specific UI implementation;
- specific AI model/provider;
- exact Scheme lifecycle;
- exact OPAQUE internal module structure;
- exact storage format;
- exact algorithms for detecting cognitive or emotional states;
- exact implementation of interest-drop compensation;
- exact implementation of traceability;
- exact validation algorithms.

These may become design constraints, capabilities, specifications, or implementation decisions later.

## 5. Consolidated Constraints / Design Principles

These are important governing considerations but are not automatically requirements merely because they constrain design:

1. OPAQUE must remain compatible with legitimate human authority.
2. OPAQUE must operate under incomplete knowledge.
3. OPAQUE must avoid uncontrolled complexity and unnecessary cognitive load.
4. OPAQUE must preserve project continuity.
5. OPAQUE must remain auditable and traceable.
6. OPAQUE must not silently promote conversational material into authoritative state.
7. OPAQUE must not silently erase materially relevant distinctions.
8. OPAQUE should support strong AI reasoning without granting silent project authority.
9. OPAQUE should allow the specification to evolve without becoming an uncontrolled moving target.
10. The system should favor maximum practical identification rather than maximum possible decomposition.

## 6. Consolidated Unresolved Matters

These are genuine specification questions remaining after consolidation. They are not hidden requirements.

### U-001 — Universal Authority Precedence
How conflicts between different authority domains are resolved when more than one controlled source applies.

### U-002 — Supersession and Replacement
The exact conditions under which a newer determination supersedes, replaces, narrows, or invalidates an existing controlled state.

### U-003 — Authority Escalation
How authority is determined when a matter crosses existing domain boundaries.

### U-004 — Validation Authority
Who or what is authorized to make, accept, reject, or revoke particular validation determinations.

### U-005 — Controlled Propagation
When a changed dependency requires downstream reassessment, and when propagation can be contained.

### U-006 — Requirement Granularity
The final boundary between one requirement and a family of related requirements once formal specification begins.

### U-007 — Interaction-State Representation
Which human–AI interaction conditions require formal representation and which can remain transient operational signals.

### U-008 — Quantification Boundary
Which OPAQUE properties should be measurable numerically and which should be represented categorically, relationally, or qualitatively.

### U-009 — Exception Authority
The authority and conditions required to create or maintain an exception to an otherwise applicable rule.

### U-010 — Closure Semantics
The exact meaning and consequences of blocked, paused, deferred, abandoned, superseded, invalidated, and completed states.

### U-011 — OPAQUE/Scheme Operational Interface
The precise interface through which OPAQUE governs the Scheme of Work without absorbing its operational responsibilities.

### U-012 — Termination Governance
The exact conditions and procedure under which the EverWorlds project, OPAQUE, or a major project subsystem may be formally terminated.

## 7. Dependency Structure

The candidate requirements have a broad dependency direction:

**Constitutional integrity**
→ information/state identification  
→ authority/relationship/dependency integrity  
→ controlled change and validation  
→ conditional operation and outcome governance  
→ traceability and feedback  
→ human–AI/process control  
→ Scheme/execution governance.

Cross-cutting invariant:

**Distinction Preservation** applies across all layers.

The dependency direction is conceptual at this stage. Exact formal dependency edges belong to the next specification step.

## 8. Coverage Check

The consolidated baseline covers the previously identified requirement families:

- purpose and boundaries;
- project-state integrity;
- epistemic integrity;
- controlled incompleteness and uncertainty;
- AI/human authority;
- identification and classification;
- state;
- authority;
- relationships and dependencies;
- conflict;
- semantic fidelity;
- incorporation;
- change and history;
- validation;
- conditional operation;
- indeterminacy;
- response/operation state;
- outcomes;
- failure/recovery;
- exceptions;
- closure;
- traceability;
- feedback;
- evolution;
- metacognition;
- human–AI interaction;
- cognitive-load control;
- continuity;
- convergence;
- milestones;
- Scheme integrity;
- work units;
- time;
- feasibility;
- governance/execution separation.

No additional requirement family is currently demonstrated to be necessary for Stage IV completion.

## 9. Stage IV Determination

**Candidate requirement consolidation is sufficiently complete to close Stage IV**, subject to later review during formal specification.

The remaining unresolved matters are specification questions rather than justification for reopening the completed conceptual exploration.

## 10. Next Milestone

**Stage V — OPAQUE Specification**

Stage V should transform this finite candidate baseline into a formal specification by defining, for each applicable requirement:

- exact meaning;
- scope;
- inputs;
- outputs;
- states;
- conditions;
- authority;
- dependencies;
- required behavior;
- failure behavior;
- validation criteria;
- traceability;
- controlled change semantics.

Architecture and implementation should remain downstream of those specifications.
