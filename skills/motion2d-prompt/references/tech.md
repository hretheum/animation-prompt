# Technique selection, boilerplates and export

Choose the technique in round 0 and justify it in one sentence inside the prompt ("Use PixiJS because…"). Combine techniques when it helps (shader background + DOM/SVG typography on top), but name one as the primary renderer.

## Contents
1. Matrix: form → technique
2. Each technique: strengths, limits, use when
3. Boilerplates (pinned versions)
4. Time as a pure function (mandatory for export and loops)
5. Export formats
6. Performance budgets

## 1. Matrix

| Form | First choice | Alternatives |
|---|---|---|
| Generative loop | Fragment shader (fields, flows, SDF shapes) or Canvas 2D (lines, marks, trails) | PixiJS for 10k+ sprites; p5.js for sketch-like pieces |
| Endless generative piece | Canvas 2D / shader | PixiJS |
| Motion design film / explainer | SVG + GSAP timeline | PixiJS for heavy particles; Canvas for textured looks; Lottie if export to Lottie |
| Kinetic typography | DOM/SVG text + GSAP (real, selectable, variable-font axes) | Canvas/shader for text as texture or mask |
| Page / UI effect | CSS + Web Animations API (compositor-only) | Canvas/WebGL overlay for particles or distortion over DOM |
| Toy / instrument | PixiJS or Canvas 2D | Shader for fluid/field instruments |
| Data animation | SVG + D3 (scales, transitions, object constancy) | Canvas for >5k marks |
| Character scene | SVG rigs (nested groups) + GSAP, or PixiJS containers | Canvas for painterly textures |
| Micro (logo sting, loader) | SVG + CSS/WAAPI or GSAP | Lottie when the deliverable is Lottie |
| Shader piece | Raw WebGL2 full-screen fragment shader | twgl.js helper |

## 2. Techniques

**Canvas 2D** — immediate-mode drawing; great for lines, trails, marks, painterly accumulation (draw without clearing), pixel art. Comfortable up to ~5–20k simple primitives per frame; text and gradients are costly. No vector export.

**SVG + JS** — resolution-independent vectors, real text, path morphing, masks, stroke animation (dash offset), filters (sparingly — expensive). Comfortable up to ~1–2k animated nodes. Exportable as SVG (static or animated). Best for typography, diagrams, characters, logo work.

**CSS / Web Animations API** — for UI and page effects. Animate only `transform` and `opacity` (and `filter` sparingly) to stay on the compositor; `view-transition` API for page-state morphs; scroll-driven animations (`animation-timeline: scroll()/view()`) where supported, with a JS fallback.

**Fragment shader (WebGL2)** — every pixel computed: noise fields, domain warping, flow, SDF shapes and typography masks, reaction-diffusion (ping-pong), feedback trails, halftone/riso/grain post. Infinite resolution, cheap per shape, expensive per pixel — cap render scale.

**PixiJS (v8)** — 2D WebGL scene graph: sprites, Graphics, text, masks, filters (blur, displacement, color matrix), 100k+ particles with ParticleContainer. Best for rich scenes, games-feel toys, layered parallax, character rigs at scale.

**p5.js** — fastest to sketch generative ideas; slower than raw Canvas/WebGL at scale; good for pieces where the sketchbook feel is the point.

**GSAP** — timeline sequencing, staggers, easing library, morphing and SVG plugins (free since 2025). Use for any choreographed film-like piece; drive it with a single master timeline so time can be scrubbed and exported.

**D3** — scales, layouts, data joins and transitions with object constancy.

**Lottie (lottie-web player)** — only when the deliverable is a Lottie file. The piece must be authored in the Lottie-compatible subset from the start: shape layers, transforms, trim paths, masks, simple gradients, keyframed properties with bezier easing. No shaders, no particles systems, no blur filters, no procedural noise per frame.

## 3. Boilerplates (pin exact versions at least two weeks old)

Script hosts: cdnjs.cloudflare.com, cdn.jsdelivr.net. Load UMD builds with `<script>` tags or ESM via an import map — never unpinned URLs.

- **Canvas / WebGL2 / CSS / SVG native**: "Use only native browser APIs; no libraries."
- **PixiJS**: "Load PixiJS v8 via an import map mapping "pixi.js" to a pinned jsDelivr ESM build, and import only via that name."
- **GSAP**: "Load GSAP (and the plugins you use) as pinned UMD scripts from cdnjs before the module script; drive everything from one master timeline."
- **p5.js**: "Load p5.js as a pinned UMD script from cdnjs; use instance mode."
- **D3**: "Load d3 as a pinned ESM build via an import map."
- **lottie-web**: "Load lottie-web as a pinned UMD script from cdnjs; render the Lottie JSON you author inline."
- Always: "All content is generated in code; no external images or audio, and no fonts beyond Google Fonts."

## 4. Time as a pure function

Mandatory when the piece loops or exports, recommended always:
> Every visual state must be a pure function of time t (and a seed): render(t) draws the frame with no hidden accumulated state, or accumulated state is rebuilt deterministically from t. The live view drives t from the clock; export drives t frame by frame at a fixed step.

Exceptions: feedback/accumulation looks (trails, paint, reaction-diffusion) — then export renders by stepping the simulation at the fixed step from a known seed.

## 5. Export

Decide in round 0. Add a compact "Export" control and specify:
- **MP4/WebM video** — frame-accurate offline render: step t at 1/fps, draw, encode with WebCodecs `VideoEncoder` and a pinned MP4 muxer (fallback: `canvas.captureStream()` + `MediaRecorder` to WebM in real time). State resolution (e.g. 1920×1080, 1080×1920), fps (30/60), bitrate, duration or exact loop length.
- **GIF** — pinned GIF encoder in a worker; limited palette (≤64 colors designed in), dithering choice stated; small dimensions (≤800 px); exact loop length so the GIF loops seamlessly.
- **PNG sequence** — zipped frames (pinned JSZip) for post-production.
- **SVG** — static poster frame as a clean SVG, or animated SVG (CSS keyframes inside) for simple vector loops.
- **Lottie JSON** — only for pieces built in the Lottie subset; export the same JSON the player renders, with frame rate, in/out points and layer names.
- For DOM/SVG pieces exported to video: render through an offscreen canvas pipeline (draw the same scene to canvas) or limit export to SVG/Lottie — say which.

## 6. Performance budgets

- Target 60 fps on a modern laptop; 30 fps acceptable for heavy shaders if motion is designed for it.
- Pixel ratio capped at 2; shader render scale adaptive (drop to 0.75 when frame time exceeds budget).
- Pause when the tab is hidden or the element is offscreen (IntersectionObserver).
- Avoid layout thrash in DOM pieces; batch reads/writes; no animated `width/height/top/left`.
- Overdraw is the 2D enemy: limit stacked full-screen translucent layers and blur filters.
