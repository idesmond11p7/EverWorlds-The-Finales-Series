# OPAQUE — Stage VII-F Enforcement, Intervention & Control Mechanism Architecture

## Status

**Architectural analysis — provisional.**

Stage VII-F defines how OPAQUE controls become operational mechanisms.

This document does not select JavaScript APIs, SillyTavern hooks, databases, UI libraries, model providers, or final implementation technologies. It does not resolve or ratify unresolved governance matters.

## 1. Architectural Finding

OPAQUE cannot achieve its purpose through documentation and AI reasoning alone.

Its rules must be connected to mechanisms that can:

- observe;
- evaluate;
- gate;
- block;
- permit;
- intervene;
- record;
- recover;
- escalate;
- reconcile;
- audit.

However, not every OPAQUE rule requires blocking.

The correct architecture is therefore a **graduated control model** rather than one universal enforcement mechanism.

~~~text
CONTROL REQUIREMENT
        ↓
CONTROL TYPE
        ↓
observe / advise / verify / gate / block / intervene / recover
        ↓
mechanism
        ↓
recorded result
        ↓
continued or altered processing
~~~

## 2. Control Classes

OPAQUE should distinguish at least seven operational control classes.

### EC-01 Inform

The system records or presents relevant information without preventing operation.

Examples:

- informational uncertainty;
- non-blocking audit finding;
- contextual explanation;
- low-materiality observation.

### EC-02 Observe

The system monitors an event, state, process, or condition.

Observation does not itself modify state.

### EC-03 Verify

The system checks whether a condition, reference, dependency, schema, state version, or completion condition is satisfied.

Verification produces a finding, not necessarily a state transition.

### EC-04 Gate

The system determines whether processing may proceed past a controlled point.

A gate may produce:

- pass;
- fail;
- blocked;
- unresolved;
- awaiting authority;
- awaiting validation;
- awaiting external condition.

### EC-05 Block

The system prevents a governed operation from proceeding when the applicable control condition requires prevention.

Blocking should preserve the reason and relevant state.

### EC-06 Intervene

The system changes the immediate processing path without silently changing authoritative project meaning.

Examples:

- request human decision;
- request missing information;
- route to validation;
- trigger reconciliation;
- defer;
- retry;
- switch reasoning path.

### EC-07 Recover

The system restores controlled processing after interruption or failure using a preserved recovery point and without bypassing required gates.

These classes may coexist for one control.

## 3. Enforcement Is Not One Layer

OPAQUE enforcement should be distributed according to the nature of the control.

~~~text
                    OPAQUE CONTROL
                         │
       ┌─────────────────┼─────────────────┐
       ▼                 ▼                 ▼
   deterministic       AI-assisted        human
     controls           analysis         authority
       │                 │                 │
       └─────────────────┼─────────────────┘
                         ▼
                 controlled workflow
                         │
                    host adapter
~~~

The architecture must not place all enforcement inside the AI prompt.

Likewise, deterministic code must not be expected to perform semantic reasoning it cannot reliably perform.

## 4. Deterministic Enforcement Boundary

Deterministic mechanisms are appropriate when a control can be expressed operationally without requiring open-ended semantic judgment.

Strong candidates include:

- identity resolution;
- schema validation;
- state-version comparison;
- dependency status checks where dependency conditions are structured;
- required-field checks;
- completion-condition checks when formally represented;
- authorization-record presence;
- validation-record presence;
- operation eligibility;
- temporal calculations;
- deadline/overdue calculations;
- persistence integrity;
- recovery-point existence;
- duplicate-event detection;
- transaction integrity;
- stale-result detection;
- immutable-history preservation.

These controls should not be delegated to model judgment when deterministic evaluation is possible.

## 5. AI-Assisted Enforcement Boundary

Some controls require semantic interpretation.

AI may assist with:

- identifying whether text appears to contain a contradiction;
- interpreting whether feedback may affect a requirement;
- identifying potentially relevant dependencies;
- assessing semantic impact;
- classifying an interaction;
- identifying likely missing context;
- evaluating qualitative feasibility;
- identifying possible causes of process degradation;
- analyzing whether additional exploration may materially help.

The AI result remains a candidate finding.

A deterministic or human-controlled mechanism determines what happens next.

## 6. Human Intervention Boundary

Human involvement is appropriate where the governed process requires human authority or where semantic uncertainty cannot safely be resolved automatically.

Possible intervention states include:

- awaiting human decision;
- awaiting clarification;
- awaiting authority;
- awaiting validation;
- unresolved;
- conflict requiring adjudication;
- exception requiring authorized handling.

The intervention mechanism should preserve the exact state that caused the intervention.

## 7. Gate Architecture

A gate is a controlled decision point in runtime processing.

Conceptually:

~~~text
PROCESS
  ↓
GATE INPUT
  ├── current state
  ├── operation/request
  ├── conditions
  ├── dependencies
  ├── authority
  ├── validation
  ├── unresolved matters
  └── relevant evidence
        ↓
   GATE EVALUATION
        ↓
 ┌──────┼───────────────┐
 ▼      ▼               ▼
PASS   BLOCK          INTERVENE
~~~

A gate must not invent a missing governance rule.

If the applicable rule is genuinely unresolved, the correct result may be **unresolved/deferred** rather than an invented pass or block.

## 8. Block Architecture

Blocking is justified only where the applicable control condition requires preventing progression.

A block should preserve:

- blocked operation;
- triggering condition;
- relevant object/state;
- dependency or prerequisite;
- evidence/basis;
- timestamp;
- current processing state;
- next possible resolution path.

A block is not a failure of OPAQUE.

It is an explicit controlled state of processing.

## 9. Soft vs Hard Controls

OPAQUE should distinguish controls by consequence.

### Soft control

The system can continue while recording or presenting the finding.

### Hard control

The system cannot safely proceed until the condition is resolved or an applicable authorized path permits continuation.

The distinction should be based on the materiality and nature of the governed control, not on arbitrary UI preference.

Where the specification does not establish whether a control must be hard, the implementation must not silently invent that policy.

## 10. Control Decision Model

A control evaluation should conceptually produce:

~~~text
CONTROL RESULT
├── control_identity
├── subject
├── observed_state
├── required_condition
├── evaluation_basis
├── result
├── severity/materiality where governed
├── uncertainty
├── evidence
├── required_next_action
├── authority requirement
├── validation requirement
└── provenance
~~~

Possible result values:

- pass;
- fail;
- blocked;
- unresolved;
- indeterminate;
- awaiting authority;
- awaiting validation;
- stale;
- not applicable.

These are operational result categories, not new governance concepts.

## 11. Control Result ≠ State Change

A control may detect that a condition failed.

That does not automatically mean the controlled project state has changed.

~~~text
CONTROL FINDING
      ≠
STATE TRANSITION
~~~

A governed transition must still follow the transition mechanism.

This distinction prevents enforcement code from becoming an uncontrolled state mutation engine.

## 12. Operation Lifecycle

An executable operation should have a controlled lifecycle.

~~~text
requested
   ↓
identified
   ↓
eligible check
   ↓
dependency check
   ↓
authority check
   ↓
validation check where required
   ↓
authorized/executable
   ↓
executing
   ↓
observed
   ↓
completed / failed / partially completed
   ↓
outcome
   ↓
controlled transition where applicable
~~~

At every stage, the operation remains distinct from controlled project state.

## 13. Pre-Execution Gate

Before a material operation begins, OPAQUE should evaluate the conditions required for execution.

Candidate checks:

- target exists;
- target state is compatible;
- predecessor state is current;
- prerequisites are satisfied;
- dependencies are satisfied;
- required authority exists;
- required validation exists;
- operation is within scope;
- required resources are available;
- no blocking unresolved matter applies;
- temporal conditions are satisfied.

If a required condition fails, the operation should not silently proceed.

## 14. Post-Execution Verification

Execution success does not automatically imply successful controlled incorporation.

After execution:

~~~text
actual effect
    ↓
observe
    ↓
compare with expected result
    ↓
identify deviations
    ↓
validate where required
    ↓
determine resulting controlled state
~~~

This is particularly important when external systems can behave differently from the requested operation.

## 15. External Side Effects

OPAQUE may eventually interact with systems capable of real external effects.

Examples include:

- changing host state;
- writing files;
- sending messages;
- invoking model requests;
- modifying runtime configuration;
- creating or updating external records.

OPAQUE should distinguish:

**request → attempted effect → actual effect**

The system must not assume that a requested operation occurred merely because the request was issued.

Where an external effect cannot be rolled back, OPAQUE must record the observed result and reconcile controlled state accordingly.

## 16. Transaction Boundary

Material controlled state changes should have an integrity boundary.

Conceptually:

~~~text
READ CURRENT STATE
       ↓
EVALUATE CONTROL CONDITIONS
       ↓
AUTHORIZE / VALIDATE AS REQUIRED
       ↓
EXECUTE GOVERNED TRANSITION
       ↓
PERSIST TRANSITION + RESULTING STATE + PROVENANCE
       ↓
CONFIRM COMMIT
~~~

A failed commit must not be represented as a successful controlled transition.

## 17. Idempotency

Runtime mechanisms should account for duplicate delivery or repeated execution.

Where an operation is safely repeatable, the system may recognize the operation as already completed.

Where repetition could cause an unintended external effect, OPAQUE should require a controlled reconciliation decision rather than blindly retrying.

The exact idempotency strategy remains implementation work.

## 18. Concurrency Control

Two operations may attempt to modify related controlled state concurrently.

OPAQUE should therefore compare the expected predecessor state with current state before committing.

~~~text
PROCESS A ──┐
            ├── current state
PROCESS B ──┘
               ↓
        predecessor check
          ├── match → proceed
          └── mismatch → reconcile/block
~~~

A stale operation must not silently overwrite newer controlled state.

## 19. Intervention Routing

When a control cannot safely pass automatically, OPAQUE should route the process according to the reason.

~~~text
CONTROL FAILURE
      │
      ├── missing information → request information
      ├── semantic ambiguity → AI analysis / human clarification
      ├── authority missing → authorization path
      ├── validation missing → validation path
      ├── dependency unsatisfied → dependency path
      ├── stale state → reconciliation path
      ├── external failure → recovery path
      └── unresolved governance → unresolved/deferred path
~~~

This prevents every failure from becoming a generic error.

## 20. Recovery Architecture

Recovery must preserve the controlled recovery point defined in Stage VII-D.

~~~text
INTERRUPTION / FAILURE
        ↓
capture actual state
        ↓
capture processing position
        ↓
record partial effects
        ↓
identify blockers/unresolved matters
        ↓
persist recovery point
        ↓
resume / retry / defer / human intervention
        ↓
re-enter normal gates
~~~

Recovery must not be a hidden bypass channel.

## 21. Failure Containment

When a mechanism fails, OPAQUE should preserve the last known safe controlled state and separately record the failed processing attempt.

The system should distinguish:

- control failure;
- operation failure;
- persistence failure;
- AI failure;
- host failure;
- external-service failure;
- unknown outcome.

An unknown outcome must remain unknown until observed or otherwise governed.

## 22. Audit Trigger Architecture

Auditing should be conditional rather than continuously exhaustive.

Candidate triggers include:

- material state transition;
- failed gate;
- repeated operation failure;
- stale-state conflict;
- unresolved contradiction;
- material scope change;
- recovery;
- repeated AI failure;
- suspicious or anomalous state;
- milestone completion;
- interruption/resumption;
- controlled evolution;
- periodic review.

Exact trigger thresholds remain implementation and governance work where not already defined.

## 23. Control Hierarchy

OPAQUE should support nested control scopes.

~~~text
GLOBAL / SYSTEM
      ↓
PROJECT
      ↓
SUBSYSTEM
      ↓
GOVERNED OBJECT
      ↓
OPERATION
      ↓
INDIVIDUAL TRANSITION
~~~

A lower-level mechanism must not silently contradict a higher-level applicable constraint.

However, unresolved authority-precedence semantics remain governed by U-001 and must not be invented here.

## 24. Enforcement and AI Boundary

The AI should not be the final enforcement mechanism.

Instead:

~~~text
AI
 ↓
candidate finding / proposal
 ↓
OPAQUE deterministic checks
 ↓
human authority where required
 ↓
controlled operation
 ↓
state transition
~~~

AI can improve semantic detection.

OPAQUE retains control over whether detected information becomes operationally consequential.

## 25. Enforcement and SillyTavern Boundary

SillyTavern may expose hooks and APIs through which OPAQUE can observe or influence host behavior.

OPAQUE should not assume that every desired control is technically enforceable through the host.

The adapter should distinguish:

- host event observed;
- host operation requested;
- host operation actually executed;
- host operation outcome observed.

If a host-level action cannot be physically blocked, OPAQUE must still preserve controlled-state integrity and record the discrepancy.

OPAQUE therefore remains independent of SillyTavern's implementation limitations.

## 26. Prevention vs Detection

OPAQUE should distinguish:

**prevention** — stop an invalid operation before it occurs;

**detection** — identify an invalid or unexpected condition after or during occurrence;

**containment** — prevent further propagation;

**recovery** — restore controlled processing;

**reconciliation** — determine how actual external state relates to controlled state.

These are separate mechanisms.

A system that cannot prevent a condition may still detect, contain, reconcile, and recover from it.

## 27. Control Strength Escalation

A useful architecture should permit escalation without assuming that every finding starts as a hard block.

~~~text
observe
  ↓
verify
  ↓
warn / inform
  ↓
intervene
  ↓
gate
  ↓
block
  ↓
recover / reconcile
~~~

Escalation should be triggered by governed conditions, materiality, repeated failure, or other established criteria—not by arbitrary implementation preference.

## 28. No Silent Escalation

A soft finding must not silently become a hard block merely because implementation considers it convenient.

Likewise, a hard control must not silently be weakened to keep the workflow moving.

The control consequence must be traceable to an applicable rule, requirement, authorized determination, or governed implementation decision.

## 29. User-Facing Control Presentation

OPAQUE's internal enforcement can be complex while its user-facing presentation remains simple.

A blocked operation might present:

- what is blocked;
- why;
- what information/condition is missing;
- what can resolve it;
- what is currently preserved;
- whether human action is required.

The interface should not require the user to understand the internal control graph.

This follows R-038.

## 30. Control Logging

Material control evaluations should be reconstructable.

A control log should preserve where relevant:

- control identity;
- subject;
- input/current-state version;
- evaluation time;
- result;
- evidence;
- reasoning references;
- authority/validation references;
- resulting intervention;
- later disposition.

Control logs are evidence of process behavior, not automatically authoritative project state.

## 31. Enforcement Failure Matrix

| Failure | Immediate controlled response |
|---|---|
| missing required field | reject/return for completion |
| unresolved dependency | block or defer according to applicable control |
| stale state | reconcile/re-evaluate |
| missing authority | route to authorization |
| missing validation | route to validation |
| malformed AI result | reject/contain result |
| AI unavailable | defer/retry/alternate path |
| external operation failed | record failure and recover/reconcile |
| persistence failed | do not report transition as committed |
| unknown external outcome | preserve unknown and reconcile |
| recovery point unavailable | prevent unsafe resume |
| repeated non-convergence | route to convergence/intervention control |

The table describes operational response categories, not final governance decisions where those remain unresolved.

## 32. Enforcement Architecture in One View

~~~text
                         OPAQUE
                           │
                  CONTROLLED STATE
                           │
                 ┌─────────┴─────────┐
                 ▼                   ▼
          DETERMINISTIC            AI
             CHECKS             ANALYSIS
                 │                   │
                 └─────────┬─────────┘
                           ▼
                    CONTROL RESULT
                           │
          ┌────────────────┼────────────────┐
          ▼                ▼                ▼
        PASS             GATE            BLOCK
                           │
                           ▼
                      INTERVENTION
                           │
       ┌───────────────────┼───────────────────┐
       ▼                   ▼                   ▼
    HUMAN              VALIDATION          RECONCILIATION
       │                   │                   │
       └───────────────────┼───────────────────┘
                           ▼
                       OPERATION
                           │
                     actual effect
                           │
                  ┌────────┴────────┐
                  ▼                 ▼
               SUCCESS            FAILURE
                  │                 │
                  ▼                 ▼
               OUTCOME          RECOVERY
                  │                 │
                  └────────┬────────┘
                           ▼
                    STATE TRANSITION
                           │
                           ▼
                     AUDIT / HISTORY
~~~

## 33. Architectural Consequences

Stage VII-F establishes:

1. OPAQUE requires graduated control mechanisms rather than one universal enforcement layer.
2. Deterministic controls should enforce structurally expressible conditions.
3. AI should assist semantic detection and analysis, not act as the final enforcement authority.
4. Human intervention remains available where authority, ambiguity, validation, or unresolved matters require it.
5. Control findings remain distinct from state transitions.
6. Operation state remains distinct from controlled project state.
7. Prevention, detection, containment, recovery, and reconciliation are distinct capabilities.
8. External side effects must distinguish requested, attempted, and actual effects.
9. Material transitions require integrity-preserving persistence.
10. Stale operations cannot silently overwrite newer state.
11. Recovery cannot bypass governance.
12. SillyTavern is an adapter boundary; host limitations do not redefine OPAQUE.
13. Control strength cannot silently escalate or weaken.
14. Internal control complexity may exceed user-facing complexity.
15. Material control behavior must be auditable.
16. OPAQUE can remain meaningful even when prevention is technically impossible at the host boundary.

## 34. Stage VII-F Completion Condition

Stage VII-F is complete when the architecture defines:

- operational control classes;
- deterministic enforcement boundaries;
- AI-assisted control boundaries;
- human intervention boundaries;
- gates;
- blocking;
- intervention routing;
- operation controls;
- transaction integrity;
- concurrency/stale-state protection;
- external side-effect handling;
- failure containment;
- recovery;
- reconciliation;
- audit triggers;
- control escalation;
- host enforcement boundaries;
- user-facing control presentation.

**Current determination: Stage VII-F meets this condition.**

The architecture still does not select concrete APIs or technologies.

## 35. Next First Action

**Stage VII-G — OPAQUE Host Integration & SillyTavern Adapter Architecture**

Determine:

> **Exactly what OPAQUE must receive from a host, what it may request from a host, which SillyTavern capabilities can support those interfaces, which controls cannot be guaranteed by the host, and how EverWorlds remains governed by OPAQUE without making SillyTavern the definition of OPAQUE.**

The next stage should map the independent OPAQUE architecture onto the actual EverWorlds/SillyTavern execution environment.
