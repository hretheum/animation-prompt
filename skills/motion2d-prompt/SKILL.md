---
name: motion2d-prompt
description: Guides a conversation that ends in a fucking outstanding prompt for Claude Fable 5 (or another whole-job model) for a flagship 2D browser animation. Covers generative loops and pieces, motion design, explainers, kinetic typography, effects on web pages and in UI, illustrated character scenes, 2D toys and instruments, animated data and shader pieces, with a technique choice (Canvas 2D, SVG, CSS/WAAPI, shader, PixiJS, p5.js, GSAP) and optional export to video, GIF, Lottie or SVG. Use whenever the user wants a "prompt for a 2D animation", "motion design prompt for Fable", a "generative loop", "kinetic typography", an "animation for a web page", a "loader / logo sting", an "animated explainer", a "character scene", asks "how do I brief a model for a 2D animation", or pastes example prompts of this kind and asks for another one, even if the words "2D" or a library name never appear. For 3D scenes / Three.js use threejs-world-prompt.
---

# Flagship 2D motion prompt

This skill turns a loose vision into a prompt after which the model makes no important decision by default: form, technique, frame and format, style law, signature motion, timing in frames, beats or loop length, interaction, export, must-keep list. It is a sibling of `threejs-world-prompt`. The skeleton is the same, but in 2D the "wow" is carried by **composition, motion craft and shape language**, not by camera and realism.

## Reference files: when to read

- `references/forms.md`: **always, once the form is set**. Mandatory sections for each of the 10 forms.
- `references/tech.md`: **always in round 0**. The form → technique matrix, the limits of each technique, boilerplates with pinned versions, export and its consequences.
- `references/anatomy.md`: **always before writing**. Shared blocks and tiers (micro / mid / max / spec).
- `references/craft.md`: the motion craft glossary: animation principles in code, easing and springs, timing in frames, choreography, transitions, typography in motion, loops, texture, composition. Read in rounds 2–4.
- `references/patterns.md`: optional modules (beats, signature motion, object continuity, morphs, layer parallax, cursor as actor, sound sync, poster frame, hygiene).
- `references/examples.md`: three synthetic calibration prompts (generative loop max, kinetic typography mid, character scene max). Read the one that matches the form. Do not copy its content.

## How to run the conversation

Overriding rule: **the user has the vision, you have the knowledge**. Propose concrete decisions (palette, typeface, easing, loop length, technique) and ask whether they fit. Do not ask about what you can settle yourself. Each round: summarize what is decided, propose defaults, ask 1–3 questions about what you really do not know. For closed choices use clickable options if the tool is available. "Next / you pick" = accept the proposals. Skip rounds the user has already answered. Goal: 2–5 exchanges before a draft.

### Round 0: Form, tier, delivery, technique
- **Form** (`forms.md`): generative loop / endless generative piece / motion design film or explainer / kinetic typography / effect on a page or in UI / 2D toy or instrument / animated data / character scene / micro (logo sting, loader) / shader piece. Forms can be combined; one is primary.
- **Tier**: micro (~80–150 words), mid (~350–600), max (~1000–1800), spec (engineering format).
- **Delivery**: live page / export (MP4, WebM, GIF, PNG sequence, Lottie, SVG) / both. Settle export now, because it constrains the technique: every export requires the **animation to be a pure function of time**, and Lottie requires building from shapes and keyframes from the first line (`tech.md`).
- **Frame format**: full responsive viewport / 16:9 / 9:16 / 1:1 / 4:5 / embedded component. For export, give resolution and fps.
- **Technique**: propose it yourself from the matrix in `tech.md` and justify it in one sentence. Ask only when the user has a constraint (site stack, a library already in the project).

### Round 1: Hook, opening, core idea
- **Hook**: what makes someone not scroll past in the first second.
- **Opening strategy**: *poster frame* (the first frame is already the best image) / *held breath → ignition* / *anchor → turn* (e.g. a normal page that starts behaving differently) / *in medias res*.
- **Core idea**: one sentence everything revolves around.

### Round 2: Style law and legibility
Propose yourself: shape language (geometric / organic / cut paper / ink / pixel / flat vector / engineering drawing), line (weight, caps, wobble), fills and texture (grain, paper, halftone, riso, print misregistration), a palette of 3–6 named colors with hex values, typography (a Google Fonts typeface, its role, variable font axes), composition (grid, safe margins, hierarchy of attention points, empty space), 3–4 anti-patterns, and a **legibility rule** (every frame readable at a glance; text readable at the pace of the motion).

### Round 3: Hero, signature, mechanic
- **Hero**: the element or system that carries the whole piece (line, particles, letters, character, grid, fluid).
- **Signature motion**: one movement by which this piece can be recognized (`craft.md`).
- **Mechanic**: the hero interaction (cursor, scroll, click, drag, sound) or a timeline with beats.
- **Thesis frame**: one frame that sums up the whole piece, for the poster.

### Round 4: Motion and time
Tempo (BPM or seconds per beat), timing in frames for the key movements, easing and springs as named values, choreography (stagger, cascade, overlap), transitions, loop length or a shot list with timecodes, ≥5 independent motion systems in max forms. Pick modules from `patterns.md`.

### Round 5: Interaction, performance, accessibility, export
Controls (minimal), `prefers-reduced-motion` (always, with a concrete reduced version), the performance budget for the technique, export details (control, format, resolution, fps, length, seamlessness), the must-keep list. Prompt language: English by default.

## Writing the prompt

1. Skeleton: the shared blocks from `anatomy.md` + the form's sections from `forms.md` + the technique boilerplate from `tech.md` + modules from `patterns.md`. `####` headings name the idea.
2. Imperative mood, dense. Describe motion with numbers: frames, milliseconds, curves (`cubic-bezier(.2,.8,.2,1)`), springs (stiffness/damping), stagger in ms, BPM. Colors as hex, typefaces by name.
3. Tiers max and spec end with an **acceptance bar** paragraph, then one sentence "In one sentence: …".
4. Run the checklist, fix, deliver in a code block (or as an `.md` file if long or on request). Below it, 2–3 sentences about the decisions made on the user's behalf.

## Checklist before delivery

- [ ] First sentence: form + technique + a hero image with 4–6 concrete details in motion.
- [ ] "Do not build …" (3–4 2D anti-patterns, e.g. stock motion template, PowerPoint fade-in, confetti screensaver, clip-art) and a "Build …" reframe; "Core idea:".
- [ ] Technique named and justified, boilerplate with pinned versions from `tech.md`.
- [ ] Frame format, resolution and fps (if exporting), behavior on resize.
- [ ] Opening matches the strategy; poster-frame and first-second test.
- [ ] Style law: shape, line, texture, palette with hex values, typeface with its role.
- [ ] Legibility rule, including the reading pace of text in motion.
- [ ] Signature motion described with numbers; easing and timing as named values.
- [ ] Loop: length in frames and the seamlessness rule; film: shot list with timecodes and beats.
- [ ] ≥5 independent motion systems (max); frozen-frame test.
- [ ] Every mentioned feature is visible, moving or viewable.
- [ ] Scope-creep bans; tone calibration if the topic is delicate.
- [ ] `prefers-reduced-motion` with a concrete reduced version.
- [ ] Export (if any): animation as a pure function of time, frame-by-frame rendering, format, control; Lottie only in the compatible subset.
- [ ] Performance: the technique's budget, DPR ≤ 2, pause off-screen, must-keep list ("… is never traded away").
- [ ] Acceptance bar (max/spec) and "In one sentence: …".
- [ ] Sections required by the form are present; length within the tier's range.

## Boundaries

- Wording from the example phrases in the reference files and in `examples.md` never goes into the prompt as it stands. Take the structure and the decisions, and write every sentence in your own words, including technical formulas and the acceptance criteria paragraph.
- No known characters, mascots, logos or recognizable copyrighted projects, including "in the style of" a specific character. The style of a movement or era (Bauhaus, ukiyo-e, Swiss, mid-century cut-paper forms as a general language) is fine; propose original characters and marks.
- Fonts only from Google Fonts or system fonts, unless the user supplies their own.
- The prompt must be executable in a browser. If the vision exceeds the technique's limit (e.g. a million vector shapes in SVG), change the technique or the trick and name it in the prompt.
