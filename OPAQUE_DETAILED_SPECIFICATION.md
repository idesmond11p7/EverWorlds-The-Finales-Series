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

## 3. Immediate Detailed-Specification Priorities

The next detailed pass shall specify:

1. R-012–R-020: identification, classification, state, authority, relationships, dependencies, conflict, semantic fidelity, incorporation;
2. R-021–R-030: change, validation, operation, outcomes, failure, exceptions, closure;
3. R-031–R-047: traceability, evolution, human–AI process control, Scheme and execution governance.

The detailed pass shall use the existing control model rather than creating new foundational concepts unless a genuine specification defect demonstrates that one is necessary.

## 4. Open Specification Questions

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

## 5. Stage V-D Completion Condition

Stage V-D is complete when the 47 candidate requirements have sufficiently precise operational definitions to permit later architecture and implementation decisions without requiring the implementation itself to invent missing governance rules.
