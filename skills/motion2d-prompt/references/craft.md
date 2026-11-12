# Craft: the vocabulary of motion

> Phrases quoted in this file are illustrations. Write every prompt sentence in your own words.

Use these words and values in prompts instead of adjectives.

## The principles, translated to code
- **Timing**: duration in frames at the named fps (12f = 200 ms at 60 fps). Heavier things take longer.
- **Spacing / easing**: where the frames bunch. Name curves: ease-out for arrivals `cubic-bezier(.16,1,.3,1)`, ease-in for departures `cubic-bezier(.7,0,.84,0)`, in-out for travels `cubic-bezier(.65,0,.35,1)`. Never linear except for constant mechanical motion (rotation, conveyor, scroll-linked).
- **Springs**: for anything that should feel physical: stiffness 120–300, damping 12–26, mass 1; name overshoot ("settles with one visible overshoot of ~8%").
- **Anticipation**: a counter-move before the action (3–6 frames, 5–15% amplitude).
- **Follow-through and overlap**: parts arrive at different times (offset 2–6 frames); appendages, tails, hair, cloth, text descenders.
- **Squash and stretch**: volume-preserving scale on impact and speed (stretch along velocity, squash on contact); keep subtle for UI, bold for characters.
- **Arcs**: organic motion travels on curves, not straight lines.
- **Secondary action**: small motion that supports the main one (dust on landing, a ripple, a trailing echo).
- **Staging**: one focal action at a time; everything else quieter.
- **Exaggeration**: push key poses beyond realistic for clarity.
- **Solid drawing**: consistent volumes and perspective rules even in flat style.
- **Appeal**: clear silhouettes, intentional shapes.

## Choreography
- **Stagger**: offset per item in ms (20–60 ms for lists, 8–20 ms per glyph), with an order (index, distance from origin, random seeded).
- **Cascade / wave**: offsets from a source point; delay = distance × k.
- **Hold**: moments of stillness give motion meaning; specify holds in frames.
- **Rhythm**: tie beats to BPM; accent on downbeats; syncopation for surprise.

## Transitions (name one per cut)
Match cut (shape A becomes shape B in the same position) · morph (path interpolation with equal point counts and matched winding) · mask wipe (shape-led reveal) · push · zoom-through (enter a letter/shape into the next scene) · split · ink/paper tear · pixel dissolve (dithered) · liquid (metaball/SDF blend).

## Typography in motion
Per-glyph or per-word split; variable-font axes (weight, width, slant, optical size) as animation channels; baseline as a path; type as mask over image or field; scale-through; collisions and stacking; kerning breathing. Reading rule: never move a word while it must be read; minimum hold ≈ 0.3 s per word + 0.5 s.

## Loops
Exact length in frames; periodic functions only (sin/cos of 2πt/T); noise sampled on a circle (2D noise at (r cos θ, r sin θ)) or torus for seamless 4D-like loops; state that returns exactly; test: frame 0 and frame N identical.

## Texture and print looks
Film grain (animated, 1–3% amplitude) · paper fibre · halftone dots · risograph misregistration (1–3 px per ink layer) · limited ink palettes · hand wobble on lines (low-frequency noise on vertices, re-seeded every 2–4 frames for "boiling line") · cut-paper drop shadows · chalk/charcoal grain via noise-modulated strokes.

## Composition
Grid (columns, baseline), safe margins (5–8% of short side), focal hierarchy (one primary, one secondary), negative space as an active element, rule of thirds or strong centre. Choose and state which, with aspect-specific compositions for 16:9 vs 9:16.

## Colour
3–6 named hex values with roles (ground, ink, accent, light, shadow); contrast ratios for text ≥ 4.5:1; colour changes as events, not decoration.

## Test vocabulary
Poster-frame test (any frame is a poster) · first-second test (the hook lands before 1 s) · squint test (silhouettes and hierarchy survive blur) · mute test (sound-synced pieces still make sense silent) · loop seam test (frame N = frame 0).
