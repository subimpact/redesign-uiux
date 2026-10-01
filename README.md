# redesign-uiux

A merged design skill pack: [taste-skill](https://github.com/Leonxlnx/taste-skill) (anti-slop judgment layer) fused with [ui-ux-pro-max-skill](https://github.com/nextlevelbuilder/ui-ux-pro-max-skill) (BM25-searchable UI/UX design catalog engine).

Live demo: https://redesign.subimpact.net (the page itself is built with this skill).

## Why merge

These two skills are complements, not competitors:

- **taste-skill** is the judgment layer: how to read a brief, how bold/moving/dense a design should be (the three dials), what AI slop looks like, and a pre-flight checklist.
- **ui-ux-pro-max** is the grounded layer: a local BM25 search engine over catalogs of styles, palettes, font pairings, GSAP presets, UX guidelines, and 22 stack guides.

The bridge already existed inside ui-ux-pro-max: its `search.py --design-system` mode accepts `--variance`, `--motion`, and `--density` -- the exact three taste-skill dials. This repo wires them together.

## Layout

```
skills/
  merged-skill.md        <- start here: the merged skill (judgment + engine + workflow)
  taste/
    README.md            <- taste-skill SKILL.md, verbatim (sections 6/8/10/11/12 referenced on demand)
    redesign-skill.md    <- redesign audit + fix priority
  ui-ux-pro-max/
    README.md            <- upstream SKILL.md, verbatim
    scripts/search.py    <- BM25 search engine (stdlib Python, no dependencies)
    data/                <- catalogs: styles, colors, products, fonts, icons, motion, stacks...
    references/          <- pro-rules.md, quick-reference.md
site/                    <- landing page demo (redesign.subimpact.net), built with the merged skill
```

## Use it

```bash
# 1-2. Read the brief, set the dials (DESIGN_VARIANCE / MOTION_INTENSITY / VISUAL_DENSITY)
# 3. Query the engine with the dials attached
python skills/ui-ux-pro-max/scripts/search.py "modern saas landing" --design-system --variance 7 --motion 6 --density 4
# 4-5. Build per taste discipline + catalog guidance
# 6-7. Self-check (pre-flight + pro-rules), then gate with a real browser render
```

For redesigns: read `skills/taste/redesign-skill.md` (audit categories, fix priority 1-7).

## Attribution

- taste-skill by [Leonxlnx](https://github.com/Leonxlnx/taste-skill), MIT License, see `LICENSE.upstream-taste`.
- ui-ux-pro-max by [Next Level Builder](https://github.com/nextlevelbuilder/ui-ux-pro-max-skill), MIT License, see `LICENSE.upstream-uiux-pro-max`. Its ui-styling companion skill is Apache-2.0.
- Merge layout, dial bridge, workflow, and site: MIT, see `LICENSE`.