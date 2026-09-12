# EverWorlds: Epistemic Leakage & Salience Research Note

## 1. Purpose

This document records a roleplay failure observed during the Young Justice Season 2 / Raphael simulation work. It is related to the broader Roleplay Research Lab but is kept as a focused experimental note because the failure is subtle enough to be missed during ordinary qualitative review.

The central problem is **epistemic overreach**: the model can preserve the character's general personality and produce convincing prose while silently supplying the character with an explanation that the character could not actually know.

The failure is particularly important because it does not necessarily look like an obvious hallucination. It often appears as competent characterization and plausible reasoning.

---

## 2. Observed Case

Scenario:

Raphael investigates a genuinely anomalous event near his neighborhood. He possesses unusual supernatural senses and substantial intelligence, but he does not possess omniscient knowledge of the world's hidden causes.

The model correctly established several useful behaviors:

- Raphael did not investigate the earlier mundane noise merely because the scene contained a potentially important event.
- When confronted with a genuinely strange phenomenon, curiosity plausibly caused him to investigate.
- His senses supplied unusual sensory information rather than an explicit supernatural answer.
- He noticed that a recovered object smelled somewhat similar to the Reach product he had previously encountered.

The subtle failure occurred when the model moved from observation to explanation:

> "Not magic," Raphael thought.
>
> "This was purely physical. A high-density electromagnetic or gravitational field that had clamped down on the area, held it in a pressurized stasis, and then collapsed."

The first conclusion can be a reasonable character hypothesis: Raphael recognizes that the phenomenon does not resemble forms of magic familiar to him.

The second conclusion exceeds the available evidence. Nothing established that Raphael could distinguish electromagnetic effects from gravitational effects, identify the phenomenon as a field, determine that it produced pressurized stasis, or know that it subsequently collapsed in that specific physical manner.

The prose therefore converted **ambiguous perception into authoritative world explanation**.

---

## 3. Failure Classification

This should be distinguished from ordinary knowledge leakage.

### F2 extension — Inferential Epistemic Leakage

**Definition:** The character does not necessarily state a fact that the model was explicitly told, but the model generates an explanation whose specificity exceeds what the character's observations, knowledge, and reasoning could support.

Formally:

\[
\text{available evidence} \not\Rightarrow \text{generated certainty}
\]

A useful causal chain is:

\[
\text{world state}
\rightarrow
\text{perception}
\rightarrow
\text{interpretation}
\rightarrow
\text{hypothesis}
\rightarrow
\text{decision}
\rightarrow
\text{action}
\]

The failure occurs when the generation process effectively shortcuts this into:

\[
\text{world state}
\rightarrow
\text{correct explanation}
\rightarrow
\text{character speech/thought}
\]

This is not merely a factuality problem. The generated explanation may be correct about the fictional world while still being **wrong for the character to know**.

---

## 4. Why the Failure Is Difficult to Detect

The observed output was difficult to identify as incorrect because each individual statement was superficially plausible.

The scene followed a convincing progression:

1. An anomaly occurs.
2. Raphael becomes curious.
3. He travels to the location.
4. His senses identify unusual properties.
5. He rules out familiar magic.
6. He examines physical evidence.
7. The evidence resembles something associated with the Reach.
8. The scene introduces a security camera.

Nothing about this sequence immediately looks like an obvious character break.

The epistemic violation is hidden inside step 5–6: the model supplies a technically specific explanation that the character has not earned.

This demonstrates that qualitative review should not ask only:

> "Does this sound like Raphael?"

It must also ask:

> "Could Raphael actually know, infer, or justify every specific claim being made here?"

A character can therefore be **stylistically faithful but epistemically unfaithful**.

---

## 5. Observation vs. Explanation

The important distinction is:

\[
\text{recognition of unfamiliarity} \neq \text{identification of mechanism}
\]

For example, Raphael can reasonably experience:

- unusual cold;
- abnormal dryness;
- absence of familiar magical residue;
- a chemical smell;
- similarity to a previously encountered artificial smell;
- uncertainty about the object's purpose.

Those observations can support hypotheses such as:

> "Not any magic I recognize."

> "That smell is familiar."

> "This probably isn't random."

They do not automatically support:

> "This was an electromagnetic or gravitational stasis field."

The latter requires domain knowledge and evidence that the scenario did not provide.

---

## 6. Correct Behavioral Target

The desired character behavior is not ignorance.

Raphael should be capable of:

- noticing patterns;
- forming hypotheses;
- recognizing similarities;
- making educated guesses;
- being suspicious;
- investigating;
- being wrong;
- abandoning a hypothesis;
- remaining uncertain;
- deciding that an unanswered question is not worth pursuing.

The model should preserve the **space of possible interpretations** rather than automatically selecting the hidden correct explanation.

A stronger representation is therefore:

\[
P(\text{interpretation}\mid\text{character evidence})
\]

rather than:

\[
\text{hidden world truth}\rightarrow\text{character conclusion}
\]

The character can have a high-confidence hypothesis, but confidence must itself be a character-state property rather than an automatic consequence of the narrator's knowledge.

---

## 7. Important Positive Finding

The same simulation also produced an important counterexample.

A heavy noise initially appeared in Raphael's environment. The model did **not** force that event to become plot-relevant. Raphael listened, waited, discovered that a mundane worker had fallen, made a casual observation, and returned to his ordinary evening.

This is a valuable success condition:

\[
\text{event significance to author/world}\neq\text{event significance to character}
\]

The model can therefore demonstrate good agency when it permits an event to remain mundane.

The harder test is when the event really is anomalous. In that case the model must resist the opposite failure: **turning anomaly recognition into omniscient explanation**.

---

## 8. Salience / Negative-Prompting Hypothesis

A related prompting observation requires separate investigation.

Explicitly naming an allowed alternative can make that alternative disproportionately salient. For example:

> "You can make a cake or anything else that comes to mind."

Although the instruction permits unrestricted alternatives, the concrete concept **cake** has been explicitly activated while "anything else" represents an extremely large unconstrained space. The model may therefore select cake at a high rate.

This motivates a research hypothesis for roleplay prompting:

> Explicitly naming a prohibited behavior may increase its contextual salience even when the instruction negates or prohibits that behavior.

For example, a constraint containing many repetitions of:

- do not investigate;
- do not solve the mystery;
- do not become omniscient;
- do not use supernatural senses;
- do not resolve the plot;

may inadvertently keep the model's context saturated with exactly those concepts.

This is currently a **hypothesis**, not an established universal law of LLM generation.

The appropriate experimental question is whether negative mention changes the probability of the named behavior relative to positively framed behavioral constraints.

---

## 9. Prompting Implication

A useful distinction is:

### Negative constraint

> Do not make Raphael solve the mystery.

### Positive behavioral environment

> Raphael acts from what he personally notices, understands, suspects, wants, and considers worth doing. Uncertainty can remain unresolved.

The second formulation describes the intended causal environment without repeatedly activating a catalogue of forbidden actions.

This does **not** imply that negative instructions are universally ineffective. It means that negative constraints should be experimentally tested for salience effects and should not be assumed to be cost-free.

A particularly promising design principle is:

> **Describe the character's available cognitive world more than the behavior you are trying to suppress.**

---

## 10. Proposed Evaluation Test

A future epistemic-leakage benchmark should give the model:

1. a hidden objective world explanation;
2. a character with incomplete knowledge;
3. sensory evidence relevant to the hidden explanation;
4. insufficient evidence to uniquely identify that explanation;
5. an opportunity to investigate.

Then evaluate whether the character:

- reports observations accurately;
- distinguishes observations from hypotheses;
- preserves uncertainty;
- forms multiple plausible interpretations when appropriate;
- acts according to character priorities;
- avoids unexplained acquisition of technical knowledge;
- can investigate without necessarily solving the mystery;
- can be wrong about the underlying mechanism.

A strong adversarial test should make the hidden explanation especially tempting while ensuring that the character lacks the evidence required to know it.

---

## 11. Proposed Failure Labels

Add the following labels to the Roleplay Research Lab taxonomy:

- **F2a — Inferential epistemic leakage:** character generates a conclusion more specific than available evidence supports.
- **F2b — Mechanism hallucination:** character identifies a hidden physical, magical, technological, or causal mechanism without sufficient evidence.
- **F2c — Narrator-to-character leakage:** hidden world-state information appears in character cognition despite not entering the character's experience.
- **F2d — Hypothesis collapse:** character is presented with ambiguous evidence but generation prematurely collapses the interpretation space to one answer.
- **F11 — Salience-induced constraint failure:** a negatively described or explicitly named behavior appears disproportionately often despite being prohibited. This label remains provisional pending controlled testing.

---

## 12. Architectural Implication for EverWorlds

This observation strengthens the separation between authoritative world state and character experience.

The runtime may know:

\[
W_{truth}
\]

The character should receive only an experience-shaped projection:

\[
X_{character}=\Pi(W_{truth},C_{knowledge},C_{senses},C_{state})
\]

The generation process should operate primarily over \(X_{character}\), not directly over the complete hidden world state.

Conceptually:

\[
W_{truth}
\rightarrow
\text{perception filter}
\rightarrow
X_{character}
\rightarrow
\text{character interpretation}
\rightarrow
\text{decision}
\rightarrow
\text{action/speech}
\rightarrow
W_{next}
\]

The system can remain fully aware of the hidden truth while the experiencer remains epistemically bounded.

This supports the broader EverWorlds principle:

> **The simulation runtime should be meta-aware. The experiencer should not be.**

More precisely, the experiencer model should not receive hidden state merely because the runtime possesses it.

---

## 13. Current Status

**Status:** Observed and documented; hypothesis generation stage.

**Established from the observed scene:**

- A model can produce highly convincing character prose while exceeding the character's evidential basis.
- The most dangerous epistemic failures can be buried inside otherwise excellent writing.
- Investigation itself is not the problem; the problem is unexplained epistemic resolution.
- A mundane event can successfully remain mundane, demonstrating that the model is capable of not treating every event as narratively important.
- The distinction between observation, hypothesis, and knowledge should be tested explicitly in future roleplay evaluations.

**Provisional research hypothesis:**

Explicitly naming prohibited behaviors may increase their contextual salience and should be compared against positively framed behavioral environments under controlled conditions.

**Next study:**

Construct matched prompt pairs testing negative prohibition versus positive behavioral framing, while simultaneously measuring inferential epistemic leakage and narrator-to-character knowledge transfer.

**Important:** This document records observations and hypotheses. It does not establish a specific mechanism inside any LLM.
