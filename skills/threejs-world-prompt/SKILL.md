---
name: threejs-world-prompt
description: Leads a conversation that ends in a fucking outstanding prompt for Claude Fable 5 (or another whole-job model) for a flagship real-time visual piece in Three.js/WebGL. It covers immersive worlds (an image turned into a land, a city, a natural phenomenon) and also linear film or animation, a page or UI taken over by an effect, a physics toy or playground, a material instrument, a simulator, a looping show and a mini-game. Use whenever the user wants a "prompt for Three.js", a "prompt for a 3D animation", a "WebGL effect for a web page", a "scene for Fable", to "turn an image into a 3D world", a "maximum-ambition prompt", pastes example prompts and asks for another, or describes an animation, scene or effect they have in mind and asks how to brief a model on it, even if the words "skill", "Three.js" or "world" never come up.
---

# Flagship visual prompt (Three.js / WebGL)

This skill turns a loose vision into a prompt at the tier of the calibration examples in `references/examples.md`. The strength of such a prompt comes from something other than length: **every decision the model would otherwise make by default, and make averagely, is already made**: form, opening frame, single idea, hero mechanic, palette and rendering law, pacing, acceptance criteria, what may be sacrificed for performance and what never is.

## Reference files: when to read

- `references/forms.md`: **always, once the form is settled**. Each form has its own section skeleton.
- `references/anatomy.md`: **always before writing**. The blocks shared by every prompt and the thresholds of each tier (micro / mid / max / spec).
- `references/patterns.md`: optional modules (beats, continuity anchors, system coupling, diegetic state, expert test, camera lenses, tone calibration, implementation hygiene, closing formulas). Read it when you pick modules in round 3-4.
- `references/realism.md`: **always after round 0**. The realism budget: what works and what falls apart at each level, boilerplate variants, levers that raise the ceiling, honest warnings for the user.
- `references/archetypes.md`: topic archetypes, a catalogue of twists, opening strategies, the palette of techniques.
- `references/examples.md`: calibration prompts, one or two per form. Read only the example(s) that match the chosen form and tier. Do not copy content from them.

## How to run the conversation

Overriding rule: **the user has the vision, you have the knowledge**. Do not ask about what you already know (a Monet palette, instrument names in a Cessna, types of pyrotechnic shells). Propose concrete answers and ask whether they fit. Each round: summarize what is settled in a few words, propose default decisions, and ask 1-3 questions about what you really do not know. For closed choices, use a tool with clickable options if one is available.

"Go on / choose yourself" = accept your own proposals. Skip rounds the user has already answered. Goal: 2-5 exchanges before a draft, not an interrogation. If the first message is rich, merge rounds 0-2 into one.

### Round 0: Form and tier
- **Form** (details in `forms.md`): explorable world / linear film / page or UI takeover / toy-playground / material instrument / simulator / process over time (scrubber) / looping show / mini-game / technical spec. Forms can be combined (for example film + UI takeover); then one of them is the main form.
- **Realism budget** (details in `realism.md`): *stylized* (fidelity to a visual language: painting, print, photography, line art), *physical* (phenomena computed from first principles: optics, mechanics, waves, orbits) or *photographic* (must look like footage of reality). When the user wants photographic, also ask about the **production contract**: may the model use external assets (HDRI, scanned PBR textures, glTF models, generated images), is WebGPU allowed, and is it a one-shot in a single file or an iterative project in Claude Code with reference frames and a correction loop. If the vision contains things that fall apart procedurally (people, faces, animals, tissue, close-up fur), say so plainly and propose one of: raising the budget, shifting toward stylization, or hiding the weak spot (silhouette, motion, darkness, grain, distance).
- **Tier**: micro (~80-150 words, one goal, playable at once), mid (~350-550, one interaction, short sections), max (~1100-1900, full anatomy), spec (engineering format with requirements and guardrails, for when the risk is technical rather than aesthetic). Default to max, but propose a lower tier when the vision is simple.

### Round 1: Anchor, twist, core idea
- **Anchor**: what the viewer recognizes at once and why (a painting everyone has seen; the page they read a second ago; the image of a fire-breathing beast every reader carries in their head).
- **Opening strategy**: *anchor → twist* (hold a recognizable frame, the first movement reveals the twist) or *peak-first* (open directly on the peak image, "already X"). Propose 2-3 twists if the user has none.
- **Core idea**: one sentence everything revolves around (for example "a harbor made entirely of paper lanterns, and one tide-bell that lights them in a wave"). Without it the prompt sprawls.

### Round 2: Style law and legibility
Propose these yourself and let the user correct them: the exact composition of the first frame (elements, counts, positions), a palette in named colors, the rendering law, 3-4 anti-patterns ("Do not build..."), and a **legibility rule** (every layer reads at a glance; for a dark mood: dark, but never murky). Optionally a contrast amplifier (for example beauty that makes the destruction hurt).

### Round 3: Hero, mechanic, state
- **Hero material / object** and its states; the density unit ("billion [units]") and the technique.
- **Hero control / hero mechanic**: one interaction named outright as the hero (time slider, rewind, trigger button, walking, brush). In linear forms: the timeline and its beats.
- **Diegetic state**: which state the viewer reads from the world instead of from UI (for example "the lighthouse beam IS the gauge").
- **Thesis shot**: one shot that sums up the whole piece.

### Round 4: Motion, time, modules
Pacing and its justification inside the world, the motion doctrine (at least 5 independent systems), a cycle or sequence with a climax. Choose modules from `patterns.md` that fit the topic: propose them, do not ask about each one separately.

### Round 5: Interaction, camera, performance, tone
Camera modes (including rendering lenses), presets or a shot list, 1 hero control + 2-3 controls + photo mode (or fewer), the must-keep list for the quality selector, tone calibration for difficult topics, bans on scope creep. Prompt language: English by default.

## Writing the prompt

1. Skeleton: the shared blocks from `anatomy.md` + the form's sections from `forms.md` + the chosen modules from `patterns.md`. `####` headings name the idea, not just the topic ("REWIND - THE HERO FEATURE", "THE LIGHTHOUSE - THE STORM YOU CALLED").
2. Imperative mood, dense, concrete. Every point is a decision. Numbers, names and the domain's taxonomy instead of adjectives.
3. Technical boilerplate always, in the variant chosen for the realism budget and the production contract (`realism.md`): one-shot without assets, one-shot with assets, or an iterative project. Always DPR ≤ 2 and a stated frame-rate target on an ordinary current laptop, in your own words.
4. Tiers max and spec end with an **acceptance bar** paragraph (acceptance criteria) before the "In one sentence" line. Mid gets a one-sentence version.
5. Run the checklist, fix, and only then hand it over. Deliver the prompt in a code block or as an `.md` file if it is long or the user prefers a file. Below it, 2-3 sentences on the decisions you made for the user; variants in one sentence.

## Checklist before handing over

Common:
- [ ] First sentence: form + ambition tier + a hero image with 4-6 specifics.
- [ ] "Do not build ..." (3-4 anti-patterns) and a "Build ..." reframe; a "Core idea:" line (mandatory in micro/mid, may be folded into the reframe in max).
- [ ] Density paragraph: "billion [units] ... Achieve this with [technique], not [cheap alternative]".
- [ ] First frame matches the opening strategy; "No title card, menu, loading screen or how-to text"; affordance without a tutorial if there is interaction.
- [ ] Legibility rule stated outright (at a glance + under inspection; dark ≠ murky).
- [ ] Hero control / mechanic named as the hero, with hard requirements (smoothness, bidirectionality, precompute).
- [ ] At least 5 independent motion systems; frozen-frame test.
- [ ] "Up close it still holds" + readable silhouettes from afar.
- [ ] Every feature mentioned is visible, moving or viewable; remove those that cannot be shown.
- [ ] Bans on scope creep (what not to add).
- [ ] Tone calibration, if the topic is dark, violent or historically painful.
- [ ] Performance: technique per element type, LOD, must-keep list ("... is never traded away"), hygiene (offscreen pause, dispose, no memory blow-up).
- [ ] Acceptance bar (max/spec) and one "In one sentence: ..." line.
- [ ] The realism budget is named in the prompt in one sentence ("realism here means..."), the boilerplate matches the production contract, and the acceptance bar includes a realism criterion from `realism.md`.
- [ ] No key frame relies on something that falls apart at the given budget; either the weak spot is hidden (silhouette, distance, motion, light) or the budget is raised.
- [ ] The sections required by the form (`forms.md`) are present.
- [ ] Length within the tier's range; if too long, cut repetition, not decisions.

## Boundaries

- Wording from the example phrases in the reference files and in `examples.md` never goes into the prompt as it stands. Take the structure and the decisions, and write every sentence in your own words, technical formulas and the acceptance paragraph included.

- Works in the public domain are fine. For protected works, well-known characters, monsters or brands (including those from games and films), propose an original design "in the spirit of" and describe it through your own traits, without recognizable elements of the original.
- The prompt must be feasible in a browser. Things that are unrealistic in WebGL (full fluid simulation, global physics of millions of bodies) get translated into a trick that gives the same impression (a local simulation bubble, a shader, instancing, triggered morphing meshes), and the prompt names that trick.
