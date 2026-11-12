# Realism budget

Ask in round 0. The answer changes the boilerplate, which modules matter, the acceptance bar and what you must warn the user about. The ceiling in a browser is set more by the medium and the production contract than by the model.

## The three budgets

| Budget | The viewer judges | Strong in one-shot, no assets | Weak in one-shot, no assets |
|---|---|---|---|
| **Stylistic** | "Does it look like THAT language?" (Hokusai print, Monet dabs, silver-gelatin print, ink) | Almost everything: the style is a rendering law the model controls fully; grain, outlines, posterization and dabs hide geometric simplicity | Faces if the style is realistic portraiture |
| **Physical** | "Does it behave correctly?" (optics, mechanics, waves, orbits, granular flow) | Light, refraction, lensing, atmospheres, fog, water surfaces, metal, glass, stone, mechanisms, particles, astronomy, anything computable from first principles | True global fluid and cloth simulation (fake it with a local simulation bubble) |
| **Photographic** | "Could this be footage?" | Wide landscapes under strong atmosphere, architecture at distance, hard-surface objects, skies, water at mid distance | Humans, faces, animals, fur, wet organic tissue in close-up, dense photoreal vegetation, real-time global illumination — procedural results drift to uncanny or toy-like |

## Hiding weak points (cheaper than raising the budget)

Silhouette against light; distance and atmosphere; motion blur and fast motion; darkness with one focal point; heavy grain, halation, depth of field; stylization of just the weak element (a creature that is all cable and fungus, never skin); the "never seen moving" trick; framing the weak element in fragments.

## Levers that raise the ceiling

1. **External assets** — HDRI environments, scanned PBR textures, glTF models, generated images. The single biggest lever for the photographic budget.
2. **WebGPU** — three.js WebGPURenderer with TSL materials and compute shaders: more particles, local simulations, heavier post.
3. **Iterative project instead of one-shot** — a pinned build (e.g. Vite + TypeScript), reference frames, headless screenshots (Playwright) compared against the references each phase, a notes file of verified API facts, repeated polish passes.

## Asset types — what each brings

Rule of thumb: **vectors for shape, raster for material, HDRI for light.** Only add an asset when it carries something the model cannot invent (the user's logo, a specific illustration, a scanned surface, real light).

| Asset | Brings | Use when | Watch out for |
|---|---|---|---|
| **SVG / vector** | Exact shapes, silhouettes, logos, patterns; resolution-independent | Stylistic budget; silhouettes and masks; extruded shapes (SVGLoader → ExtrudeGeometry); a shader then adds the material | No light or surface information — never makes things photoreal; complex paths explode triangle counts; SVGLoader drops gradients and filters — rasterize complex SVG to a texture instead; the model can author simple vectors itself |
| **MSDF / SDF text and glyphs** | Text and icons that stay sharp at any zoom | The camera flies close to letters (page takeovers, prints, signage) | Needs a generated atlas; or have the model build SDFs procedurally |
| **Raster texture (sRGB)** | Colour detail, illustrations, photos, the reconstructed page | Any budget; a specific image must appear | Blurs when the camera gets closer than its resolution allows; set colour space correctly |
| **PBR texture set** (albedo, normal, roughness, AO, height) | Micro-surface: pores, scratches, wetness, wear — how light grazes a surface | Photographic and physical budgets; hero materials seen up close | Memory; tiling repetition at distance (break up with detail noise); use compressed formats (KTX2) for many sets |
| **HDRI environment** | Real lighting and reflections with true dynamic range | Photographic budget; anything glossy, metallic, glassy or wet | Its light must match the scene's sun and mood; large files — one is usually enough |
| **glTF / GLB model** | Precise organic or manufactured geometry, rigs, animations | Faces, creatures, animals, products — what procedural geometry fails at | Licensing, polycount, style mismatch with procedural surroundings; compress (Draco/Meshopt) |
| **Generated image** (image model) | Concept-accurate textures, decals, matte backdrops, title art | Unique surfaces nobody has scanned; distant backdrops | Flat lighting baked in; seams when tiled; keep it off hero close-ups unless it is a print or poster in the world |

## Boilerplate variants

**A. One-shot, no assets** (default for stylistic and physical):
> Load Three.js through an import map placed ahead of the module script, with "three" and "three/addons/" both pointing at one pinned release; every import goes through those two specifiers. All content is generated in code; nothing is fetched from outside.

**B. One-shot, with assets** (photographic, single deliverable):
> Deliver a single HTML file. Load three.js and addons through an import map pinned to one version. You may load assets only from [named CDN or embedded data URIs]: an HDRI environment for lighting and reflections, PBR texture sets for [materials], and [models]. Every asset must have a procedural fallback so the scene still renders if a load fails; show no loading screen longer than [N] seconds — begin with a procedural version and upgrade in place.

**C. Iterative project** (photographic or flagship, Claude Code or similar):
> Build this as a project: three.js pinned in a lockfile, [WebGPURenderer with TSL | WebGLRenderer], TypeScript, a dev server. Before building, write a reference sheet of [N] target frames described in words (camera, light, materials, what must convince). After each phase, capture headless screenshots at those cameras, compare against the references, and log deltas and fixes in a notes file. Keep a file of verified API notes for the pinned version. Continue polishing until every reference frame passes, then report what still falls short.

## Ambition-bar sentence per budget

- Stylistic: "A screenshot from any angle must pass as [a lost plate / a canvas / a print] in that language."
- Physical: "Correct enough that a [physicist / engineer / pilot] would nod; behaviour is computed, not animated by hand."
- Photographic: "At [hero distances], frames must be mistakable for footage; where the budget cannot reach photoreal, hide the weakness with [light, distance, motion, grain] rather than show it plainly."

## Honest warnings to give the user

- Organic close-ups (faces, creatures, tissue, fur) are the weakest point without assets — say so when the vision depends on them.
- One-shot pieces often need one or two refinement rounds; plan for it.
- A photographic budget in a single file with no assets is a contradiction — offer budget B, C or a stylistic reframe.
