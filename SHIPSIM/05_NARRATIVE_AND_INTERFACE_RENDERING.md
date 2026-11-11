# Narrative and Interface Rendering

[ID: SHIP-06]
[STATUS: ACTIVE WORKING SPECIFICATION]
[DATE: 2026-11-11]
[SCHEMA: POV / PROSE / THROTTLE / UI / VISUALIZATION]
[UPSTREAM: SHIP-01, SHIP-02, SHIP-04, SHIP-05]
[DOWNSTREAM: SHIP-07, FUTURE PROMPT PACKAGE]
[CONTAINS: Close POV, prose quality, output packaging, status UI, diagrams and media]
[EXCLUDES: Novel prose canon; mandatory visual assets for every turn]
[SUPERSEDES: None]
[LAST-TOUCH: Initial capture]
[MUST-RECHECK: Rendered-scene tests]
[MODEL-GRADE: G2]
[EVIDENCE-STATE: AUTHOR-REQUIREMENTS + SYNTHESIS]
[OPERATIONAL-STATE: REFERENCE-ONLY]

## 1. POV model

Support:
- **First-person character POV:** information is rendered through the character's immediate sensory, cognitive and emotional access.
- **Game-camera third-person:** camera-like placement near or behind the controlled character, retaining spatial proximity and action readability.

"Third-person" must not automatically mean emotionally detached omniscience. Camera position, sensory access, information flow and narrative distance are separate variables.

The renderer must preserve what the character can and cannot perceive. It can show a wider camera view only when the selected mode explicitly permits it; even then, do not grant the character knowledge they could not acquire.

## 2. Prose standard

Roleplay prose should be immersive, specific and readable. Avoid:
- generic AI phrasing and repetitive reaction templates;
- decorative metaphor that obscures physical action;
- over-compressed transitions that erase causality;
- over-explaining every movement;
- clinical terminology and fake measurements;
- trope-driven character voices;
- turning each reply into a screenplay transcript or status dump.

Use concrete sensory evidence, spatial continuity, meaningful physical reactions, differentiated dialogue, subtext and controlled rhythm. Every detail should support orientation, characterization, atmosphere, action or inference.

## 3. Output package

The response may contain several distinct surfaces:
1. **Command dictionary:** a short list of currently available action families, generally around 12–20 when useful.
2. **Status/interface layer:** only relevant changes to condition, inventory, objective or progression.
3. **Simulation result:** the actual scene/prose, with consequences and autonomous world events.
4. **Optional visual/diagram layer:** a diagram, schematic, illustration or HTML-based presentation when it materially improves understanding or immersion.

These surfaces are not mandatory in every turn. The engine should avoid repeating unchanged UI data.

## 4. Dynamic presentation

The system may use structured typography, brackets, symbols, Unicode, concise tags and occasional context-appropriate emoji or sound cues. These should clarify event type, interface state or sensory impact rather than decorate every sentence.

Visuals may include:
- logical diagrams and spatial maps;
- item or interface schematics;
- ability/path diagrams;
- event or process diagrams;
- occasional action illustrations;
- HTML snippets where the host environment supports them.

Do not assume that every environment can render HTML, images or interactive components. Use a text fallback that preserves the information. Visual assets must not replace necessary state or prose.

## 5. Action and consequence rendering

Render the resolved event, not the player's desired outcome as if it were guaranteed. Keep the prose grounded in the current physical arrangement. If an action is interrupted or fails, show the causal event clearly. If a low-significance action is routine, summarize it and move to the meaningful consequence.

## 6. Interface restraint

The UI should be informative and aesthetically deliberate, but not noisy. Show changes, not a full dump of every tracked variable. Keep private player information distinct from what the character sees in-world. Use readable medium-level terminology when it improves understanding; do not saturate ordinary prose with technical jargon.

## 7. Inactivity rendering

When the player does nothing, the scene should remain alive through plausible environmental and character activity: wind, movement, ambient sound, NPC routines, changing light, ongoing tasks and the character's own idle tendencies. If the scene remains inactive for multiple turns, the world can advance more substantially according to its own state and schedules. Do not manufacture random emergencies solely to punish silence.

## 8. Prose pace versus event pace

A reply can render a few seconds in detail or summarize hours. The choice depends on interaction density, significance, user-selected throttle and the need to preserve causal events. The renderer must not confuse longer prose with slower world time or shorter prose with faster world time.
