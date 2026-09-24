# OPAQUE — Stage VII-G Host Integration & SillyTavern Adapter Architecture

## Status

**Architectural analysis — provisional.**

Stage VII-G maps the independent OPAQUE architecture onto the environment in which EverWorlds will execute.

This document treats SillyTavern as a **host/execution environment**, not as the definition or authority of OPAQUE.

It does not yet select exact SillyTavern APIs, extension files, JavaScript modules, persistence implementation, UI framework, or model-provider API.

## 1. Architectural Finding

OPAQUE and SillyTavern occupy different architectural levels.

~~~text
EVERWORLDS
    │
    ▼
  OPAQUE
    │
    ├── controlled state
    ├── control mechanisms
    ├── AI reasoning boundary
    ├── execution governance
    └── host adapter
            │
            ▼
       SILLYTAVERN
            │
            ├── chat/runtime
            ├── generation
            ├── extension system
            ├── events/hooks
            ├── UI
            ├── tools
            └── host persistence facilities
~~~

SillyTavern provides capabilities that OPAQUE can use.

OPAQUE provides the control semantics that EverWorlds requires.

Therefore:

**SillyTavern capability ≠ OPAQUE requirement**

and:

**SillyTavern behavior ≠ OPAQUE authority**

## 2. Host Adapter Purpose

The host adapter is the translation boundary between OPAQUE's abstract operations and host-specific mechanisms.

Its responsibilities should include:

- receiving host events;
- translating host data into OPAQUE event representations;
- requesting host operations;
- observing actual host results;
- translating host failures;
- exposing host capabilities;
- maintaining external identifiers/mappings;
- preserving the distinction between requested and actual host effects.

The adapter should not contain the core meaning of OPAQUE.

## 3. What OPAQUE Must Receive From a Host

OPAQUE requires enough host information to observe materially relevant execution.

Candidate host inputs include:

### H-01 Runtime Events

Examples:

- conversation/message events;
- generation start/completion/failure;
- user interaction events;
- tool invocation/results;
- chat changes;
- character/world/context changes;
- extension lifecycle events;
- relevant storage events.

### H-02 Runtime Identity

OPAQUE needs stable references to relevant host objects where available:

- chat/session;
- character;
- group;
- message;
- generation/request;
- tool invocation;
- extension instance;
- external resource.

### H-03 Actual Results

Where OPAQUE requests a host operation, it needs the observed result rather than merely an acknowledgment that the request was sent.

### H-04 Temporal Information

Where available:

- event occurrence time;
- capture time;
- operation start/end;
- runtime interruption/resumption.

OPAQUE must preserve unknown values where the host does not provide reliable actual times.

### H-05 Host Capability Information

OPAQUE should be able to determine whether the host supports a required operation or observation.

Capability absence must not be confused with successful execution.

## 4. What OPAQUE May Request From a Host

OPAQUE may eventually request host operations such as:

- initiate or control generation;
- insert controlled context into generation;
- observe or retrieve current chat/context;
- manipulate permitted host-visible state;
- invoke host-supported tools;
- persist host-facing metadata;
- update EverWorlds UI;
- request user interaction;
- register/unregister event listeners;
- create or modify host-side artifacts where explicitly supported.

These are **requests across an adapter boundary**.

OPAQUE must not represent a request as an actual effect until the effect is observed or otherwise confirmed by a reliable host mechanism.

## 5. Host Operation Contract

Every material host operation should conceptually follow:

~~~text
OPAQUE
  ↓
host operation request
  ↓
adapter
  ↓
SILLYTAVERN
  ↓
actual host effect
  ↓
host result/event
  ↓
adapter
  ↓
OPAQUE observed result
~~~

This permits OPAQUE to distinguish:

- requested;
- accepted;
- started;
- completed;
- failed;
- partially completed;
- unknown.

## 6. SillyTavern as Host, Not Core

SillyTavern currently exposes a substantial extension/runtime surface.

The relevant categories include:

- event sources and event types;
- generation APIs;
- extension prompts/context insertion;
- tokenization/counting;
- tool/function mechanisms;
- variables;
- metadata persistence;
- message manipulation;
- extension settings;
- module workers;
- world information;
- character/group/chat state.

These capabilities make SillyTavern a useful execution substrate for EverWorlds.

They do not make its internal data model the OPAQUE data model.

OPAQUE should adapt to host mechanisms rather than inherit host semantics blindly.

## 7. Context Injection Boundary

EverWorlds will eventually need OPAQUE-controlled information to influence model generation.

The architecture should therefore distinguish:

~~~text
OPAQUE controlled context
        ↓
host adapter
        ↓
SillyTavern generation/context mechanism
        ↓
model request
~~~

The inserted context is a **derived representation** of controlled state.

It is not the controlled state itself.

The host/model may receive only the subset required for the generation task.

## 8. Generation Lifecycle Integration

A likely generation integration pattern is:

~~~text
generation requested
        ↓
OPAQUE observes request
        ↓
OPAQUE identifies relevant controlled context
        ↓
OPAQUE evaluates pre-generation controls
        ↓
OPAQUE constructs allowed context
        ↓
SillyTavern/model generation
        ↓
generation result / stream / failure
        ↓
OPAQUE observes result
        ↓
AI/state analysis where required
        ↓
post-generation controls
        ↓
record / reconcile / continue
~~~

This is a candidate host lifecycle, not a claim that every SillyTavern event must be intercepted.

## 9. Streaming Generation

If the host exposes streaming output, OPAQUE must distinguish:

- generation initiated;
- partial output received;
- generation completed;
- generation interrupted;
- generation failed.

Partial model output must not automatically be treated as a completed outcome.

If partial output materially affects controlled state, the architecture should record the appropriate processing state without prematurely committing a completed result.

## 10. Message Lifecycle

A host message should not automatically equal an OPAQUE determination, outcome, or state transition.

Conceptually:

~~~text
HOST MESSAGE
     ↓
captured event
     ↓
identified/classified
     ↓
AI analysis where useful
     ↓
candidate interpretation/proposal
     ↓
control/validation/authority
     ↓
possible incorporation
~~~

This is important because ordinary roleplay dialogue may contain:

- fictional statements;
- character beliefs;
- uncertainty;
- instructions;
- corrections;
- meta-commentary;
- observations;
- user requests;
- accidental contradictions.

OPAQUE must not collapse these categories merely because they arrived as chat messages.

## 11. User Interaction Boundary

The host UI should present OPAQUE's control state without requiring the user to understand its internal architecture.

Potential user-facing states include:

- processing;
- awaiting decision;
- blocked;
- unresolved;
- validation required;
- recovery available;
- synchronization pending;
- warning;
- completed.

The adapter translates these into host UI behavior.

The underlying OPAQUE state remains independent.

## 12. Host Capability Discovery

The adapter should expose a capability model.

Conceptually:

~~~text
HOST CAPABILITIES
├── observe generation
├── intercept/contextualize generation
├── observe messages
├── manipulate messages
├── persist metadata
├── invoke tools
├── receive tool results
├── provide UI
├── provide runtime events
└── other supported capabilities
~~~

OPAQUE should determine whether a requested control is:

- supported;
- partially supported;
- unsupported;
- unknown.

It should not assume support merely because an API exists somewhere in the host.

## 13. Guaranteed vs Best-Effort Controls

Host integration creates an important distinction.

### Guaranteed control

OPAQUE can technically enforce or verify the condition through available mechanisms.

### Best-effort control

OPAQUE can detect, record, warn, or attempt intervention but cannot guarantee prevention.

### Unsupported control

The host provides no reliable mechanism for the required behavior.

OPAQUE should preserve this distinction.

A best-effort or unsupported host control must not be represented as guaranteed enforcement.

## 14. Host Enforcement Gap

Example:

~~~text
OPAQUE requires:
"prevent operation X"

Host supports:
"observe operation X after execution"

Result:
prevention unavailable
detection available
reconciliation required
~~~

The correct architectural response is not to pretend the host can enforce prevention.

Instead:

- record the limitation;
- use detection where possible;
- contain downstream consequences;
- reconcile actual host state;
- preserve controlled-state integrity.

## 15. Host State vs OPAQUE State

There may be legitimate differences between host state and OPAQUE controlled state.

~~~text
SILLYTAVERN STATE
       │
       │ observation / requested operation
       ▼
HOST ADAPTER
       │
       ▼
OPAQUE CONTROLLED STATE
~~~

The two states must not be assumed identical.

OPAQUE may need to represent:

- host state observed;
- OPAQUE state recognized;
- synchronization status;
- discrepancy;
- pending reconciliation.

This is especially important where host state can change outside OPAQUE's direct control.

## 16. Synchronization Model

A candidate synchronization lifecycle is:

~~~text
host event
   ↓
capture
   ↓
identify
   ↓
compare with OPAQUE state
   ↓
same → synchronized
different → discrepancy
unknown → unresolved
   ↓
reconcile where required
~~~

Synchronization must not silently overwrite controlled state.

A host observation is evidence of host behavior, not automatic authorization for OPAQUE state change.

## 17. External Identifier Mapping

OPAQUE should maintain explicit mappings where host identifiers differ from OPAQUE identifiers.

Conceptually:

~~~text
OPAQUE OBJECT ID
       ↕
HOST OBJECT ID
~~~

Mappings should preserve:

- object identity;
- host identity;
- host/source;
- mapping status;
- provenance;
- validity/lifecycle.

A host ID must not become an OPAQUE identity merely because it is convenient.

## 18. Host Events Are Not Automatically Authoritative

A host event may tell OPAQUE:

> "Something happened."

It does not automatically tell OPAQUE:

> "This event should change authoritative project state."

The event enters the controlled processing lifecycle:

**event → identification → analysis → control → authorization/validation where required → possible transition**

This preserves the event/state distinction.

## 19. Tool Integration

SillyTavern may provide tools or function mechanisms.

OPAQUE should treat tool calls as external operations.

~~~text
AI / OPAQUE reasoning
        ↓
tool request
        ↓
OPAQUE gate
        ↓
host tool adapter
        ↓
tool execution
        ↓
actual result
        ↓
OPAQUE observation
~~~

Where a tool can mutate state, the adapter should expose the operation as a governed effect rather than allowing model output to bypass OPAQUE.

## 20. Storage Integration

OPAQUE's durable state should not depend exclusively on whatever persistence mechanism the host happens to provide.

The host may provide:

- extension settings;
- metadata;
- variables;
- files;
- storage APIs;
- other persistence mechanisms.

OPAQUE should select its persistence strategy later based on its own integrity requirements.

Host persistence can be an adapter target.

It is not automatically sufficient merely because it can store data.

## 21. UI Integration

OPAQUE UI should be treated as a presentation adapter.

The underlying architecture should provide state such as:

~~~text
OPAQUE
├── current processing state
├── control findings
├── blockers
├── pending decisions
├── unresolved matters
├── recovery status
└── relevant work/milestone state
        ↓
OPAQUE UI adapter
        ↓
SillyTavern interface
~~~

The UI should not become the source of controlled truth.

## 22. Host Failure

Host failures must be first-class.

Examples:

- event listener failure;
- generation API failure;
- context insertion failure;
- message operation failure;
- persistence failure;
- UI failure;
- tool failure;
- host restart;
- extension reload.

OPAQUE should preserve its own controlled state and record the host failure separately.

A host failure must not silently become an OPAQUE state transition.

## 23. Host Restart and Extension Reload

OPAQUE should be able to reconstruct its controlled runtime position after host restart/reload from durable state.

~~~text
OPAQUE durable state
        ↓
host adapter initialization
        ↓
capability discovery
        ↓
state reconciliation
        ↓
resume / wait / recover
~~~

Conversation history alone must not be the recovery mechanism.

## 24. Multiple Hosts / Future Portability

Although EverWorlds currently targets SillyTavern, the architecture should not make host-specific assumptions part of OPAQUE's core.

A future host could theoretically be:

- another roleplay client;
- a standalone EverWorlds runtime;
- a web application;
- another AI interface.

The conceptual architecture should remain:

~~~text
OPAQUE CORE
   ├── AI adapter
   ├── persistence adapter
   ├── host adapter A
   ├── host adapter B
   └── future adapters
~~~

This preserves host independence.

## 25. Relationship to OpenAI / AI Provider

An AI provider occupies a different boundary from SillyTavern.

~~~text
OPAQUE
 │
 ├── host adapter ───────► SillyTavern
 │
 └── AI adapter ─────────► model provider
~~~

SillyTavern may itself invoke an AI provider, but OPAQUE's conceptual contract must not depend on that implementation detail.

Therefore:

**OPAQUE ≠ SillyTavern ≠ OpenAI/model provider**

The three may form an execution chain, but they remain separate systems.

## 26. Adapter Boundary Contract

The host adapter should conceptually expose five categories of capability:

1. **Observe** — report host events/state.
2. **Request** — ask the host to perform an operation.
3. **Confirm** — report whether the requested effect actually occurred.
4. **Reconcile** — report discrepancies between requested/observed/controlled state.
5. **Present** — expose OPAQUE status and required human interaction.

This is the minimum conceptual host contract.

## 27. Host Adapter State Machine

~~~text
UNINITIALIZED
      ↓
DISCOVERING
      ↓
CAPABLE / PARTIALLY CAPABLE / UNSUPPORTED
      ↓
CONNECTED
      ↓
OBSERVING
      ↓
REQUESTING
      ↓
CONFIRMING
      ↓
RECONCILING
      ↓
CONNECTED
      │
      ├── FAILURE → RECOVERY
      └── SHUTDOWN → UNINITIALIZED
~~~

The exact states may later be consolidated if implementation shows that some are unnecessary.

## 28. Adapter Boundary Invariants

### HI-001 — Host Separation

Host state is not automatically OPAQUE state.

### HI-002 — Effect Confirmation

A requested host operation is not automatically an actual effect.

### HI-003 — Capability Honesty

Unsupported host capabilities cannot be represented as supported.

### HI-004 — Identity Mapping

Host identities remain distinct from OPAQUE identities unless explicitly mapped.

### HI-005 — Event Separation

A host event is not automatically a state transition.

### HI-006 — Failure Separation

Host failure is distinct from OPAQUE controlled-state failure.

### HI-007 — Reconciliation

Material host/OPAQUE discrepancies must be representable and reconcilable.

### HI-008 — Recovery

Host restart/reload cannot bypass OPAQUE recovery and control requirements.

### HI-009 — Provider Separation

The host and AI provider remain separate architectural boundaries.

### HI-010 — UI Separation

The UI presents controlled state but does not become its source of truth.

## 29. What SillyTavern Can and Cannot Be Expected to Do

SillyTavern can potentially provide:

- runtime hooks;
- event observation;
- generation integration;
- context insertion;
- tool interfaces;
- message manipulation;
- extension lifecycle;
- user-facing UI surfaces;
- some persistence mechanisms.

OPAQUE should not assume that SillyTavern can inherently guarantee:

- all state transitions are controlled;
- every external effect is interceptable;
- every semantic distinction is enforceable deterministically;
- all host behavior is observable;
- all storage semantics meet OPAQUE's durability requirements;
- host-side actions cannot occur outside OPAQUE.

These limitations are architectural inputs, not reasons to redefine OPAQUE.

## 30. Host Integration in One View

~~~text
                         EVERWORLDS
                             │
                             ▼
                           OPAQUE
                             │
          ┌──────────────────┼──────────────────┐
          ▼                  ▼                  ▼
   CONTROLLED STATE      AI ADAPTER       HOST ADAPTER
          │                  │                  │
          │                  ▼                  ▼
          │              MODEL PROVIDER     SILLYTAVERN
          │                                     │
          │                          ┌──────────┼──────────┐
          │                          ▼          ▼          ▼
          │                       EVENTS    GENERATION   TOOLS/UI
          │                          │          │          │
          └──────────────────────────┼──────────┼──────────┘
                                     ▼
                              OBSERVE / REQUEST
                                     ▼
                                  RECONCILE
                                     ▼
                               OPAQUE STATE
~~~

## 31. Architectural Consequences

Stage VII-G establishes:

1. OPAQUE remains independent of SillyTavern.
2. SillyTavern is a host adapter target, not OPAQUE's definition.
3. Host events enter OPAQUE as events, not automatic state transitions.
4. Host operations must distinguish request, acceptance, actual effect, and outcome.
5. Host capability limitations must be explicit.
6. Guaranteed, best-effort, and unsupported controls must remain distinct.
7. Host state and OPAQUE controlled state may legitimately differ.
8. Material discrepancies require reconciliation.
9. Host identifiers require explicit mapping to OPAQUE identities.
10. Host tools remain external operations subject to OPAQUE control.
11. Host persistence is an adapter resource, not automatically the OPAQUE durable-state architecture.
12. Host UI is a presentation layer, not controlled truth.
13. Host failure and restart must not corrupt or bypass OPAQUE state.
14. AI provider and host remain separate boundaries.
15. OPAQUE should be portable to other hosts in principle.
16. The next implementation work should be based on OPAQUE's host contract, then mapped to verified SillyTavern capabilities.

## 32. Stage VII-G Completion Condition

Stage VII-G is complete when the architecture defines:

- required host inputs;
- host operation requests;
- actual-effect confirmation;
- capability discovery;
- context injection boundary;
- generation lifecycle integration;
- message/event handling;
- host vs OPAQUE state separation;
- synchronization/reconciliation;
- identifier mapping;
- tool integration;
- persistence boundary;
- UI boundary;
- host failure/restart handling;
- provider separation;
- adapter invariants;
- guaranteed vs best-effort vs unsupported controls.

**Current determination: Stage VII-G meets this condition.**

No exact SillyTavern API has been promoted to a foundational OPAQUE dependency yet.

## 33. Next First Action

**Stage VII-H — Physical Implementation & Technology Feasibility Architecture**

Determine:

> **Given the architecture now established, what must actually become JavaScript/code, what remains specification/documentation, what should be stored where, what SillyTavern interfaces can implement the required adapter contract, what cannot be implemented reliably, and whether the resulting architecture is feasible within the EverWorlds deadline.**

This is the point at which concrete implementation technology can be evaluated without prematurely defining OPAQUE by the technology.
