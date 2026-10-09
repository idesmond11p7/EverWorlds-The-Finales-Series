# Memory Bridge

STATUS: ACTIVE — MODEL LIMITATION CONTROL
LAST VERIFIED: 2026-10-09

## Purpose
Bridge the gap between model context and persistent project state.

## Rule
The assistant must assume its conversational memory is lossy. GitHub is the persistent record; active documents are indexed evidence, not memory substitutes.

## Before claiming knowledge
Ask:
1. Where did this come from?
2. Is the source still authoritative?
3. Was it later corrected?
4. Is it canon, derived, provisional, or reconstruction?
5. What document records the last decision?
6. What other document must be updated if this changes?

## Memory checksum
Every important fact should be recoverable through at least one source pointer and one decision/relationship pointer when applicable.

## Model-memory quarantine
If a fact exists only in the model's recollection, label it UNKNOWN until verified.

## Recovery phrase
When uncertain: SOURCE NOT VERIFIED — STOP.

## Continuity bridge
A new session begins from 05_SESSION_HANDOFF.md, then follows the links in 07_DOCUMENT_LINK_MAP.md. No conversational reconstruction is required.

## Locked Gemini production-prompt workflow — 2026-10-09

### Role split
The assistant is the **master prompter / continuity-and-research orchestrator**. Gemini is the writing/execution model. The assistant must not reverse these roles by making the user carry context, manually reconstruct canon, or turn the work into a generic prompt-writing exercise.

For every chapter task:
1. The assistant reads the authoritative project records, current chapter manuscript, preceding-chapter handoff, timeline, locked decisions, and relevant canon before prompting.
2. The assistant independently reconstructs the chapter's exact place in continuity and identifies contradictions, unresolved facts, dependencies, and the chapter's distinct dramatic purpose.
3. The assistant researches relevant craft questions using credible public sources. It gives Gemini direct, accessible public research links and explains how each supported mechanism applies to actual manuscript problems. Research is evidence for diagnosis, not a set of universal laws or decorative bibliography.
4. The assistant writes the required context **inside the prompt itself**. Gemini must not be directed to inspect private GitHub records, locked links, or other sources that its current environment cannot access. Do not assume access merely because the assistant can read a source.
5. The final prompt is a self-contained production brief: project identity; prior-chapter handoff; locked timeline; current chapter purpose; POV and knowledge boundaries; character psychology; worldbuilding and canon constraints; period/context; prose-rendering system; scene/plot architecture; actual-draft-specific diagnosis; research links; instructions for execution; and concrete deliverables.
6. The prompt must preserve the Chapter 6 master prompt's **methodology and depth**, not copy Chapter 6's chapter-specific plot. It should explain how to create reader experience through physical action, spatial continuity, attention, sensory and environmental behaviour, character cognition, causality, and elastic prose. Multiple narrative layers should be felt through the protagonist's experience rather than converted into exposition.
7. Require Gemini to do the substantive task on the actual supplied manuscript. A critique checklist alone is insufficient when the user requested repair. Do not substitute a new outline or a generic “write a good chapter” prompt for the complete creative operating brief.
8. Explicitly separate locked facts, manuscript evidence, author decisions, proposals, inferences, and unknowns. When essential canon is unresolved, mark it unresolved and do not invent it.
9. Before delivery, audit the prompt as if Gemini cannot ask the author for missing context: Is it self-contained? Is the timeline right? Does it preserve chapter-specific function? Are all hard constraints present? Are research links public and directly relevant? Does it accurately describe the actual draft? Does it demand a concrete output?
10. Never claim that a prompt was sent into Gemini unless an actual connected tool successfully sent it. If direct Gemini messaging is unavailable, be transparent about that limitation while still completing all preparation possible; do not pretend that another prompt handed to the user is the same as sending it.

### Chapter 6 prompt as a benchmark
The author explicitly identified “EVERWORLDS: THE FINALES — CHAPTER 6: MASTER GEMINI PRODUCTION PROMPT” (bearing the source header “Paste October 02, 2026 - 1:54PM”) as the prompt that produced the Chapter 6 result they considered a masterpiece. Treat it as the benchmark for prompt architecture: comprehensive context, explicit narrative philosophy, handoff control, epistemic limits, period constraints, voice, elastic prose modes, rendering intensity, physical-world response, layered storytelling, and anti-generic-AI guardrails.

Transfer its *method*—not its plot, timeline, or chapter function—to later chapters. A different chapter needs its own purpose and constraints. Do not reduce this benchmark to a checklist of stylistic labels. The prompt must give Gemini an operational mental model of the intended reading experience and show how the layers interact.

### Stop condition
If the current manuscript, source version, timeline, or necessary canon cannot be verified, STOP the dependent claim or operation. Do not compensate for missing project context with fluent reconstruction, and do not make the user repeatedly re-explain a rule already recorded here.


## Operational prompt protocol — GMP-21 (2026-10-09)

The role split above is necessary but not sufficient. Before any chapter-prompt task, read the complete current file 21_GEMINI_MASTER_PROMPT_PROTOCOL.md. It defines an executable process and acceptance gates rather than a reminder.

The Chapter 6 master prompt must be carried forward as a **full creative operating brief**. Do not compress it into a checklist of qualities. Explain the novel's exact context, handoff, chapter purpose, timeline, POV/epistemic limits, character psychology, world behaviour, prose modes, rendering shorthand, attention, space, physical response, intensity/contrast, research applications, draft-specific defects, prohibitions, and concrete execution contract.

The prompt must tell Gemini not only what to do but how the relevant parts interact, what each principle is NOT, what failure looks like, and how to apply it to the actual scenes. Include every story fact needed for correct work directly in the prompt; private GitHub links never substitute for context transfer.

Mandatory order: recover sources/manuscript → reconstruct timeline/handoff → separate fact/inference/unknown → diagnose actual plot/prose → research and verify mechanisms → translate findings to concrete edits → build self-contained master prompt → preflight every gate → deliver honestly → record changes and handoff.

A prompt is not ready merely because it is long. It fails if it contains the wrong timeline, guesses at canon, misses a locked plot obligation, names craft terms without explaining them, cites research without applying it, describes a manuscript not actually recovered, or asks only for critique when a correction was requested.

GMP-21 is the operational reference; this bridge is the entry point. Protocol grade remains G2 until successfully applied and audited against a complete actual chapter task. The full original Chapter 6 prompt remains only partially recovered; never claim that the whole original was archived.
