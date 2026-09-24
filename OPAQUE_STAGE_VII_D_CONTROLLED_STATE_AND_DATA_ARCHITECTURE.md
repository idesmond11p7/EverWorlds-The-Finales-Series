# OPAQUE — Stage VII-D Controlled State & Data Architecture

## Status

**Architectural analysis — provisional.**

Stage VII-D defines the information architecture OPAQUE requires to preserve controlled state, history, provenance, relationships, dependencies, operations, validation, recovery, and restart integrity.

This document does not select a database, programming language, serialization format, or final storage technology. It also does not ratify unresolved governance matters.

## 1. Architectural Finding

OPAQUE cannot safely operate from one undifferentiated “project state” object.

The runtime needs a **controlled state model composed of distinct record classes with explicit identity, status, relationships, provenance, authority, and lifecycle semantics**.

The minimum durable architecture should therefore separate:

- current controlled state;
- governed objects;
- state dimensions;
- events;
- processing records;
- proposals;
- operations;
- evidence;
- determinations;
- validation;
- authorization;
- changes/transitions;
- outcomes;
- provenance/history;
- dependencies/relationships;
- recovery points;
- audit records;
- unresolved matters;
- work/milestone state;
- temporal records.

These records may eventually share physical storage, but their conceptual distinctions must remain intact.

## 2. State Is Not One Thing

OPAQUE must distinguish:

### 2.1 Current Controlled State

The latest authoritative state OPAQUE recognizes.

### 2.2 Historical State

Prior controlled states retained so material changes can be reconstructed.

### 2.3 Processing State

The current position of an unfinished runtime process.

### 2.4 Operation State

The state of an authorized or executing work operation.

### 2.5 Evidence State

What has actually been observed or supplied.

### 2.6 Reasoning State

AI-generated or semantic analysis that has not necessarily become authoritative.

### 2.7 Authorization State

The status and basis of authority for a proposed action.

### 2.8 Validation State

Whether a relevant claim, result, or transition has been validated.

### 2.9 Recovery State

The information required to recover interrupted or failed processing.

Collapsing these into a single status field would destroy distinctions that the specification explicitly requires.

## 3. Governed Object as the Primary Identity Anchor

Every materially governed thing should have a stable identity.

A governed object should minimally have:

- object identity;
- object type;
- human-readable name/label where useful;
- lifecycle status;
- current-state reference;
- provenance reference;
- relevant relationships;
- relevant dependencies;
- creation/first-observed information where known;
- historical identity.

Examples may include requirements, work units, milestones, project components, specification items, decisions, unresolved matters, operations, external artifacts, validation subjects, and controlled system objects.

OPAQUE should not require every conceivable object type to be predefined before operation. New object types may be introduced through controlled evolution.

## 4. State as Dimensions Rather Than a Single Label

A governed object may simultaneously have multiple material state dimensions.

For example, a work unit may be:

- execution: active;
- authorization: authorized;
- validation: pending;
- dependency: blocked;
- recovery: clear.

Therefore a single global status such as “active” is insufficient.

A state representation should permit:

**object → state dimension → value → basis → timestamp/provenance**

State values should retain their semantic basis where material.

## 5. Candidate Core Record Model

A conceptual controlled-state record can be represented as:

~~~text
STATE RECORD
├── state_identity
├── governed_object_identity
├── state_dimension
├── state_value
├── status
├── effective_time
├── recorded_time
├── basis
├── authority_reference
├── validation_reference
├── provenance_reference
├── predecessor_state
└── transition_reference
~~~

The exact fields are architectural candidates, not final schema commitments.

## 6. Current State vs History

OPAQUE should not repeatedly overwrite the only copy of current state.

Instead:

~~~text
Current State
     ↓
controlled transition
     ↓
New State
     ↓
History
(previous states, transitions, material basis)
~~~

Current state can be optimized for retrieval.

History must be optimized for reconstruction and traceability.

The two may share storage infrastructure, but they serve different purposes.

## 7. Immutable vs Mutable Information

OPAQUE requires a deliberate distinction between records that represent historical facts about what occurred and records representing current mutable processing state.

### Strong candidates for immutable/history-bearing records

- captured events;
- authorization decisions;
- material state transitions;
- material outcomes;
- validation results;
- failure records;
- material audit findings;
- provenance links;
- historical state versions.

### Strong candidates for mutable current-state records

- active processing status;
- pending request status;
- current operation status;
- recovery status;
- current UI/work position;
- scheduling state.

A mutable record may change, but material prior versions must remain reconstructable where required.

## 8. Event Record

The event record is the durable entry point for runtime processing.

Conceptually:

~~~text
EVENT
├── event_identity
├── source
├── event_type
├── original_payload/reference
├── occurrence_time
├── capture_time
├── related_objects
├── provenance
└── processing_status
~~~

Important distinctions:

- occurrence time ≠ capture time;
- source ≠ authority;
- payload ≠ determination;
- event ≠ state change.

Unknown values remain explicitly unknown.

## 9. Processing Record

A processing record tracks what OPAQUE is currently doing with an event/request.

It should identify:

- processing identity;
- triggering event;
- current stage;
- status;
- input references;
- relevant context references;
- pending AI request if any;
- pending human decision if any;
- blockers;
- unresolved matters;
- next action;
- recovery point.

This allows runtime recovery without reconstructing the process from conversation.

## 10. Proposal Record

A proposal is a non-authoritative candidate change.

Conceptually:

~~~text
PROPOSAL
├── proposal_identity
├── target_object(s)
├── current_state_reference
├── proposed_state
├── rationale
├── evidence
├── dependencies
├── consequences
├── uncertainty
├── required_validation
├── required_authority
├── originating_reasoning
└── disposition
~~~

The proposal must remain distinct from the resulting state.

## 11. Operation Record

An operation represents governed execution.

It should minimally identify:

- operation identity;
- operation type;
- initiating proposal/request;
- authorization basis;
- target object(s);
- prerequisites;
- dependencies;
- expected output;
- completion condition;
- current operation state;
- start/end times when known;
- actual result reference;
- failure/recovery references.

Operation state must not be used as a substitute for project state.

## 12. Evidence Record

Evidence records what is known to have been observed or supplied.

Conceptually:

~~~text
EVIDENCE
├── evidence_identity
├── source
├── content/reference
├── observation_time
├── capture_time
├── scope
├── reliability/limitations where established
└── provenance
~~~

Evidence should not automatically contain an interpretation.

This preserves:

**evidence → interpretation → determination**

as distinct stages.

## 13. Determination Record

A determination records a conclusion or interpretation derived from evidence/reasoning.

It should preserve:

- determination identity;
- subject;
- statement;
- basis;
- evidence references;
- reasoning reference;
- uncertainty;
- scope;
- status;
- validation status.

A determination can therefore exist without being validated.

## 14. Validation Record

Validation should be a distinct record because validation answers a different question from determination.

Conceptually:

~~~text
VALIDATION
├── validation_identity
├── subject
├── criteria
├── scope
├── evidence
├── method/reference
├── result
├── limitations
├── validator/authority reference
├── time
└── status
~~~

The exact meaning of “validator/authority” remains subject to U-004 and must not be invented here.

## 15. Authorization Record

Authorization should not be inferred from the existence of a proposal or AI output.

An authorization record should identify:

- authorization identity;
- subject/proposal/operation;
- authority basis;
- decision;
- decision source;
- decision time;
- scope;
- conditions;
- expiration if applicable and governed;
- provenance.

This provides the boundary between:

**proposed → authorized**

without resolving unresolved authority precedence rules.

## 16. Transition Record

A controlled state change requires an explicit transition record.

Conceptually:

~~~text
TRANSITION
├── transition_identity
├── governed_object
├── predecessor_state
├── resulting_state
├── triggering_event
├── proposal
├── authority
├── validation
├── operation/outcome
├── disposition
├── effective_time
├── recorded_time
└── provenance
~~~

The transition is the authoritative bridge between historical and current state.

## 17. Outcome Record

An outcome represents what an operation or process actually produced.

It should preserve:

- expected result;
- actual result;
- deviations;
- affected objects;
- evidence;
- completion-condition result;
- uncertainty;
- validation status;
- originating operation.

An outcome does not automatically mean the operation completed successfully.

## 18. Relationship and Dependency Model

OPAQUE should use a common underlying graph mechanism while retaining distinct semantic types.

Conceptually:

~~~text
OBJECT A
  ├── relationship ──► OBJECT B
  └── dependency ────► OBJECT C
                         └── prerequisite state
~~~

A graph edge should minimally identify:

- source object;
- target object;
- edge type;
- status;
- basis/provenance;
- creation/change identity;
- conditions where applicable.

This permits relationship and dependency to share infrastructure without becoming the same concept.

## 19. Dependency Record

A dependency should explicitly identify:

- dependent object;
- prerequisite object;
- dependency type;
- satisfaction condition;
- current satisfaction status;
- blocking status;
- basis/provenance;
- affected operation/work.

An unsatisfied dependency should not be represented as satisfied merely because a model believes it is likely satisfied.

## 20. Provenance Model

Provenance must permit backward and forward traceability.

A conceptual provenance chain is:

~~~text
SOURCE
  ↓
EVENT
  ↓
INTERPRETATION / REASONING
  ↓
PROPOSAL
  ↓
AUTHORITY / VALIDATION
  ↓
OPERATION
  ↓
OUTCOME
  ↓
STATE TRANSITION
  ↓
CURRENT STATE
~~~

Provenance links should answer:

- where did this information originate?
- what transformed it?
- what reasoning affected it?
- what decision incorporated it?
- what state resulted?
- what later material state depends on it?

Provenance is not itself authority.

## 21. Unresolved Matter Record

Because U-001–U-012 remain unresolved, the data architecture must represent unresolved matters without pretending they are settled.

An unresolved record should identify:

- matter identity;
- question;
- affected objects;
- current impact;
- dependencies;
- blocking status where established;
- evidence;
- proposed resolutions;
- status;
- provenance.

This allows OPAQUE to continue controlled operation while preserving incompleteness.

## 22. Recovery Point Model

A recovery point is a durable representation of where interrupted processing can resume.

It should preserve:

~~~text
RECOVERY POINT
├── recovery_identity
├── controlled_state_reference
├── processing_reference
├── operation_reference
├── current_stage
├── completed_stages
├── pending_stages
├── blockers
├── unresolved_matters
├── pending_external_effects
├── first_next_action
├── recorded_time
└── provenance
~~~

The recovery point must not itself authorize bypassing an unfinished gate.

## 23. Audit Record

An audit record should preserve:

- audit identity;
- trigger;
- scope;
- target state/process;
- checks performed;
- findings;
- evidence;
- AI reasoning references where applicable;
- disposition;
- resulting procedural action;
- time;
- provenance.

Audit findings remain distinct from automatic state modification.

## 24. Work and Milestone State

Because R-044 and R-041 govern execution, OPAQUE needs durable work-unit information.

A work unit should preserve:

- work identity;
- objective;
- scope;
- inputs;
- expected output;
- prerequisites;
- dependencies;
- authority;
- completion condition;
- current status;
- carried material;
- unresolved material;
- originating Scheme reference;
- provenance.

Milestones should preserve:

- milestone identity;
- completion condition;
- affected work;
- dependencies;
- current status;
- completion evidence;
- validation status;
- temporal information.

## 25. Temporal Data

Temporal information must preserve distinctions required by R-045.

A time-bearing record should distinguish where relevant:

~~~text
planned time
occurrence time
capture time
start time
end time
duration
deadline
overdue state
interruption time
resumption time
~~~

OPAQUE must never replace an unknown actual time with a planned time or inferred estimate without explicitly representing that transformation.

## 26. Controlled State Snapshot

For efficient runtime operation, OPAQUE may maintain a current snapshot assembled from durable records.

Conceptually:

~~~text
CURRENT CONTROLLED SNAPSHOT
├── active governed objects
├── current state dimensions
├── active relationships
├── active dependencies
├── unresolved matters
├── active operations
├── authorization status
├── validation status
├── recovery status
├── milestone/work status
└── relevant temporal state
~~~

The snapshot is an optimization/read model.

It must not become the only source of historical truth.

## 27. Minimum Safe Persistent State

OPAQUE's minimum safe durable state must be sufficient to restart without reconstructing authority or history from conversation.

At minimum it must preserve:

1. governed object identities;
2. current controlled state;
3. state dimensions;
4. material relationships;
5. material dependencies;
6. unresolved matters;
7. active processing records;
8. active operation records;
9. material evidence/determinations;
10. authorization records;
11. validation records;
12. material transitions;
13. provenance/history;
14. recovery points;
15. material temporal records;
16. work/milestone state;
17. audit/failure records where material.

If any of these are necessary to explain or safely resume a controlled process, they cannot exist only in conversational context.

## 28. Transactional Integrity Boundary

A material controlled transition should behave conceptually as one integrity unit:

~~~text
validate prerequisites
      ↓
authorize where required
      ↓
record transition
      ↓
record resulting state
      ↓
record provenance
      ↓
make current state reflect transition
~~~

The physical implementation may use transactions, event sourcing, versioned records, snapshots, or another mechanism.

The architecture only requires preservation of the integrity property.

A partial persistence failure must not create the false appearance that a transition was successfully committed when it was not.

## 29. Concurrency and Stale State

OPAQUE must account for the possibility that two processes operate against different versions of controlled state.

A conceptual transition therefore needs a predecessor-state reference.

Before committing:

~~~text
expected predecessor
        ↓
compare with current controlled state
        ↓
match → continue
mismatch → reconcile / block / re-evaluate
~~~

The architecture should not allow a stale proposal to silently overwrite a newer controlled state.

Exact conflict-resolution semantics remain later implementation work.

## 30. AI Context Is a Derived View

AI should not receive “the database” or “all of OPAQUE.”

F-09 should construct a controlled context view from durable state.

Conceptually:

~~~text
DURABLE OPAQUE STATE
        ↓
relevance selection
        ↓
constraint selection
        ↓
provenance selection
        ↓
uncertainty selection
        ↓
AI CONTEXT PACKAGE
        ↓
MODEL
~~~

AI context limits are an implementation constraint, while controlled state must remain independent of model context size.

## 31. Physical Storage vs Conceptual Data Model

OPAQUE should not prematurely decide that every conceptual record becomes a separate database table, file, class, or JSON document.

The correct order is:

**concept → record semantics → relationships → integrity rules → access patterns → physical representation**

Only later should implementation feasibility determine whether multiple records are physically consolidated.

## 32. Data Integrity Rules

### DI-001 — Identity Stability

A materially governed object retains its identity across state changes.

### DI-002 — State Separation

Current state is distinct from historical state.

### DI-003 — Proposal Separation

A proposal is not authoritative state.

### DI-004 — Evidence Separation

Evidence is not automatically an interpretation.

### DI-005 — Determination Separation

Determination is not automatically validation.

### DI-006 — Authorization Separation

A proposed or reasoned action is not automatically authorized.

### DI-007 — Operation Separation

Operation state is distinct from controlled project state.

### DI-008 — History Preservation

Material transitions remain reconstructable.

### DI-009 — Provenance Preservation

Material state can be traced backward and forward.

### DI-010 — Unknown Preservation

Unknown values remain unknown unless a governed determination establishes otherwise.

### DI-011 — Dependency Integrity

Dependencies cannot silently become satisfied.

### DI-012 — Stale-State Protection

A stale process cannot silently overwrite newer controlled state.

### DI-013 — Recovery Integrity

Recovery cannot bypass required governance.

### DI-014 — Persistence Integrity

The runtime cannot report a durable transition that was not durably committed.

## 33. Relationship to the 14 Core Concepts

| Core concept | Required data representation |
|---|---|
| C-01 Governed Object | stable object identity + object metadata |
| C-02 State | state records/dimensions + current snapshot |
| C-03 Authority | authorization + authority references |
| C-04 Condition | condition definitions/evaluations |
| C-05 Relationship | typed graph edges |
| C-06 Dependency | dependency records/edges |
| C-07 Operation | operation records + operation state |
| C-08 Determination | determination records |
| C-09 Validation | validation records |
| C-10 Change | transition/change records + history |
| C-11 Outcome | outcome records |
| C-12 Closure | closure/completion state + basis |
| C-13 Provenance | provenance graph/links |
| C-14 Controlled Incorporation | transition/integration records linking basis to state |

This confirms that the 14 concepts require distinct semantics but do not require fourteen physical storage systems.

## 34. Relationship to F-01–F-12

| Subsystem | Primary data responsibility |
|---|---|
| F-01 Controlled State Core | current state, state transitions, state identity |
| F-02 Control Graph | relationships, dependencies, affected-object graph |
| F-03 Authority & Transition Gate | conditions, authorization, transition eligibility |
| F-04 Operation & Work Controller | operations, work units, milestones, completion |
| F-05 Temporal Controller | timestamps, duration, deadlines, interruption/resumption |
| F-06 Evidence/Validation/Determination | evidence, determinations, validation, outcomes |
| F-07 Provenance/History | history, transitions, source links, reconstruction |
| F-08 Failure/Recovery | failures, partial effects, recovery points |
| F-09 AI Reasoning Interface | reasoning requests/results and derived context packages |
| F-10 Human Decision Interface | human decision records and interaction references |
| F-11 Audit/Process Control | audit records, findings, procedural responses |
| F-12 External Adapters | external identifiers, mappings, synchronization state |

## 35. Data Architecture in One View

~~~text
                    OPAQUE DURABLE STATE
                             │
       ┌─────────────────────┼─────────────────────┐
       ▼                     ▼                     ▼
 GOVERNED OBJECTS       CURRENT STATE         EVENT HISTORY
       │                     │                     │
       ├──────────┐          │          ┌──────────┤
       ▼          ▼          ▼          ▼          ▼
 RELATIONSHIPS DEPENDENCIES TRANSITIONS PROVENANCE AUDITS
       │          │          │          │          │
       └──────────┼──────────┼──────────┼──────────┘
                  ▼          ▼
              OPERATIONS   EVIDENCE
                  │          │
                  ▼          ▼
              OUTCOMES   DETERMINATIONS
                  │          │
                  └────┬─────┘
                       ▼
                   VALIDATION
                       │
                       ▼
                  AUTHORIZATION
                       │
                       ▼
                  RECOVERY / WORK
~~~

The diagram describes semantic relationships, not physical storage.

## 36. Architectural Consequence for Implementation

Stage VII-D establishes an important constraint on the eventual executable layer:

**The executable system should operate over a structured controlled-state model, not over free-form documents alone.**

The written OPAQUE specification remains the semantic authority for what the system is supposed to preserve.

The executable implementation requires machine-readable representations for what currently exists, what is pending, what occurred, what was proposed, what was authorized, what was validated, what changed, and what must be recovered.

This is the concrete bridge between:

**“the book”**

and

**“the JS.”**

Neither is sufficient alone.

## 37. Architectural Consequence for Memory

OPAQUE's controlled state should not be equated with model memory.

The model may receive a derived context package.

OPAQUE retains the durable controlled state independently.

Therefore:

~~~text
OPAQUE durable state
        ↓
controlled context
        ↓
AI reasoning
        ↓
candidate result
        ↓
OPAQUE control
        ↓
possible state transition
~~~

This is the mechanism by which OPAQUE can preserve continuity without depending on the model's conversational memory being perfect.

## 38. Stage VII-D Completion Condition

Stage VII-D is complete when the architecture identifies the minimum durable information required to represent the 14 core concepts, support the 12 functional subsystems, preserve current and historical state, maintain relationships/dependencies/provenance, support controlled transitions, and recover safely from interruption without requiring a technology-specific schema.

**Current determination: Stage VII-D meets this condition.**

The remaining questions are increasingly implementation-facing rather than foundational:

- exact physical schema;
- state-transition transaction mechanics;
- AI request/response contract;
- enforcement mechanism;
- host adapter contract;
- persistence technology;
- performance and context constraints.

## 39. Next First Action

**Stage VII-E — AI Reasoning Interface & Control Contract**

Determine:

> **Exactly what OPAQUE asks an AI to do, what structured information the AI may return, how uncertainty/confidence/provenance are represented, how model output is checked and contained, and exactly where AI reasoning stops and deterministic OPAQUE control begins.**

The next stage should define the AI boundary before choosing a model provider or prompt architecture.
