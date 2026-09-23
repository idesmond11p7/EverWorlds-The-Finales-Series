# OPAQUE — Core Control Model

## Status

**Stage V-B — Core Control Model: Complete (working determination).**

This document defines the minimum conceptual model required to move from the candidate requirement baseline into formal specification. It is not an architecture, implementation model, or ratification record.

## 1. Model Objective

The purpose of the model is not to describe everything OPAQUE may ever contain.

Its purpose is narrower:

> establish the smallest set of distinct concepts necessary to determine what is being governed, what state it is in, what may happen to it, under whose authority, under what conditions, with what dependencies, and with what resulting consequences.

A concept is retained only when removing or collapsing it would make a materially different governance question impossible to represent reliably.

## 2. Core Concepts

### C-01 — Governed Object

**Definition:** A distinct thing, information item, decision, work unit, rule, determination, state-bearing entity, or other entity whose identity and treatment are subject to OPAQUE control.

**Answers:** What is being governed?

**Not:** Its current state, authority, relationship, or history.

**Necessity:** Without an identifiable subject, control has nothing determinate to apply to.

### C-02 — State

**Definition:** The current condition of a governed object or controlled process along one or more relevant dimensions.

**Answers:** What condition is it currently in?

**Not:** A universal single status field. Epistemic, authority, lifecycle, execution, validation, and other materially distinct dimensions must remain distinguishable.

**Necessity:** Control requires knowing current condition without collapsing different kinds of state.

### C-03 — Authority

**Definition:** The source, scope, and legitimacy under which a determination, permission, rule, or state modification has standing.

**Answers:** Who or what has standing to determine, authorize, or govern this matter?

**Not:** Truth, validation, or mere authorship.

**Necessity:** OPAQUE must distinguish a correct inference from an authorized project determination.

### C-04 — Condition

**Definition:** A circumstance or predicate that must hold, or whose presence materially affects whether a rule, operation, determination, or transition applies.

**Answers:** Under what circumstances does this apply or become possible?

**Not:** A dependency itself.

**Necessity:** Conditionality is central to OPAQUE; identical actions may be valid under one state and invalid under another.

### C-05 — Relationship

**Definition:** A meaningful association between governed objects or between an object and another controlled entity.

**Answers:** How are these things related?

**Not:** Necessarily a dependency.

**Necessity:** Not all meaningful relationships impose operational prerequisites.

### C-06 — Dependency

**Definition:** A relationship in which the state, validity, availability, or required treatment of one governed object materially depends on another.

**Answers:** What must remain true or available for this matter to remain valid or operable?

**Not:** Every relationship.

**Necessity:** Dependency affects sequencing, propagation, feasibility, and change impact.

### C-07 — Operation

**Definition:** A permitted or proposed act performed against or within controlled state.

**Answers:** What is being done or proposed?

**Not:** Its authorization, execution success, or resulting outcome.

**Necessity:** OPAQUE must govern actions separately from the states and consequences surrounding them.

### C-08 — Determination

**Definition:** A conclusion, classification, interpretation, decision, or other asserted resolution produced within the governed process.

**Answers:** What has been determined?

**Not:** Automatically validated or authoritative merely because it exists.

**Necessity:** OPAQUE must represent conclusions without confusing existence of a conclusion with its standing.

### C-09 — Validation

**Definition:** A governed evaluation establishing whether a determination, state, result, or other controlled claim satisfies specified criteria for a defined purpose and scope.

**Answers:** Has this been sufficiently established for the intended purpose?

**Not:** Authority itself.

**Necessity:** Determination and acceptance of validity are distinct governance events.

### C-10 — Change

**Definition:** A material transition in controlled state, rule, requirement, relationship, dependency, determination, or other governed condition.

**Answers:** What changed?

**Not:** The operation that caused it, nor merely the observation that something is now different.

**Necessity:** Material change requires controlled impact, authorization, history, and reassessment.

### C-11 — Outcome

**Definition:** The determined result and relevant consequence of an operation, change, validation, or other governed event.

**Answers:** What resulted, and what does that result mean for controlled state?

**Not:** The operation itself or raw observation alone.

**Necessity:** Execution and consequence cannot safely be treated as identical.

### C-12 — Closure

**Definition:** A governed condition indicating the disposition of a work item, determination, process, or other controlled matter.

**Answers:** What is the current disposition of this matter?

**Not:** A generic synonym for completed.

**Necessity:** Completed, paused, blocked, deferred, abandoned, superseded, and invalidated have materially different consequences.

### C-13 — Provenance

**Definition:** The origin and transformation history sufficient to establish where controlled information, determination, or state came from and how it became its present form.

**Answers:** Where did this come from, and what happened to it?

**Not:** Authority or truth.

**Necessity:** Semantic fidelity, traceability, conflict handling, and controlled incorporation require source history.

### C-14 — Controlled Incorporation

**Definition:** The governed transition through which permitted material becomes part of controlled project state.

**Answers:** How does external/conversational/research/execution material acquire controlled standing?

**Not:** Merely recording information.

**Necessity:** The boundary between “material exists” and “material governs” is constitutional.

## 3. Why These Concepts Remain Separate

The model deliberately preserves several distinctions that could superficially be collapsed:

- **Object ≠ State:** the thing is not its condition.
- **State ≠ Closure:** current condition is not necessarily final disposition.
- **Authority ≠ Validation:** authorized does not automatically mean validated; validated does not automatically determine authority.
- **Relationship ≠ Dependency:** association does not necessarily create a prerequisite.
- **Operation ≠ Change:** an operation may produce no material change; a change may have multiple causes.
- **Determination ≠ Validation:** a conclusion may exist before it is sufficiently established.
- **Observation/Outcome ≠ Determination:** what happened is not identical to what the system concludes it means.
- **Provenance ≠ Authority:** origin does not determine standing.
- **Recording ≠ Controlled Incorporation:** storing information does not automatically grant it governing status.

These distinctions directly protect the candidate Distinction Preservation invariant.

## 4. Minimum Control Relationship

The core model can be represented as:

**Governed Object**
→ has **State**
→ exists within **Relationships / Dependencies**
→ is subject to **Authority** and **Conditions**
→ may undergo **Operations / Changes**
→ produces or receives **Determinations / Outcomes**
→ may undergo **Validation**
→ acquires or retains controlled standing through **Controlled Incorporation**
→ remains traceable through **Provenance**
→ reaches a governed **Closure** state.

This is a conceptual relation map, not a prescribed data structure or software architecture.

## 5. Control Logic

A generic controlled transition can therefore be expressed as:

**Object + Current State + Authority + Conditions + Dependencies + Permitted Operation**
→ **Operation / Determination**
→ **Observed Result / Outcome**
→ **Validation where required**
→ **Controlled State Transition**
→ **Provenance / Traceability**
→ **Closure or Continued Operation**

Not every operation requires every stage. Applicability is determined by the specification of the particular requirement.

## 6. Concepts Deliberately Not Added

The following are not retained as independent core concepts at this stage:

### Information

Information is a broad material category that can be represented through governed objects, determinations, provenance, state, and relationships. It does not presently require a separate control primitive.

### Event

Events can be represented as material occurrences associated with operations, changes, outcomes, and provenance. No independent event primitive is presently demonstrated necessary.

### Permission

Permission is represented through authority, conditions, and operation eligibility. A separate primitive would currently duplicate those functions.

### Rule

Rules are governed objects/determinations with applicable authority, conditions, scope, and effects. No independent primitive is presently required.

### Requirement

Requirements are a specialized governed object with additional specification semantics. They do not require a new foundational control primitive.

### Resource

Resources matter to feasibility and execution but can remain domain-specific governed objects and dependencies until a specification finding demonstrates otherwise.

### Time

Time remains a required governance dimension, especially for R-045, but a separate universal core primitive is not yet demonstrated necessary. Temporal semantics can be specified as a state/condition/dependency dimension.

## 7. Boundary to Human–AI Process Control

The core model does not attempt to represent every human or AI condition as project state.

For human–AI interaction:

**observable signal → interpretation/hypothesis → permitted procedural response**

remains preferable to silently converting inferred human conditions into governed facts.

Process controls such as metacognitive audit, convergence, interaction control, and momentum compensation operate on or around the core model rather than requiring a separate ontology for every psychological or conversational condition.

## 8. Remaining Questions That Actually Block Formal Specification

Only three questions are presently demonstrated to require resolution before the authority/transition portions of the model can be specified coherently:

1. **Authority precedence:** how conflicts between simultaneously applicable authority domains are resolved.
2. **Validation authority:** who/what may establish, accept, reject, or revoke validation for a defined scope.
3. **Controlled state transition:** the exact conditions under which a proposed change becomes a controlled state transition.

The other unresolved matters in the Stage IV baseline remain downstream specification questions and need not block the existence of this core model.

## 9. Stage V-B Determination

**Stage V-B is sufficiently complete for advancement.**

The model contains 14 distinct core concepts and deliberately excludes concepts whose independent necessity has not been demonstrated.

No architecture, database, programming language, UI, AI provider, or implementation mechanism has been introduced.

The model is finite enough to become the semantic basis for requirement mapping.

## 10. Next Milestone

**Stage V-C — Requirement-to-Control Mapping**

Objective:

Map R-001–R-047 against C-01–C-14 and I-001.

For each requirement, determine:

- primary control concepts;
- supporting concepts;
- required relationships;
- prerequisite concepts;
- unresolved specification dependencies;
- whether the requirement can now proceed to formal specification.

Completion condition:

Every candidate requirement has an explicit control-model placement, and any remaining gap is classified as either a genuine specification question or a demonstrated model defect.

