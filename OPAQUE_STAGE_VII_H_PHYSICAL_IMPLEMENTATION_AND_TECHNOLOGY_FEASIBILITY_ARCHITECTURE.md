# OPAQUE — Stage VII-H Physical Implementation & Technology Feasibility Architecture

## Status

**Architectural analysis — provisional.**

Stage VII-H translates the established OPAQUE architecture into a physically implementable system without turning implementation choices into OPAQUE governance.

It answers what becomes executable code, what remains specification/documentation, what must be durable machine-readable state, how persistence and adapters should be bounded, what SillyTavern can realistically support, and what constraints affect feasibility.

This document does **not** ratify OPAQUE, finalize every technology choice, or begin feature implementation.

---

## 1. Architectural Finding

The preceding stages establish that OPAQUE is neither:

- a book;
- a prompt;
- a persistent conversation;
- a single JavaScript module;
- a database alone;
- an AI agent;
- SillyTavern itself.

OPAQUE is a **hybrid controlled runtime system** whose parts have different physical forms.

The implementation boundary is therefore:

~~~text
OPAQUE GOVERNANCE / SPECIFICATION
        │
        ├── written specification
        ├── machine-readable schemas
        └── control rules
                │
                ▼
OPAQUE RUNTIME
        ├── deterministic control kernel
        ├── state/data services
        ├── event/processing lifecycle
        ├── AI reasoning interface
        ├── host adapter
        ├── persistence
        ├── audit/history/recovery
        └── presentation interface
                │
                ▼
        SILLYTAVERN HOST
                │
                ▼
        MODEL / EXTERNAL SERVICES
~~~

The system therefore has a **documentation layer, data layer, executable control layer, reasoning layer, integration layer, and presentation layer**.

---

## 2. Physical Responsibility Classes

Every important OPAQUE capability should have an explicit physical responsibility.

### PI-01 — Specification / Documentation

Contains:

- requirements;
- invariants;
- definitions;
- governance rules;
- unresolved matters;
- architectural decisions;
- control semantics;
- verification evidence;
- traceability references.

This is authoritative explanatory material, not runtime state.

### PI-02 — Machine-Readable Schema

Defines the shape and constraints of runtime records.

Examples:

- governed objects;
- state dimensions;
- dependencies;
- relationships;
- operations;
- determinations;
- validation;
- authorization;
- provenance;
- recovery points;
- audit records.

Schema is not itself the current state.

### PI-03 — Deterministic Runtime Code

Implements rules that can be evaluated reliably by software.

Examples:

- identity integrity;
- schema validation;
- state-version checks;
- dependency checks where structurally represented;
- required-field checks;
- authorization-record presence;
- completion-condition checks;
- temporal calculations;
- operation eligibility;
- transaction boundaries;
- persistence;
- recovery;
- history recording;
- stale-result detection.

### PI-04 — AI Reasoning

Handles semantic work where deterministic software is insufficient.

Examples:

- interpretation;
- semantic classification;
- ambiguity analysis;
- contradiction detection;
- qualitative dependency analysis;
- qualitative impact analysis;
- feedback interpretation;
- convergence analysis;
- feasibility analysis;
- controlled context construction.

AI output remains candidate reasoning until controlled by the runtime.

### PI-05 — Human Interface

Provides:

- authorization;
- rejection;
- correction;
- clarification;
- exception decisions;
- validation decisions where human authority is required;
- recovery decisions;
- visibility into blockers and uncertainty.

### PI-06 — Host Adapter

Translates OPAQUE operations/events to and from SillyTavern.

### PI-07 — Persistence

Stores durable controlled state, history, provenance, recovery information, and required configuration.

### PI-08 — Tests

Verify deterministic behavior, adapter contracts, data integrity, failure behavior, and AI containment.

---

## 3. What Actually Becomes JavaScript

The primary OPAQUE runtime implementation for the EverWorlds/SillyTavern target should become JavaScript.

The code should include the mechanisms that cannot be reliably represented by prose alone.

A conceptual implementation boundary is:

~~~text
OPAQUE JS
├── bootstrap / lifecycle
├── deterministic control kernel
├── state manager
├── relationship/dependency evaluator
├── operation controller
├── temporal controller
├── evidence/validation controller
├── provenance/history recorder
├── failure/recovery controller
├── AI interface
├── host adapter
├── persistence adapter
├── audit/process controller
└── presentation bridge
~~~

This is a **logical grouping**, not a requirement that every item become a separate file or package.

Over-fragmentation should be avoided.

---

## 4. What Does Not Become JavaScript

The following should remain primarily outside executable code:

- constitutional purpose;
- conceptual definitions;
- requirements;
- governance semantics;
- unresolved governance questions;
- rationale;
- verification evidence;
- architecture explanations;
- decision history;
- formal ratification records;
- human-readable operating documentation.

However, runtime code should implement **machine-readable representations** of rules where execution requires them.

The distinction is:

**documentation explains the rule; code enforces or evaluates the executable consequence of the rule.**

---

## 5. Machine-Readable State Is Mandatory

OPAQUE cannot operate safely if important controlled state exists only in prose.

At minimum, machine-readable durable state must represent:

- governed object identity;
- current state dimensions;
- state version;
- relationships;
- dependencies;
- unresolved matters;
- proposals;
- active processing;
- operation state;
- material evidence;
- determinations;
- validation records;
- authorization records;
- transitions;
- outcomes;
- provenance;
- recovery points;
- temporal information;
- work-unit/milestone state;
- material audit/failure information.

Conversation text may be an input or evidence source.

It is not a sufficient substitute for controlled state.

---

## 6. State vs Configuration

Configuration and controlled state must remain distinct.

### Configuration

Examples:

- extension preferences;
- UI preferences;
- enabled features;
- model/provider settings;
- host integration options;
- diagnostic settings.

Configuration may be changed through configuration mechanisms.

### Controlled State

Examples:

- authoritative project state;
- governed objects;
- requirements;
- decisions;
- unresolved matters;
- authorized transitions;
- validation;
- history;
- recovery state.

Configuration must not silently overwrite controlled state.

---

## 7. Persistence Boundary

The architecture requires durable storage independent of conversational context.

A conceptual persistence hierarchy is:

~~~text
OPAQUE RUNTIME
      │
      ▼
PERSISTENCE INTERFACE
      │
      ├── current controlled state
      ├── append/history records
      ├── provenance
      ├── recovery checkpoints
      ├── audit records
      └── configuration
      │
      ▼
PHYSICAL STORAGE
~~~

The physical storage technology is an implementation decision, not an OPAQUE governance rule.

For the initial SillyTavern target, candidate storage mechanisms include:

- extension settings for small configuration;
- host-supported metadata where appropriate;
- browser-local durable storage for structured OPAQUE state where suitable;
- files where export/import, portability, or human inspection materially requires them;
- other storage mechanisms if later feasibility analysis demonstrates a better fit.

No single host storage facility should be assumed sufficient merely because it exists.

---

## 8. Storage Selection Criteria

Physical storage should be selected against these requirements:

1. durability across extension reload;
2. durability across browser/session restart;
3. transactional or sufficiently atomic updates;
4. concurrency/stale-state handling;
5. structured querying;
6. recovery support;
7. versioning/migration;
8. export/import;
9. reasonable performance;
10. compatibility with SillyTavern deployment;
11. privacy/security characteristics;
12. manageable implementation complexity.

The storage decision should be made as an engineering decision against these criteria rather than by convenience alone.

---

## 9. Candidate Initial Storage Direction

A plausible initial implementation is a **local structured store behind a persistence abstraction**, rather than scattering state across host variables, extension settings, and message metadata.

The abstraction should permit later migration.

The exact physical choice between browser storage technologies should be finalized by implementation feasibility testing.

The architecture should therefore avoid hard-coding:

> “OPAQUE state lives in SillyTavern variables.”

or:

> “OPAQUE state lives in a collection of JSON files.”

Those may be mechanisms, not architecture.

---

## 10. Runtime Topology

The likely initial topology is:

~~~text
                    OPAQUE
                      │
        ┌─────────────┼─────────────┐
        ▼             ▼             ▼
 CONTROL KERNEL   STATE/DATA     PROCESSING
        │             │             │
        └─────────────┼─────────────┘
                      │
            ┌─────────┴─────────┐
            ▼                   ▼
       AI ADAPTER          HOST ADAPTER
            │                   │
            ▼                   ▼
        MODEL API          SILLYTAVERN
                                  │
                         ┌────────┼────────┐
                         ▼        ▼        ▼
                       chat    generation  UI
~~~

Persistence and audit/history are cross-cutting services around the runtime.

The architecture does not require a continuously running server.

A browser-resident extension runtime is sufficient as an initial execution model if storage and host APIs meet the required integrity conditions.

---

## 11. Event Bus / Processing Queue

OPAQUE should use an internal event/processing abstraction.

Conceptually:

~~~text
HOST / USER / AI / TIMER
          │
          ▼
      EVENT CAPTURE
          │
          ▼
   NORMALIZED EVENT
          │
          ▼
   PROCESSING QUEUE
          │
          ▼
 CONTROLLED LIFECYCLE
~~~

The queue need not initially be a distributed message broker.

For a browser extension, an in-process serialized processing queue may be sufficient.

The architectural requirement is not a particular queue technology.

The requirement is controlled ordering and processing of materially related events.

---

## 12. Processing Serialization

Material controlled-state transitions should not be allowed to race arbitrarily.

The initial runtime should provide a serialization boundary for operations affecting the same controlled state.

Conceptually:

~~~text
event A ─┐
event B ─┼──► serialized controlled processing ───► state transition
event C ─┘
~~~

Parallelism may still be used for independent AI reasoning or non-conflicting work.

Concurrency must not silently produce conflicting authoritative state.

---

## 13. Deterministic Kernel

The deterministic kernel is the most important executable boundary.

It should evaluate:

- identity validity;
- state validity;
- state version;
- relationship/dependency conditions where representable;
- operation eligibility;
- authority-record requirements;
- validation requirements;
- completion conditions;
- transition preconditions;
- temporal calculations;
- stale result detection;
- persistence success;
- recovery conditions;
- invariant preservation.

It should not attempt to replace AI semantic reasoning.

Its purpose is to enforce what software can reliably know and control.

---

## 14. AI Adapter

The AI adapter should implement the Stage VII-E contract.

Conceptually:

~~~text
OPAQUE
  │
  ▼
context builder
  │
  ▼
AI request
  │
  ▼
model/provider
  │
  ▼
AI result
  │
  ▼
schema + containment checks
  │
  ▼
candidate reasoning
  │
  ▼
control evaluation
~~~

The adapter must:

- version requests;
- identify the subject;
- restrict context;
- validate response structure;
- preserve uncertainty;
- preserve evidence/provenance references;
- reject malformed output;
- reject stale output where applicable;
- prevent direct state mutation by model output;
- preserve provider separation.

---

## 15. AI Provider Boundary

The physical architecture should permit an interchangeable AI provider.

~~~text
OPAQUE AI INTERFACE
        │
        ├── provider adapter A
        ├── provider adapter B
        └── future provider
~~~

OPAQUE should not contain provider-specific assumptions in its core control logic.

SillyTavern may invoke a provider independently; that does not eliminate the need for OPAQUE's own reasoning boundary where OPAQUE requires controlled analysis.

---

## 16. Host Adapter Implementation

The SillyTavern adapter should be a concrete JavaScript implementation of the Stage VII-G contract:

- Observe;
- Request;
- Confirm;
- Reconcile;
- Present.

The adapter should translate between:

**OPAQUE-native records**

and:

**SillyTavern-native events, objects, APIs, and UI mechanisms.**

Host-specific code should remain concentrated at the boundary.

---

## 17. SillyTavern Interface Feasibility

The existing architectural research indicates that SillyTavern exposes relevant extension surfaces including:

- event sources/event types;
- generation integration;
- extension prompt/context mechanisms;
- tokenization/counting;
- tool/function mechanisms;
- variables;
- message manipulation;
- metadata persistence;
- extension settings;
- workers;
- world information;
- character/group/chat state.

These provide plausible integration points for the adapter.

However, an available API does not automatically provide the guarantee OPAQUE may require.

Each required capability must be tested as:

~~~text
required control
      ↓
host mechanism
      ↓
actual interception/observation test
      ↓
guaranteed / best-effort / unsupported
~~~

The implementation must not infer guarantees from documentation alone.

---

## 18. Controls SillyTavern May Not Guarantee

The host should not be assumed capable of guaranteeing:

- interception of every externally initiated effect;
- prevention of every tool or host-side action;
- observation of every internal state mutation;
- deterministic enforcement of semantic truth;
- exclusive ownership of chat state;
- atomic durability for all OPAQUE records;
- complete prevention of state changes occurring outside OPAQUE;
- persistence across every host/browser failure mode.

Where guarantees are unavailable, OPAQUE must fall back to detection, containment, reconciliation, or explicit limitation.

---

## 19. Context / Token Constraint

EverWorlds ultimately operates through an LLM context window.

OPAQUE therefore must not attempt to inject all controlled state into every generation.

The architecture requires:

~~~text
controlled state
      ↓
relevance selection
      ↓
context compression / representation
      ↓
token-budget evaluation
      ↓
host generation context
~~~

The context package should be:

- task-relevant;
- bounded;
- provenance-aware;
- state-version aware;
- semantically faithful;
- explicit about uncertainty;
- separated from the underlying durable state.

This is essential to EverWorlds' internalization goal.

---

## 20. Internalization Implication

OPAQUE cannot itself guarantee that an LLM will psychologically “internalize” information.

What it can physically provide is a controlled mechanism that repeatedly supplies the model with relevant, state-consistent, appropriately prioritized information.

The architecture should therefore distinguish:

**OPAQUE guarantee:**

> controlled information selection, representation, consistency, provenance, and delivery.

from:

**model behavior:**

> whether the model actually reasons from that information as intended.

This distinction prevents an implementation promise that the runtime cannot prove.

---

## 21. UI / Presentation Layer

OPAQUE UI should be a presentation layer over controlled state.

The initial UI may include:

- current OPAQUE status;
- processing indicator;
- blockers;
- unresolved matters;
- pending decisions;
- validation requests;
- recovery state;
- synchronization status;
- relevant work/milestone state;
- audit findings;
- controlled warnings.

UI actions that affect authoritative state must route through the same control mechanisms as non-UI operations.

The UI must never directly mutate authoritative records.

---

## 22. Audit and History Storage

Audit/history should be physically distinct in purpose from current state.

Conceptually:

~~~text
CURRENT STATE
     │
     ├── current controlled records
     │
     ▼
HISTORY / PROVENANCE
     ├── prior state
     ├── transition
     ├── source
     ├── determination
     ├── validation
     ├── authorization
     └── outcome
~~~

History should preserve enough information to reconstruct materially relevant transitions.

The implementation should prefer append-oriented history for material changes.

---

## 23. Recovery / Checkpoint Mechanism

Recovery requires a durable checkpoint containing, at minimum:

- current controlled state reference/version;
- current work position;
- completed work;
- carried work;
- blockers;
- unresolved matters;
- active dependencies;
- pending operations;
- next first action;
- relevant temporal state.

A browser reload or extension restart should be recoverable from durable state rather than conversation memory.

---

## 24. Failure Containment

Physical implementation should treat failure as a controlled boundary.

Example:

~~~text
requested operation
      ↓
execution attempt
      ↓
actual effect
      ↓
success / partial / failure / unknown
      ↓
record actual result
      ↓
contain / reconcile / recover
~~~

A failed persistence write must not be reported as a successful state transition.

A failed host request must not be reported as a completed host effect.

A failed AI call must not corrupt controlled state.

---

## 25. Testing Architecture

Testing should be layered.

### T-01 Deterministic Unit Tests

Test:

- state transitions;
- dependency evaluation;
- temporal calculations;
- authorization gates;
- validation requirements;
- completion conditions;
- stale-state handling;
- serialization;
- persistence failure.

### T-02 Property / Invariant Tests

Test preservation of:

- I-001;
- runtime invariants;
- data integrity invariants;
- adapter invariants.

### T-03 Integration Tests

Test:

- OPAQUE ↔ persistence;
- OPAQUE ↔ AI adapter;
- OPAQUE ↔ SillyTavern adapter.

### T-04 Host Compatibility Tests

Test actual SillyTavern behavior for:

- event observation;
- generation interception/insertion;
- streaming;
- message lifecycle;
- tool lifecycle;
- metadata persistence;
- reload/restart;
- UI integration.

### T-05 Failure Tests

Intentionally simulate:

- missing events;
- duplicate events;
- stale state;
- failed persistence;
- interrupted generation;
- partial host effects;
- unavailable AI provider;
- malformed AI output;
- host reload;
- storage corruption.

### T-06 Recovery Tests

Verify reconstruction from durable checkpoints.

### T-07 AI Containment Tests

Verify that AI output cannot:

- grant authority;
- directly mutate authoritative state;
- silently convert uncertainty to fact;
- bypass validation;
- bypass dependency conditions;
- bypass human authorization.

---

## 26. Security and Privacy Boundary

OPAQUE will potentially hold sensitive project information and may send selected information to external AI providers.

The physical architecture must therefore separate:

- local controlled state;
- host-visible state;
- model-visible context;
- provider configuration/secrets;
- diagnostics;
- exported project records.

Secrets must never become ordinary project-state records.

API credentials should remain in the host/provider secret mechanism appropriate to the deployment.

AI context should follow minimum-necessary disclosure.

Diagnostic logging must avoid accidental capture of secrets or unnecessary sensitive context.

---

## 27. Deployment and Upgrade

OPAQUE should include explicit runtime versioning.

Conceptually:

~~~text
OPAQUE runtime version
        │
        ├── schema version
        ├── state version
        ├── adapter compatibility
        └── migration requirements
~~~

An extension update must not silently reinterpret old controlled state.

Where schema changes are required:

~~~text
old state
   ↓
migration check
   ↓
compatible → migrate / continue
incompatible → controlled migration / blocked state
~~~

Historical records should remain interpretable after migration.

---

## 28. Compatibility Boundary

OPAQUE should define compatibility at three levels:

1. **OPAQUE schema compatibility**
2. **runtime compatibility**
3. **host adapter compatibility**

A host update that changes an integration surface should be detectable.

Unsupported or degraded host capability should become explicit runtime state rather than silently behaving as before.

---

## 29. Physical Module Consolidation

The 12 functional subsystems from Stage VII-B should not automatically become 12 independently deployed modules.

A more practical initial physical organization is:

~~~text
OPAQUE RUNTIME
├── core
│   ├── controlled state
│   ├── control graph
│   ├── authority/transition
│   └── operation/work
│
├── runtime
│   ├── lifecycle
│   ├── temporal
│   └── processing
│
├── evidence
│   ├── determination
│   ├── validation
│   └── provenance/history
│
├── resilience
│   ├── failure
│   ├── exception
│   └── recovery
│
├── interfaces
│   ├── AI adapter
│   ├── host adapter
│   └── human/UI adapter
│
├── persistence
│
└── audit
~~~

This is a candidate physical grouping.

The final file/package structure should follow implementation coupling and testability rather than conceptual symmetry.

---

## 30. Browser Runtime vs Server Runtime

The architecture does not inherently require a backend server.

A browser-resident JavaScript runtime can potentially provide:

- event processing;
- deterministic control;
- local persistence;
- AI calls through approved host/provider interfaces;
- host integration;
- UI;
- recovery.

A server becomes necessary only if requirements later demonstrate a need such as:

- cross-device synchronization;
- shared multi-user authoritative state;
- server-side secret isolation;
- long-running background processing independent of browser state;
- centralized persistence;
- remote orchestration.

None of these should be assumed necessary for the initial EverWorlds target.

---

## 31. Performance Constraints

The runtime must avoid turning every message into a heavyweight OPAQUE cycle.

Processing should be proportional to materiality.

Candidate strategy:

~~~text
low-materiality event
    ↓
lightweight deterministic processing

material event
    ↓
expanded control lifecycle

semantic ambiguity / impact / conflict
    ↓
AI reasoning when justified

authority / validation requirement
    ↓
human interaction when required
~~~

This supports R-038 complexity control and R-040 convergence control.

AI calls should be conditional rather than universal.

---

## 32. Cost and Latency

AI reasoning introduces:

- latency;
- provider availability dependency;
- token cost;
- context construction cost;
- response parsing;
- failure/retry complexity.

OPAQUE should therefore use AI where its semantic value justifies the cost.

Deterministic checks should remain local whenever possible.

The runtime should avoid unnecessary serial AI calls.

Where multiple independent analyses are safe, they may be parallelized and then joined under controlled processing.

---

## 33. Deadline Feasibility — 2026-10-16

The architecture is technically plausible for the EverWorlds deadline **only if implementation scope is staged**.

The critical path should not attempt to implement the full conceptual universe simultaneously.

The first executable slice should establish the minimum control backbone:

~~~text
persistent identity/state
      ↓
controlled event processing
      ↓
deterministic transition gate
      ↓
provenance/history
      ↓
recovery checkpoint
      ↓
basic AI interface
      ↓
SillyTavern host adapter
      ↓
minimal UI
~~~

Only after this backbone is demonstrably stable should broader semantic capabilities be added.

---

## 34. Implementation Priority

### Priority 1 — Runtime Backbone

- bootstrap;
- normalized events;
- controlled state;
- state versioning;
- deterministic transition boundary;
- persistence abstraction;
- history/provenance;
- recovery.

### Priority 2 — Host Integration

- capability discovery;
- event observation;
- generation lifecycle;
- context insertion;
- host result confirmation;
- reconciliation.

### Priority 3 — AI Interface

- context package;
- structured request;
- structured response;
- containment;
- uncertainty;
- stale-result protection.

### Priority 4 — Human Control

- pending decision UI;
- authorization;
- rejection;
- clarification;
- validation;
- recovery controls.

### Priority 5 — Advanced Control

- semantic dependency analysis;
- contradiction analysis;
- impact analysis;
- feedback incorporation;
- convergence control;
- metacognitive audits;
- momentum/continuity signals.

This priority order is an implementation strategy, not a modification of OPAQUE requirements.

---

## 35. Critical Path

The current critical path is:

~~~text
Stage VII-H feasibility
        ↓
physical implementation boundary
        ↓
minimal schemas
        ↓
runtime kernel
        ↓
persistence
        ↓
host adapter proof
        ↓
AI adapter proof
        ↓
recovery/history proof
        ↓
integration prototype
        ↓
controlled expansion
~~~

The most dangerous sequencing error would be to build UI or advanced AI features before proving the controlled-state/persistence/transition backbone.

---

## 36. What Should Be Prototyped First

The first implementation prototype should prove one complete controlled lifecycle rather than many disconnected features.

Candidate proof:

~~~text
capture event
  ↓
identify governed object
  ↓
read current state/version
  ↓
evaluate dependencies/conditions
  ↓
produce AI-assisted proposal if needed
  ↓
apply authorization gate
  ↓
perform controlled operation
  ↓
observe actual effect
  ↓
record outcome
  ↓
persist new state
  ↓
record provenance/history
  ↓
create recovery point
~~~

If this lifecycle cannot be made reliable, adding more OPAQUE features would only multiply the failure surface.

---

## 37. Architecture Feasibility Gate

Before broad implementation begins, the architecture should pass these checks:

- Can durable controlled state survive host reload?
- Can materially related processing be serialized?
- Can state versions prevent stale transitions?
- Can host effects be distinguished from requests?
- Can AI output be contained as non-authoritative?
- Can material transitions be recorded with provenance?
- Can failures produce recoverable state?
- Can the host adapter honestly classify capability?
- Can context be constructed within practical token limits?
- Can the runtime remain responsive?
- Can the minimum backbone be implemented and tested before 2026-10-16?

If a critical answer is no, the implementation boundary must be revised before feature expansion.

---

## 38. Remaining Architecture Questions

Stage VII-H narrows technology but does not silently finalize unresolved implementation questions.

Remaining questions include:

- exact browser persistence mechanism;
- exact schema serialization format;
- exact internal queue implementation;
- exact AI provider transport;
- exact SillyTavern API calls;
- exact UI placement;
- exact module/file boundaries;
- exact migration mechanism;
- exact automated test framework;
- exact export/import format.

These are implementation questions, not unresolved OPAQUE governance matters.

They should be resolved through feasibility testing and implementation evidence.

---

## 39. Architecture Blockers

No new foundational OPAQUE concept is currently required to proceed.

Potential **implementation blockers** remain:

1. host APIs may not provide required guarantees;
2. persistence may not meet atomicity/durability needs;
3. model context limits may constrain internalization delivery;
4. SillyTavern version changes may alter adapter behavior;
5. deadline may constrain breadth;
6. browser/runtime limitations may constrain long-running processing.

These are feasibility risks, not reasons to silently redefine the requirements.

---

## 40. Stage VII-H Determination

Stage VII-H establishes the following:

1. OPAQUE requires executable JavaScript/runtime mechanisms.
2. OPAQUE also requires written specification and machine-readable schemas.
3. Durable controlled state cannot live only in conversation history.
4. Deterministic software should enforce structurally expressible controls.
5. AI should perform bounded semantic reasoning under a controlled interface.
6. Human decisions must remain explicit where authority is required.
7. SillyTavern integration belongs in a host adapter.
8. Persistence requires an abstraction boundary.
9. History/provenance and recovery require durable representation.
10. Material processing requires controlled serialization/concurrency handling.
11. Context delivered to the model must be derived and bounded.
12. OPAQUE cannot guarantee model internalization itself; it can control relevant information delivery and consistency.
13. The browser-resident extension model is potentially sufficient for the initial target; a server is not currently architecturally mandatory.
14. Physical implementation should avoid unnecessary module fragmentation.
15. Testing must cover deterministic controls, AI containment, host behavior, failure, and recovery.
16. Security must separate controlled state, host-visible state, model-visible context, and secrets.
17. Compatibility and migration must be explicit.
18. The 2026-10-16 deadline requires a staged implementation beginning with the runtime backbone.
19. No new foundational governance concept is required by this stage.
20. Several exact technology choices remain implementation questions to be resolved through evidence rather than assumption.

---

## 41. Stage VII-H Completion Condition

Stage VII-H is complete when the architecture establishes:

- physical responsibility boundaries;
- executable JavaScript responsibilities;
- documentation/specification boundaries;
- machine-readable state requirements;
- persistence boundary;
- deterministic kernel boundary;
- AI adapter boundary;
- human/UI boundary;
- SillyTavern adapter boundary;
- runtime topology;
- event/processing model;
- history/provenance model;
- recovery model;
- failure containment;
- security/privacy boundary;
- compatibility/migration boundary;
- testing architecture;
- performance/token constraints;
- deadline feasibility;
- implementation priority and critical path;
- remaining implementation questions and blockers.

**Current determination: Stage VII-H meets this condition at the architectural level.**

The remaining exact technology selections are intentionally implementation questions.

---

## 42. Next First Action

**Stage VII-I — Implementation Boundary, Prototype Strategy & Feasibility Proof**

Determine the smallest end-to-end implementation that can prove the architecture before broad EverWorlds integration.

The next stage should establish:

- exact first prototype boundary;
- minimum machine-readable schema;
- minimum deterministic kernel;
- minimum persistence proof;
- minimum SillyTavern adapter proof;
- minimum AI contract proof;
- minimum recovery proof;
- test/evidence requirements;
- explicit pass/fail criteria;
- what must be deferred until the backbone works.

No broad feature implementation should begin until the proof boundary is explicit.
