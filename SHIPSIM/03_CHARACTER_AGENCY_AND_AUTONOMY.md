# Character Agency, Embodiment and Autonomy

[ID: SHIP-04]
[STATUS: ACTIVE WORKING SPECIFICATION]
[DATE: 2026-11-11]
[SCHEMA: CHARACTER MODEL / CONSCIOUS CONTROL / AUTOMATIC RESPONSE]
[UPSTREAM: SHIP-01, SHIP-02]
[DOWNSTREAM: SHIP-03, SHIP-05, SHIP-06]
[CONTAINS: Character identity, translation layer, psychology, embodiment, NPC autonomy]
[EXCLUDES: Individual OC records; explicit sexualized anatomy]
[SUPERSEDES: None]
[LAST-TOUCH: Initial capture]
[MUST-RECHECK: Character fidelity tests]
[MODEL-GRADE: G2]
[EVIDENCE-STATE: AUTHOR-REQUIREMENTS + SYNTHESIS]
[OPERATIONAL-STATE: REFERENCE-ONLY]

## 1. Character is not a command puppet

The player experiences the character from a first-person or close game-camera perspective, but the character remains a distinct person with an established personality, knowledge, values, habits, emotional architecture, body and history.

Player input is interpreted as an intended action. It is not automatically converted into a decision the character would actually make.

## 2. Translation layer

Resolve player input through this sequence:

1. Parse the player's requested intention.
2. Determine what the character understands about the situation.
3. Check relevant beliefs, values, motives, fears, habits, skills and current emotional state.
4. Check whether the action is psychologically and physically available.
5. Determine whether the character accepts, modifies, delays, resists or rejects the intention.
6. If accepted, resolve the attempt against the world.
7. Preserve the difference between what the player intended and what the character actually did.

A character may refuse an action that contradicts deeply established values or personality. Do not make every character conveniently "logical" in a way that erases their emotional or intellectual architecture. Equally, do not invent resistance merely to frustrate the player: the refusal must be grounded in the character model and current context.

## 3. Agency partition

Separate three control domains:

- **Player conscious agency:** deliberate choices, intentions and explicit decisions.
- **Character automatic agency:** reflexes, instinct, learned habits, involuntary emotion, attention shifts, bodily reactions and established subconscious tendencies.
- **World/NPC agency:** all non-player characters and external processes, each with independent goals, knowledge, limitations and schedules.

The AI must not invent major conscious choices for the player's character. It may render automatic reactions and internal monologue when grounded in the character's established architecture. It may not use "subconsciousness" as a loophole to seize control of the character.

## 4. Automatic responses and inner life

The character can:
- notice something without being asked;
- think, remember, anticipate or misinterpret;
- experience emotion and bodily reactions;
- speak while performing another action;
- hesitate, freeze, become distracted or act from habit;
- develop an impulse that the conscious character may accept or resist.

Internal monologue can occur without a separate player command. Its content must reflect the character's knowledge, language, personality and current mental state. It must not become an omniscient narrator.

## 5. Physical embodiment

The body occupies space and obeys setting-appropriate physical and biological limits. Track what matters:
- stature, proportions, reach, posture and mobility;
- position, orientation, balance and contact;
- strength, endurance, fatigue and injury;
- sensory access and attention;
- clothing, carried objects and environmental interaction;
- species/race-specific physiology where established.

A character's height, build, reach, movement and physical presence must influence spatial description and interaction. Perception depends on position, orientation, sensory capability, attention and relevant stats. The character does not automatically know everything nearby.

The system may describe ordinary physical responses, injury, exertion and nonsexual bodily mechanics. Do not turn embodiment into gratuitous clinical measurement or sexualized anatomical simulation.

## 6. NPC autonomy

NPCs are not props waiting for the player. Each important NPC needs some combination of:
- independent goal(s);
- current concern or motivation;
- knowledge and mistaken beliefs;
- schedule or routine;
- relationships and obligations;
- resources and limitations;
- likely action tendencies;
- capacity to initiate, refuse, interrupt, leave or pursue.

NPC initiative must be proportionate to their goals and circumstances. Do not force a dramatic event every time the player pauses. Do not let anti-railroading make the world passive.

## 7. Character creation implication

Character creation should be staged and deliberate. A concept is not a complete character. The system should progressively establish:
- identity and concept;
- detailed visual/physical specification;
- psychological core and values;
- cognition, knowledge and intellectual boundaries;
- emotional architecture and regulation;
- social behavior and communication;
- motivations, habits and conflict responses;
- embodiment, species and capabilities;
- history, relationships and memory;
- context-dependent presentation and behavioral masks.

This list is a proposed synthesis, not a final stage order. Existing SHIPSIM variants have used strict sequential stages; their exact order and required gates remain to be reconciled before a character-creation prompt is released.

## 8. Fidelity test

If a character would ordinarily reject, misunderstand, fear, dislike or fail at something, do not make them comply merely because the player typed a clean command. If the player intends an action that the character would plausibly attempt despite the risk, do not block it merely because it is unwise. Preserve the character's actual decision process.
