# Anatomy — shared blocks and tiers

> Example phrasings in this file are illustrations only. Never copy their wording into a prompt; write the same idea in your own words. The calibration examples in `references/examples.md` set the standard.

These blocks appear in every max-tier prompt regardless of form. Form-specific sections live in `forms.md`; optional modules in `patterns.md`.

## Tiers

| Tier | Length | Shape | Use when |
|---|---|---|---|
| micro | 80–150 words | one paragraph + "Core idea" + one list sentence | a contained game or toy with one goal |
| mid | 350–550 words | opening, "Core idea", 4–5 short `####` sections, one interaction, "Tiny HUD", PERFORMANCE DISCIPLINE | a single spectacle with one trigger (natural phenomena, festivals) |
| max | 1100–1900 words | full anatomy below + form sections + modules + acceptance bar | flagship pieces |
| spec | 400–900 words | engineering format (see forms.md §10) | correctness risk outweighs aesthetic risk |

---

## 0. Opening paragraph (no header)

1. **Hero sentence** — `Build a flagship Three.js [experience | environment | playground | simulator | cutaway | film] of [subject]: [hero image with 4–6 concrete elements, each with a verb].` Variants of the ambition word: "unprecedented, museum-quality", "the most ambitious possible", "the definitive".
2. **Cultural anchor (optional)** — why the audience already carries this image ("Anyone who has read the myth can already picture the lighthouse in the storm"; "Everyone has walked past a market stall like this; nobody has seen one from a mouse's height at dawn").
3. **Negative definition + reframe** — `Do not build [cheap 1], [2], [3] or [4]. Build [one-line reframe].` Optionally a counter-position: "Set it against the expected choice: where a chase would be expected, the spectacle is stillness."
4. **Core idea** (mandatory in micro/mid, optional line in max): `Core idea: [one sentence the whole piece orbits].`

## 1. Density paragraph (no header)

`The target look: a million [unit]: [3–5 forms the unit takes]. Achieve this with [technique], not [cheap alternative].` Add when relevant: a line saying the parts must visibly separate and move on their own / the style IS the material / precision held at close range and at distance together.

## 2. Technical boilerplate (verbatim-ish)

> Load Three.js through an import map placed ahead of the module script, with "three" and "three/addons/" both pointing at one pinned release; every import goes through those two specifiers. All content is generated in code; nothing is fetched from outside.

This is the variant for a one-shot with no assets. For one-shot with assets and for the iterative project, use the variants in `realism.md`. The spec tier may require full offline embedding instead.

Right after the boilerplate, one sentence naming the realism budget: `Realism here means [stylistic fidelity to X | physically computed Y | photographic Z]: [what must convince the eye].`

## 3. `#### FIRST FRAME - [idea]`

Choose the opening strategy (see archetypes.md):
- **Anchor → twist**: exact composition; fidelity non-negotiable with named palette; "hold for a breath"; the first movement reveals the twist.
- **Peak-first**: "Open directly on the finished scene at full strength. No title screen, intro, fly-in, build-up animation, loading show, menu, bare ground or postponed reveal." / "Already in motion, already at its best." / "The very first image must already be the strongest one."
Always: legibility ("every layer readable at a glance, inexhaustible when studied"; "understood within a fraction of a second"), light stance ("bright and clear, never muddy" — or for dark briefs "dark, never muddy"), affordance if interactive ("what to touch is obvious at once"), and `No menus, titles or on-screen instructions.`

## 4. Hero section(s)

States of the hero, the signature material effect, the thesis shot, `Up close it still holds: …`. For interactive forms: the hero control/mechanic with hard requirements. See forms.md.

## 5. Dynamism

≥5 independent motion systems listed; pace named and justified inside the world; the paused-frame test (`Freeze any frame and it reads as [X]; watch for [N] seconds and it feels like [Y].`).

## 6. Controls

`Keep controls to a handful:` one hero control + 2–3 others + photo mode, and nothing more. UI "small, elegant and collapsible". Info overlays OFF by default.

## 7. `#### PERFORMANCE` (or "PERFORMANCE DISCIPLINE" in mid)

- Technique per element type; LOD tiers that "blend invisibly"; local simulation bubble around the camera blending into shader motion where physics is needed.
- `Lower quality tiers give up [counts, sampling, far detail] first; [must-keep list] is never traded away.`
- Hygiene: pause expensive offscreen work, avoid memory explosions, precompute choreography at load.
- `Keep a steady frame rate on a current mid-range laptop; cap the pixel ratio at 2.`

## 8. Acceptance bar (max and spec; one sentence in mid)

A closing paragraph of acceptance criteria. Template — adapt the numbers and nouns:

> Acceptance bar: the job is not done if the result is a small symbolic model, a sparse set piece, one object on its own, a mostly still scene, a flat shader trick or a clever shortcut that looks thin. Done means: the first frame lands on its own; at least [five] motion systems run independently; detail holds up from a hand's width away and silhouettes read from far off; [the camera modes / the hero control] work without a hitch; every control changes something you can see; the code respects the frame budget. Build the spectacle itself rather than interface that explains it. Anything this brief names must show up on screen, move or be explorable — if it cannot, cut it from the brief instead of faking it.

## 9. Outcome line (last sentence)

`In one sentence: …` — see the closing formulas in patterns.md.

---

## Style rules

- Imperative, present tense, dense full-sentence bullets with dashes and semicolons.
- CAPS for the one word carrying the twist or mechanic ("a COLOSSUS", "Water BEHAVES", "REWIND", "BEING the firework").
- Absolute words ("non-negotiable", "never traded away") only for the must-keep things.
- Numbers and domain names everywhere (counts, heights, speeds, durations, real taxonomies).
- Headers name ideas: "THE ZOOM IS THE SPECTACLE", "CONTINUITY IS THE MAGIC", "EXPLORATION THAT REVEALS CRAFT, NEVER HIDES IT".
