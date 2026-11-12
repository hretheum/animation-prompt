# Calibration examples (synthetic)

Written for this skill to show tone, density and structure for three 2D forms. They have not been run through a model; treat them as calibration, never copy their content.

## Contents
1. The Line That Never Lifts - generative loop, max, Canvas 2D + export
2. Slow Is a Feature - kinetic typography, mid, DOM/SVG + GSAP
3. Night Shift - character scene, max, SVG rigs + GSAP

---

## 1. The Line That Never Lifts
*Generative loop · max · Canvas 2D · GIF/MP4 export*

Build a flagship 2D generative loop in Canvas 2D: a single unbroken ink line, never lifting from the paper, draws a tidal coastline, folds itself into a flock of two hundred birds that wheel across the sheet, lands as rain on a harbour, and settles back into the exact coastline it started from - twelve seconds, one stroke, no seam. Avoid vector logo animation, a particle swarm with a line drawn through it, a stroke-dashoffset reveal on a static path, or a loop with a visible fade at the end. It is one gesture of a calligrapher's brush that has learned to become everything it draws.

Single idea: one line, never lifted, that becomes the world and returns to itself.

The target look is real ink on real paper: a stroke that swells and thins with speed, pools at turns, dry-brushes on fast passes, bleeds faintly into the fibre - one continuous polyline of about 6,000 points carrying width, wetness and pressure. Achieve this with a custom stroke renderer (variable-width ribbon built per frame from the point list, plus an ink-texture pass), not with lineWidth and a gradient.

Use only native browser APIs; no libraries. Every frame is a pure function of t and a seed: draw(t) rebuilds the line from t with no hidden state, so the loop is exact and export is frame-accurate.

#### FORMAT AND FRAME
- 1:1 square, centred in the viewport with warm paper filling the rest; composition re-flows to 4:5 on narrow screens, never cropping the line. Export at 1080×1080, 30 fps, exactly 360 frames.

#### POSTER FRAME - THE COASTLINE
- Frame 0 is already a finished ink drawing: a coastline with headlands, a small harbour and a lighthouse made of the same line, the brush resting at the lighthouse tip. No intro, no title.

#### STYLE LAW
- Paper #EFE8DA with visible fibre noise and a faint deckle at the edges; ink #1C1A17 with a cool undertone #2A3138 where it pools; one accent only - a vermilion seal #C2402B stamped in the corner, still.
- Line width 1.2–7 px at 1080 px, driven by inverse speed; dry-brush breaks above a speed threshold; ink pools as darker blobs at sharp turns.
- Bans: no colour gradients, no glow, no drop shadows, no second line ever.

#### THE LINE - THE SIGNATURE MOVE
- The brush tip moves; the line behind it is the entire visible history of the last 6,000 points, oldest points slowly drying lighter. The tip always moves on arcs, never straight segments, and anticipates every turn with a 4-frame counter-swing.
- Transformations by match cut: the coastline's headland peels upward into a wing; the wing multiplies into a flock by the line looping through two hundred bird silhouettes in sequence (each bird three looping strokes), the flock wheels as a murmuration whose envelope is computed from noise sampled on a circle so it returns exactly; the flock dives and each bird unspools into a falling raindrop dash; rain lands as ripples on the harbour; the ripples straighten into the original coastline.
- Thesis frame (frame 180): the line is simultaneously the last of the coastline, the whole flock and the first raindrops.

#### MOTION LAW
- Beats at 12 s: COAST 0–60 f, LIFT 60–120 f, FLOCK 120–240 f, RAIN 240–300 f, RETURN 300–360 f; the tip eases with cubic-bezier(.65,0,.35,1) between beats and never stops except a 6-frame hold at frame 0/360.
- Independent systems: tip path, width/pressure, drying, flock envelope, ink texture boiling (re-seeded every 3 frames), paper fibre parallax of 1 px.

#### CONTROLS AND EXPORT
- Click: new seed (new coastline and flock path, same style law; every seed poster-worthy). "Save loop": MP4 via WebCodecs at 1080×1080/30 fps, or GIF at 720×720 with a 16-colour palette and ordered dithering - both exactly 360 frames. reduced-motion: show the poster frame with the brush tip breathing.

#### PERFORMANCE
- Ribbon rebuilt per frame from a typed array; ink texture as a pre-rendered noise tile; DPR clamped to 2; pause offscreen. Quality reduces point count and texture resolution before ever sacrificing the single unbroken line, the seamless loop or the ink behaviour.

Absolute ambition bar: no stroke-dashoffset tricks, no second line, no visible seam - a single stroke that stays alive for 360 frames, every frame a poster. The outcome: the oldest drawing exercise in the world - never lift the pen - finally taken all the way.

---

## 2. Slow Is a Feature
*Kinetic typography · mid · DOM/SVG + GSAP*

Create a 40-second kinetic-typography piece in DOM text animated with GSAP: a short manifesto about slowness, set in one variable typeface, where every line arrives at the speed of the idea it carries - fast words sprint in, slow words take their time, and the final line is so slow it is still arriving when the piece ends. Avoid lyric-video template, words flying in from random directions, a typewriter effect, or emphasis by turning one word a different colour. It is typography that performs its own meaning.

Single idea: the speed of each word is its meaning.

Load GSAP and SplitText as pinned UMD scripts from cdnjs; one master timeline, scrubbable. Font: Fraunces from Google Fonts with weight, optical-size and "SOFT" axes animated.

#### FORMAT, STYLE, LEGIBILITY
- 16:9, full-viewport, black ink #141210 on bone #F2EEE6, one rule line #141210 at 1 px. Type scale 32/64/128/256 px at 1080p. Left-aligned on a 12-column grid, 8% margins.
- Never move a word while it must be read: hold ≥ 0.3 s per word + 0.5 s.

#### SCRIPT AND BEATS (BPM 72)
- 0–8 s "Everything is faster now." - each glyph snaps in at 8 ms stagger, cubic-bezier(.16,1,.3,1), weight 900 → 400 as it lands.
- 8–18 s "Feeds. Replies. Deadlines." - three words, each slammed in on a downbeat with 2-frame anticipation, then shoved off-left by the next.
- 18–30 s "But some things only work slowly." - "slowly" stretches its width axis from 62 to 125 over four seconds while the other words wait.
- 30–40 s "Trust. Bread. Design." each fades up over 2 s, optical size growing; the last word is still gaining weight at 40 s.

#### MOTION LAW AND CONTROLS
- No linear easing; holds are part of the rhythm; the rule line breathes width with the beat. Space pauses, arrow keys scrub by beat, "Replay". reduced-motion: the lines appear in place with opacity only, same timing.

Ambition bar: every beat present, every hold readable, and the last word visibly unfinished. The outcome: a manifesto that you have to read at the speed it asks for.

---

## 3. Night Shift
*Character scene · max · SVG rigs + GSAP · MP4 export*

Build a flagship 2D animated scene in SVG with GSAP: a lighthouse keeper's night shift in a storm, a 24-second seamless loop - the keeper climbs the spiral stair with a lantern, trims the great lamp, is nearly knocked over by a gust through the door, while his old dog sleeps through all of it except the moment the beam sweeps over its face. Avoid flat-vector stock illustration with one moving cloud, a puppet that slides its limbs linearly, a parallax wallpaper, or a storm made of decorative particles. It is a short film loop with acting, weather and light, built entirely in vectors.

Single idea: a storm outside, a ritual inside, and a dog that only wakes for the light.

The goal is the feeling of hand-made animation: considered acting with anticipation and follow-through, layered weather, light that changes the colours of everything it touches. Achieve this with nested SVG rigs (pivoted groups), shape-based lighting (light and shadow as their own shapes clipped to each character), and a master GSAP timeline - not with CSS keyframes per element.

Load GSAP as pinned UMD scripts from cdnjs; one master timeline of exactly 24 s at 24 fps that loops with no seam. All content is generated in code; load no external assets.

#### FORMAT AND FRAME
- 16:9; a cross-section of the lighthouse top: lamp room above, spiral stair below, the open door on the right to the storm; composition holds on 9:16 by re-framing to the stair and lamp. Export MP4 1920×1080/24 fps via an offscreen canvas render of the same SVG.

#### STYLE LAW
- Shape language: chunky rounded geometry, no outlines, shapes separated by value. Palette: storm night #1B2433, sea #22374A, stone #5B5F66, warm lamp #F6C76B, lamp core #FFF2C6, keeper coat #8A3B2E, dog #B48A5A.
- Light law: when the beam or lantern touches a shape, a lit version of that shape (warmer, lighter) is revealed through a clip mask - every character has light and shadow shapes.
- Bans: no gradients except the lamp glow, no drop shadows, no outlines, no text.

#### THE KEEPER - ACTING
- Rig: hips, spine (2 segments), neck, head, upper/lower arms, hands, upper/lower legs, feet, coat tail (3 segments with lag), lantern on a 2-segment chain.
- Beats: CLIMB (heavy steps, 14 frames per step, head bob, lantern swinging on follow-through), TRIM (anticipation lean, careful hand, small satisfied settle), GUST (door bangs at 15 s; he braces with a 4-frame squash, coat tail whips, lantern chain overshoots twice), RECOVER (shakes head, looks at dog, small shrug), DESCEND (returns to the exact pose of frame 0).

#### THE DOG AND THE WEATHER
- The dog breathes (2.5 s cycle) and ignores the gust entirely; when the beam crosses its face at 19 s, one ear lifts, an eye opens for 18 frames, then closes - the only time it moves.
- Weather in 4 layers with parallax: far cloud bands, sheeting rain at 70°, near rain streaks, spray hitting the door frame; lightning twice per loop as a 3-frame value flip of the whole palette.
- The beam rotates with a constant 8 s period (linear - it is a machine), lighting rain streaks as it passes.

#### MOTION LAW
- Characters never move linearly: springs for chain and coat (stiffness 180, damping 14), cubic-bezier(.65,0,.35,1) for body travels, 2–4 frame overlap between body parts. At least seven systems: keeper, dog breathing, beam, three rain layers, lightning, door, lantern.

#### CONTROLS, ACCESSIBILITY, PERFORMANCE
- Space pauses (photo mode), "Save loop" exports MP4. reduced-motion: rain stops, beam slows to a glow pulse, acting remains.
- Under 1,500 animated SVG nodes; rain drawn as a few long paths per layer; pause offscreen; DPR irrelevant for SVG but clamp the export canvas to 1×.
- Quality reduces rain density before ever sacrificing the acting, the light law or the seamless loop.

Absolute ambition bar: real acting with anticipation and follow-through, light that recolours every surface it touches, seven independent systems, a 24-second loop with no seam - a frame from a studio short, built in vectors. The outcome: a storm you could watch every night, for the one second the dog opens its eye.
