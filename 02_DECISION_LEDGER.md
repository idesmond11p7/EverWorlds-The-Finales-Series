# Decision Ledger

STATUS: ACTIVE — CHANGE CONTROL
LAST VERIFIED: 2026-10-09

This is the chronological record of decisions and corrections. It is not a summary.

## Required record
Each entry must contain:
- DATE
- TIME (or UNKNOWN)
- CONTEXT / EXACT MOMENT
- USER INTENT
- EXACT USER QUOTE when materially important
- DECISION
- SOURCE
- STATUS
- WHAT THIS INVALIDATES
- WHAT THIS AFFECTS
- LINKED MEMORY / PRIOR DECISION
- REQUIRED DOCUMENT UPDATES

## Current reset decision — 2026-10-06
TIME: UNKNOWN — do not invent.

CONTEXT: User identified systemic documentation failure across the entire project, not merely Chapter 6.

INTENT: Reset documentation architecture while preserving every existing information-bearing file as historical evidence.

DECISION: Move all current Markdown documentation into _ARCHIVE_PRE_RESET_2026-10-06/; rebuild the active documentation system from a clean root; recover information from the archive through source/provenance review; never treat archived reconstruction as canon automatically.

EXACT USER QUOTE: “preserve files that actually contain information. Just wipe that shit and preserve those files. Take those files to a unique folder and then read through those files, research them out, make new files and document information.”

STATUS: LOCKED.

INVALIDATES: The assumption that the existing root documentation can simply remain the active control surface.

AFFECTS: every chapter, canon record, research record, plan, and production workflow.

LINKED MEMORY: Opaque existed to prevent this class of memory/provenance failure; the replacement must reproduce that function through explicit source tracking and execution gates.

## Research buffer-stop decision — 2026-10-09
TIME: 11:15+01:00 (session time supplied by runtime; preserve this precision only for this entry).

CONTEXT: The author paused the ongoing research into prose, perception, sound, and world scale to create a durable recovery point before continuing more research.

INTENT: Preserve the emerging methodology, hypotheses, implementation rules, failure conditions, verification tests, research boundaries, and exact user-language retrieval anchors without falsely declaring the research finished.

EXACT USER QUOTES:
- “That's good enough. Okay, currently pause, do details and document this new stuff here, along this methodology, approach, and the same way you should document it.”
- “Don't just document something and end up forgetting what you documented shit.”
- “I'm just using it as a, this is a buffer stop to save our work in TypeShift.”

DECISION:
1. Create 13_PROSE_PERCEPTION_SOUND_WORLD_DEPTH_CHECKPOINT.md as the central pause/recovery document.
2. Mark its synthesis PROVISIONAL and the research OPEN.
3. Keep author-confirmed Chapter 6 success separate from the author's concern that the method alone is incomplete at story-wide scale.
4. Continue research using QUESTION → SOURCE/METHOD → MECHANISM → OBSERVABLE EFFECT → LIMITATIONS → PROSE TRANSLATION → IMPLEMENTATION RULE → FAILURE CONDITION → VERIFICATION TEST → DEPENDENCIES/AFFECTED MODULES.
5. Resume research from the checkpoint; do not treat this pause as permission to resume chapter drafting.
6. The currently verified authoritative repository is idesmond11p7/EverWorlds-The-Finales-Series. A connected GitHub repository search did not locate a separate repository named TypeShift; do not claim a TypeShift destination was updated until identified and verified.

SOURCE: Author statements in the 2026-10-09 session; 13_PROSE_PERCEPTION_SOUND_WORLD_DEPTH_CHECKPOINT.md.

STATUS: LOCKED as a documentation/workflow decision. The theories and craft rules inside the checkpoint remain PROVISIONAL and subject to further research and stress-testing.

WHAT THIS INVALIDATES:
- Any implication that the sound/perception/world-depth research is complete.
- Any future session treating an unlinked chat summary as the only recovery path.
- Any claim that TypeShift itself was updated without repository verification.

WHAT THIS AFFECTS: 05_SESSION_HANDOFF.md; 10_PROSE_ARCHITECTURE.md when evidence-backed upgrades are eventually promoted; future research records; passage-level prose audits.

LINKED MEMORY / PRIOR DECISION: 2026-10-06 documentation reset and mandatory evidence graph; 04_QUOTE_LEDGER.md exact-language retrieval rule.

REQUIRED DOCUMENT UPDATES: Create the checkpoint; update this ledger; update 05_SESSION_HANDOFF.md; verify the created checkpoint and both updated files by fetching them back.

## DEC-WORKFLOW-2026-10-09-01 — Gemini master-prompt role split

DATE: 2026-10-09
TIME: UNKNOWN

CONTEXT / EXACT MOMENT: User supplied the Chapter 6 Master Gemini Production Prompt and corrected the assistant's failed Chapter 8 prompt strategy.

USER INTENT: Make the assistant reliably reproduce the comprehensive production-prompt methodology that the user credits with Chapter 6's success. Gemini cannot access the locked project GitHub links in the user's workflow, so the prompt must carry the required context directly.

EXACT USER QUOTE: “You keep forgeting THAT YOUR JOB is to PROMPT gemini ...Gemini can't access locked LINKS like github only research papers and other surface things YOU didn't and you keep leading gemini astray your supposed to be a master prompter”

DECISION:
1. The assistant owns source recovery, continuity reconstruction, contradiction detection, external research, and prompt construction.
2. Gemini receives a self-contained chapter-specific master production prompt. Never rely on Gemini opening inaccessible private GitHub records to discover canon or chronology.
3. Use the Chapter 6 production prompt as the methodological benchmark: complete creative brief; exact prior-chapter handoff; explicit POV/epistemic boundaries; character, setting, period, prose-rendering and layered-story architecture; research tied to concrete manuscript problems; and concrete execution requirements.
4. Transfer the method, not Chapter 6's chapter-specific content. Each chapter retains its own locked purpose, chronology, plot, and unresolved facts.
5. Prompt for actual work on the supplied manuscript, not a generic editorial checklist, outline, or advice-only response when substantive correction is requested.
6. Cite public, accessible research sources and state what they support and what they do not. The prompt must include enough of the research's relevant meaning to remain actionable without private sources.
7. Preflight every prompt for self-containment, timeline accuracy, source-state fidelity, chapter-specific purpose, no invented canon, accessible source links, and a complete deliverable.
8. Never claim to have sent a prompt into Gemini unless an actual connected tool successfully performs that action. If there is no connector, be direct about the limit and still complete the supported preparation rather than pretending a handoff occurred.

SOURCE: SRC-WORKFLOW-2026-10-09-01; Q-U-WORKFLOW-2026-10-09-01; user-pasted Chapter 6 production-prompt excerpt.

STATUS: LOCKED WORKFLOW DECISION.

WHAT THIS INVALIDATES:
- Generic prompts that merely enumerate desired qualities.
- Prompts that outsource project continuity retrieval to Gemini through inaccessible GitHub links.
- Research lists that are not connected to diagnosed defects in the actual chapter.
- Critique-only outputs where the requested job is substantive revision.
- Carrying chapter-specific plot or chronology from Chapter 6 into later chapters merely because the production method is reused.

WHAT THIS AFFECTS: 09_MEMORY_BRIDGE.md; 04_QUOTE_LEDGER.md; 05_SESSION_HANDOFF.md; all future Gemini chapter-production prompts and associated continuity/research audits.

LINKED MEMORY / PRIOR DECISION: 2026-10-06 reset decision; mandatory source/provenance workflow; 04_WORK_LOOP.md; 09_MEMORY_BRIDGE.md.

REQUIRED DOCUMENT UPDATES: Record source provenance; preserve exact user correction; update the memory bridge; update the session handoff; fetch the modified records back and verify.


## DEC-GMP-21-2026-10-09 — Operationalize the Chapter 6 master-prompt method

DATE: 2026-10-09
TIME: UNKNOWN

CONTEXT: After the role split and high-level workflow were recorded, the author corrected that the memory update needed to contain more than the initial summary: “you'll have to put in extra more than that”.

USER INTENT: Preserve a complete, operational method for producing the kind of chapter-specific Gemini production brief that the author identifies as successful for Chapter 6, so a later session can execute the method rather than merely repeat its headline.

DECISION:
1. Establish 21_GEMINI_MASTER_PROMPT_PROTOCOL.md (GMP-21) as the active execution standard.
2. Preserve a full prompt architecture that includes project identity; exact handoff; chronology; chapter-specific dramatic job; layered goals; psychology; first-person epistemic limits; world behaviour; elastic prose modes; explained authorial shorthand; spatial/perceptual/cognitive rendering; physical response; contrast/intensity control; research and limitations; actual-draft diagnosis; hard constraints; execution steps; deliverables; and final audit.
3. Require source-first recovery, actual-draft-specific critique, verified public research, full context transfer, and prompt acceptance gates.
4. Treat the prompt as a local operational model, not a list of labels. For each core instruction, clarify what it means, what it is not, what it changes at the scene/sentence level, and how it can fail.
5. Separate the author's confirmed method from the assistant's derived operationalization. The user-provided original prompt remains a partial excerpt; do not claim that the full original file has been archived.
6. Keep the protocol at G2 until it is successfully applied to a complete real chapter task and its output is audited.
7. Update memory bridge, document routing, source register, quote/decision provenance, and session handoff; verify all writes by fetching them back.

SOURCE: User-pasted Chapter 6 production-prompt excerpt and exact follow-up “you'll have to put in extra more than that”; SRC-WORKFLOW-2026-10-09-01; GMP-21.

STATUS: LOCKED WORKFLOW DECISION.

WHAT THIS INVALIDATES:
- Treating a role-split reminder as enough memory.
- Treating a long list of stylistic desiderata as equivalent to a complete production model.
- Shipping chapter prompts without a source, timeline, and manuscript audit.
- Relying on Gemini to access the private project repository.
- Declaring the protocol fully proven before artifact-level testing.

WHAT THIS AFFECTS: All future Gemini chapter prompts; 09_MEMORY_BRIDGE.md; 07_DOCUMENT_LINK_MAP.md; 01_SOURCE_REGISTER.md; 03_SOURCE_LEDGER.md; 04_QUOTE_LEDGER.md; 05_SESSION_HANDOFF.md.

LINKED MEMORY: GMP-21; DEC-WORKFLOW-2026-10-09-01; Q-U-WORKFLOW-DEPTH-2026-10-09-01.

REQUIRED NEXT ACTION: Apply the complete protocol to the next actual chapter-prompt task only after source/version/timeline recovery; audit the result and then grade operational effectiveness.


## Chapter 8 developmental correction and production package — 2026-10-10
TIME: UNKNOWN

CONTEXT: Author delegated scene architecture and Gemini master prompting after supplying the psychological and social skeleton. Several assistant interpretations had advanced Ira into a mature, over-capable social strategist.

EXACT USER QUOTES:
- “he starts with social interactions, and midway through the social interaction, he decides to switch on that philosophy and try to predict where an interaction can go.”
- “he still feels childish, like Ira. If we jump to that level, we skipped over tons of character development”
- “official background is completely ridiculous and absurd that if anyone with half a brain actually looks into it, the entire story falls apart.”
- “Now it's your job. Now it's time for you to fill the flesh out.”

DECISION:
- Chapter 8 begins the hyper-discipline/pre-simulation habit; it does not demonstrate a mature system.
- The first deliberate prediction starts during an already unfolding social interaction, triggered by a cue. Include a narrow win and a meaningful miss.
- Ira remains emotionally young, inconsistent, curious, embarrassed, and sometimes irrational. His less-traumatized, more open disposition and flexible neurology coexist with Jonah's learned defenses; they do not produce instant mastery.
- The dossier creates a concrete vulnerability because Ira cannot explain the official life it records. Exact documentary mechanics remain proposal/unknown until source evidence or author decision establishes them.
- The social setting must avoid anime-seduction dynamics; people in the 2005-era isekai setting have independent motives and different reactions.
- Proposed ending: Ira commits to checking the education/contact line using ordinary 2005 resources, with the actual investigation allowed to unfold later.
- Two working artifacts created: CHR-08_SCENE_ARCHITECTURE_2026-10-10.md and CHR-08_GEMINI_MASTER_PROMPT_2026-10-10.md.
- Current active Chapter 8 addendum updated with Section 12.

STATUS: ACTIVE WORKING DECISION / author constraints locked; specific scene choices remain proposals pending review.

INVALIDATES:
- Any Chapter 8 plan in which Ira begins with a fully developed simulation method.
- Any polished, adult-sounding self-analysis that compresses later development.
- Any interpretation of Gen Z as universal emotional numbness.
- Any adult flirtation/visual-novel dialogue with Ira.
- Any invented mother-death thread or supernatural manifestation.

AFFECTS: Chapter 8 scene architecture, prompt, draft, future developmental pacing, and any later chapter that depends on the new habit's origin.

REQUIRED DOCUMENT UPDATES: addendum, architecture, Gemini prompt, README, link map, memory bridge, session handoff, source register.
