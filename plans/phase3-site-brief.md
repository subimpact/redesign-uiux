# Phase 3 Build Brief - site/index.html

- Repo: /root/projects/redesign-uiux (work HERE; do not create new projects)
- Stack: one file, site/index.html. Inline CSS via one <style> block. Vanilla JS in one inline <script defer> block at the end of <body>. Copy lives inline in the HTML. No build step, no npm, no external JS, no framework, no Tailwind CDN, no Google Fonts links. Fonts: system font stack only (font-family from MASTER.md tokens is fine but must degrade to system fonts).
- Read site/design-system/redesign-uiux-site/MASTER.md first. It holds the token set (colors, radii, shadows, spacing scale) and the pre-delivery checklist. Check the pages/index.md override file too. Follow them.
- The page sells redesign-uiux: a merged design skill pack for AI agents. It combines the taste-skill judgment layer (a Design Read, three dials named DESIGN_VARIANCE, MOTION_INTENSITY, VISUAL_DENSITY, an anti-slop rule set, a pre-flight checklist) with the ui-ux-pro-max catalog engine (a local BM25 search over catalogs of styles, palettes, font pairings, GSAP motion presets, UX guidelines, and 22 tech-stack guides, invoked as: python skills/ui-ux-pro-max/scripts/search.py "query" --design-system --variance 7 --motion 6 --density 4).
- Sections, mobile-first, at 390/768/1280px:
  1. Sticky top nav (one row, at most 64px tall, never taller than 80px). Brand wordmark left (text is fine). Two links in the middle (How it works, The dial bridge). One button on the right linking to https://github.com/subimpact/redesign-uiux with the label "GitHub".
  2. Hero. Split layout on desktop. Left: an eyebrow is optional but at most one; then a headline at most 2 lines on desktop; then body subtext of at most 20 words; then one primary CTA "Read the skill" linking to the https://github.com/subimpact/redesign-uiux repo, plus at most one secondary CTA of a different intent. Nothing else in the hero. No version labels, no taglines under CTAs, no trust strips, no decorative dots, no scroll cue. Then directly below the hero as its own section: three stat-type items (catalog row counts such as "89 styles", "119 UX guidelines", "22 stack guides") as a simple inline strip, one line of mono text, no card boxes around them.
  3. "Two layers, one bridge" section. Two-column asymmetric grid (7/5 split, not 50/50). Left column: short prose describing the judgment layer (from taste-skill) and the catalog engine (from ui-ux-pro-max). Right column: a working demonstration, see section 4.
  4. Working demo, real, no fake. An input and a button in a search-style form. The user types a query ("dark hero landing", "developer font pairing", anything). On submit, JavaScript intercepts the event and renders the top result's title and description (clearly labeled "top result") into a read-only output area below the form. Realistic behavior, not simulated: the demo must actually do this. The output area must start invisible and only reveal after a real search runs. On an empty query, show a short hint to type a query instead of a fake result.
  5. Working demo 2, real, no fake: the dial bridge. Sliders for variance, motion, density, each 1 to 10. On input, JavaScript updates an on-page command line so it always shows the current invocation: python skills/ui-ux-pro-max/scripts/search.py "modern saas landing" --design-system --variance <V> --motion <M> --density <D> with V/M/D filled in live. A "copy" button next to it that copies the command and shows inline feedback ("copied"). No animation library required.
  6. Catalog strip section. Six to ten small chips listing real catalog domains from the repo (styles, colors, products, typography, google fonts, icons, landing patterns, motion, ux guidelines, charts), each just a label chip in one line wrapping, no cards, no icons, no emoji, no per-domain counts.
  7. How it works section. The seven-step pipeline of the merged skill (from skills/merged-skill.md Part D) as a numbered list using real numbers, one line each: 1 Read the brief and declare a Design Read; 2 Set the dials; 3 Query the engine with the dials attached; 4 Follow catalog guidance plus taste discipline; 5 Build the page; 6 Self-check pre-flight; 7 Gate with a real browser render.
  8. Final CTA section, one centered card, one primary button "Get the skill on GitHub" linking to https://github.com/subimpact/redesign-uiux. No second CTA with the same intent anywhere else on the page.
  9. Footer, one row, mono small text: "redesign-uiux - MIT", a link to the repo, and attribution lines for the two upstream skills (taste-skill by Leonxlnx MIT; ui-ux-pro-max by Next Level Builder MIT). No legal pages needed, no fake addresses.

## Hard rules (from the merged skill, these are the taste gates)
- Zero em-dashes and zero en-dashes anywhere, including code, comments, aria-labels, and button text. Regular hyphen only.
- Do not use the words elevate, seamless, unleash, revolutionize, next-gen, tapestry, delve, or lorem ipsum, anywhere.
- Max 1 accent color: green #22C55E (the MASTER.md accent). Base neutrals #0F172A / #1B2336 / #272F42. Text #F8FAFC, muted #94A3B8, border #475569. The accent is used the same way in every section (the taste consistency lock). Do not introduce a second accent.
- Max 1 eyebrow per 3 sections; at most 3 total on the page. If unsure, drop eyebrows.
- No section-numbering eyebrows (no "01 /" prefixes), no decorative dots, no scroll cues, no locale strips, no version footers, no fake screenshot UIs, no div-built product mockups.
- Dark theme locked on the whole page (the MASTER.md palette). No light-mode sections. No pure #000 and no pure #FFF.
- One corner-radius system: 8px controls, 12px cards. Applied everywhere with no exceptions.
- Buttons: one-line labels at desktop, no wrap, 4.5:1 contrast, cursor pointer, hover transition 150-300ms, active scale 0.98.
- Any animation must have a stated reason (hierarchy, feedback, or state) and must respect prefers-reduced-motion; no infinite loops, no parallax, no scroll hijack, no marquee.
- No emojis anywhere.
- Every clickable element has cursor: pointer and a visible focus ring.
- No horizontal scroll at 390px: document.scrollWidth must equal innerWidth at 390px viewport.
- Semantic HTML: nav, main, section, footer. One h1 only. Title tag: "redesign-uiux - merged design skill for AI agents".
- No lorem ipsum, no fake data. All catalog domain names, dial names, repo links, and attribution lines above come from the real merged-skill.md and README.md.

## Self-check before finishing
Run the taste pre-flight mentally: hero fits in one viewport with the CTA visible; no CTA label wraps; no two CTAs share an intent; sections use different layout families; contrast holds; focus rings visible; reduced-motion respected; no horizontal scroll at 390px; the demo form and demo sliders actually work.

MERGED-SKILL-DONE