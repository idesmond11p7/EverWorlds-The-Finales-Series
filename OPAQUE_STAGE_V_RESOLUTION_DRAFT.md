# OPAQUE — Stage V Resolution Draft

## Status

**Provisional working analysis.**  
This document proposes resolutions to the three specification gaps currently blocking closure of the core control model. It does not ratify them.

## 1. Authority Precedence

### Problem

OPAQUE must determine what happens when multiple controlled authorities apply to the same matter.

### Proposed rule

Authority shall be determined by **scope before hierarchy**:

1. identify every applicable authority;
2. determine the scope of each authority;
3. prefer the authority whose scope directly governs the matter;
4. where two authorities genuinely govern the same matter, apply an explicitly established precedence relation;
5. where no precedence relation exists, do not invent one;
6. mark the matter as unresolved and escalate it to the appropriate legitimate decision authority.

### Important consequence

OPAQUE must not assume that a newer, more detailed, more convenient, or AI-generated source automatically outranks another source.

## 2. Validation Authority

### Problem

A determination can exist without being validly established for its intended purpose.

### Proposed rule

Validation authority shall be **purpose- and scope-dependent**.

A validation may be established only by an authority that is legitimate for the subject and intended scope of that validation.

OPAQUE may determine that validation is required and may check whether validation conditions appear satisfied, but it shall not silently manufacture validation authority.

Where the responsible validation authority is undefined, validation remains unresolved.

## 3. Controlled State Transition

### Problem

OPAQUE needs a precise boundary between information that exists and information that legitimately changes controlled project state.

### Proposed rule

A controlled state transition requires:

1. a defined governed object;
2. a defined current state;
3. an identified proposed transition;
4. applicable conditions;
5. applicable dependencies;
6. sufficient authority;
7. required validation, where applicable;
8. an identified resulting state;
9. a record of the transition and its provenance.

If a required condition is unsatisfied, the transition shall not be treated as authoritative.

The system may record the attempted or proposed transition separately without pretending that the controlled state changed.

## 4. Common Principle

These three areas share one rule:

**OPAQUE must distinguish "a change can be described" from "a change is authorized to become controlled state."**

This preserves the boundary between reasoning, proposal, execution, and authoritative state.

## 5. Consequences for the Core Model

These resolutions do not require a new core concept.

They clarify relationships among:

- Authority;
- Condition;
- Determination;
- Validation;
- Change;
- Controlled Incorporation;
- State;
- Provenance.

The current 14-concept model therefore remains sufficient unless later evidence demonstrates otherwise.

## 6. Remaining Work

After review of these candidate resolutions:

- formalize authority precedence;
- formalize validation authority;
- formalize state-transition conditions;
- test the resulting rules against representative OPAQUE scenarios;
- then finalize the requirement-to-control mapping and close Stage V-C.

No unrestricted conceptual expansion is required at this point.
