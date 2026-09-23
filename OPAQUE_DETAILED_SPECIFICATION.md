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

## 4. Immediate Detailed-Specification Priorities

The next detailed pass shall specify:

1. R-021–R-030: change, validation, operation, outcomes, failure, exceptions, closure;
2. R-031–R-047: traceability, evolution, human–AI process control, Scheme and execution governance.

The detailed pass shall use the existing control model rather than creating new foundational concepts unless a genuine specification defect demonstrates that one is necessary.

---

## 5. Open Specification Questions

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

These are now treated as explicit specification work items.

---

## 6. Stage V-D Completion Condition

Stage V-D is complete when the 47 candidate requirements have sufficiently precise operational definitions to permit later architecture and implementation decisions without requiring the implementation itself to invent missing governance rules.
