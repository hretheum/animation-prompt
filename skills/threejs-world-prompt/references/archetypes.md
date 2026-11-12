# Archetypes, twists and technique palette

> Any English phrases in this file are only illustrations of an idea. Never copy their wording into a prompt; write the same idea in your own words. For calibration, use the examples in `references/examples.md`.

Use to propose options in round 1 and to fill technical decisions in rounds 3–5.

## Archetypes

| Archetype | Anchor (opening frame) | Typical twist | Reference |
|---|---|---|---|
| **Artwork → world** | Pixel-faithful reproduction of the canvas/print | Flatness breaks: depth, volume, scale, infinite continuation | Starry Night, Water Lilies, Great Wave, The Kiss, Tower of Babel |
| **Everyday place at absurd scale** | The ordinary place, already mid-action | Viewer is tiny/huge; time dilates with scale | A garden in the rain seen from one millimetre up |
| **Natural phenomenon from inside** | Recognisable photo-like view (aurora, eclipse, lightning, migration) | Viewer is inside the event, time stretched | See the calibration examples in `references/examples.md` |
| **Historical place alive** | Period-accurate view or famous depiction | Teeming population and logistics you can follow end to end | Tower of Babel |
| **Abstract/scientific made physical** | A known diagram or image (cell, galaxy, circuit) | It is a landscape you can traverse | A cutaway city section you can walk through |
| **Being the event** | The moment just before (inside the mortar tube) | The viewer IS the thing, not a spectator | Riding a firework shell |
| **Legend held mid-moment** | The image every reader carries | The miracle/threat frozen at its peak, at full scale | A dragon's treasure pile, a sea splitting open |
| **Interface invaded** | The page or UI the viewer was just using | Something was growing/living behind the screen | A fungus spreading behind the page |
| **Material made world** | A real surface (paper, marble, glass) | The material generates a landscape or a body | Ink floating on oil, marble coming to life |
| **All of it at once** | A famous view, but complete | Everything that never coexists, together and alive | All the ancient wonders together, a whole city at once |

Artwork archetype: only public-domain works (see SKILL.md, Boundaries).

## Twist catalogue

- **Depth reveal**: the flat image is layers that slide on parallax (Starry Night, Water Lilies).
- **Scale reveal**: the composition was a distant view of a colossus (The Kiss as a 50 m monument).
- **True scale**: the viewer is placed inside at the size the image depicts (oarsman under the Great Wave).
- **Infinite continuation**: flying into it never reaches an end; procedurally streamed depth shells.
- **Time dilation**: 1/10 or 1/100 speed; event always happening, never completing.
- **Living pattern**: the surface stays still but its pattern moves within it (Klimt robes).
- **Wholesale re-painting**: a light cycle re-colours each unit individually in traveling washes (Monet series).

## Opening strategies

- **Anchor → twist**: hold the recognizable frame, the first movement breaks it. Best when recognition is the hook (paintings, prints, a familiar page).
- **Peak-first**: the very first frame the viewer sees is already the strongest image; no reveal, no construction animation. Best for density showpieces, toys, simulators.
- **Held breath**: about a second of near-stillness, then the sudden release. Best for rides and films.
- **Mid-action**: the scene opens with the event already underway, for example a barrage well under way or the camera already in flight. Best when the event is the subject.

## Pace vocabulary

slow water · stately · glacial menace · macro-camera speed (1/10) · one-hundredth · slow springy wave · tens of seconds per rotation · ten-minute cycle.

## Technique palette (name these in the PERFORMANCE / goal paragraph)

| Need | Technique |
|---|---|
| Millions of strokes/dabs/units | InstancedMesh + per-instance attributes; flow field (curl noise) advection in shader; recycling pool |
| Pattern that moves within a surface | Procedural pattern shader with time-driven UV/cell offsets |
| Glitter / tesserae | Instanced facets near camera, collapsing to micro-glitter normal map at distance; angle-dependent specular |
| Print / cartoon style | Cel/toon shading with quantized ramps, full-screen outline pass (depth+normal edges), paper grain |
| Impasto paint | Ribbon geometry with ridge normals, bristle-groove texture, emissive only for brightest pigments |
| Water drops | Instanced refractive spheres (env/backbuffer refraction), wobble in vertex shader |
| Splashes / impacts | Triggered morphing crown meshes, pooled lifetimes |
| Soft bodies (domes, blobs) | Shaded blobs with tension-like vertex wobble, merge by metaball-ish blending or swap |
| Flexing ground | Vertex wave propagation from impact points |
| Crowds / creatures | Instanced low-bone or vertex-animated rigs; LOD to animated silhouettes; behaviour loops |
| Infinite flight | Depth shells streamed ahead / released behind; atmospheric haze toward palette colour |
| Macro look | Depth-of-field bokeh as standing post effect, focused mid-distance |
| Light cycle | Palette LUT per phase, interpolated per instance by a travelling front |
| Clouds / mist | Layered sprite veils or raymarched low-res volume, half resolution |

## Typical must-keep lists

- Artwork: opening-frame fidelity, palette accuracy, signature motion system, signature material effect.
- Scale worlds: time dilation, the physical "law" of the material (surface tension), the global cycle.
- Historical: hero silhouette, close-range detail, the key atmospheric interaction.

Typical first to reduce: counts (units, particles, population), splash/claw complexity, post-effect sampling, far detail, shell depth.
