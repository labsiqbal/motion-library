---
name: design-library
description: Curated, growing library of web ANIMATION/MOTION effects (named + moodtagged + paste-ready code) PLUS a Next.js application playbook that maps UI context → effect. Solves "you must name the effect to summon it", "motion can't be screenshotted", and "how does the AI know which animation goes where". Use when designing a UI that should feel alive — landing pages, hero sections, micro-interactions, scroll effects, text animation, WebGL/three.js, loaders, or composing a whole page's motion. Pairs with builder skills (impeccable, claude-design); this skill PROVIDES the motion vocabulary + code + where-to-use guidance, it does not build the page.
version: 0.11.0
author: Iqbal + Kuya agents
license: MIT
platforms: [linux, macos, windows]
metadata:
  hermes:
    tags: [design, animation, motion, css, gsap, threejs, webgl, scroll, micro-interaction, ui]
    related_skills: [impeccable, claude-design, popular-web-designs, design-md]
---

# design-library — motion effects, named and ready

This skill is a **data provider, not a builder.** It hands a builder (impeccable,
claude-design, or you directly) a curated catalog of web *animation* effects, each
with a name, a mood, when-to-use rules, dependency cost, and **paste-ready code**.

It exists because animation has two problems static design doesn't:
1. **You must know the term to ask for it.** "parallax", "magnetic hover", "text
   scramble" — without the word, you can't summon the effect.
2. **Motion can't be screenshotted.** It lives in time; it must be *run* to be seen.

So this library names every effect (vocabulary) and ships a **live gallery**
(`galeri.html`) where each effect runs — a human can watch and point, an agent can
read and grab the code.

## The artifacts

| File | For | Role |
|---|---|---|
| `CATALOG.md` | the AI | **index of all 217 effects** — name · `id` · istilah · when-to-use · `[library]`, each tagged ⭐ signature / workhorse, plus a "signature palette by family" for the flavor menu. Includes a **UI Transitions** category (the §5.6 app-UI state transitions) + native CSS scroll-driven effects. The map; code lives in `galeri.html` |
| `PLAYBOOK.md` | the AI | **application layer** — context→effect slot map, composition rules, 7 Next.js page kits (SaaS, portfolio, campaign, app/dashboard, content, corporate, e-commerce), the Next.js wrapper pattern (SSR-safe client components + cleanup + npm imports), and a **performance doctrine (§5.5)** (perf as a practice — facade, static poster, `canAnimate()` fallback; Lighthouse is a later/live check, not a design gate), and a **transition-craft doctrine (§5.6)**: make every design feel *expensive* through motion — premium per-element transitions (buttons/cards/modals/tabs/lists/inputs/numbers), the motion axes (duration·easing·distance·blur·scale·spring·origin·stagger·FLIP), and the toolbox (FLIP, View Transitions API, springs, origin-aware) — plus **§5.7 modern native transition tech** (CSS scroll-driven animations, the View Transitions API + Next.js page-transition kit, and the theme-switch circular reveal), all with runnable versions in `galeri.html` |
| `galeri.html` | the human | every effect rendered live; filter by category/dependency; copy code |
| `effects/` | growth | per-category source notes as the library expands |

The effect code lives **once** (in `CATALOG.md`, mirrored into `galeri.html`).
`CATALOG.md` = *what effects exist*; `PLAYBOOK.md` = *which goes where + how to ship it in Next.js*.

## How an agent uses this (the selection logic)

**Composing a whole page (or building in Next.js)? Start with `PLAYBOOK.md`.** It maps each
UI slot (hero bg, CTA, section reveal, card, stats, loader…) to recommended effects, gives the
composition rules that keep motion varied (not the same fade-up everywhere), provides 7
ready page kits, and shows the Next.js wrapper pattern. Then come back here / to `CATALOG.md`
for each chosen effect's actual code. The steps below are the per-effect picking logic the
playbook leans on.

**Building a new site? FIRST offer 3 flavors (PLAYBOOK §0 + §0.5).** Before writing any code,
present three genuinely divergent style directions (e.g. Neon / Liquid / Editorial) — each with
its **signature** long-tail effect — and let the user pick. Every page must commit to ≥1 rotated
signature effect; this anti-convergence rule is what keeps builds from collapsing onto the same
safe ~15 effects. Don't skip the flavor menu.

When a builder needs motion, follow these steps — this is filtering over labels,
not guessing:

1. **Tangkap niat** — from the brief derive: mood (2–3 adjectives, e.g.
   *premium, playful, futuristik*), surface (hero / card / nav / section),
   intensity budget (subtle ↔ bold), and dependency budget (is a 30KB lib OK?).
2. **Saring** — in `CATALOG.md`, keep effects whose `mood`/`kapan` match the intent
   and drop `hindari` matches. Respect the dependency budget via the `deps` field.
3. **Rakit + signature move** — pick a small set (usually 1 hero effect + 2–3
   micro/ambient). Push **one** effect toward bold for character; keep the rest
   calm. Honour `pasangin` (good pairings) and avoid clashing combos
   (e.g. don't stack three attention-grabbing effects in one viewport).
4. **Validasi** — performance (transform/opacity only for 60fps; no layout
   thrash), reduced-motion fallback (`prefers-reduced-motion`), and that the
   dependency is actually justified.
5. **Serahin** — return the chosen effect code to the builder, which integrates it.

## Dependency tiers (NOT vanilla-only)

Vanilla-first **as a default, not a rule.** Use the lightest thing that delivers
the effect; reach up a tier when the effect genuinely needs it.

- **Tier 1 — vanilla** CSS / JS (`deps: vanilla`). Zero dependencies. Default.
- **Tier 2 — focused libs** (`deps: gsap`, `deps: three`). GSAP/ScrollTrigger for
  complex timelines & scroll-scrubbing; three.js for real 3D/WebGL. Loaded from
  CDN. Use when vanilla would be fragile or verbose. **Flag the cost** so the
  builder knows what it's pulling in.

Every entry states its tier in `deps`. Builders filter by their dependency budget.

## Growth loop (manual for now)

The library is meant to keep growing. To add effects:
1. **Source** (see `CATALOG.md` → Sources): Tier-1 = author from knowledge;
   Tier-2 = adapt from Codrops/Tympanus, GSAP/Framer/Motion-One/Lenis demos,
   three.js examples, real production sites. **Reimplement the technique** rather
   than copying verbatim; note the source + license.
3. **Verify by running** — render the new effect in `galeri.html`. Animation is
   live code: if it moves correctly at 60fps with a reduced-motion fallback, it
   passes. If not, it doesn't enter the library.
4. **Curate (human gate)** — new finds are presented; Iqbal approves which stay.
5. **Promote** — add to `CATALOG.md` + `galeri.html`, bump version, log the change.

A scheduled "morning report" version of this loop is deferred until the core proves
useful — keep it manual first (YAGNI).

## Boundaries

- This skill never builds the final page; it returns motion code to a builder.
- Always include a `prefers-reduced-motion` fallback when integrating.
- Prefer `transform`/`opacity` animations; avoid animating layout properties.
