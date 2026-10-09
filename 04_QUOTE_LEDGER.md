# Quote Ledger

[ID: QTE-04]
[STATUS: ACTIVE / EXACT-LANGUAGE MEMORY]
[LAST-UPDATED: 2026-10-09]
[UPSTREAM: SRC-03, SCH-01]
[DOWNSTREAM: MMG-06, DEC-05, CHR-09, PRO-10]

## Function
Quotes are retrieval anchors and evidence units. They are not decoration.

## Quote classes
Q-U = exact user-authored wording.
Q-A = exact assistant-authored wording that became an important working formulation.
Q-S = exact source/manuscript wording.
Q-R = quoted research/source material.

## Q-U rule
Copy the user's wording exactly. Store date/time/context when available. Never replace it with a cleaner paraphrase.

For multi-part voice input, preserve each materially meaningful statement separately where necessary. Do not discard short clauses because they appear conversational, repetitive, emotional, corrective or grammatically incomplete.

## Q-A rule
Assistant-retained wording is explicitly marked as assistant-origin. It can guide retrieval but cannot become user canon merely because the assistant remembers it.

## Required quote record
QUOTE-ID
CLASS
EXACT-TEXT
SOURCE-ID
DATE
TIME
CONTEXT
INTENT
WHAT-IT-ESTABLISHES
WHAT-IT-DOES-NOT-ESTABLISH
LINKED-CLAIMS
LINKED-DECISIONS
MODEL-GRADE
STATUS

## Retrieval principle
If a complex idea has a memorable exact formulation, preserve the formulation and link the expanded model to it. The quote is the handle; the model is the structure.

## Answer-alignment rule
When a user explicitly says something like “give me exactly what I said,” the exact quote is the primary retrieval anchor. The response must answer that quoted statement rather than a generalized interpretation of the surrounding conversation.

## Q-U-WORKFLOW-2026-10-09-01

- QUOTE-ID: Q-U-WORKFLOW-2026-10-09-01
- CLASS: Q-U
- EXACT-TEXT: “You keep forgeting THAT YOUR JOB is to PROMPT gemini ...Gemini can't access locked LINKS like github only research papers and other surface things YOU didn't and you keep leading gemini astray your supposed to be a master prompter”
- SOURCE-ID: SRC-WORKFLOW-2026-10-09-01
- DATE: 2026-10-09
- TIME: UNKNOWN
- CONTEXT: User correction after assistant gave a Chapter 8 prompt that failed to reproduce the successful Chapter 6 master-prompt methodology.
- INTENT: Establish the assistant's role as master prompter and context/research orchestrator, and require Gemini's prompt to include required context directly because the user's Gemini cannot access locked GitHub links.
- WHAT-IT-ESTABLISHES: Role split; requirement for a self-contained prompt; need for accessible public research links; prohibition on pointing Gemini at inaccessible project records.
- WHAT-IT-DOES-NOT-ESTABLISH: That this ChatGPT session has an operational Gemini-send connector.
- LINKED-CLAIMS: Gemini receives only what is supplied to it or what it can access in its own environment; the assistant must not assume private GitHub access.
- LINKED-DECISIONS: DEC-WORKFLOW-2026-10-09-01
- MODEL-GRADE: G3 for the stated workflow requirement
- STATUS: LOCKED

## Q-U-CH6-METHOD-2026-10-09-01

- QUOTE-ID: Q-U-CH6-METHOD-2026-10-09-01
- CLASS: Q-U (user-supplied production-prompt text; original authorship of every line not independently established)
- EXACT-TEXT: “The goal is NOT: Tell the reader what happened. The goal is: Make the reader experience what happened.”
- SOURCE-ID: SRC-WORKFLOW-2026-10-09-01
- DATE: Original prompt header indicates 2026-10-02; user supplied it in this conversation on 2026-10-09
- TIME: Original header says 1:54PM; timezone not independently established
- CONTEXT: Core statement in the Chapter 6 master Gemini production prompt which the author identifies as the successful prompting benchmark.
- INTENT: Preserve experiential rendering as a central instruction when constructing future production prompts.
- WHAT-IT-ESTABLISHES: The production prompt's declared target is reader experience, not event reporting.
- WHAT-IT-DOES-NOT-ESTABLISH: That the quoted principle alone fully describes the whole prose system or guarantees success without the remaining context.
- LINKED-CLAIMS: 09_MEMORY_BRIDGE.md / Locked Gemini production-prompt workflow
- LINKED-DECISIONS: DEC-WORKFLOW-2026-10-09-01
- MODEL-GRADE: G2 pending recovery of complete original artifact and operational testing
- STATUS: LOCKED AS A PROMPTING PRINCIPLE


## Q-U-WORKFLOW-DEPTH-2026-10-09-01

- QUOTE-ID: Q-U-WORKFLOW-DEPTH-2026-10-09-01
- CLASS: Q-U
- EXACT-TEXT: “you'll have to put in extra more than that”
- SOURCE-ID: SRC-WORKFLOW-2026-10-09-01
- DATE: 2026-10-09
- TIME: UNKNOWN
- CONTEXT: User rejected the initial memory update as insufficient and required deeper operational memory.
- INTENT: Require more than a high-level role-split summary; preserve the actual method in a usable, testable protocol that can prevent recurrence.
- WHAT-IT-ESTABLISHES: The memory must operationalize the entire Chapter 6 prompting method and its failure conditions, not merely state that the assistant is the master prompter.
- WHAT-IT-DOES-NOT-ESTABLISH: Permission to claim complete recovery of the original prompt, or that a protocol is effective before it is applied to an actual task.
- LINKED-CLAIMS: GMP-21; 09_MEMORY_BRIDGE.md
- LINKED-DECISIONS: DEC-GMP-21-2026-10-09
- MODEL-GRADE: G3 for the instruction's meaning; future protocol effectiveness remains unverified.
- STATUS: LOCKED
