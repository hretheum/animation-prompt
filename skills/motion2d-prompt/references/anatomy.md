# Anatomy: shared blocks and tiers

> Phrases quoted in this file are illustrations. Write every prompt sentence in your own words.

## Tiers

| Tier | Length | Form | Use when |
|---|---|---|---|
| micro | 80–150 words | one paragraph + "Core idea" + one sentence of constraints | a loader, a sting, a tiny toy |
| mid | 350–600 words | opening, "Core idea", 4–6 short `####` sections, one mechanic | a single loop, a short type piece, a UI effect |
| max | 1000–1800 words | full anatomy + form sections + optional modules + acceptance criteria | flagship pieces |
| spec | 400–900 words | OBJECTIVE / CONTROLS / requirements tagged "(Requirement: …)" / TECHNICAL / GUARDRAILS / FINAL OUTPUT INSTRUCTION | correctness matters more than flair (data, UI components, export pipelines) |

## 0. Opening paragraph (no header)

1. **Hero sentence**: `Build a flagship 2D [loop | film | kinetic-type piece | page effect | scene | toy] in [technique]: [hero image in motion, 4–6 concrete elements each with a verb].`
2. **Negative definition + reframe**: `Do not build [a stock motion template], [PowerPoint fade-ins], [a confetti screensaver] or [a clip-art scene]. Build […].`
3. **Core idea**: `Core idea: […].`

## 1. Density / craft paragraph (no header)

The 2D equivalent of "a billion pieces": state what makes the piece rich and how it is achieved. Examples:
- "The target is the look of ten thousand hand-cut paper marks, each with a torn edge and a shadow of its own, moving together like one tide. Get there with … and avoid …"
- "The target is motion so deliberate that any single frame could hang as a poster and every transition carries a small idea."

## 2. Technique and boilerplate (no header)

One sentence that picks the technique and says why, then the pinned boilerplate from `tech.md`. Add the time rule from `tech.md` §4 when the piece loops or exports.

## 3. `#### FORMAT AND FRAME`

Aspect ratio or full-viewport behaviour, safe margins, responsive rule (for example: the composition re-flows and never crops the hero), export resolution and fps if any.

## 4. `#### FIRST FRAME / POSTER FRAME - [idea]`

The opening strategy: poster frame (the first frame is already the best image), held breath → ignition, anchor → twist (an ordinary page or state that starts to misbehave), or mid-action. Always add a line ruling out an intro screen, logo reveal, loading spinner or instructions, unless one of those is the piece.

## 5. `#### STYLE LAW`

Shape language, line (weight, caps, wobble), fills and texture (grain, paper, halftone, misregistration), palette as 3–6 named hex values with roles, typeface and roles, composition grid, 3–4 bans. Declare any drift toward the generic look a failure.

## 6. Legibility

State that every frame reads at a glance, the focal point is never ambiguous and text holds still long enough to be read. For dark looks, require dark but never muddy.

## 7. Hero / signature section(s)

The hero element and its states, the signature motion described in numbers (frames, curve, overshoot), the thesis frame, close-up survival for vector or textured detail (for example: at 4× zoom the line still shows its wobble and grain).

## 8. `#### MOTION LAW`

Tempo (BPM or beat length), easing vocabulary for this piece (named curves and springs with values), choreography rules (stagger in ms, overlap, arcs), what never moves linearly, at least 5 independent systems in the max tier, paused-frame test.

## 9. Form sections

Shot list, loop spec, interaction, data, rig, taken from `forms.md`.

## 10. `#### CONTROLS` (if any)

Minimal: one hero control + 2–3 others; reduced-motion behaviour; export control.

## 11. `#### EXPORT` (if any)

From `tech.md` §5.

## 12. `#### PERFORMANCE`

Budget for the technique, DPR ≤ 2, offscreen pause, adaptive render scale, and a line saying that lower quality tiers give up [counts, render scale, filters] first while the must-keep list is never traded away.

## 13. Acceptance criteria (max/spec; one sentence in mid)

> Acceptance criteria: the job is not done if the result looks like a template, a few shapes easing in and out, linear motion, a loop that visibly resets, or a still layout with one moving part. Done means: the first frame holds up on its own; there is one signature motion you remember; at least [five] motion systems run independently; every movement has a chosen curve; any frame could be a poster; [a seamless loop of exactly N frames / every beat of the shot list on screen]; the layout is responsive and stays within the performance budget. Everything this prompt names must show up on screen, move or be explorable. If it cannot, cut it from the prompt instead of faking it.

## 14. Outcome line

`In one sentence: …`. Formulas are in `patterns.md`.

## Style rules
- Imperative, dense, numbers everywhere (frames, ms, BPM, hex, px).
- CAPS only for the one word carrying the idea.
- Name curves and springs; never write "smooth animation" without values.
- Headers name ideas: "THE LINE NEVER LIFTS", "TYPE IS THE CAMERA".
