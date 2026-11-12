# Forms: required sections per form

> Phrases quoted in this file are illustrations. Write every prompt sentence in your own words.

Every prompt uses the shared blocks from `anatomy.md`. This file says what ELSE each form must contain.

## Contents
1. Generative loop · 2. Endless generative piece · 3. Motion design film / explainer · 4. Kinetic typography · 5. Page / UI effect · 6. Toy / instrument · 7. Data animation · 8. Character scene · 9. Micro (logo sting, loader) · 10. Shader piece · 11. Combining forms

## 1. Generative loop
- THE RULE: the system that generates the image (agents, field, subdivision, growth) in 3–5 bullets with numbers.
- THE LOOP: exact length in frames at a named fps; seamlessness method (periodic functions, noise sampled on a circle/torus, state that returns to start); "no visible reset, no crossfade".
- Seed control: a seed that changes the composition while keeping the style law; "every seed must be poster-worthy".
- Poster frame test: any frame printable as a poster.
- Export: GIF/MP4 of exactly one loop.

## 2. Endless generative piece
- Evolution over minutes: phases or drift axes, each capped before legibility breaks.
- Never repeats; never degrades into noise or empty canvas; recovery rules when density drifts.
- Optional interaction that perturbs but never breaks the system.

## 3. Motion design film / explainer
- SCRIPT: what the film says, as on-screen beats (no voice unless asked); words per screen ≤ 7, hold long enough to read (≈ 0.3 s per word + 0.5 s).
- SHOT LIST with timecodes and beats; transitions named (match cut, morph, mask wipe, push, zoom-through).
- Visual system: grid, type scale, palette, iconography rules, one motion signature reused across shots.
- Ending: end card, loop, or replay.
- Master timeline scrubbable; export settings.

## 4. Kinetic typography
- The copy, exactly, with its rhythm (line breaks, emphasis by motion, not by colour of one word).
- Type law: typeface and axes (weight, width, slant, optical size), size scale, tracking; glyph-level split rules.
- Reading rhythm: tempo/BPM, minimum on-screen time per word, never animate a word while it must be read.
- Techniques chosen: per-glyph stagger, variable-axis animation, text on path, text as mask over imagery, scale-through transitions, typographic collisions.
- Legibility rule and contrast at every frame.

## 5. Page / UI effect
- Fidelity rule for the existing page (in context): reconstruct or act on the real DOM; "no seam at frame one".
- Trigger (load, scroll, hover, click, idle, visibility) and what each UI element type does.
- Non-blocking: the page stays usable, the effect never traps focus or hides content permanently; dismiss/skip.
- Compositor-only animation; performance budget on mid-range mobile.
- `prefers-reduced-motion` alternative, keyboard and screen-reader behaviour unchanged.

## 6. Toy / instrument
- THE ENTIRE POINT: the core behaviour, material by material.
- Hero tool/gesture + undo/reset as spectacle; affordance without tutorial.
- Feedback through the piece itself (no scores unless asked).
- Every control with an obvious visual consequence.

## 7. Data animation
- The data: real or clearly synthetic, named fields, units, source line.
- Object constancy: each datum keeps identity across transitions (keyed joins).
- Staging: one change at a time; annotation appears where the eye already is.
- Honest scales (zero baselines for bars, labelled log scales); no chart junk.

## 8. Character scene
- Original characters only: silhouette description, proportions, shape language, palette per character.
- Rig: nested groups/containers with pivots named (hips, spine, head, upper/lower limbs); procedural cycles (walk, breathe, blink) plus keyed acting beats.
- Acting: what each character wants in the scene, 3–6 acting beats with anticipation and follow-through; readable silhouette in every pose.
- Staging: layered background/midground/foreground with parallax; lighting by flat shapes (rim, cast shadow shapes).
- Loop or shot list; secondary motion (cloth, hair, props, environment).

## 9. Micro (logo sting, loader)
- Duration (2–5 s sting; loader loop 0.8–2 s), exact frames, one signature move, resolve to the static mark.
- Loader: indeterminate vs determinate; never distracting; reduced-motion version.
- Tier usually micro or mid.

## 10. Shader piece
- The field: the mathematical idea (domain warping, SDF composition, flow, reaction-diffusion) in plain words plus the key parameters.
- Palette mapping (cosine palette or named stops), banding control, grain/dither.
- Time behaviour (loop period or evolution), interaction uniforms (cursor, scroll, audio).
- Render-scale and fps budget.

## 11. Combining forms
Pick one primary form for structure and borrow sections from the secondary (e.g. kinetic typography primary + page effect secondary).
