# OPAQUE — Stage VII-A Implementation Boundary Analysis

## Status

**Architectural analysis — provisional.**

This document begins Stage VII: OPAQUE Control Architecture & Implementation Model.

It does not ratify OPAQUE, alter the requirement baseline, resolve any open governance question, or select a final programming language, storage technology, model provider, host integration, or database architecture.

Its purpose is narrower:

> Determine what kind of implementation mechanism each existing OPAQUE requirement needs, and identify the minimum machinery required to make the requirement operational without inventing substantive governance.

## 1. Architectural Premise

The Stage V specification establishes what OPAQUE must preserve, distinguish, control, record, evaluate, and govern. It does not by itself determine the software machinery used to accomplish those functions.

Stage VII therefore separates:

1. **Representation** — information that must exist and remain intelligible.
2. **Persistent state** — controlled information that must survive interaction/session boundaries.
3. **Deterministic execution** — behavior that should be mechanically evaluated rather than entrusted solely to model instruction.
4. **AI reasoning** — interpretation, analysis, detection, comparison, challenge, proposal, and recommendation.
5. **Human authorization/interaction** — decisions or confirmations requiring legitimate human authority.
6. **Host/external interface** — interaction with EverWorlds, SillyTavern, model providers, files, clocks, or other runtime facilities.
7. **Hybrid mechanisms** — cases where multiple categories are necessary.

These classifications describe implementation responsibility, not authority.

## 2. Classification Key

### WR — Written Representation
Human-readable specification, definitions, rationale, policy records, explanations, diagrams, and other persistent documentation.

### PS — Persistent Structured State
Machine-readable state that must survive sessions and support reconstruction, comparison, history, or recovery.

### DE — Deterministic Executable Mechanism
Code whose behavior can be mechanically evaluated from explicit inputs and rules.

### AI — AI Reasoning Mechanism
LLM/model-supported analysis or interpretation. AI output remains subject to OPAQUE authority, state, validation, and incorporation controls.

### HA — Human Authorization / Interaction
A user-facing mechanism for decisions, approvals, confirmations, corrections, or other human-authority actions.

### HI — Host / External Interface
An adapter or interface to another system or runtime capability.

### HY — Hybrid
More than one of the above is materially required.

### NR — Not independently implementation-defining
The requirement constrains the system but does not, by itself, determine a unique implementation mechanism.

## 3. Requirement Classification Matrix

| ID | Primary implementation classification | Minimum mechanism required |
|---|---|---|
| R-001 | HY | Persistent OPAQUE control representation plus an executable means of evaluating applicable control conditions. |
| R-002 | HY | Explicit domain identities/boundaries in structured state; control checks preventing silent boundary absorption. |
| R-003 | HY | Scheme identity/interface representation plus executable checks for Scheme conditions; OPAQUE must not become Scheme execution. |
| R-004 | PS + DE + HY | Versioned controlled state, governed transition mechanism, prior-state preservation, and transition provenance. |
| R-005 | PS + DE + AI | Explicit epistemic-state representation, classification mechanism, and AI-assisted interpretation where classification cannot be deterministic. |
| R-006 | PS + DE + AI | Representation of missing information and dependency impact; deterministic blocking/conditional behavior; AI may assess materiality. |
| R-007 | PS + AI | Explicit uncertainty fields/statuses and AI-supported uncertainty identification where required. |
| R-008 | AI + DE + HA | AI reasoning channel separated from authoritative state mutation; executable authority gate; human path where required. |
| R-009 | HA + DE + PS | Explicit human-decision state, authorization interface, and controlled transition into authoritative state. |
| R-010 | PS + DE + HY | Structured proposed transition, prerequisite/authority checks, atomic or controlled state transition, and provenance. |
| R-011 | PS + DE | Persistent recovery state containing current position, blockers, dependencies, unresolved matters, and next action. |
| R-012 | PS + AI + DE | Stable object identity, scope/context fields, and ambiguity detection; AI may resolve or propose identity where necessary. |
| R-013 | PS + DE + AI | Multi-dimensional classification representation and classification workflow; AI assists semantic classification. |
| R-014 | PS + DE | Separate state dimensions with independently stored values and controlled transition rules. |
| R-015 | DE + HA + AI | Authority applicability evaluation, explicit authority records, unresolved/escalation state, and human decision path where applicable. |
| R-016 | PS + DE + AI | Typed relationship records with controlled creation/removal/change; AI may identify candidate relationships. |
| R-017 | PS + DE + AI | Explicit dependency graph/records, dependency-status evaluation, and enforcement of dependent-operation consequences. |
| R-018 | AI + DE + PS + HA | Conflict detection, conflict records preserving both sides, unresolved state, and controlled resolution path. |
| R-019 | AI + PS + DE | Source/representation linkage, semantic transformation records, and fidelity checks; AI performs interpretation/transformation. |
| R-020 | PS + DE + HA + AI | Separate non-authoritative material from authoritative state; controlled incorporation transaction with applicable checks. |
| R-021 | PS + DE + HY | Change records, affected-state identification, impact/control checks, and governed state mutation. |
| R-022 | PS | Append-preserving material history with prior/resulting state and change provenance. |
| R-023 | HY | Validation subject/criteria/scope/authority/evidence representation plus deterministic and/or AI validation mechanisms. |
| R-024 | DE + PS + AI | Condition/dependency evaluator and explicit operation permission state; AI assists where conditions require semantic judgment. |
| R-025 | PS + DE | Independent operation state and controlled-state result records; execution completion cannot imply successful state transition. |
| R-026 | PS + DE + AI | Outcome record separate from operation and determination; AI may interpret outcome; state impact remains controlled. |
| R-027 | PS + AI + DE | Explicit indeterminate state and evidence-gap/conflict representation; prevent forced certainty. |
| R-028 | PS + DE + HY | Failure record, pre-failure state preservation, partial-effect detection, containment/recovery workflow, and validation of recovery. |
| R-029 | PS + DE + HA | Explicit exception object with scope, authority, duration, safeguards, and resulting state; no ordinary-rule mutation. |
| R-030 | PS + DE + HA | Closure object and closure-condition evaluator; preserve unresolved material and reopening/continuation semantics. |
| R-031 | PS + DE | Persistent graph/links connecting material sources, decisions, changes, operations, outcomes, validation, and state. |
| R-032 | PS + AI + DE + HA | Feedback classification, controlled incorporation path, traceable state effect, and authority gate. |
| R-033 | PS + DE + HY | Versioned current/proposed/superseded states, transition records, and preservation of historical identity. |
| R-034 | AI + DE + PS | Impact-analysis mechanism, affected-object/dependency discovery, uncertainty representation, and change gating. |
| R-035 | DE + AI + PS | Audit scheduler/trigger, audit-state capture, deterministic checks, AI analysis, findings, and traceable responses. |
| R-036 | DE + AI + PS | Process-defect detection, bounded procedural adjustment mechanism, and separation from authoritative project-state mutation. |
| R-037 | PS + AI + DE + HA | Interaction-artifact classification, separation from authoritative state, and controlled incorporation/authorization path. |
| R-038 | DE + AI + HY | Internal control state separated from user-facing presentation; presentation can adapt without deleting material internal distinctions. |
| R-039 | DE + AI + PS | Observable signal capture, hypothesis/check distinction, procedural response mechanism, and continuity preservation. |
| R-040 | AI + DE + PS | Inquiry-state representation, sufficiency/convergence checks, closure and advancement controls; AI supports relevance/extraction. |
| R-041 | PS + DE + HY | Explicit milestone/work-unit state, completion-condition evaluator, evidence linkage, and reopening/supersession handling. |
| R-042 | PS + DE | Recovery-point persistence, interruption/resumption state, and deterministic reconstruction of the next justified action. |
| R-043 | DE + PS + AI + HI | Scheme integrity model, defect detection, control response, and explicit OPAQUE/Scheme interface. |
| R-044 | PS + DE + AI | Structured work-unit object with required fields, completeness checks, and controlled execution eligibility. |
| R-045 | DE + PS + HI | Runtime clock/time source, timestamp persistence, duration/sequence calculations, and explicit unknown temporal values. |
| R-046 | AI + DE + PS + HI | Feasibility model combining requirements, dependencies, resources, capabilities, constraints, and time. |
| R-047 | HY | Explicit governance/execution boundary plus interface and state controls preventing execution from silently becoming governance. |
| I-001 | Cross-cutting HY | Architectural rule that all material representations, state models, transitions, interfaces, and transformations preserve required distinctions unless an explicitly governed transformation permits equivalence. |

## 4. What the Matrix Tells Us

The requirements do **not** imply that OPAQUE should be a single program, a single prompt, or a single document.

They imply a distributed internal architecture with at least three materially different mechanisms:

### A. Persistent control representation

OPAQUE needs durable machine-readable state for matters such as:

- governed objects;
- state dimensions;
- relationships;
- dependencies;
- authority;
- operations;
- determinations;
- validation;
- changes;
- outcomes;
- closure;
- provenance;
- recovery;
- work units;
- milestones.

The existing 14-concept control model maps naturally to this persistent representation.

### B. Executable control

Some requirements cannot be safely satisfied by instructions to an AI alone.

The clearest examples are:

- temporal integrity;
- dependency enforcement;
- completion conditions;
- state-transition control;
- operation eligibility;
- recovery-point preservation;
- history preservation;
- audit triggering;
- exception boundaries;
- authority gates.

These require deterministic machinery.

### C. AI reasoning

Other requirements inherently involve interpretation or semantic reasoning:

- identifying ambiguous material;
- classifying meaning;
- detecting semantic conflict;
- interpreting feedback;
- evaluating qualitative impact;
- deciding whether an unknown is materially relevant;
- convergence/relevance analysis;
- feasibility reasoning;
- interpreting outcomes.

Those should not be reduced to deterministic code merely for the sake of making everything “mechanical.”

## 5. Preliminary Internal Architecture

The current evidence supports investigation of the following internal layers:

1. **Specification / Constitution**
2. **Controlled State Store**
3. **History / Provenance Store**
4. **Object / Relationship / Dependency Model**
5. **Authority & Transition Controller**
6. **Operation / Work-Unit Controller**
7. **Temporal Controller**
8. **Validation Controller**
9. **Audit Controller**
10. **Failure / Exception / Recovery Controller**
11. **AI Reasoning Interface**
12. **Human Decision Interface**
13. **Presentation / Complexity Adapter**
14. **Host / External Adapters**

These are architectural candidates derived from the requirements, not ratified final component names.

## 6. What Should Be Code vs Documentation

### Primarily documentation / written records

- OPAQUE constitutional meaning;
- specification;
- requirements;
- rationale;
- unresolved governance matters;
- human-readable explanations;
- architectural diagrams;
- design decisions;
- implementation records;
- audit reports.

### Primarily executable

- time tracking;
- dependency evaluation;
- eligibility checks;
- state-transition enforcement;
- gates/locks;
- completion-condition checks;
- recovery checkpoint creation;
- audit triggering;
- deterministic consistency checks;
- persistence operations;
- history integrity;
- interface enforcement.

### Primarily AI-mediated

- semantic interpretation;
- ambiguity analysis;
- conflict interpretation;
- qualitative impact reasoning;
- feedback interpretation;
- relevance/convergence reasoning;
- feasibility reasoning;
- procedural recommendations.

### Necessarily hybrid

- authority determination;
- validation;
- controlled incorporation;
- change control;
- conflict handling;
- Scheme integrity;
- milestone completion;
- process self-correction;
- interaction control;
- feasibility;
- governance/execution boundary.

## 7. Important Architectural Boundary

SillyTavern is not OPAQUE.

OpenAI/model infrastructure is not OPAQUE.

EverWorlds is not OPAQUE.

They are external systems or domains that may interact with OPAQUE.

The architectural relationship should therefore be investigated as:

OPAQUE core → explicit interfaces/adapters → host/runtime/model/project systems.

The host must provide capabilities OPAQUE requires; those capabilities do not define OPAQUE itself.

## 8. Minimum Executable Kernel — Candidate

The next architectural pass should test whether OPAQUE can be reduced to a small deterministic kernel around which AI reasoning and persistent records operate.

A candidate kernel would provide only:

- identity;
- state representation;
- transition evaluation;
- authority gate;
- condition evaluation;
- dependency evaluation;
- operation state;
- temporal state;
- persistence;
- provenance/history;
- recovery;
- audit invocation.

Semantic reasoning would be requested from an AI interface when deterministic evaluation is insufficient.

This is a hypothesis for architectural testing, not a final architecture.

## 9. Questions This Analysis Now Enables

Stage VII-A has converted the broad implementation question into concrete architectural questions:

1. What exact state objects must OPAQUE persist?
2. What exact transitions must the deterministic kernel control?
3. Which decisions require AI reasoning?
4. Which AI outputs may enter which state channels?
5. Where are human authorization gates required?
6. What is the minimum interface between OPAQUE and its host?
7. What is the minimum interface between OPAQUE and an AI model?
8. What information must be stored outside the conversation?
9. Which controls must survive process/session restart?
10. Which controls can be reconstructed from persistent state?
11. What constitutes an executable “lock”?
12. How should controlled failure prevent state corruption?
13. How does OPAQUE interact with the Scheme without becoming the Scheme?
14. What is the smallest viable OPAQUE implementation that satisfies the ratified requirements?

## 10. Architectural Non-Decisions

This analysis deliberately does **not** choose:

- JavaScript as the only implementation language;
- a database;
- a file format;
- a particular AI model/provider;
- a specific SillyTavern API;
- a particular UI framework;
- a browser-only or server-only architecture;
- a specific locking technology;
- a particular scheduling system.

Those decisions belong after the internal architecture and runtime model are sufficiently established.

## 11. Stage VII-A Completion Condition

Stage VII-A is complete when the implementation responsibility of each requirement has been classified sufficiently to derive the internal architecture without silently inventing substantive governance.

**Current determination:** the requirement set clearly implies that OPAQUE cannot be implemented as documentation alone or as AI prompting alone. It requires persistent controlled state, deterministic control mechanisms, AI reasoning interfaces, human authorization mechanisms where applicable, and explicit interfaces to external systems.

The exact component architecture, runtime lifecycle, state schema, and host/model interfaces remain to be designed in subsequent Stage VII passes.

## 12. Next First Action

**Stage VII-B — Internal Functional Architecture**

Derive the smallest set of internal OPAQUE capabilities/modules required by the Stage VII-A classification, then map every capability back to the existing 14-concept control model and R-001–R-047/I-001.

No technology selection should occur until this capability architecture is established.
