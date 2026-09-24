# OPAQUE — Stage VII-C Runtime Lifecycle Architecture

## Status

**Architectural analysis — provisional.**

Stage VII-C defines the runtime lifecycle of OPAQUE independently of any particular programming language, database, AI provider, or host application.

This document does not ratify OPAQUE, resolve open governance questions, or select final implementation technologies.

## 1. Architectural Finding

OPAQUE should operate as an **event-driven controlled state system** with explicit processing stages, governed transitions, persistent checkpoints, and conditional invocation of reasoning, authorization, validation, auditing, and recovery mechanisms.

It does not require a continuously running AI conversation to remain valid.

The central lifecycle is:

**event/input → controlled processing → proposal/interpretation → control evaluation → authorization where required → operation → observation → outcome/validation → controlled state transition → provenance/history → persistence → audit/recovery as required**

This is a lifecycle model, not a mandatory linear pipeline. Stages are invoked conditionally according to the event, governed object, operation, dependencies, authority, and applicable controls.

---

## 2. Runtime Units

OPAQUE should distinguish at least four runtime units.

### 2.1 Event

Something has occurred or has been submitted for processing.

Examples include human input, AI output, host events, temporal triggers, operation results, validation results, audit triggers, and recovery requests.

An event is **not automatically a state change**.

### 2.2 Processing Request

OPAQUE has determined that internal processing is required, such as identification, dependency evaluation, semantic analysis, transition evaluation, validation, or audit.

A processing request is **not automatically authorized execution**.

### 2.3 Operation

A governed action that may produce an external or controlled effect. It has its own state and completion condition.

### 2.4 Controlled State Transition

The authoritative change to OPAQUE's controlled state. It occurs only after the applicable control conditions have been satisfied.

---

## 3. Primary Runtime Lifecycle

```text
EVENT / INPUT
     ↓
Capture & Normalize
     ↓
Identify / Classify
     ↓
Assemble Relevant Controlled Context
     ↓
Relationship / Dependency Evaluation
     ↓
Authority / Condition Evaluation
     ↓
Reason if Required
     ↓
Form Proposal if Required
     ↓
Validate if Required
     ↓
Human Authorization if Required
     ↓
Transition Gate
     ↓
Execute if Required
     ↓
Observe Actual Effect
     ↓
Outcome / Completion Evaluation
     ↓
Controlled State Transition
     ↓
Provenance / History
     ↓
Audit if Triggered
     ↓
Persist
     ↓
Await Next Event
```

At any stage the lifecycle may branch into **blocked, indeterminate, deferred, rejected, failed, paused, recovery, or reconciliation** states.

---

## 4. Stage 0 — Runtime Entry

OPAQUE receives an event through an adapter or internal subsystem.

Possible sources:

- human interface;
- host application;
- AI reasoning interface;
- scheduled/temporal trigger;
- operation result;
- validation system;
- audit system;
- recovery system.

At entry, the runtime establishes an identifiable event with source, type, payload/reference, occurrence time when known, and current-state context.

Capture does not imply acceptance, authority, truth, or state change.

---

## 5. Stage 1 — Capture and Normalization

OPAQUE converts an external representation into a controlled internal representation while preserving the original source through provenance.

Normalization may identify source, assign runtime identity, normalize available timestamps, identify referenced objects, separate conversational language from formal project state, and preserve unknown values.

Normalization must not silently convert uncertainty into certainty.

---

## 6. Stage 2 — Identification and Classification

OPAQUE determines what the event is relevant to and what kind of information it contains.

Potential classifications include observation, question, proposal, correction, instruction, determination, validation result, operation request/result, failure, exception, emotional expression, project-state candidate, procedural signal, or unresolved matter.

AI may assist semantic classification, but its result remains a candidate until incorporated through the applicable control path.

The lifecycle therefore follows:

**identify → classify → preserve uncertainty → continue processing**

not:

**AI labels it → OPAQUE treats the label as fact.**

---

## 7. Stage 3 — Controlled Context Assembly

Before reasoning or control evaluation, OPAQUE assembles the context relevant to the current processing request.

Relevant context can include current controlled state, affected objects, relationships, dependencies, requirements, prior determinations, provenance, active operations, unresolved matters, work position, temporal state, validation status, and recovery state.

OPAQUE must distinguish **available project information** from **context required for this decision**. Relevant context should be selected by control relevance rather than indiscriminately loading the entire project.

---

## 8. Stage 4 — Relationship and Dependency Evaluation

The Control Graph is consulted for direct relationships, dependencies, prerequisite status, downstream effects, conflicts, affected work, and validation consequences.

A relationship does not automatically constitute a blocking dependency.

A dependency does not automatically determine authority.

If required dependency information is unavailable, OPAQUE preserves an unresolved or indeterminate condition rather than inventing satisfaction.

---

## 9. Stage 5 — Authority and Condition Evaluation

OPAQUE evaluates whether the proposed processing path is allowed under established governance.

The runtime must distinguish:

```text
proposed
  ≠ authorized
  ≠ executing
  ≠ completed
  ≠ validated
```

Questions include whether authority applies, prerequisites are satisfied, human authorization is required, the object is in a valid state for the operation, and known constraints are respected.

Where authority cannot be determined from established governance, OPAQUE must not invent a precedence rule. It records the unresolved condition and follows the applicable governed disposition when one exists.

---

## 10. Stage 6 — AI Reasoning Request

When semantic reasoning is necessary, F-09 receives a controlled request containing the processing identity, purpose, relevant controlled context, uncertainty, constraints, requested output type, and provenance references.

Possible outputs include identification/classification candidates, interpretations, relationship/dependency candidates, conflict analysis, impact analysis, feasibility assessment, convergence assessment, and procedural recommendations.

AI output remains separate from authoritative state:

**request → model reasoning → structured result → control evaluation**

AI reasoning is an input to control, not the control authority itself.

---

## 11. Stage 7 — Proposal Formation

Where reasoning identifies a possible action or state change, OPAQUE forms a non-authoritative proposal containing the proposed change, affected objects, current/proposed state, rationale, evidence, dependencies, consequences, uncertainty, validation needs, authority basis, and originating reasoning/event.

Rejected proposals remain historically meaningful where materially relevant.

---

## 12. Stage 8 — Validation Gate

Validation is invoked when required by the applicable control path.

OPAQUE must distinguish:

```text
observed
  ≠ determined
  ≠ proposed
  ≠ validated
```

Validation may concern evidence, semantic interpretation, requirement satisfaction, operation results, completion conditions, consistency, integrity, or external effects.

If validation cannot be completed, the runtime records incomplete or indeterminate validation rather than converting unavailable validation into a pass.

---

## 13. Stage 9 — Human Authorization Gate

Human authorization is invoked where established authority requires it.

The human interface should expose the relevant proposed transition, current state, evidence, dependencies, consequences, uncertainty, validation status, unresolved matters, affected work, and recovery implications where relevant.

Possible decisions include authorize, reject, correct, defer, or request additional information.

Conversational wording alone does not automatically constitute formal authorization.

---

## 14. Stage 10 — Transition Gate

F-03 and F-01 perform the final controlled transition evaluation.

Possible outcomes:

- **Allowed** — progression may proceed.
- **Blocked** — the transition cannot proceed under the current state.
- **Indeterminate** — a necessary condition cannot be established.
- **Deferred** — the transition is intentionally held.
- **Rejected** — the proposal/operation is explicitly refused under applicable authority.
- **Superseded** — the proposal is no longer applicable because a governed change replaced it.

Material disposition is itself part of provenance/history.

---

## 15. Stage 11 — Operation Execution

If permitted, F-04 starts the operation. Operation state remains distinct from resulting controlled project state.

Candidate operation states are:

```text
proposed → authorized → ready → active → paused/completed/failed/cancelled/blocked
```

The operation records its identity, authorization basis, start time, expected output, completion condition, dependencies, affected objects, and current operation state.

---

## 16. Stage 12 — Observation of Actual Effect

OPAQUE records what actually happened rather than assuming the expected effect occurred.

The runtime distinguishes:

```text
expected effect
  ≠ actual effect
  ≠ interpreted effect
  ≠ validated effect
```

An operation can execute successfully at the technical level while producing an unexpected or partial result.

---

## 17. Stage 13 — Failure and Partial-Effect Path

Material execution failure follows a first-class lifecycle:

```text
pre-operation state
  ↓
operation attempt
  ↓
actual effect
  ↓
failure / partial effect
  ↓
failure classification
  ↓
containment
  ↓
recovery decision
  ↓
recovery operation
  ↓
resulting controlled state
```

OPAQUE preserves the pre-operation state, attempted operation, failure event, actual effect, partial changes, known inconsistency, recovery point, recovery action, and resulting state.

Failure does not automatically authorize its own recovery.

---

## 18. Stage 14 — Outcome Formation

F-06 forms an outcome representation answering what actually happened, what changed, what did not change, whether the completion condition was met, what remains uncertain, and what evidence supports the result.

Outcome formation is not itself a controlled state transition.

---

## 19. Stage 15 — Completion Evaluation

Completion is evaluated against the governed completion condition.

OPAQUE must not equate:

- activity with completion;
- elapsed time with completion;
- AI confidence with completion;
- user satisfaction with completion;
- absence of an error message with completion.

A work unit becomes complete only when its governed completion condition is satisfied.

If a completed item later becomes materially invalid or reopened, the new state must be governed and recorded.

---

## 20. Stage 16 — Controlled State Transition

Once required gates are satisfied, F-01 commits the controlled state transition.

The transition records:

- previous state;
- resulting state;
- transition identity;
- initiating event;
- operation/outcome reference;
- authority basis;
- validation basis where applicable;
- timestamp;
- provenance;
- disposition.

This is the authoritative state-change boundary.

Everything before it is processing, evidence, reasoning, proposal, authorization, or operation state.

---

## 21. Stage 17 — Provenance and History Commit

F-07 preserves the material chain leading to the current state:

```text
source/event
  ↓
interpretation
  ↓
proposal
  ↓
dependency/authority evaluation
  ↓
validation
  ↓
authorization
  ↓
operation
  ↓
actual result
  ↓
outcome
  ↓
state transition
```

Not every event requires every stage. Materially relevant links must remain reconstructable.

---

## 22. Stage 18 — Audit Trigger Evaluation

F-11 evaluates whether an audit is required after a material event/state change or another configured trigger.

Possible triggers include material state changes, failures, unresolved dependencies, contradictions, validation failures, recovery, repeated process failure, milestone boundaries, convergence checkpoints, continuity/momentum signals, integrity concerns, or explicit human requests.

Audit is conditional; expensive semantic auditing should not be assumed for every trivial event.

---

## 23. Stage 19 — Persistence Boundary

Durable persistence should occur around material integrity boundaries, including:

1. event capture;
2. material proposal/disposition;
3. authorization decision;
4. operation start;
5. operation completion/failure;
6. controlled state transition;
7. recovery point;
8. audit result;
9. material interruption/resumption.

Exact transaction semantics remain later implementation work.

The architectural rule is:

**A restart must not require reconstructing authoritative state from conversational memory.**

---

## 24. Interruption Model

OPAQUE assumes processing can stop at any point because of application closure, model failure, network loss, host crash, human interruption, intentional pause, unresolved external execution, or other causes.

A recovery point preserves:

- current controlled state reference;
- current operation;
- current processing stage;
- completed stages;
- uncompleted stages;
- pending requests;
- blockers;
- unresolved matters;
- dependencies;
- first next action.

Conversation continuity alone is insufficient.

---

## 25. Restart and Resume

After restart, OPAQUE should:

```text
load durable state
  ↓
identify unfinished runtime work
  ↓
check state consistency
  ↓
determine whether external effects may have occurred
  ↓
reconcile known results
  ↓
restore pending operations
  ↓
resume from controlled recovery point
```

If an external effect cannot be established, the runtime preserves uncertainty instead of assuming success, failure, or no change.

---

## 26. Event-Driven Rather Than Continuously Active

OPAQUE does not need to remain continuously active merely to remain in control.

A better baseline is:

```text
Persistent State
      ↓
Event arrives
      ↓
OPAQUE processes
      ↓
State/result persisted
      ↓
OPAQUE waits
      ↓
Next event
```

This reduces runtime cost, simplifies recovery, permits selective AI invocation, and keeps OPAQUE valid without an open conversational session.

A continuously running component may later be justified for particular functions, but it is not a foundational architectural requirement.

---

## 27. Synchronous and Asynchronous Processing

OPAQUE should support both.

### Synchronous

Suitable for fast deterministic checks such as state validity, dependency checks, transition eligibility, and basic completion conditions.

### Asynchronous

Suitable for AI reasoning, long-running external operations, delayed validation, pending human decisions, temporal triggers, pauses, and recovery/reconciliation.

Processing identity must survive asynchronous boundaries.

---

## 28. AI Processing Is Not the Runtime

AI reasoning is one mechanism inside the runtime:

```text
OPAQUE Runtime
│
├── deterministic control
├── persistent state
├── graph/dependency control
├── operation control
├── temporal control
├── provenance/history
├── failure/recovery
├── validation control
├── human decision interface
└── AI reasoning interface
          ↓
       AI / Model
```

The model can be unavailable without destroying OPAQUE's identity. A model can also return an incorrect interpretation without directly rewriting controlled state.

---

## 29. Where OPAQUE Can Block

OPAQUE should block controlled progression wherever it has a deterministic basis, including unsatisfied dependencies, false transition conditions, absent authorization, ineligible operations, unmet completion conditions, required validation not being available, inconsistent controlled state, or incomplete recovery.

Where a host cannot technically prevent an external effect, OPAQUE should still record the effect, determine authorization status, classify the resulting state, prevent unauthorized completion from being represented as legitimate, and trigger reconciliation/recovery/audit where required.

---

## 30. Runtime Invariants

### RI-001 — Capture Is Not Acceptance

An event can be captured without being authoritative.

### RI-002 — Reasoning Is Not Authority

AI output cannot itself authorize a controlled state transition.

### RI-003 — Proposal Is Not State

A proposal remains distinct from current controlled state.

### RI-004 — Execution Is Not Completion

Execution does not automatically establish completion.

### RI-005 — Determination Is Not Validation

A conclusion may remain unvalidated.

### RI-006 — Failure Is State-Relevant

Material failure and partial effect remain represented.

### RI-007 — Restart Does Not Erase State

Durable controlled state survives conversational/session interruption.

### RI-008 — Unknown Remains Unknown

Missing temporal, validation, dependency, authority, or execution information is not fabricated.

### RI-009 — Material History Is Reconstructable

Material controlled changes remain traceable.

### RI-010 — Host Failure Does Not Become Legitimate OPAQUE State

A host-specific failure cannot silently become a valid project-state transition.

---

## 31. Runtime Processing Contract

The generic contract is:

```text
INPUT
 ↓
CAPTURE
 ↓
NORMALIZE
 ↓
IDENTIFY
 ↓
CLASSIFY
 ↓
ASSEMBLE RELEVANT CONTROLLED CONTEXT
 ↓
EVALUATE RELATIONSHIPS / DEPENDENCIES
 ↓
EVALUATE AUTHORITY / CONDITIONS
 ↓
REASON IF REQUIRED
 ↓
FORM PROPOSAL IF REQUIRED
 ↓
VALIDATE IF REQUIRED
 ↓
AUTHORIZE IF REQUIRED
 ↓
TRANSITION GATE
 ↓
EXECUTE IF REQUIRED
 ↓
OBSERVE ACTUAL EFFECT
 ↓
FORM OUTCOME
 ↓
EVALUATE COMPLETION
 ↓
COMMIT CONTROLLED STATE TRANSITION
 ↓
RECORD PROVENANCE / HISTORY
 ↓
AUDIT IF TRIGGERED
 ↓
PERSIST
 ↓
WAIT FOR NEXT EVENT
```

The lifecycle may branch, loop, pause, fail, recover, reconcile, or terminate individual processing paths according to actual conditions.

---

## 32. Runtime Failure Matrix

| Failure point | Required response |
|---|---|
| Capture fails | Preserve failure; do not report capture success |
| Normalization fails | Retain original input; processing remains incomplete |
| Identification uncertain | Preserve uncertainty; request reasoning/clarification where required |
| AI request fails | Preserve pending reasoning state; do not fabricate a result |
| AI result malformed | Reject/contain result; preserve raw response where appropriate |
| Dependency evaluation unavailable | Preserve indeterminate state; block where required |
| Authority cannot be established | Do not invent authority; preserve unresolved state |
| Validation fails | Preserve failure; prevent required transition |
| Human decision unavailable | Preserve pending authorization state |
| Operation cannot start | Preserve authorized-but-not-executed distinction |
| Operation partially executes | Record actual effect and partial state |
| Operation fails | Enter failure/recovery path |
| Outcome cannot be determined | Preserve indeterminate outcome |
| State transition fails | Preserve pre-transition state and transition failure |
| Persistence fails | Do not report durable commit; enter persistence recovery |
| Audit fails | Preserve audit-pending/failed state where material |
| Runtime stops | Resume from durable recovery point |

---

## 33. Relationship to F-01–F-12

| Runtime stage | Primary subsystem(s) |
|---|---|
| Capture / normalization | F-12 + F-01 |
| Identification / classification | F-06 + F-09 |
| Context assembly | F-01 + F-02 + F-07 |
| Relationship/dependency evaluation | F-02 |
| Authority/condition evaluation | F-03 |
| Reasoning | F-09 |
| Human decision | F-10 |
| Validation | F-06 |
| Transition gate | F-03 + F-01 |
| Operation execution | F-04 + F-12 |
| Temporal recording | F-05 |
| Failure/recovery | F-08 |
| Outcome | F-06 + F-04 |
| State transition | F-01 |
| Provenance/history | F-07 |
| Audit | F-11 |
| Persistence | F-01 + F-07 + implementation adapter |
| Host integration | F-12 |

The mapping does not require each subsystem to be a separate process or software package.

---

## 34. What This Means for the Executable Layer

The executable implementation should not primarily be a continuously awake diary.

Its central role is to implement runtime control:

- receive events;
- load controlled state;
- evaluate deterministic conditions;
- invoke reasoning when required;
- preserve intermediate states;
- gate transitions;
- track operations;
- record time;
- persist material state;
- recover interrupted work;
- invoke audits;
- communicate with host systems.

The written specification remains necessary, but it is not the runtime itself.

---

## 35. What This Means for the Written Layer

The written layer explains what OPAQUE is, what it must preserve, why controls exist, what requirements exist, what remains unresolved, and how implementation decisions are justified.

The runtime should not depend on rereading the entire specification for every event.

The intended chain is:

**specification → implementation architecture → executable control**

with traceability between them.

---

## 36. What This Means for SillyTavern

SillyTavern remains a host adapter, not the OPAQUE runtime definition.

Conceptually:

```text
SillyTavern
    ↓
F-12 Host Adapter
    ↓
OPAQUE Runtime
    ├── controlled state
    ├── dependency/control evaluation
    ├── AI reasoning
    ├── operation management
    ├── persistence
    └── audit/recovery
    ↓
F-12 Host Adapter
    ↓
SillyTavern
```

The OPAQUE runtime model should remain conceptually valid if the host changes.

SillyTavern-specific APIs therefore belong to later host-adapter and feasibility work.

---

## 37. Runtime State Categories

The runtime should keep these categories conceptually distinct:

- **Controlled state** — what OPAQUE currently recognizes as authoritative.
- **Processing state** — where OPAQUE is in handling an event/request.
- **Operation state** — what an executable operation is doing.
- **Evidence state** — what has been observed or supplied as evidence.
- **Reasoning state** — what AI/semantic analysis has proposed or determined.
- **Authorization state** — whether relevant action has been authorized.
- **Validation state** — whether required validation occurred and its result.
- **Recovery state** — whether interrupted/failed processing requires recovery or reconciliation.

These categories may later share storage, but they should not be collapsed conceptually.

---

## 38. Runtime Boundary Principle

The runtime maintains a strict distinction between:

```text
information entering OPAQUE
        ↓
OPAQUE interpretation
        ↓
OPAQUE proposal
        ↓
OPAQUE authorization
        ↓
OPAQUE operation
        ↓
OPAQUE observation
        ↓
OPAQUE validation
        ↓
OPAQUE state
```

Each boundary answers a different question and provides a practical expression of I-001 Distinction Preservation.

---

## 39. Stage VII-C Completion Condition

Stage VII-C is complete when the architecture can explain the lifecycle of a materially relevant runtime event from entry through capture, normalization, identification, classification, controlled context, dependency/relationship evaluation, authority/condition evaluation, reasoning, proposal, validation, human authorization, transition gating, execution, observation, outcome, completion, controlled state transition, provenance/history, persistence, audit, interruption, failure, recovery, restart, and resumption without requiring technology-specific decisions or inventing substantive governance.

**Current determination: Stage VII-C meets this condition.**

The runtime lifecycle is sufficiently defined to proceed to the next architectural question: the exact controlled-state/data architecture and persistence model.

---

## 40. Next First Action

**Stage VII-D — Controlled State & Data Architecture**

Determine:

> **What exact information must exist in OPAQUE's durable state, how the 14 control concepts and 12 functional subsystems are represented, what records are immutable/history-bearing versus mutable/current, how provenance and relationships are represented, and what the minimum persistent state must be for safe restart and recovery?**

Technology selection should remain deferred until the state model is sufficiently defined.
