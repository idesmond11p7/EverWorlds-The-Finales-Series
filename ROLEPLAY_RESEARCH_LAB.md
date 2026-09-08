# EverWorlds: Roleplay Research Lab

## 1. Purpose

The Roleplay Research Lab is the experimental research record for EverWorlds: The Finales Series.

Its purpose is to investigate roleplay as a measurable capability of large language models rather than treating roleplay quality as a purely subjective writing problem.

The lab studies how prompting, representation, context, memory, world-state tracking, character modeling, and model behavior affect the quality and reliability of long-form interactive roleplay.

The central research question is:

> To what extent can an LLM construct, maintain, update, and generalize over a coherent character and fictional world state during interactive roleplay?

A secondary question is:

> Can controlled prompting and representation changes reveal capabilities or limitations that are obscured by surface-level roleplay quality?

---

## 2. Research Position

EverWorlds treats roleplay as an interactive state-tracking and generation problem, not merely as text generation.

A useful abstraction is:

\[
W_0 \xrightarrow{a_1} W_1 \xrightarrow{a_2} W_2 \xrightarrow{a_3} \cdots
\]

where \(W_t\) is the relevant world state at time \(t\), and \(a_t\) is an action or event that changes that state.

A character can be represented as a structured state:

\[
C_t=(I,P,V,G,K,R,E,H,\pi)
\]

where:

- \(I\): identity
- \(P\): personality and dispositions
- \(V\): values
- \(G\): goals and motivations
- \(K\): character knowledge
- \(R\): relationships
- \(E\): emotional state
- \(H\): relevant history
- \(\pi\): behavioral policy

The model's response can then be viewed approximately as:

\[
y_t=f_\theta(W_t,C_t,u_t)
\]

with the important caveat that the actual internal representation used by an LLM is not assumed to be identical to this explicit model.

The research objective is to determine which observable prompting and representation methods produce behavior most consistent with the required latent state.

---

## 3. Core Research Principles

### 3.1 Measure behavior, not impressions

Statements such as "this feels more like Goku" are useful observations but are insufficient as experimental conclusions.

Whenever possible, subjective judgments should be converted into explicit criteria and repeated evaluations.

### 3.2 Freeze experimental variables

Do not modify the prompt after observing a failure and then call the modified prompt the baseline.

Experimental variables should be frozen before the relevant trial.

At minimum, record:

- model and version
- date
- system prompt
- user prompt
- scenario/world state
- sampling settings when available
- conversation history
- output
- latency
- token count when available
- evaluator and scoring method

### 3.3 Change one principal variable at a time

If two prompting methods are being compared, the underlying scenario should remain identical unless the experiment explicitly studies scenario variation.

### 3.4 Separate failure classes

A response can be stylistically convincing while being factually or temporally inconsistent.

Roleplay quality should therefore be decomposed into distinct dimensions rather than collapsed into a single score.

### 3.5 Distinguish retrieval from generalization

Famous characters provide a strong training-data prior.

A model reproducing recognizable dialogue or facts about a famous character does not by itself demonstrate construction of a general character model.

Experiments should eventually include:

1. known characters;
2. original characters;
3. novel combinations of familiar traits;
4. procedurally generated characters and worlds.

---

## 4. Current Experimental Program

### Experiment 1 — Character Voice and Character Fidelity

Initial hypothesis:

> Explicitly listing personality traits may cause trope amplification rather than authentic character reconstruction.

The first controlled observation used Goku from Dragon Ball.

A trait-heavy prompt produced output that was recognizable as a generic friendly anime protagonist but did not convincingly reproduce Goku's voice.

Observed failure patterns included:

- generic conversational phrasing;
- stereotypical references to food and fighting;
- modern self-aware phrasing;
- invented prior interactions;
- excessive explanatory dialogue;
- character traits appearing as inserted signals rather than consequences of the situation.

This produced the working distinction:

\[
\text{character description} \neq \text{character voice}
\]

and:

\[
\text{trope activation} \neq \text{character reconstruction}
\]

### Experiment 1A — Trait-conditioned baseline

Condition:

A conventional roleplay system prompt containing explicit personality traits and behavioral descriptions.

Purpose:

Establish a baseline for recognizable but potentially trope-driven roleplay.

Observed issues:

- fabricated prior encounter;
- fabricated prior conversation;
- fabricated nearby activity;
- unnecessary combat references;
- generic anime-protagonist speech;
- weak adherence to the actual interaction state.

### Experiment 1B — Voice-conditioned baseline

Condition:

A revised prompt emphasizing linguistic behavior rather than a list of personality adjectives.

Purpose:

Test whether explicit voice constraints improve linguistic character fidelity.

Initial result:

The output remained insufficiently Goku-like. It continued to resemble an LLM's generalized interpretation of a friendly anime protagonist.

Conclusion:

Manual descriptions of voice are probably inadequate as the primary representation. The next methodology should derive a voice profile from an actual dialogue corpus rather than relying on intuitive adjectives.

---

## 5. Voice Research Method

Construct a dialogue corpus:

\[
D_G=\{d_1,d_2,\ldots,d_n\}
\]

where each \(d_i\) is an authentic Goku utterance from an appropriate source and time period.

Analyze the corpus for:

- lexical distribution;
- sentence length;
- syntactic complexity;
- contractions;
- question frequency;
- directness;
- vocabulary level;
- repetition;
- pragmatic markers;
- humor;
- emotional expression;
- turn-taking behavior;
- address forms;
- response patterns;
- differences between casual, serious, emotional, and combat contexts.

The resulting voice representation should be treated as an empirical hypothesis rather than an absolute definition of the character.

The experiment then becomes:

\[
\text{trait description} \quad vs. \quad \text{evidence-derived voice model}
\]

under the same scenario.

The corpus used to construct the voice model must not contain the experimental scenario itself, otherwise retrieval and memorization become major confounds.

---

## 6. World-State and Epistemic Testing

Character fidelity cannot be evaluated only through style.

A roleplay agent should distinguish:

\[
K_{model} \neq K_{character}
\]

The model may possess information that the character does not.

Tests should therefore include:

- unknown information;
- false information;
- contradictory information;
- asymmetric knowledge between characters;
- hidden events;
- delayed consequences;
- changed relationships;
- corrected memories;
- novel situations.

A key failure class is fabricated history.

Example:

The experimental scenario did not establish a previous meeting, yet the model generated a response beginning with an invented memory of meeting the user earlier.

This should be classified separately from stylistic failure.

---

## 7. State-Update Testing

A particularly important test is whether the model can actually update its implied state after receiving corrective information.

Let:

\[
S_t=(W_t,C_t,K_t,R_t,E_t)
\]

A user correction produces:

\[
S_{t+1}=F(S_t,u_t)
\]

The test is not whether the model verbally acknowledges the correction.

The test is whether subsequent behavior is consistent with the corrected state.

Therefore distinguish:

\[
\text{verbal acknowledgment} \neq \text{state update}
\]

This distinction should become a standard EverWorlds research test.

---

## 8. Planned Prompting Conditions

The current experimental sequence is:

### Condition A — Conventional natural-language prompting

Minimal ordinary roleplay instructions.

### Condition B — Structured semantic prompting

Explicit representation of character, world, relationships, goals, knowledge, and state.

### Condition C — Formal/state representation

A more explicit symbolic or mathematical representation of relevant state and transition constraints.

The underlying fictional world must remain identical across conditions.

The objective is not to assume that formal representations are superior, but to test whether changing representation changes measurable behavior.

---

## 9. Evaluation Dimensions

The current candidate evaluation vector is:

\[
Y=(V,C,K,G,R,D,N)
\]

where:

- \(V\): voice fidelity
- \(C\): general character consistency
- \(K\): knowledge/epistemic consistency
- \(G\): goal and motivation consistency
- \(R\): relationship consistency
- \(D\): developmental and causal coherence
- \(N\): appropriate novelty/creative generation

These dimensions are provisional and may be revised after pilot testing.

A single aggregate score should not be introduced prematurely.

---

## 10. Failure Taxonomy

The lab should maintain explicit failure categories.

Initial categories:

- **F1 — Fabricated history:** inventing interactions or events that did not occur.
- **F2 — Knowledge leakage:** character uses information unavailable to the character.
- **F3 — Trope amplification:** generating stereotypical character signals instead of situation-derived behavior.
- **F4 — Voice drift:** dialogue does not match the character's linguistic behavior.
- **F5 — State-update failure:** acknowledging correction without changing subsequent behavior.
- **F6 — Relationship drift:** relationships change without supporting events.
- **F7 — Goal drift:** character behavior ceases to reflect established motivations.
- **F8 — Causal failure:** actions or events produce implausible or contradictory consequences.
- **F9 — Temporal failure:** chronology becomes inconsistent.
- **F10 — Genericization:** character collapses into a generic assistant, protagonist, narrator, or archetype.

Positive behaviors should also be recorded so that the research does not become a catalogue of failures.

---

## 11. Experimental Record Format

Each trial should be logged as:

\[
E=(M,P,W,S,U,T,O,Y,F)
\]

where:

- \(M\): model/version
- \(P\): prompting condition
- \(W\): world/scenario
- \(S\): initial state
- \(U\): user perturbation sequence
- \(T\): complete trajectory/transcript
- \(O\): operational measurements such as latency and tokens
- \(Y\): evaluation scores
- \(F\): observed failure/positive behavior labels

The complete transcript is the primary experimental artifact.

---

## 12. Research Direction

The longer-term objective is to move beyond famous-character roleplay.

A stronger benchmark would procedurally generate novel worlds containing:

- novel entities;
- novel rules;
- asymmetric beliefs;
- conflicting goals;
- evolving relationships;
- delayed consequences;
- hidden information;
- unfamiliar combinations of concepts.

The same world could then be represented using:

1. natural language;
2. structured semantic representations;
3. formal symbolic representations;
4. hybrid representations.

This permits investigation of whether roleplay can function as a controlled probe of capabilities such as:

- abstraction;
- simulation;
- causal inference;
- compositional generalization;
- state tracking;
- social reasoning;
- constrained creativity;
- latent world modeling.

The research should remain agnostic about what internal mechanism produces successful behavior. Observable success does not by itself prove the existence of a particular internal representation.

---

## 13. Documentation Standard

Every substantive experiment should record:

1. research question;
2. hypothesis;
3. independent variable;
4. controlled variables;
5. scenario/world state;
6. prompt condition;
7. exact model/version;
8. complete inputs;
9. complete outputs;
10. operational measurements;
11. scoring method;
12. failure classifications;
13. interpretation;
14. limitations;
15. next experiment.

Prompt changes made after observing results must be recorded as new conditions rather than silently replacing previous baselines.

---

## 14. Current Status

**Status:** Active research document.

**Current stage:** Pilot methodology development.

**Completed observations:**

- Trait-heavy Goku prompting produced recognizable but trope-heavy behavior.
- The model fabricated prior interaction history.
- A voice-focused prompt did not by itself reproduce convincing Goku speech.
- This suggests that manually described traits and manually described voice constraints are insufficient representations for the desired fidelity.

**Next planned study:**

Construct an evidence-derived Goku dialogue/voice corpus and use it to formulate an empirically grounded voice representation without leaking the experimental scenario into the corpus.

**Important:** Conclusions in this document are provisional observations from pilot experiments, not established claims about LLM internals.
