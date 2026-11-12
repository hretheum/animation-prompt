# Animation prompt skills

> **Public domain.** Released under [CC0 1.0 Universal](LICENSE): use, copy, change and redistribute without asking and without attribution.

Two Claude skills that turn a loose animation idea into a prompt a whole-job model can build from, with every important decision already made.

| Skill | Use it for |
|---|---|
| `motion2d-prompt` | 2D motion: generative loops, motion design, kinetic typography, page and UI effects, character scenes, 2D toys, animated data, shader pieces. Picks the technique (Canvas 2D, SVG, CSS/WAAPI, shader, PixiJS, p5.js, GSAP) and the export route. |
| `threejs-world-prompt` | Real-time Three.js / WebGL pieces: immersive worlds, linear film, page takeovers, physics toys, material instruments, simulators, looping shows, mini-games. |

Each skill runs a conversation in rounds, writes the prompt, checks it against a checklist and states its own boundaries.

## Contents

- `installable/` — ready-to-install `.skill` packages.
- `skills/` — the same skills unpacked, for reading and editing.
  - `SKILL.md` — the conversation rounds, writing rules, checklist, boundaries.
  - `references/` — forms with mandatory sections, anatomy of a prompt, optional modules, techniques (`tech.md`, `realism.md`), and a few original calibration examples (`examples.md`).

## Install

1. Download a file from `installable/` (`motion2d-prompt.skill` or `threejs-world-prompt.skill`).
2. In Claude, open Settings → Capabilities → Skills and upload the file.
3. Ask for a prompt, for example "write a prompt for a 2D kinetic typography piece" or "prompt for a Three.js world".

To edit a skill, change the files under `skills/` and zip the skill folder as a `.skill` file again.

## Background

The skills borrow the structure of strong animation prompts, not their sentences. They were inspired by Peter Gostev's [3d-prompt-collection](https://github.com/petergpt/3d-prompt-collection) (https://github.com/petergpt/3d-prompt-collection), used with the author's permission for the accompanying article. This repository contains none of its prompts; every example here is original.

## License

[CC0 1.0 Universal](LICENSE). No rights reserved.
