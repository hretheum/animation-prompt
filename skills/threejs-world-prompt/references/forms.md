# Forms: required sections per form

> Example phrases in this file are illustrations only. Never copy their wording into a prompt; write the same idea in your own words.

Every prompt uses the shared blocks from `anatomy.md` (opening, density paragraph, boilerplate, FIRST FRAME, PERFORMANCE, acceptance bar, outcome). This file says what ELSE each form must contain and what replaces the generic sections. Section titles are templates; rename them after the idea.

## Contents
1. Explorable world
2. Linear film / sequence
3. UI or page takeover
4. Toy / playground
5. Material instrument
6. Simulator
7. Process in time (scrubber)
8. Loop show / ride
9. Mini-game (micro)
10. Technical spec
11. Combining forms

---

## 1. Explorable world
*Reference pattern: a painted night sky, a vertical tower city, a dense European capital, a skyscraper island, a dragon's treasure room (see the calibration examples in `references/examples.md`).*
- THE HERO (material and motion) · THE WORLD (layered near/mid/far, agents with routines) · DYNAMISM · GLOBAL CYCLE with payoff.
- LIVING WORLD SIMULATION when there are people: agents with destinations, states and visible interactions; forbid identical walking loops, random jitter, frozen silhouettes and decorative dots.
- EXPLORATION AND CONTROLS: movement mode, reset to first frame, default drift, 5–7 presets, 3–4 controls + photo mode.

## 2. Linear film / sequence
*Reference pattern: a lantern-festival launch told in beats, a mold colony overtaking a kitchen (see the calibration examples in `references/examples.md`).*
- Replace presets with **SHOT SEQUENCE**: timecoded beats (start–end, what happens, camera behaviour) with one named climax and its staging (dolly-zoom, held breath, cut to black).
- Pacing doctrine: where it is patient, where it accelerates, where silence sits. Forbid cheap shocks, or grant explicit permission for one.
- Ending: what happens after the last frame (replay control fading in on black; loop back seamlessly).
- Controls minimal: pause (= photo mode), replay, sound, quality. Optional scrub bar if rewatching beats is valuable.
- If audio: SOUND section with procedural Web Audio layers per beat + the user-gesture unlock rule.

## 3. UI or page takeover
*An effect that grows out of, over or through an existing page/interface the executing model has in context.*
- Fidelity rule for the starting UI: reconstruct it faithfully (layout, type, colours, text) as a surface the effect can physically act on. State that any visible seam between the page and the scene at frame one counts as a failure.
- How the effect interacts with UI elements specifically (text, buttons, images, grid): name each.
- Continuity anchors: fragments of the original UI that persist through the transformation.
- Exit state: does the page come back, stay destroyed, become something else.
- Non-blocking: if it runs on a live site, state whether the page stays usable, how to dismiss, and reduced-motion behaviour (`prefers-reduced-motion`).

## 4. Toy / playground
*Reference pattern: a demolition sandbox (see the calibration examples in `references/examples.md`).*
- THE ENTIRE POINT section: the core physical behaviour, material by material (for example: timber splinters along the grain, ceramic cracks in a web before it falls apart).
- THE TOOLS: each tool with its control feel; one tool marked as the hero (for example: a time-reversal tool that gets the longest description and the most polish).
- Undo / rewind / reset as a spectacle in itself (record snapshots; require it to stay clean across a long recent history, with a number).
- SCORING WITHOUT BUREAUCRACY: feedback through the world (the crowd gasps, birds take off), minimal tally.
- Contrast amplifier: make the thing beautiful enough that breaking it feels transgressive.
- Affordance: show the first action to take with a visual hint at the object itself (for example, a soft glow breathing on the lever), so the invitation is obvious without text.

## 5. Material instrument
*Reference pattern: a liquid-pigment world (see the calibration examples in `references/examples.md`).*
- The material's behaviours as a verb list (for example: pool, split, seep, creep along a grain, bloom, harden at the edges).
- Phrase the goal as an interactive material instrument: list user gestures and parameters, each with an obvious visual consequence.
- Camera modes as lenses (macro liquid-level, split-screen cross-section, follow-cam).
- Default frame already mid-performance: state what must already be visible when the page loads.

## 6. Simulator
*Reference pattern: a detailed cockpit (see the calibration examples in `references/examples.md`).*
- Demand high fidelity on both sides at once: the instrument/interface and the world it reflects.
- FIDELITY SHOWPIECE: the domain taxonomy enumerated (every instrument, control, behaviour) and the expert-nod test (correct enough that a practitioner of the domain would approve).
- Cross-system coupling: displays must match the world exactly.
- Model behaviour honestly but welcoming: assisted default + REALISM toggle.
- Free play with suggested delights placed in the world instead of missions.
- The showpiece never degrades in the quality selector.

## 7. Process in time (scrubber)
*Reference pattern: a painting made over time, a river valley across centuries, a statue emerging from stone (see the calibration examples in `references/examples.md`).*
- The timeline is THE hero control: always visible, elegant, snapping to named stages + free scrub.
- Stages listed explicitly, each a complete state with its own light signature.
- Transformations, never crossfades: describe how elements change in short, readable, staged transformations (for example: walls rise, get plastered, weather, collapse, are rebuilt), so scrubbing back and forth is itself a spectacle.
- Bidirectional and buttery; trajectories/states precomputed at load (pure animation, no physics stalls).
- Continuity anchors that persist and evolve across stages.
- Invite the viewer to freeze mid-transformation and orbit: the best photograph lives in a paused intermediate state.

## 8. Loop show / ride
*Reference pattern: riding a firework, a boat ride over a waterfall (see the calibration examples in `references/examples.md`).*
- The viewer as the impossible participant (for example: the camera is the spark itself, or the drop of water).
- Fast events staged in named readable beats (for example: IGNITE / PRESSURE WAVE / OPEN) and tuned like music (hush before climax).
- Repertoire catalogue so no two cycles repeat + a grand finale every N cycles.
- Breathers between cycles; the whole thing should feel like a paced performance, not one clip on repeat.
- Time dilation as the hero control; in the deepest slowdown the viewer can drift inside the frozen event.
- One outside seat for contrast.

## 9. Mini-game (micro, ~80–150 words)
*Reference pattern: a rooftop-running game, a canal speedboat game (see the calibration examples in `references/examples.md`).*
- Opening: the genre, the place, and what the player is already doing at frame one.
- No start screen of any kind (title, menu, level picker, onboarding, "press to start"): the game is running at frame one.
- Core idea: [verb] through [checkpoints] to reach [goal] before [constraint].
- One sentence of world props that make the route readable.
- One closing line listing the essentials (timer, [counter], reset, a few controls, [camera]) and the feel (bright, fast, readable, instantly playable), in your own words.
No sections, no performance essay.

## 10. Technical spec
*Reference pattern: a voxel city rebuilt from a historical map, a voxel monument (see the calibration examples in `references/examples.md`).* Use when the risk is engineering correctness (layout logic, collision, determinism, offline delivery).
- #### OBJECTIVE · USER CONTROLS (with key shortcuts) · domain sections each tagged "(Requirement: …)" · VISUAL FIDELITY (named palette) · TECHNICAL SPECIFICATIONS (measurable: FPS target, instancing mandatory, atlas) · IMPLEMENTATION GUARDRAILS (retry limits for procedural placement, dispose on regenerate, no global pollution, error handling) · FINAL OUTPUT INSTRUCTION (a closing line telling the model to produce the complete result now and to check the listed requirements).
- Bold labels, terse bullets, fewer adjectives. Can still carry an acceptance bar.

## 11. Combining forms
Pick one primary form for structure; borrow sections from the secondary. Example: film (primary) + UI takeover (secondary) → SHOT SEQUENCE + the takeover fidelity rule + continuity anchors from the page.
