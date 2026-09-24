# OPAQUE — Stage VII-B Internal Functional Architecture

## Status

**Architectural analysis — provisional.**

Stage VII-B derives a minimal internal capability architecture from Stage VII-A and the existing OPAQUE control model.

This document does not ratify OPAQUE, resolve open governance questions, or select final technologies.

## 1. Architectural Finding

Stage VII-A showed that OPAQUE requires persistent state, deterministic control, AI reasoning, human authorization where applicable, and external interfaces.

The next question is whether the fourteen candidate layers should become fourteen independent software modules.

**Current finding: no.**

That would reproduce the complexity problem OPAQUE is intended to control.

The requirements can be organized into a smaller set of functional subsystems around a central controlled-state mechanism.

## 2. Proposed Minimal Functional Architecture

### F-01 — Controlled State Core

The central OPAQUE capability.

Responsibilities:

- represent governed objects;
- represent state dimensions;
- maintain current controlled state;
- accept only governed state transitions;
- preserve state identity;
- expose current state to other subsystems;
- prevent uncontrolled mutation.

Primary concepts:

C-01 Governed Object, C-02 State, C-10 Change, C-12 Closure, C-14 Controlled Incorporation.

Primary requirements:

R-004, R-010, R-014, R-020, R-021, R-025, R-030, R-033, R-041, R-042, I-001.

This is the likely center of the executable OPAQUE kernel.

---

### F-02 — Control Graph

A unified representation of relationships and dependencies.

Responsibilities:

- maintain typed relationships;
- maintain dependencies;
- determine dependency status;
- expose affected/dependent objects;
- identify downstream material impact;
- support conflict and propagation analysis.

Primary concepts:

C-05 Relationship, C-06 Dependency, C-01 Governed Object.

Primary requirements:

R-016, R-017, R-018, R-031, R-034, R-043, R-044.

Important architectural point:

**Relationship and dependency should remain distinct concepts even if they share one underlying graph mechanism.**

---

### F-03 — Authority & Transition Gate

Controls whether a proposed state change is legitimately allowed.

Responsibilities:

- identify applicable authority;
- evaluate authority conditions;
- distinguish proposed from authorized;
- determine whether human authorization is required;
- prevent unauthorized state mutation;
- route unresolved authority matters to an unresolved/escalation state;
- enforce transition prerequisites.

Primary concepts:

C-03 Authority, C-04 Condition, C-07 Operation, C-14 Controlled Incorporation.

Primary requirements:

R-008, R-009, R-010, R-015, R-020, R-021, R-024, R-029, R-030, R-032, R-037, R-047.

**Open governance matters remain open.**

The gate cannot invent authority precedence, validation authority, exception authority, or termination rules that OPAQUE has not established.

---

### F-04 — Operation & Work Controller

Represents work that is being proposed, authorized, executed, interrupted, completed, failed, or cancelled.

Responsibilities:

- represent operations;
- represent work units;
- evaluate execution eligibility;
- maintain operation state independently from resulting controlled state;
- maintain milestone/work-unit status;
- preserve completion conditions;
- distinguish activity from completion;
- coordinate with Scheme interface without becoming the Scheme.

Primary concepts:

C-07 Operation, C-11 Outcome, C-12 Closure.

Primary requirements:

R-003, R-024, R-025, R-026, R-041, R-043, R-044, R-047.

---

### F-05 — Temporal Controller

Responsibilities:

- obtain runtime time;
- record actual timestamps;
- calculate duration/order/deadline relationships;
- determine overdue state;
- record interruption/resumption;
- preserve unknown temporal values rather than inventing them.

Primary requirements:

R-011, R-022, R-028, R-042, R-045.

This should be deterministic wherever possible.

---

### F-06 — Evidence, Validation & Determination Layer

This layer separates evidence from what the evidence means.

Responsibilities:

- represent observations/evidence;
- represent determinations;
- represent validation subjects/criteria/results;
- preserve validation scope and limitations;
- associate evidence with outcomes and state;
- distinguish validated from merely determined or proposed material;
- preserve indeterminate matters.

Primary concepts:

C-08 Determination, C-09 Validation, C-11 Outcome, C-13 Provenance.

Primary requirements:

R-005, R-007, R-018, R-019, R-023, R-026, R-027, R-032, R-034.

Some functions are deterministic; semantic validation/determination may require AI reasoning.

---

### F-07 — Provenance & History Layer

Responsibilities:

- preserve prior controlled states;
- record material changes;
- preserve source/interpretation/transformation relationships;
- support backward and forward traceability;
- preserve historical identity;
- reconstruct why a current state exists.

Primary concepts:

C-10 Change, C-13 Provenance.

Primary requirements:

R-004, R-019, R-021, R-022, R-031, R-033, R-042.

This is not merely a log file. It is a controlled historical record.

---

### F-08 — Failure, Exception & Recovery Controller

Responsibilities:

- detect/control material failures;
- preserve pre-failure state;
- represent partial effects;
- control containment and recovery;
- represent exceptions separately from ordinary operation;
- create recovery points;
- prevent recovery from bypassing governance;
- support resumption.

Primary concepts:

C-04 Condition, C-07 Operation, C-11 Outcome, C-12 Closure, C-14 Controlled Incorporation.

Primary requirements:

R-028, R-029, R-030, R-042, with support from R-011 and R-025.

---

### F-09 — AI Reasoning Interface

This is the controlled boundary through which OPAQUE requests or receives model reasoning.

Responsibilities:

- provide relevant controlled context;
- request analysis;
- receive structured reasoning results;
- preserve distinction between model output and controlled state;
- identify candidate objects, relationships, dependencies, conflicts, impacts, interpretations, proposals, and procedural responses;
- never directly grant authority merely because the model produced an answer.

AI output enters an intermediate/non-authoritative channel before any governed incorporation.

Primary requirements:

R-005, R-006, R-008, R-012, R-013, R-015, R-016, R-018, R-019, R-023, R-026, R-027, R-032, R-034, R-035, R-036, R-037, R-039, R-040, R-046.

Core boundary:

**AI reasoning is an input to control, not the control authority itself.**

---

### F-10 — Human Decision Interface

Responsibilities:

- present decisions requiring human authority;
- show relevant evidence, consequences, dependencies, uncertainty, and proposed transition;
- capture explicit human authorization/rejection/correction;
- preserve the resulting decision as a governed event/state transition where authorized.

Primary requirements:

R-008, R-009, R-015, R-018, R-020, R-023, R-029, R-030, R-032, R-037.

This interface should expose only the complexity needed for the human decision while retaining richer internal state.

---

### F-11 — Audit & Process Control

Responsibilities:

- trigger audits;
- run deterministic integrity checks;
- request AI-assisted audits where semantic reasoning is required;
- record findings;
- distinguish detection from modification;
- support process correction;
- monitor convergence;
- detect continuity/momentum signals;
- preserve procedural response history.

Primary requirements:

R-035, R-036, R-038, R-039, R-040, plus support for R-043 and I-001.

Important boundary:

Audit detection does not itself mutate authoritative state.

---

### F-12 — External / Host Adapters

OPAQUE requires interfaces to systems outside itself.

Potential interfaces include:

- EverWorlds project state;
- Scheme of Work;
- SillyTavern;
- AI/model provider;
- persistent storage;
- runtime clock;
- user interface.

Responsibilities:

- translate external representations into OPAQUE-understandable inputs;
- expose only required capabilities;
- prevent host-specific behavior from becoming implicit OPAQUE architecture;
- preserve identity and provenance across boundaries.

Primary requirements:

R-002, R-003, R-043, R-045, R-046, R-047.

## 3. Consolidated Architecture

The functional subsystems can be visualized as:

    HUMAN
      │
      ▼
    F-10 Human Decision Interface
      │
      ▼
    F-03 Authority & Transition Gate
      │
      ▼
    ┌───────────────────────────────────┐
    │       F-01 CONTROLLED STATE CORE  │
    └───────────────────────────────────┘
       │       │        │        │
       ▼       ▼        ▼        ▼
    F-02    F-04      F-06      F-07
    Graph   Work     Evidence   History
             │         │
             ▼         ▼
           F-08      F-09
          Recovery   AI Reasoning
                         │
                         ▼
                    AI / Model
                         
    F-05 Temporal Controller ─────► F-01 / F-04 / F-07
    F-11 Audit & Process Control ─► all relevant subsystems
    F-12 External Adapters ───────► controlled interfaces

This is a functional architecture, not a final class/file diagram.

## 4. What Becomes “The JS”

The architecture indicates that executable code is concentrated rather than spread indiscriminately.

The likely deterministic executable core contains:

- state-transition enforcement;
- authority/condition gates;
- dependency evaluation;
- operation/work-state management;
- temporal calculation;
- persistence;
- provenance/history recording;
- recovery-point creation;
- completion-condition evaluation;
- audit triggering;
- interface enforcement.

AI-mediated code handles:

- context assembly;
- model requests;
- structured response interpretation;
- candidate identification;
- semantic analysis;
- impact analysis;
- conflict interpretation;
- qualitative feasibility;
- convergence reasoning.

The AI-mediated layer still cannot bypass F-01/F-03 controlled state.

## 5. What Remains “The Book”

The persistent written layer remains responsible for:

- constitutional meaning;
- requirements;
- specification;
- rationale;
- architectural decisions;
- unresolved governance matters;
- human-readable state explanations;
- audit reports;
- implementation records;
- recovery explanations where human readability is useful.

Machine-readable state and human-readable records should be linked rather than treated as interchangeable.

## 6. Relationship to the Existing 14 Concepts

The 14 concepts do not need fourteen independent modules.

| Control concept | Primary functional home |
|---|---|
| C-01 Governed Object | F-01 + F-02 |
| C-02 State | F-01 |
| C-03 Authority | F-03 |
| C-04 Condition | F-03 + F-08 |
| C-05 Relationship | F-02 |
| C-06 Dependency | F-02 |
| C-07 Operation | F-04 |
| C-08 Determination | F-06 + F-09 |
| C-09 Validation | F-06 |
| C-10 Change | F-01 + F-07 |
| C-11 Outcome | F-04 + F-06 + F-08 |
| C-12 Closure | F-01 + F-04 + F-08 |
| C-13 Provenance | F-07 |
| C-14 Controlled Incorporation | F-01 + F-03 + F-06 |

This suggests the ontology and implementation architecture can remain separate:

**14 conceptual objects/concepts → approximately 12 functional subsystems.**

Further consolidation may be possible, but should be justified by actual architectural benefit rather than aesthetic simplicity.

## 7. The Critical Architectural Flow

A representative controlled transition is:

    External / Human / AI Input
              │
              ▼
       Identify governed object
              │
              ▼
       Classify material/state
              │
              ▼
      Determine relationships
              │
              ▼
       Determine dependencies
              │
              ▼
      Determine applicable authority
              │
              ▼
       Evaluate conditions
              │
              ▼
        Propose transition
              │
              ▼
        Validate if required
              │
              ▼
       Human authorization if required
              │
              ▼
      F-03 Transition Gate
              │
        ┌─────┴─────┐
        │           │
     allowed      blocked
        │           │
        ▼           ▼
   F-01 State     preserve
    transition    proposal/
        │          attempted
        ▼           change
     F-07 history
        │
        ▼
     F-06 outcome/validation
        │
        ▼
     F-11 audit where triggered
        │
        ▼
      next state

This is the first concrete candidate for OPAQUE's runtime control loop.

## 8. Architecture Principle: Control Before Convenience

OPAQUE should not be optimized by asking:

> “What is easiest to code?”

The architectural question is:

> “What is the minimum mechanism that reliably preserves the required control property?”

Only after that should implementation efficiency be considered.

## 9. Architecture Principle: AI Is Not the Lock

An AI instruction such as “do not proceed until the dependency is satisfied” is not equivalent to an executable lock.

A true control gate should be capable of preventing the governed operation from being treated as permitted even when an AI proposes it.

Therefore:

**AI can recommend → deterministic control evaluates → authority permits → execution occurs.**

Where the host cannot technically prevent execution, OPAQUE should at minimum prevent the resulting state from being represented as legitimately authorized/complete.

## 10. Architecture Principle: Failure Must Be First-Class

Failure is not an exceptional afterthought.

The architecture must preserve:

**before → attempted operation → actual effect → failure/partial effect → controlled recovery → resulting state**

rather than simply:

**operation failed → try again.**

## 11. Architecture Principle: Persistence Is Outside Conversation

Conversation is an interface and reasoning medium.

It is not a sufficient source of controlled project state.

OPAQUE therefore requires persistent state/history outside ordinary conversational context.

## 12. Architecture Principle: Host Independence

OPAQUE's internal architecture must be defined before mapping it to SillyTavern.

The mapping should answer:

- What OPAQUE needs.
- What the host provides.
- What the adapter translates.
- What the host cannot enforce.
- What OPAQUE must enforce independently.

SillyTavern should therefore be treated as one host adapter rather than as the architecture itself.

## 13. Remaining Architectural Questions

Stage VII-B resolves the functional subsystem boundary sufficiently to continue, but does not yet resolve:

1. exact persistent state schema;
2. runtime lifecycle;
3. event/input model;
4. transaction/state-transition mechanics;
5. AI request/response contract;
6. persistence technology;
7. host adapter contract;
8. executable lock semantics;
9. restart/recovery behavior at runtime level;
10. performance/context/token constraints;
11. exact boundary between deterministic evaluation and AI judgment.

These become Stage VII-C and later architectural work.

## 14. Stage VII-B Completion Condition

Stage VII-B is complete when the requirements can be represented by a minimal functional architecture without requiring technology-specific decisions or inventing substantive governance.

**Current determination:** the requirements support a consolidated functional architecture centered on a Controlled State Core, with specialized control, graph, work, temporal, evidence/validation, history, recovery, AI, human, audit, and adapter capabilities.

The architecture remains provisional until subsequent runtime, state, AI-interface, enforcement, host-integration, and feasibility analysis.

## 15. Next First Action

**Stage VII-C — Runtime Lifecycle Architecture**

Determine what actually happens inside OPAQUE from the moment an input/event enters the system through reasoning, control evaluation, authorization, execution, observation, state transition, persistence, auditing, and recovery.

The next pass must answer:

> **When does each subsystem run, what triggers it, what data crosses each boundary, and what happens when the process fails or stops halfway through?**
