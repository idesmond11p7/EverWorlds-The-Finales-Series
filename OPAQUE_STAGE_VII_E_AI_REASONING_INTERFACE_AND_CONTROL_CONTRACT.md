# OPAQUE — Stage VII-E AI Reasoning Interface & Control Contract

## Status

**Architectural analysis — provisional.**

Stage VII-E defines the boundary between OPAQUE's deterministic control system and external AI reasoning.

This document does not select a model provider, model family, API, programming language, prompt framework, or SillyTavern implementation. It also does not ratify unresolved governance matters.

## 1. Architectural Finding

AI is a reasoning component of OPAQUE, not OPAQUE itself.

OPAQUE must therefore treat model output as **candidate semantic information** that enters a controlled processing path.

The fundamental separation is:

**AI output ≠ determination ≠ validation ≠ authority ≠ state**

AI may help produce each of these as a candidate or provide evidence for them, but the existence of model output does not automatically create any of them.

The AI boundary must therefore be explicit:

~~~text
OPAQUE controlled state
        ↓
controlled context selection
        ↓
AI reasoning request
        ↓
external AI/model
        ↓
structured candidate result
        ↓
OPAQUE result validation / containment
        ↓
proposal / evidence / determination candidate
        ↓
authorization / validation where required
        ↓
controlled state transition
~~~

## 2. What AI Is For

AI reasoning may be used where semantic interpretation, synthesis, ambiguity handling, qualitative analysis, or language understanding materially benefits OPAQUE.

Candidate AI functions include:

- identify potentially relevant information;
- classify supplied material;
- extract entities, states, relationships, dependencies, conditions, or claims;
- detect possible contradictions;
- identify missing information;
- identify possible impacts of a proposed change;
- analyze evidence;
- generate candidate determinations;
- generate candidate proposals;
- assess semantic similarity or relevance;
- support convergence and controlled compression;
- identify possible failure causes;
- analyze feedback;
- identify possible recovery considerations;
- construct or refine human-readable explanations;
- identify uncertainty and competing interpretations;
- evaluate whether a question appears answerable from supplied context;
- assist with feasibility analysis;
- assist with audit analysis.

These are reasoning capabilities, not automatic authority.

## 3. What AI Is Not For

AI must not independently:

- grant itself authority;
- silently ratify requirements;
- silently change authoritative project state;
- silently resolve an unresolved governance matter;
- erase or rewrite historical state;
- treat its own output as validation merely because it produced the output;
- treat confidence as truth;
- treat plausibility as evidence;
- treat absence of contradiction as proof;
- treat a conversational instruction as authoritative merely because it appears in a prompt;
- bypass a required authorization or validation gate;
- report a transition as committed when deterministic persistence did not commit it;
- infer missing timestamps as actual timestamps;
- convert an unknown into a known value without preserving the basis of the transformation;
- conceal uncertainty merely to produce a more decisive answer;
- bypass recovery or failure controls.

The AI may recommend an action that would have these effects, but OPAQUE must keep the recommendation distinct from the resulting controlled state.

## 4. AI as an External Mechanism

The AI/model should be treated as an external reasoning mechanism.

Conceptually:

~~~text
OPAQUE
  │
  ├── reasoning request
  │
  ▼
AI PROVIDER / MODEL
  │
  ├── generated reasoning/result
  │
  ▼
OPAQUE
~~~

The model provider is therefore replaceable.

The architecture must not depend on one provider's identity, one model's behavior, or one prompt interface.

OpenAI, another model provider, a local model, or another reasoning service may eventually occupy this external boundary without changing OPAQUE's conceptual architecture.

## 5. AI Request Contract

Every governed AI request should have an identifiable request context.

Conceptually:

~~~text
AI REQUEST
├── request_identity
├── request_type
├── purpose
├── triggering_event/process
├── target_object(s)
├── relevant_state references
├── relevant evidence references
├── relevant relationships/dependencies
├── applicable constraints
├── known uncertainty
├── requested output schema
├── allowed operations
├── prohibited operations
├── provenance references
└── request timestamp
~~~

The request should contain only the context required for the reasoning task, subject to later security/privacy and performance constraints.

## 6. AI Context Is a Derived View

AI should not receive the entire durable OPAQUE state by default.

The controlled context package should be derived from authoritative state.

~~~text
DURABLE OPAQUE STATE
        │
        ├── relevance filtering
        ├── dependency/context expansion
        ├── constraint selection
        ├── provenance selection
        ├── uncertainty selection
        └── task-specific shaping
                 │
                 ▼
          AI CONTEXT PACKAGE
                 │
                 ▼
               MODEL
~~~

This prevents model context from becoming a substitute for durable state.

The model may therefore operate with incomplete context by design. The request must make relevant limitations explicit where material.

## 7. Reasoning Request Types

OPAQUE should use typed reasoning requests rather than one generic “ask the AI” operation.

Candidate request classes include:

### AR-01 Identification

Identify potentially relevant objects, claims, states, relationships, dependencies, or distinctions.

### AR-02 Classification

Assign candidate semantic categories to supplied information.

### AR-03 Extraction

Extract structured information from unstructured material.

### AR-04 Consistency Analysis

Identify possible contradictions, mismatches, or incompatible states.

### AR-05 Dependency Analysis

Identify possible dependencies, prerequisites, blockers, or affected downstream objects.

### AR-06 Impact Analysis

Analyze reasonably identifiable consequences of a proposed change.

### AR-07 Determination Support

Produce candidate conclusions from supplied evidence and context.

### AR-08 Proposal Generation

Produce candidate changes, actions, or next steps.

### AR-09 Feedback Analysis

Classify and analyze feedback without automatically incorporating it.

### AR-10 Audit Analysis

Identify possible control/process defects or anomalies.

### AR-11 Recovery Analysis

Analyze possible causes, consequences, and recovery options after interruption or failure.

### AR-12 Feasibility Analysis

Assess practical feasibility using supplied constraints and evidence.

### AR-13 Convergence Analysis

Identify whether continued exploration appears materially useful or whether the current information may be sufficient to advance.

### AR-14 Explanation

Generate a human-readable explanation of controlled state, reasoning, uncertainty, or consequences.

These request types are architectural categories, not final API names.

## 8. AI Output Contract

AI results should be structured enough for OPAQUE to distinguish semantic content from authority.

Conceptually:

~~~text
AI RESULT
├── result_identity
├── request_identity
├── result_type
├── subject/reference(s)
├── candidate_content
├── supporting_evidence references
├── reasoning_basis
├── uncertainty
├── confidence
├── alternatives
├── limitations
├── provenance
├── requested_follow_up
└── status
~~~

The exact serialization format remains implementation work.

## 9. Candidate Result Status

AI output should enter OPAQUE as a candidate result.

Candidate statuses may include:

- generated;
- partially structured;
- accepted for analysis;
- rejected;
- superseded;
- awaiting validation;
- awaiting human decision;
- incorporated through a governed transition.

The exact lifecycle should align with the controlled information lifecycle already defined by OPAQUE.

No candidate result becomes authoritative merely because processing succeeded technically.

## 10. Uncertainty Representation

AI output must preserve uncertainty where material.

Uncertainty should distinguish at least:

- unknown;
- incomplete context;
- ambiguous;
- competing interpretations;
- low-evidence inference;
- unresolved;
- conditionally supported;
- sufficiently supported for the current task, where a governed threshold exists.

Uncertainty is not merely a numeric confidence score.

A model can be highly confident and still be wrong.

Therefore:

**confidence ≠ truth**

## 11. Confidence Representation

Where confidence is useful, it should be represented as a property of the AI result rather than as an authority signal.

A confidence value should be accompanied by:

- what the confidence refers to;
- the basis or method if available;
- scope;
- relevant limitations;
- whether the value is model-generated or externally established.

OPAQUE must not use an arbitrary model confidence value as a substitute for validation or authority.

## 12. Evidence and Provenance

AI output should preserve references to the material on which the reasoning depended.

Conceptually:

~~~text
AI RESULT
   │
   ├── evidence reference(s)
   ├── context reference(s)
   ├── prior determination reference(s)
   ├── relevant state reference(s)
   └── originating request
~~~

The model's generated prose is not itself provenance.

Provenance must identify the source material and the controlled processing path through which the result was produced.

## 13. Reasoning Basis vs Hidden Chain-of-Thought

OPAQUE requires auditability of reasoning results, but this does not require storing or exposing private chain-of-thought.

The system should preserve an **auditable reasoning summary or basis** sufficient to understand:

- what question was asked;
- what context was supplied;
- what evidence was considered;
- what result was produced;
- what uncertainty/limitations were reported;
- what candidate implications followed.

The architecture should not require storage of unrestricted private internal model reasoning.

## 14. Structured Output Is a Control Boundary

OPAQUE should prefer structured AI results over free-form text when the result is intended for machine processing.

Free-form explanation may still be generated for humans.

Conceptually:

~~~text
MODEL
 ├── structured result → OPAQUE processing
 └── explanation → human interface
~~~

Where both are produced, the structured result is the machine-consumed artifact and the explanation is a presentation artifact.

Malformed or incomplete structured output must not be silently interpreted as valid controlled state.

## 15. Result Validation and Containment

Every AI result entering a controlled workflow should pass deterministic containment checks appropriate to its type.

Candidate checks include:

- required fields present;
- referenced objects exist;
- referenced state versions are current or explicitly historical;
- provenance references resolve;
- proposed changes target valid objects;
- claimed dependencies resolve;
- requested authority is represented as a requirement rather than assumed;
- unsupported state transitions are rejected;
- output does not contain prohibited authority claims;
- schema/type constraints are satisfied;
- unknown values remain explicit;
- contradictory fields are flagged;
- stale context is detected where possible.

A result failing structural checks is not a valid controlled result.

## 16. AI Output Is Not a State Transition

This is a central boundary.

~~~text
AI RESULT
   ≠
STATE TRANSITION
~~~

A model may propose:

> “Change object X from pending to complete.”

OPAQUE must interpret this as a candidate proposal.

Only the governed transition mechanism can determine whether the change is structurally eligible.

Authorization and validation requirements remain separate.

## 17. AI Output and Authority

The AI may identify that an action appears to require authority.

It may identify the applicable authority record if the authority model permits that lookup.

It must not create authority merely by asserting:

- “approved”;
- “authorized”;
- “the user intended this”;
- “this is obviously allowed”;
- “this should be treated as final.”

Authority must originate from the controlled authority mechanism.

Where authority semantics remain unresolved, the AI may surface the unresolved matter but must not resolve it silently.

## 18. AI Output and Validation

The AI may assist validation.

Examples:

- compare a result against criteria;
- identify missing evidence;
- identify inconsistencies;
- summarize validation evidence;
- propose a validation conclusion.

But:

**AI validation assistance ≠ authoritative validation**

The final validation state must follow the applicable governed validation mechanism.

This preserves U-004 rather than inventing its resolution.

## 19. AI Output and Determinations

A determination may be generated with AI assistance.

The result should preserve:

- determination candidate;
- evidence;
- reasoning basis;
- uncertainty;
- scope;
- validation status;
- authority status where relevant.

The determination remains distinct from both validation and authority.

## 20. AI Output and Proposals

AI is particularly suitable for proposal generation.

A proposal should identify:

- target;
- proposed change/action;
- rationale;
- evidence;
- dependencies;
- consequences;
- uncertainty;
- required validation;
- required authority;
- originating reasoning.

OPAQUE then decides how the proposal enters the governed workflow.

## 21. AI Failure Modes

OPAQUE must expect model failure as a normal architectural condition.

Relevant failure classes include:

- unavailable model;
- timeout;
- malformed output;
- incomplete output;
- hallucinated object;
- hallucinated evidence;
- incorrect interpretation;
- contradictory result;
- stale-context reasoning;
- overconfident reasoning;
- unsupported authority claim;
- unsupported validation claim;
- context truncation;
- provider/API error;
- tool-call failure;
- repeated non-convergent reasoning.

These failures must be handled without corrupting controlled state.

## 22. Model Failure Handling

Conceptually:

~~~text
AI REQUEST
   ↓
MODEL FAILURE
   ↓
record failure
   ↓
preserve prior controlled state
   ↓
retry / alternate reasoning / human review / defer
   ↓
resume through governed path
~~~

A model failure must not be represented as a project-state change merely because the request was initiated.

If an AI request produces no valid result, the governed state remains unchanged unless another valid process explicitly changes it.

## 23. Hallucination Containment

OPAQUE must treat model-generated references as untrusted until resolved.

For example:

~~~text
AI claims object X exists
        ↓
OPAQUE resolves object identity
        ↓
exists → continue
does not exist → flag unsupported reference
~~~

Similarly, claimed evidence, prior decisions, authority records, timestamps, and validation results must resolve against controlled records where such records are required.

The model cannot manufacture provenance.

## 24. Contradictory AI Results

OPAQUE may receive multiple AI results that disagree.

The system should preserve:

- each result;
- originating request;
- context;
- evidence;
- uncertainty;
- disagreement relationship.

It should not automatically choose the most recent, most confident, or most verbose result.

Where resolution is necessary, the system should route the conflict through the applicable reasoning, evidence, validation, or human decision process.

## 25. Iterative Reasoning

Some reasoning tasks may require multiple AI calls.

OPAQUE should treat each call as part of a controlled processing sequence.

~~~text
request
  ↓
reasoning result
  ↓
gap/conflict detection
  ↓
follow-up request
  ↓
new result
  ↓
convergence assessment
  ↓
candidate conclusion
~~~

Each material reasoning step should remain traceable.

The existence of multiple iterations must not itself imply that the final result is correct.

## 26. Tool-Using AI

An AI model may eventually use tools.

Tool use must remain subordinate to OPAQUE control.

Conceptually:

~~~text
AI
 ↓
tool request
 ↓
OPAQUE / controlled adapter
 ↓
tool execution
 ↓
observed result
 ↓
AI
~~~

The model should not receive unrestricted authority to perform arbitrary state-changing operations.

A tool may return observations or request an operation; OPAQUE determines whether and how that operation enters the governed workflow.

## 27. AI Context Freshness

AI reasoning can become stale while the model is processing.

Where material:

~~~text
context version captured
        ↓
AI processing
        ↓
current state checked
        ↓
same version → result may continue
changed version → stale-result handling
~~~

A result based on obsolete state must not silently overwrite newer controlled state.

This connects directly to DI-012.

## 28. AI Result Reconciliation

When a result returns, OPAQUE should reconcile it against current controlled state.

At minimum:

1. resolve referenced objects;
2. verify relevant state versions;
3. resolve evidence references;
4. verify dependency assumptions;
5. verify requested transition/proposal shape;
6. preserve uncertainty;
7. identify changed state since request creation;
8. route conflicts or stale results appropriately.

This is a deterministic control function, not a model prompt instruction.

## 29. Human Decision Boundary

When a human decision is required, AI may prepare the decision interface.

It may summarize:

- current state;
- proposed change;
- evidence;
- dependencies;
- consequences;
- uncertainty;
- validation status;
- unresolved matters.

It must not disguise a recommendation as a completed decision.

The human-facing interface should make the distinction visible:

**AI recommendation / analysis → human decision → OPAQUE controlled transition**

## 30. Prompt Architecture Is an Implementation Mechanism

Prompting is part of implementation, not the definition of OPAQUE.

A future implementation may use:

- system prompts;
- structured prompts;
- schemas;
- tool definitions;
- function calling;
- context templates;
- retrieval;
- model-specific adapters.

None of these should become the conceptual source of authority.

If the prompt changes but the controlled-state and control contract remain intact, OPAQUE remains the same system.

## 31. Provider and Model Independence

The AI contract should be provider-neutral.

The adapter layer may translate the abstract OPAQUE request into provider-specific mechanisms.

~~~text
OPAQUE AI CONTRACT
        ↓
AI ADAPTER
        ├── Provider A
        ├── Provider B
        ├── Local model
        └── Future provider
~~~

This prevents OPAQUE from becoming an OpenAI-specific architecture.

## 32. Relationship to SillyTavern

SillyTavern is a host/execution environment for EverWorlds.

It is not the definition of OPAQUE and must not be treated as the AI reasoning contract itself.

The eventual relationship should be:

~~~text
OPAQUE
  │
  ├── AI reasoning contract
  │        ↓
  │   AI adapter/provider
  │
  └── host adapter
           ↓
      SILLYTAVERN
~~~

SillyTavern may provide generation hooks, extension APIs, event streams, context insertion, tool interfaces, storage, UI, and other host mechanisms.

Those mechanisms are implementation resources.

OPAQUE remains conceptually independent of them.

Likewise:

**AI provider ≠ SillyTavern ≠ OPAQUE**

## 33. Security and Sensitive Context

The architecture must eventually account for:

- secret exposure;
- unnecessary context transmission;
- untrusted tool results;
- malicious or malformed model output;
- prompt injection through external content;
- cross-context contamination;
- unintended data disclosure.

This stage does not define final security policy. It establishes that the AI boundary is an untrusted processing boundary and must be treated accordingly.

## 34. AI Auditability

For materially relevant reasoning requests, OPAQUE should be able to reconstruct:

- why the request occurred;
- which controlled context version was supplied;
- which model/provider mechanism was used where relevant;
- what structured result returned;
- what evidence/context references were involved;
- what containment checks occurred;
- what disposition followed;
- whether the result affected later controlled state.

This does not require retaining unrestricted private model reasoning.

## 35. AI Contract in One View

~~~text
                 OPAQUE CONTROLLED STATE
                          │
                          ▼
                CONTEXT SELECTION
                          │
                          ▼
                 AI REQUEST CONTRACT
                          │
                          ▼
                    AI ADAPTER
                          │
                          ▼
                  EXTERNAL MODEL
                          │
                          ▼
                  STRUCTURED RESULT
                          │
              ┌───────────┴───────────┐
              ▼                       ▼
        CONTAINMENT CHECKS       HUMAN EXPLANATION
              │
              ▼
        CANDIDATE RESULT
              │
      ┌───────┼────────┐
      ▼       ▼        ▼
   PROPOSAL DETERMINATION EVIDENCE/ANALYSIS
      │       │        │
      └───────┼────────┘
              ▼
       VALIDATION / AUTHORITY
              │
              ▼
      CONTROLLED TRANSITION
              │
              ▼
       UPDATED OPAQUE STATE
~~~

## 36. Architectural Consequences

Stage VII-E establishes the following implementation constraints:

1. OPAQUE requires an abstract AI reasoning contract independent of any model provider.
2. AI receives derived context, not unrestricted durable state.
3. AI outputs are candidate semantic artifacts until controlled processing establishes otherwise.
4. AI output must be structurally validated and contained before entering controlled workflows.
5. Authority and validation cannot be inferred from model confidence or assertions.
6. AI failures cannot corrupt controlled state.
7. Stale AI results must be detected where material.
8. Tool use by AI must remain subordinate to OPAQUE control.
9. AI reasoning must remain auditable without requiring unrestricted private chain-of-thought storage.
10. SillyTavern remains a host adapter, not OPAQUE's conceptual architecture.
11. Provider-specific prompt/API mechanisms remain implementation details behind the abstract contract.
12. OPAQUE must remain operationally meaningful even if the AI provider is unavailable.

## 37. Stage VII-E Completion Condition

Stage VII-E is complete when the architecture defines:

- the purpose and boundary of AI reasoning;
- request categories;
- controlled context construction;
- structured result semantics;
- uncertainty and confidence treatment;
- evidence and provenance requirements;
- containment and validation of AI output;
- authority/validation separation;
- model failure handling;
- stale-context handling;
- iterative reasoning;
- tool-use boundaries;
- human decision boundary;
- provider independence;
- host independence;
- AI auditability.

**Current determination: Stage VII-E meets this condition.**

No model provider, prompt architecture, API, programming language, or SillyTavern implementation has been selected.

## 38. Next First Action

**Stage VII-F — Enforcement, Intervention & Control Mechanism Architecture**

Determine:

> **Which OPAQUE controls are merely informational, which must be monitored, which must be blocked or gated, which require intervention, and which require recovery; how those mechanisms operate without collapsing AI reasoning, deterministic control, human authority, and host behavior into one layer.**

The next stage should define enforcement mechanics before selecting concrete JavaScript or host APIs.
