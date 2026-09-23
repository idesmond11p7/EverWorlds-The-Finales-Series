# OPAQUE — Detailed Specification

## Status

**Working specification — Stage V-D.**  
This document is the detailed specification layer built from the Stage V-C requirement mapping. It remains provisional until ratified.

## 1. Specification Rule

A requirement is not considered sufficiently specified merely because its intention is understandable.

For each requirement, the specification must establish, where applicable:

- what it governs;
- when it applies;
- what state it acts on;
- required inputs;
- required outputs;
- authority;
- conditions;
- dependencies;
- required behavior;
- prohibited behavior;
- failure behavior;
- validation;
- traceability;
- change semantics;
- completion/closure semantics.

The specification should stop when these elements are sufficient to determine compliant versus non-compliant behavior. Further decomposition requires demonstrated benefit.

---

## 2. Constitutional Requirements

### R-001 — OPAQUE Purpose

**Requirement:** OPAQUE shall provide meta-level control that helps keep EverWorlds governable and executable under complexity, incompleteness, uncertainty, change, disruption, and human–AI interaction problems.

**Specified meaning:** OPAQUE is responsible for maintaining the conditions under which relevant project information, decisions, work organization, and execution remain controlled.

**Boundary:** OPAQUE does not become the substantive EverWorlds product and does not replace ordinary execution.

**Minimum evidence of compliance:** A governed situation can be evaluated for control conditions rather than relying solely on informal project judgment.

---

### R-002 — OPAQUE Boundary

OPAQUE shall remain distinct from:

- EverWorlds as the substantive project;
- the Scheme of Work;
- individual execution;
- legitimate human project authority.

A matter crossing these boundaries shall retain its identity and relationship to each domain.

**Failure:** Silent absorption of one domain's responsibilities into another.

---

### R-003 — Scheme Boundary

OPAQUE shall govern the integrity and conditions of the Scheme of Work without becoming the Scheme itself.

OPAQUE may determine that Scheme conditions are unsatisfied, that work is blocked, that dependencies require attention, or that process correction is necessary.

OPAQUE shall not silently redefine ordinary Scheme operations merely because it can identify a better arrangement.

---

### R-004 — Project-State Integrity

Controlled project state shall change only through a governed state transition.

Conversation, inference, draft material, observation, or execution activity may provide material for a transition but shall not itself constitute the transition.

OPAQUE shall preserve the prior state and the basis for any material transition.

---

### R-005 — Epistemic Integrity

OPAQUE shall distinguish materially different epistemic statuses.

At minimum, the system must be able to distinguish:

- known;
- observed;
- inferred;
- proposed;
- assumed;
- questioned;
- unresolved;
- validated;
- rejected.

A lower-certainty or different epistemic status shall not be silently promoted into a stronger status.

---

### R-006 — Controlled Incompleteness

OPAQUE shall allow work to proceed despite incomplete knowledge when the missing information is not a prerequisite for the current operation.

Where missing information is materially required, the relevant work shall be marked or treated as blocked, deferred, conditional, or otherwise unresolved rather than filled with an invented value.

---

### R-007 — Explicit Uncertainty

Material uncertainty shall be represented explicitly.

OPAQUE shall preserve uncertainty about:

- facts;
- interpretations;
- dependencies;
- authority;
- outcomes;
- validation;
- feasibility;

whenever that uncertainty can materially affect governance or action.

---

### R-008 — AI Authority Boundary

AI reasoning may:

- identify;
- analyze;
- compare;
- challenge;
- propose;
- forecast procedural consequences;
- detect defects;
- recommend action.

AI reasoning alone shall not establish authoritative project state unless the applicable authority rules explicitly permit that transition.

**Core boundary:** reasoning is not authority.

---

### R-009 — Human Decision Authority

Where legitimate human authority is applicable, OPAQUE shall preserve that authority.

OPAQUE may identify that a human decision is required, explain the consequences of available options, and prepare material for decision.

OPAQUE shall not silently substitute an AI determination for a required human decision.

---

### R-010 — Controlled State Modification

A material modification to controlled state requires:

1. identification of the governed object;
2. identification of the current state;
3. identification of the proposed change;
4. applicable authority;
5. applicable conditions;
6. applicable dependencies;
7. required validation;
8. resulting state;
9. provenance/history.

If a required condition is not satisfied, the authoritative state shall remain unchanged.

The proposal or attempted change may still be recorded separately.

---

### R-011 — Continuity

OPAQUE shall preserve sufficient information to resume controlled work after ordinary interruption.

Resumption shall reconstruct, at minimum:

- current governed state;
- current work position;
- outstanding blockers;
- relevant dependencies;
- unresolved matters;
- next justified action.

Interruption shall not by itself erase prior controlled work.

---

## 3. Information and Semantic-Control Requirements

### R-012 — Identification

OPAQUE shall identify the governed object or material sufficiently to determine what is being governed and to distinguish it from materially different objects or material.

**Required behavior:**
- assign or preserve a stable identity where one is required for control;
- distinguish the object from its descriptions, interpretations, states, and proposed changes;
- identify scope where the same material could refer to multiple objects or contexts.

**Failure:** treating ambiguous, unidentified, or conflated material as if its identity were established.

**Validation:** identity is sufficient for the relevant operation, relationship, dependency, authority, and traceability decisions.

---

### R-013 — Classification

OPAQUE shall classify materially relevant material according to its governing role and epistemic status.

Classification shall be sufficient to determine how the material may be used, changed, relied upon, or incorporated.

**Required behavior:**
- distinguish at minimum the epistemic statuses established by R-005;
- distinguish requirements, constraints, decisions, proposals, observations, questions, assumptions, and other materially different roles where the distinction affects governance;
- preserve multiple applicable classifications when collapsing them would alter meaning or control.

**Failure:** silent promotion, misclassification, or loss of a materially relevant classification.

**Validation:** the classification permits correct determination of authority, permitted use, dependency, and state effect.

---

### R-014 — State-Dimension Integrity

OPAQUE shall represent materially different dimensions of state separately when combining them could change the meaning or permitted action.

State may include, where relevant:

- epistemic status;
- operational status;
- approval/authority status;
- validation status;
- dependency status;
- work status;
- other governed state dimensions demonstrated necessary by context.

A change in one dimension shall not silently imply a change in another.

**Failure:** treating “known,” “approved,” “complete,” “validated,” or similar states as interchangeable when they are not.

**Validation:** a state representation permits the system to determine which dimensions changed and which did not.

---

### R-015 — Authority Determination

OPAQUE shall determine the authority applicable to a governed matter before an authoritative state transition is made.

Authority determination shall:

1. identify potentially applicable authorities;
2. establish the scope of each authority;
3. determine whether the authorities actually apply to the matter;
4. apply an already-established precedence relation where genuine overlap exists;
5. avoid inventing precedence where none has been established;
6. escalate or preserve the matter as unresolved when authority cannot legitimately be determined.

**Failure:** treating capability, convenience, confidence, provenance, or AI recommendation as authority without an applicable rule.

**Validation:** the authority used for a transition is identifiable and its applicability can be explained from the governed rules.

---

### R-016 — Relationship Integrity

OPAQUE shall preserve materially relevant relationships between governed objects and material.

Relationships include connections such as:

- belongs to;
- describes;
- concerns;
- derived from;
- informs;
- conflicts with;
- supersedes;
- supports;
- depends on.

A relationship shall not be inferred as equivalent to another relationship merely because the two appear similar.

**Failure:** deletion, substitution, or silent reinterpretation of a material relationship.

**Validation:** relationships required to determine meaning, dependency, authority, consequence, or traceability remain identifiable after processing.

---

### R-017 — Dependency Integrity

OPAQUE shall identify and preserve dependencies that materially constrain whether an operation, transition, or conclusion is valid.

For a material dependency, OPAQUE shall be able to determine:

- the dependent matter;
- the prerequisite matter;
- the nature of the dependency;
- whether the prerequisite is satisfied, unsatisfied, unknown, or no longer applicable;
- the consequence of an unsatisfied dependency.

**Failure:** allowing dependent work to be treated as unconditionally valid when a required prerequisite is unresolved or unsatisfied.

**Validation:** dependency state is sufficient to determine whether the affected operation may proceed.

---

### R-018 — Controlled Conflict Handling

OPAQUE shall detect and explicitly represent material conflicts between governed material, requirements, decisions, states, authorities, dependencies, or interpretations.

A detected conflict shall not be silently resolved merely because one interpretation appears more convenient.

**Required behavior:**
- identify the conflicting matters;
- determine whether the conflict is genuine or caused by ambiguity/misclassification;
- preserve both sides until a legitimate resolution is established;
- identify the authority or validation required for resolution;
- prevent an unresolved conflict from silently becoming a settled state.

**Failure:** silent selection, deletion, blending, or reconciliation of materially conflicting information.

**Validation:** the conflict and its resolution or unresolved status remain traceable.

---

### R-019 — Semantic Containment and Fidelity

OPAQUE shall preserve the material meaning of governed information when recording, transforming, summarizing, classifying, or incorporating it.

A transformation is compliant only when it preserves distinctions and consequences material to the governed purpose.

This requirement does not require literal preservation of wording or representation.

**Required behavior:**
- preserve material qualifiers, conditions, scope, authority, uncertainty, relationships, and consequences;
- distinguish source meaning from AI interpretation;
- prevent compression or restructuring from silently changing what the material permits, prohibits, establishes, or leaves unresolved.

**Failure:** a transformation causes a materially different interpretation or state effect without an explicitly governed transformation.

**Validation:** the resulting representation can be traced to its source and checked for preservation of material meaning.

---

### R-020 — Controlled Incorporation

OPAQUE shall control when identified and classified material becomes part of authoritative governed state.

Discussion, capture, analysis, proposal, or preparation shall not by itself constitute incorporation.

Before incorporation, OPAQUE shall determine, as applicable:

- what material is being incorporated;
- its intended governed object and state;
- authority for incorporation;
- required conditions;
- dependencies;
- required validation;
- resulting state;
- provenance.

If incorporation requirements are not satisfied, the material shall remain outside authoritative state while retaining an appropriate non-authoritative status.

**Failure:** silent promotion of draft, inference, proposal, external information, or execution residue into authoritative state.

**Validation:** the incorporated state has a traceable basis and satisfies the applicable transition requirements.

---

## 4. Change, Validation, Operation, Failure, and Closure Requirements

### R-021 — Controlled Change

OPAQUE shall treat any material alteration to controlled state, controlled relationships, governing requirements, or authoritative records as a controlled change.

A change shall be distinguished from:

- a proposal to change;
- an attempted but unsuccessful change;
- an observation that a change has occurred externally;
- a correction to an identified error.

Before a controlled change becomes authoritative, OPAQUE shall determine the affected object and state, proposed alteration, authority, conditions, dependencies, required validation, and resulting state.

**Failure:** an alteration becomes authoritative merely because it occurred, was requested, or was technically possible.

**Validation:** the resulting state and basis for change can be reconstructed from the change record.

---

### R-022 — Change History

OPAQUE shall preserve the history necessary to determine how a material controlled state was reached and materially changed.

For each material change, the history shall preserve, where applicable:

- prior state;
- resulting state;
- change description;
- reason or basis;
- authority;
- relevant conditions/dependencies;
- validation result;
- provenance;
- time/order sufficient to establish sequence.

History shall be append-preserving for material prior states; a later state shall not erase the fact that a materially different prior state existed.

**Failure:** overwriting controlled history in a way that makes material state evolution unreconstructable.

**Validation:** a reviewer can trace a material current state backward through its recorded changes to the relevant originating material.

---

### R-023 — Validation Integrity

OPAQUE shall distinguish validation from determination, approval, observation, and incorporation.

Validation shall occur when a governed rule requires evidence that a specified condition, claim, state, transformation, or result satisfies its applicable criteria.

Validation shall identify:

- what is being validated;
- the criteria or basis;
- the validation authority or method;
- the result;
- relevant evidence/provenance;
- any limitations or unresolved defects.

Validation shall not be treated as stronger or broader than the scope it actually covers.

**Failure:** treating an unvalidated matter as validated, or treating validation of one property as validation of unrelated properties.

**Validation:** the validation result can be matched to the exact subject, criteria, scope, and authority involved.

---

### R-024 — Conditional Operation

OPAQUE shall permit an operation to proceed only when its required conditions and dependencies are satisfied, or when the operation is explicitly permitted to proceed under an identified conditional state.

OPAQUE shall determine:

- the operation;
- required conditions;
- relevant dependencies;
- current satisfaction state;
- consequence of proceeding;
- whether the operation is permitted, blocked, deferred, or conditional.

**Failure:** treating an operation as unconditionally permitted when a required condition or dependency is unsatisfied.

**Validation:** the permission to proceed can be explained from the operation's applicable conditions and dependencies.

---

### R-025 — Operation-State Integrity

OPAQUE shall distinguish an operation's execution state from the controlled state that the operation is intended to affect.

An operation may be:

- proposed;
- authorized;
- ready;
- executing;
- completed;
- failed;
- interrupted;
- cancelled;
- otherwise explicitly represented.

Operation completion shall not by itself establish that the intended controlled state change succeeded.

**Failure:** inferring successful state transition merely from attempted or completed execution activity.

**Validation:** operation state and controlled-state result can be determined independently.

---

### R-026 — Outcome Integrity

OPAQUE shall record material outcomes separately from the operations and determinations that produced or interpreted them.

An outcome shall be represented with sufficient context to determine:

- what operation or event produced it;
- what actually occurred;
- whether the outcome was expected, unexpected, partial, or indeterminate;
- what controlled state, if any, it affects;
- whether further validation or determination is required.

**Failure:** replacing an actual outcome with the intended result, or treating an interpretation of an outcome as the outcome itself.

**Validation:** the recorded outcome can be distinguished from the operation, expectation, interpretation, and resulting state.

---

### R-027 — Controlled Indeterminacy

OPAQUE shall represent material matters as indeterminate when available evidence is insufficient to establish a required fact, state, authority, dependency, outcome, or validation result.

Indeterminacy shall not be silently converted into a convenient assumption, completion, approval, success, or failure.

Where possible, OPAQUE shall identify:

- what is indeterminate;
- what evidence is missing or conflicting;
- what depends on its resolution;
- whether work may continue conditionally;
- what event or evidence could resolve it.

**Failure:** forced certainty where the governing evidence does not support certainty.

**Validation:** an indeterminate matter remains distinguishable from both established and rejected states.

---

### R-028 — Failure and Recovery Governance

OPAQUE shall govern material failures of controlled operations, state transitions, validation, dependencies, or required control processes.

When a material failure occurs, OPAQUE shall:

1. preserve the pre-failure controlled state;
2. record the failure and affected operation/state;
3. determine whether partial effects occurred;
4. prevent unverified partial effects from being represented as successful completion;
5. determine available recovery, rollback, containment, or reattempt conditions;
6. preserve unresolved effects until determined.

Recovery shall itself be subject to applicable authority, conditions, dependencies, and validation.

**Failure:** treating failure as success, silently discarding partial effects, or allowing recovery to bypass governance.

**Validation:** post-failure state and recovery result are distinguishable and reconstructable.

---

### R-029 — Exception Governance

OPAQUE shall distinguish an exception from ordinary operation and shall prevent exceptional handling from becoming an uncontrolled bypass of governing requirements.

An exception shall identify, where applicable:

- the ordinary rule or condition affected;
- the exceptional circumstance;
- the authority permitting exceptional handling;
- scope and duration of the exception;
- conditions or safeguards;
- resulting state;
- validation or review requirements.

An exception shall not silently rewrite the ordinary rule.

**Failure:** treating convenience, urgency, failure, or unusual circumstance as automatic authority to bypass governance.

**Validation:** the exception's scope, authority, and effect are traceable and distinguishable from ordinary operation.

---

### R-030 — Closure Integrity

OPAQUE shall distinguish closure from completion, success, validation, approval, and termination.

A governed matter may be closed only when its applicable closure condition has been established.

Closure shall identify:

- the matter being closed;
- the state at closure;
- the closure condition or basis;
- outstanding unresolved material, if any;
- authority required for closure;
- resulting ability or prohibition to reopen or continue.

Closure shall not erase unresolved history or imply facts that have not been established.

**Failure:** declaring a matter closed because activity stopped, because a deadline passed, or because the immediate work ended when the applicable closure condition was not satisfied.

**Validation:** the reason for closure and its effect on future work are identifiable.

---

## 5. Traceability, Evolution, Human–AI Process, Scheme, and Execution Requirements

### R-031 — Traceability

OPAQUE shall preserve traceable relationships between materially relevant source material, determinations, requirements, decisions, changes, operations, outcomes, validation, and resulting controlled state.

Traceability shall support both:

- backward tracing: determining the material basis of a current state or determination;
- forward tracing: determining materially affected state, work, or obligations arising from a source, decision, or change.

Traceability shall not require every piece of incidental information to be individually linked when it has no material governance consequence.

**Failure:** a material controlled state or decision cannot be connected to its relevant basis or material downstream effects.

**Validation:** required backward and forward traces can be reconstructed for material matters.

---

### R-032 — Feedback Incorporation

OPAQUE shall control how observations, outcomes, failures, reviews, and other feedback affect governed state or future work.

Feedback shall first be distinguished as:

- observation/evidence;
- interpretation;
- proposal;
- required correction;
- validated finding;
- other applicable status.

Feedback shall not automatically become a requirement, decision, rule, or state change.

Where feedback is incorporated, its effect and basis shall be traceable.

**Failure:** treating feedback as authoritative merely because it was received or appears persuasive.

**Validation:** the relationship between feedback and any resulting change is identifiable.

---

### R-033 — Controlled Evolution

OPAQUE shall permit governed systems, rules, requirements, work structures, and controlled states to evolve without silently losing historical identity or applicable constraints.

Evolution shall distinguish:

- current state;
- proposed future state;
- superseded state where applicable;
- transition basis;
- affected relationships and dependencies.

A new state shall not silently invalidate prior history or applicable traceability.

**Failure:** uncontrolled drift in which a material change occurs without identifiable transition or basis.

**Validation:** an evolved matter can be related to its prior state and the material basis for evolution.

---

### R-034 — Impact Evaluation

Before a material proposed change becomes authoritative, OPAQUE shall evaluate reasonably identifiable effects on affected objects, states, relationships, dependencies, authority, work, validation, and continuity.

Impact evaluation shall be proportional to the materiality and scope of the change.

Where material impact cannot be determined, that uncertainty shall remain explicit and shall affect whether the change may proceed.

**Failure:** material downstream consequences are knowingly ignored or represented as absent without adequate basis.

**Validation:** material affected areas and unresolved impact are identifiable from the change evaluation.

---

### R-035 — Metacognitive Audit

OPAQUE shall periodically or conditionally audit the current state of project control and the process by which that state is being produced.

The audit shall examine, as applicable:

1. project-state changes;
2. workflow/process changes;
3. interaction/communication changes relevant to execution;
4. efficiency or cognitive-load effects relevant to continued work;
5. epistemic changes.

The audit shall distinguish detected signals from established causes.

**Failure:** continuing a materially defective process solely because it has already been established, or treating an inferred cause as established fact.

**Validation:** detected control defects and resulting corrective actions or non-actions are traceable.

---

### R-036 — Process Self-Correction

When OPAQUE detects a material process defect, it shall determine whether the defect can be corrected within existing authority and constraints.

Permitted self-correction may include changing immediate work procedure, sequencing, presentation, or other operational process without changing authoritative project requirements unless such change is itself governed.

A process correction shall not silently alter project authority, requirements, or controlled state.

**Failure:** preserving a demonstrably defective process without evaluation, or using process correction as a covert means of changing authoritative project state.

**Validation:** the detected defect, correction, and resulting effect can be identified.

---

### R-037 — Interaction Control

OPAQUE shall maintain sufficient control over human–AI interaction to prevent communication artifacts from being mistaken for authoritative project state.

Material interaction shall be distinguishable, where relevant, from:

- project decisions;
- proposals;
- instructions;
- emotional expressions;
- observations;
- questions;
- corrections;
- authoritative determinations.

A conversational statement shall not acquire project authority solely through its conversational form.

**Failure:** treating an ambiguous or non-authoritative interaction as a binding project decision without applicable authority.

**Validation:** the system can determine which interaction material affected controlled state and why.

---

### R-038 — User-Facing Complexity Control

OPAQUE shall separate internal control complexity from the complexity presented to the user.

The system may maintain detailed internal reasoning, dependencies, checks, and records while presenting only the information necessary for the user's current decision, action, or understanding.

Simplification shall not remove material distinctions required for correct user understanding or authority.

**Failure:** either exposing unnecessary internal complexity that obstructs execution or simplifying away material information.

**Validation:** user-facing representation remains sufficient for the user's required action or decision without requiring exposure of the entire internal control model.

---

### R-039 — Interest-Drop/Momentum Compensation

OPAQUE shall detect material degradation in work momentum or engagement where observable behavior indicates that continued execution may be impaired.

OPAQUE shall distinguish:

- observed signal;
- hypothesis about cause;
- checked or unverified cause;
- appropriate procedural response.

Possible responses may include reducing immediate scope, changing presentation, selecting a smaller justified work unit, restoring context, changing sequencing, or preserving a clean stopping/resumption point.

This requirement shall not authorize covert psychological manipulation or inference beyond what is necessary for continuity control.

**Failure:** treating a temporary engagement signal as project termination, or treating an inferred psychological cause as established fact.

**Validation:** the signal, procedural response, and effect on continuity are distinguishable.

---

### R-040 — Convergence Control

OPAQUE shall prevent exploratory work from continuing indefinitely once sufficient information exists to perform the current justified determination.

The convergence process shall distinguish:

- exploration;
- relevance determination;
- extraction;
- compression;
- sufficiency checking;
- closure of the current inquiry;
- advancement to the next justified action.

A fixed time or step limit shall not by itself establish sufficiency.

**Failure:** continuing to expand a closed or sufficiently determined question without demonstrated benefit, or closing an inquiry while a material unresolved dependency remains.

**Validation:** the basis for determining sufficiency or continued exploration is identifiable.

---

### R-041 — Milestone and Completion Control

OPAQUE shall define and preserve completion conditions for material milestones and work units.

Completion shall be determined from the applicable completion condition, not merely from activity, elapsed time, or subjective satisfaction.

A milestone may be:

- not started;
- active;
- blocked;
- conditionally complete;
- complete;
- reopened;
- superseded;
- otherwise explicitly governed.

Completion shall identify remaining material work, unresolved dependencies, and the next justified milestone where applicable.

**Failure:** advancing a milestone as complete when its material completion condition is unsatisfied.

**Validation:** completion status can be matched to its defined condition and supporting evidence.

---

### R-042 — Interruption and Recovery

OPAQUE shall preserve a controlled recovery point when work is interrupted.

A recovery point shall retain sufficient information to identify:

- current state;
- current work position;
- completed material work;
- carried work;
- blockers;
- unresolved matters;
- dependencies;
- next first action.

Recovery shall not assume that memory of the conversation alone is sufficient.

**Failure:** resumption requires reconstruction by guesswork or causes previously controlled state to be lost or contradicted.

**Validation:** an authorized resumption can reconstruct the relevant work position and state from preserved information.

---

### R-043 — Scheme Integrity

OPAQUE shall protect the integrity of the Scheme of Work as the controlled execution framework for EverWorlds.

OPAQUE shall detect and represent material defects such as:

- broken dependencies;
- orphaned work;
- contradictory work conditions;
- missing completion conditions;
- uncontrolled scope expansion;
- loss of continuity;
- work proceeding outside required conditions.

OPAQUE may require correction, blocking, deferral, or restructuring where authorized by its governing rules.

OPAQUE shall not silently become the substantive Scheme.

**Validation:** a material Scheme defect and its resulting control response are traceable.

---

### R-044 — Work-Unit Governance

OPAQUE shall ensure that each material work unit has sufficient definition to permit controlled execution.

Where applicable, a work unit shall identify:

- objective;
- scope;
- inputs;
- expected output;
- prerequisites;
- dependencies;
- authority;
- completion condition;
- current status;
- carried or unresolved material.

Work units may remain intentionally small or provisional when that is sufficient for the current task.

**Failure:** execution begins on materially undefined work where the missing definition affects validity, authority, dependencies, or completion.

**Validation:** the work unit is sufficiently defined to determine whether it may proceed and when it is complete.

---

### R-045 — Temporal Integrity

OPAQUE shall preserve materially relevant temporal information for governed work.

Where time affects control, OPAQUE shall distinguish:

- planned time;
- required deadline;
- actual occurrence;
- sequence/order;
- duration where relevant;
- overdue status;
- interruption/resumption.

OPAQUE shall not invent missing timestamps or durations.

A missing temporal value shall remain explicitly unknown when it is relevant to governance.

**Failure:** fabricated, conflated, or overwritten temporal information changes the interpretation of work status, sequence, deadline, or continuity.

**Validation:** time-dependent determinations can be reconstructed from recorded temporal evidence.

---

### R-046 — Execution Feasibility

Before materially committing to an execution path, OPAQUE shall determine whether the path is sufficiently feasible under known requirements, dependencies, resources, technology, available capabilities, constraints, and time.

Feasibility may be:

- established;
- conditionally feasible;
- requiring prerequisite work;
- requiring further research;
- blocked;
- infeasible under current conditions;
- otherwise explicitly indeterminate.

OPAQUE shall not represent feasibility as established when a material prerequisite or constraint remains unresolved.

**Failure:** execution commitment rests on an unexamined material dependency or capability assumption.

**Validation:** the feasibility determination identifies its material basis and unresolved constraints.

---

### R-047 — Governance/Execution Boundary

OPAQUE shall preserve the distinction between governance and execution.

OPAQUE governs whether work may proceed, under what conditions, with what dependencies and controls, and how resulting state is evaluated.

Execution performs the substantive work.

OPAQUE shall not silently invent substantive product decisions merely because execution requires a choice.

Where execution encounters an undefined matter that materially affects governed state, it shall be returned to the appropriate determination/authority path rather than being silently converted into an authoritative rule.

**Failure:** execution silently becomes the source of governance, or governance prevents legitimate execution without a material control basis.

**Validation:** the relationship between governing determination and substantive execution remains identifiable.

---

## 6. Open Specification Questions

The following remain unresolved and shall not be silently invented:

- universal authority precedence;
- supersession/replacement;
- authority escalation;
- validation authority;
- controlled propagation;
- requirement granularity;
- interaction-state representation;
- quantification boundary;
- exception authority;
- closure semantics;
- OPAQUE/Scheme operational interface;
- termination governance.

These are explicit specification work items. They do not justify reopening the requirement baseline without a demonstrated defect.

---

## 7. Stage V-D Completion Condition

Stage V-D is complete when the 47 candidate requirements have sufficiently precise operational definitions to permit later architecture and implementation decisions without requiring the implementation itself to invent missing governance rules.

**Working determination:** R-001–R-047 have now received a complete detailed-specification pass. Remaining work is verification of internal consistency, overlap, unresolved-question treatment, and readiness for formal ratification; this is not permission to silently ratify the specification.
