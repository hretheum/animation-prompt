# Optional modules

> The quoted phrases in this file are illustrative wording only, drawn from the calibration examples in `references/examples.md`. Never reuse their wording in a prompt; express the same idea in your own words.

Pick the modules the subject earns. Each module: what it is, the phrasing that works, when to use it.

## Contents
1. Readable beats · 2. Repertoire and rhythm · 3. Continuity anchors · 4. System coupling · 5. Living agents · 6. Diegetic state · 7. Expert-nod fidelity · 8. Contrast amplifier · 9. Camera lenses · 10. Scope bans · 11. Tone calibration · 12. Local simulation bubble · 13. Implementation hygiene · 14. Sound · 15. Closing formulas

## 1. Readable beats
Split fast events into named beats that stay legible even at full speed. Example phrasing: "the collapse of the tower is told in three distinct beats: the WHITE-OUT, the RING OF DUST, and the SETTLING, each separable by eye." Pace sequences the way a composer would, with a silent held breath before the peak. Use for any explosion, impact, transformation or reveal.

## 2. Repertoire and rhythm
For loops: list a catalogue of genuinely different variants so consecutive cycles never match, add a larger finale every N cycles, and leave quiet gaps between. The result should play as a performance with a pulse, never as one clip on repeat.

## 3. Continuity anchors
When something changes form (eras, stages, a takeover), name what keeps its identity. Example: "one hilltop chapel that is a pagan shrine, a stone abbey, a ruined shell and a visitor center, always on the same foundations"; "the coastline stays fixed while everything on it changes". Stage each transition as a transformation of the same thing, with no plain crossfade.

## 4. System coupling
Let systems trigger each other, visibly and in sync. Example: "a ferry docks at the quay, a wave of commuters spills down the ramp and fans out across the plaza"; "a manhole lid lifts and steam vents just as the tram passes overhead, on the same beat". Instruments and displays must agree with the world they report on, for instance a radar screen that shows exactly the traffic visible through the window. Section header: "DYNAMISM AND SYSTEM COUPLING".

## 5. Living agents
Forbid the static tableau of figures standing around. Give agents goals, timing, state changes, collision avoidance and visible interaction. Make routines readable, for example "a street painter steps back, squints at the canvas, adds a stroke, then steps aside for a passerby, instead of cycling one idle pose". Ban identical walk cycles, random jitter, frozen silhouettes and decorative dots. Keep life meaningful even at the lowest density. Add small vignettes that reward zooming in, for example "a 1750s ferryman hauling a goat onto a raft".

## 6. Diegetic state
Convey state through the world itself, never through UI. Example: "no agitation gauge is needed, since the beast's posture is the gauge". Express scores as the reaction of a crowd. Keep tension in the near miss, the threat that hovers and never quite lands.

## 7. Expert-nod fidelity
List the real taxonomy of the domain (instrument names, shell types, construction layers, species) and set the bar: accurate enough that a [pilot / geologist / pyrotechnician] would approve. Include candid, unglamorous details, such as "a stray cat on the market steps, because this is a real harbor town". Declare this fidelity the showpiece and protect it in the quality selector.

## 8. Contrast amplifier
State the emotional contrast that makes the payoff land. Examples: "so lovely that wrecking it feels like a guilty pleasure"; "menacing and gorgeous at once, yet lit clearly and easy to read"; "the delicacy of a close-up nature film cut to the tempo of a chase scene".

## 9. Camera lenses
Offer camera modes that change how the scene is rendered, beyond where the camera stands: x-ray view, split-screen cross-section, a section plane that slides live (declare it a showpiece), a follow-cam locked to one element, a fly-through of frozen time. Treat presets as press-kit photographs.

## 10. Scope bans
Forbid additions that dilute the idea. Example: "Do not let spectacle replace the place: no lasers, racing tracks, oversized fantasy props, crumbling buildings or win condition." Keep information overlays OFF by default, and let emphasis toggles highlight things without turning the scene into an infographic.

## 11. Tone calibration
For dark, violent or historically painful subjects, add one explicit line. Example: "Treat it with dignity and restraint: no graphic injury, and the drama comes from light and endurance." For horror: dread over gore, darkness that stays legible, and a statement of where a single shock is allowed, if anywhere.

## 12. Local simulation bubble
Run real physics only where the viewer can see it. Example: "run full rigid-body simulation for pebbles in a wide radius around the camera and around any disturbance, then hand off outward to an animated shader approximation"; the tiers must hand off without a visible seam; physics is localized around disturbances and never global. The bubble radius can be exposed as a control.

## 13. Implementation hygiene
Include rules such as: suspend costly work that is offscreen and prevent memory blowups; bake expensive results once during loading, leaving playback and scrubbing as plain animation; store simulation state snapshots; skip a procedural placement after 10 failed attempts; free geometries and materials when regenerating; keep the camera comfortable (no motion sickness, no getting stuck inside geometry, a sensible near plane).

## 14. Sound
If audio matters: list procedural Web Audio layers per beat, build the climax sound in layers aligned to the visual peak, add a master compressor, and follow the user-gesture unlock rule (resume on the first click, tap or key, with a small sound icon as fallback). If silence is a deliberate choice: state "the scene's sound is carried visually" and let density, flicker and shimmer stand in for it.

## 15. Closing formulas
- "the [superlative] [thing] of [domain], now [previously impossible action]", for example the best-loved painting of a harbor, now open to sail through.
- "everyone has [done X countless times]; this is the first time anyone has [been Y]".
- the compulsion loop, for example "the tide pool you can't look away from"; "...and your hand keeps reaching for the dial"; "...and rewinding makes it never end".
- held in the hand, for example "a thousand years of one hillside, resting in your palm."
