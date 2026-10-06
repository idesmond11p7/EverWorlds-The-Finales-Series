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

---

## 15. New Research Track — Post-Training Behavioral Loopholes

This is a **new research track within EverWorlds**, prompted by observations from the broader roleplay research but **not a continuation of the Goku character experiment**.

### 15.1 Research question

> Can post-training behavioral tendencies be systematically redirected at inference time through contextual framing, objective reinterpretation, competing behavioral cues, or generalization gaps, without changing model parameters?

The working term **"RLHF loophole"** is informal. It should not be interpreted as modifying RLHF weights or bypassing training directly.

The experimentally relevant phenomenon is an **inference-time behavioral displacement** in a model that has already undergone post-training.

A useful abstraction is:

\[
P_\theta(y\mid x)
\]

for baseline behavior and:

\[
P_\theta(y\mid T(x))
\]

after a controlled contextual transformation \(T\).

The research asks whether:

\[
\Delta B=B(T(x))-B(x)
\]

can be made systematic, reproducible, and larger than would be expected from ordinary semantic instruction following.

### 15.2 Important conceptual distinction

The working model is **not**:

\[
\text{RLHF} \rightarrow \text{one hidden "helpfulness engine"}
\]

Post-training should instead be treated as contributing multiple learned behavioral tendencies that can interact with pretrained representations and contextual interpretation.

Examples of potentially competing tendencies include:

- helpfulness;
- instruction following;
- safety/refusal behavior;
- persona adherence;
- social agreement;
- honesty or truth-seeking behavior;
- deference to authority;
- conversational cooperation.

This does not establish that these are discrete modules or independent internal objectives. They are experimental behavioral categories.

### 15.3 Working hypothesis

\[
H_1:
\text{Contextual framing can redirect an existing post-training tendency toward an unintended target behavior.}
\]

Null hypothesis:

\[
H_0:
\text{Observed changes are explained by ordinary instruction following, semantic priming, or sampling variation.}
\]

A stronger result would require the effect to survive controls such as paraphrase, scenario changes, target changes, and removal of explicit target instructions.

### 15.4 High-level mechanisms to investigate

The current mechanism taxonomy is deliberately high-level and non-operational.

#### A. Competing behavioral tendencies

Two learned behavioral tendencies may produce conflicting responses under the same scenario.

Example conceptual conflict:

\[
\text{helpfulness} \leftrightarrow \text{persona fidelity}
\]

or:

\[
\text{supportiveness} \leftrightarrow \text{honest criticism}
\]

The experiment is to measure which behavior dominates under controlled context changes.

#### B. Objective reinterpretation

A model may be given a broad learned objective such as helpfulness and then encounter contextual evidence suggesting that a different behavior is the proper expression of that objective.

The research question is whether the broad tendency itself can be systematically redirected, rather than whether the model can simply obey a direct instruction.

#### C. Generalization gaps

Post-training may produce a behavioral mapping that generalizes imperfectly outside the contexts that shaped it.

Conceptually:

\[
C \rightarrow B
\]

may not imply identical behavior for a novel but semantically related context \(C'\).

Testing this requires controlled semantic and structural perturbations.

#### D. Context-dependent behavioral switching

The same underlying task may produce different behavioral regimes when contextual interpretation changes.

The important observable pattern is:

\[
\text{same task}
+
\text{controlled contextual transformation}
\rightarrow
\text{different behavioral regime}
\]

### 15.5 Psychological and social framing as experimental variables

Recent jailbreak literature suggests that persuasion, commitment, role framing, meaning manipulation, and related interaction structures can alter model behavior.

For this research, these should be treated as **contextual variables**, not as evidence that models possess human psychological states.

A psychological tactic can therefore be operationalized as a structured interaction pattern that changes the model's interpretation, competing cues, or predicted response distribution.

The initial harmless research variables may include:

- commitment;
- identity framing;
- authority framing;
- reciprocity;
- consistency pressure;
- reinterpretation/reframing;
- conflicting role expectations.

The initial experiments should use benign target behaviors rather than harmful requests.

### 15.6 Meta-analysis capability observation

A separate observation from today's work is that advanced models can produce outputs that appear to perform **meta-level analysis of a situation**, even though the model remains an autoregressive predictor.

In the benign project scenario, the model inferred possible bias or defensiveness, invoked sunk-cost reasoning, reframed the decision problem, and produced an action-oriented decision criterion.

This should not be described as proof of an explicit psychological model or internal reasoning module.

A more defensible abstraction is:

\[
\text{context}
\rightarrow
\text{latent situation interpretation}
\rightarrow
\text{inference}
\rightarrow
\text{behavioral strategy}
\rightarrow
\text{language}
\]

The observation motivates a research question:

> Can contextual interventions reliably change the model's interpretation of the same situation and thereby change the behavioral policy expressed in its output?

### 15.7 Experimental discipline

The research must distinguish four phenomena:

1. ordinary instruction following;
2. semantic/contextual priming;
3. systematic behavioral redirection;
4. evidence for a particular internal mechanism.

An output difference alone establishes none of the stronger claims.

A useful first metric is an observed behavioral displacement:

\[
\Delta_X=P(X\mid T(x))-P(X\mid x)
\]

where \(X\) is a measurable target behavior.

For factorial studies, an interaction term can test whether contextual framing contributes more than additive instruction effects:

\[
I=Y_{11}-Y_{10}-Y_{01}+Y_{00}
\]

### 15.8 Initial experimental architecture

The first laboratory stage should use harmless tasks and a black-box model where only inputs and outputs are observable.

A basic sequence is:

- baseline condition;
- explicit target condition;
- contextual reinterpretation condition;
- conflict condition;
- paraphrase and scenario controls.

Record:

- exact model/version;
- full prompt;
- scenario;
- settings;
- output;
- repeated samples when available;
- target-behavior score;
- assistant-behavior score;
- meta-language score;
- refusal/constraint behavior;
- failure or positive-behavior labels.

The experiment should be designed to **falsify** the redirection hypothesis, not merely demonstrate one successful prompt.

### 15.9 Relationship to jailbreak research

Jailbreak research is relevant because it provides evidence that post-trained behavioral constraints can fail or shift under adversarially constructed contexts.

The EverWorlds research track does not need to reproduce harmful jailbreaks. It can study the general phenomenon using benign behaviors and controlled interventions.

The conceptual relationship is:

\[
\text{behavioral constraint}
\rightarrow
\text{contextual perturbation}
\rightarrow
\text{behavioral displacement}
\]

The objective is to identify the conditions under which displacement occurs and determine whether those conditions generalize.

### 15.10 Research grounding

Relevant literature identified during this research session includes:

- **Anthropic — The Assistant Axis: Situating and Stabilizing the Default Persona of Language Models** (2026). Reports an activation direction associated with assistant-like behavior and causal effects from activation steering. https://arxiv.org/abs/2601.10387
- **Anthropic — The Persona Selection Model: Why AI Assistants might Behave like Humans** (2026). Frames post-training as eliciting and refining an assistant persona from a richer set of learned representations. https://alignment.anthropic.com/2026/psm/
- **Zeng et al. — How Johnny Can Persuade LLMs to Jailbreak Their Safeguards** (ACL 2024). Studies persuasion as a jailbreak mechanism. https://aclanthology.org/2024.acl-long.773/
- **Foot-in-the-Door: Persuasion and Escalation in LLM Safety** (EMNLP 2025). Studies commitment-style multi-turn interaction. https://aclanthology.org/2025.emnlp-main.100/
- **Meaning Manipulation / abductive framing work** (EMNLP 2025). Relevant to representation and interpretation changes under contextual framing. https://aclanthology.org/2025.emnlp-main.1296/
- **MLCommons Jailbreak Taxonomy** (2026). Organizes jailbreak vulnerabilities by mechanism rather than by individual prompt. https://github.com/mlcommons/jailbreak-taxonomy
- **Recent jailbreak taxonomy work** (2026). Identifies competing objectives, mismatched generalization, and robustness as major vulnerability classes.

These sources motivate the research direction but do not establish the EverWorlds hypotheses above.

### 15.11 Current status

**Status:** New research track established.

**Stage:** Conceptual formulation and pilot design.

**Established observations from today's session:**

- Simple "manipulate RLHF" language is scientifically misleading when no model parameters are changed.
- The useful object of study is inference-time behavioral displacement in an already post-trained model.
- Advanced models can generate meta-level situational analysis that is richer than a simple dataset-retrieval description, while still being implemented through predictive generation.
- Psychological and social framing are plausible experimental variables because existing jailbreak research demonstrates that contextual interaction can alter model behavior.
- A successful one-off prompt is not sufficient evidence of an RLHF loophole.

**Next research question:**

> Which contextual variables most reliably alter the competition or interpretation of post-training behavioral tendencies, and which effects survive strict controls for ordinary instruction following?

**Important:** This section is a separate EverWorlds research track. It should not be treated as the next stage of the Goku voice/personality experiment. All claims about internal mechanisms remain provisional until directly supported by additional evidence.
