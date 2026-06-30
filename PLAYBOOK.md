# PLAYBOOK.md — Motion Playbook (Next.js)

The **application layer** over `CATALOG.md`. The catalog answers *"what effects exist."*
This file answers *"which effect goes where, how to vary them across a page, and how to
drop them into a **Next.js** app."* Every effect name below is a real entry in the catalog /
`galeri.html` — grab its code from there.

> Target stack is **Next.js (App Router, React, TypeScript)**. All guidance assumes that.
> The catalog code is vanilla; §4 is the bridge that turns any effect into a Next.js client
> component correctly (SSR-safe, cleaned up).

---

## 0. How an AI uses this (the flow)

When asked to build a page or site:

0. **Offer 3 flavors FIRST — do not start building.** Identify the page type, then present
   **three genuinely divergent style directions** (see §0.5) as a short text menu — each with a
   name, a one-line vibe, and its **signature effect(s)**. Wait for the user to pick one (they
   may also say "surprise me" → you pick a rotated one, or "show them" → build hero-only previews).
   This is mandatory; skipping it is how every build ends up looking the same.
1. **Take the chosen flavor + page type** → start from the matching **Kit** (§3), but swap the
   flavor's **signature effect** into the hero/focal slot (§0.5).
2. **Walk each section**, name its **slot role** (hero bg, CTA, section reveal, card, stats,
   loader, …) → pick an effect from the **Slot Map** (§1) or the Kit, biased by the flavor.
3. **Apply the Composition Rules** (§2) — *vary the reveals*, budget the motion. This is the
   step that separates "designed" from "AI made this."
4. **Wrap each effect** as a Next.js client component with the **Next.js Rules** (§4).
5. **Pull the actual code** from `galeri.html`/CATALOG.md (copy the per-effect snippet) and
   drop it inside the wrapper.

Do NOT apply the same reveal to every section. Do NOT stack two WebGL backgrounds. Do NOT
forget the reduced-motion fallback. Do NOT skip the flavor menu (§0 step 0).

---

## 0.5 Exploration — flavors & the signature rule (anti-convergence)

**The problem this solves:** a recommendation system converges. If the slot map lists "safe
options first," every build reaches for the same ~15 workhorse effects and 184 of the 199 never
get used — and the result reads as generic. The safe pick *is* the AI-slop tell. The fix is a
deliberate push the other way.

### Workhorse vs. signature effects
- **Workhorse** (the safe spine — use freely, but they don't give a page character):
  `Reveal on scroll`, `Fade-Up Stagger`, `Magnetic button`, `3D tilt card`, `Spotlight hover`,
  `Skeleton shimmer`, `Odometer Counter`, `Seamless Marquee`, `Grid Pop-In`, `Split text reveal`.
- **Signature** (the long-tail — these give a page its character; ROTATE them):
  - *Shader / WebGL:* `Plasma flow shader`, `GPU points wave field`, `Particle galaxy spiral`,
    `Fresnel glow sphere`, `Raymarch Blob`, `Noise Field Plane`, `Morphing Point Cloud`,
    `Repelling points grid`, `Cube Wave Grid`, `Plasma Triangle`.
  - *Generative / canvas:* `Liquid Metaballs`, `Flow Field Streams`, `Digital Rain`,
    `Mesh gradient (canvas)`, `Generative Wave Lines`, `Cursor Network`, `Starfield Warp`.
  - *Cyber / kinetic-type:* `Glitch Text`, `Decrypt Wipe`, `Cube Words`, `Char Flip 3D`,
    `Stroke Fill`, `Perspective Grid Floor`, `Neon Flicker Sign`.
  - *Organic / soft:* `Blob Morph`, `Blur In`, `Wave Text`, `Gradient Orb`.
  - *Physics:* `Newton's Cradle`, `Gravity Rain Pile`, `Domino Chain`, `Wobble Tower`, `Drag & Toss`.
  - *Hand-made / raw:* `Hand-Drawn Sketch` (rough.js), `Film Grain`, `Self-Drawing Text`.
  - *3D objects:* `DNA Helix`, `Spiral Tube`, `Glowing Knot Halo`, `Edge Dodecahedron`,
    `Swirling particle sphere`, `Displacement Plane`.

> The complete, verifiable signature list lives in **`CATALOG.md` → "Signature palette by
> family"** (every ⭐ effect, grouped by family, with its `id`). Pull from there — it's the full
> 199, not this abbreviated set.

### The signature rule
1. **Every page commits to ≥1 signature effect** as its character (usually the hero bg or the
   headline). A page with zero signatures is the safe rut — reject it.
2. **Rotate the signature.** Do not reuse the previous build's signature (or its whole family).
   If the last site was a shader hero, this one is generative, or physics, or hand-drawn.
3. **Anti-rut check:** if your recent builds all used `fade-up + magnetic + skeleton`, you are in
   the monoculture — deliberately pull a signature from a family you haven't touched lately.
4. **The 3-flavor menu MUST span 3 different families.** Each of the three options draws its
   signature from a *distinct* family, and **at least one must reach a heavy family**
   (`shader` / `3d` / `physics` / `hand-made`). Three flavors whose signatures are all
   canvas-generative, or all text effects, FAIL this rule — that's the convergence trap (the
   `Particle constellation` + `Mesh gradient` + glitch/scramble cluster a test build fell into).
   Pick the family trio *before* writing the menu, e.g. {shader, organic, hand-made} or
   {3d, generative, cyber}. Restrained registers (law firm, dashboard) may make one option
   signature-light, but the other two still span two distinct families.

### Flavor archetypes (use these to build the 3-option menu)
Each archetype = signature family + palette feel + type feel + motion character. To make the §0
menu, pick **3 archetypes from different families that genuinely diverge** and fit the brief
(see rule 4 above — verify the family trio is spread, not clustered):

| Flavor | Signature pull | Palette | Type | Motion |
|---|---|---|---|---|
| **Neon / cyber** | Plasma shader, Glitch Text, Grid Floor | near-black + electric cyan/magenta | techy mono / wide sans | sharp, glitchy |
| **Liquid / organic** | Liquid Metaballs, Blob Morph, Blur In | soft light + gooey gradients | rounded sans | flowing, soft |
| **Editorial / brutalist** | Hand-Drawn Sketch, Text Scramble, Marquee | paper/cream + one ink + red | condensed poster + mono | raw, kinetic |
| **Generative / scientific** | Flow Field, Particle galaxy, Wave Lines | dark + data-viz accents | grotesk + mono | calm, systemic |
| **Synthwave / retro** | Perspective Grid Floor, Starfield Warp, Neon Flicker | sunset purple/orange | retro display | parallax, glow |
| **Kinetic-type** | Cube Words, Char Flip 3D, Decrypt Wipe | high-contrast 2-tone | huge variable sans | type IS the motion |
| **Minimal / Swiss** | one restrained signature, lots of white | off-white + one accent | clean grotesk | tiny, precise |
| **Maximal / drenched** | full-screen shader + bold type | one saturated color owns the page | heavy display | immersive |

### Where to be bold vs. restrained
Spend the boldness where expression is welcome — **hero, section accents, portfolio, campaign,
launch, agency, event**. Stay restrained on **checkout, forms, dense dashboards, long reading**
(§3.4 / §3.5 / §3.7): there a signature distracts or hurts conversion/LCP. "Explore" = use the
full palette in expressive surfaces while keeping task surfaces calm.

> **Proven by the `flavor-lab` demo:** one identical landing built in Neon (plasma shader +
> glitch), Liquid (metaballs + blur-in), and Editorial (rough.js + scramble) — three worlds, zero
> overlap, all from this catalog. That divergence is the target for the §0 flavor menu.

---

## 1. Slot Map (context → effects)

Each slot lists effects by intensity tier. **Pick one per slot** unless noted. Names match the
catalog.

### Hero background (ambient, behind content)
- Subtle: `Aurora gradient`, `Mesh gradient (canvas)`, `Gradient Orb`, `Dot Grid Wave`, `Mesh Drift`
- Medium: `Particle constellation`, `Link constellation`, `Cursor Network`, `Flow Field Streams`
- Bold (WebGL — `ssr:false`): `Vanta 3D net`, `Waves Ocean`, `Fog Aurora`, `3D torus knot`, `Particle Sphere`, `GPU points wave field`, `Plasma flow shader`
- Rule: **one** ambient bg per hero, kept low-contrast behind the text. WebGL = §4 dynamic import.

### Hero headline (the focal text moment — pick ONE)
`Split text reveal`, `Word Reveal`, `Line + Char Mask Reveal`, `Blur In`, `Char Flip 3D`,
`Decrypt Wipe`, `Scramble Headline`. This is the single loud text moment; everything else stays calm.

### Primary CTA / button
`Magnetic button`, `Elastic press`, `Button Shine Sweep`, `Ripple click`, `Droplet Water-Fill Button`

### Secondary button / nav link
`Underline Grow`, `Char Lift`, `Border Draw`, `Menu Morph`

### Section reveal (scroll entrance) — **VARY THESE between sections**
`Reveal on scroll`, `Batch Stagger Reveal`, `Fade-Up Stagger` (AOS), `Zoom-In Reveal`,
`Slide-From-Left Sequence`, `Scroll Clip Reveal`, `Line Mask Reveal`, `Pinned Headline Reveal`,
`Blur In`. Consecutive sections must use *different* ones (see §2.1).

### Card / grid item
Hover: `3D tilt card`, `Spotlight hover`, `3D Flip Card`, `Image Zoom + Overlay` · 
Entrance: `Grid Pop-In`, `Spring Grid`, `Stagger List Reveal`

### Stats / numbers
`Odometer Counter`, `Count-Up on Scroll`, `Morphing Counter`, `Sliding Number Ticker`

### Loading / async (use skeletons, not spinners-in-content)
`Skeleton shimmer`, `Bouncing dots`, `Conic Spinner`, `Breathing Loader`, `Radial Progress Ring`, `Segmented Steps`

### Feedback (success / error / celebrate / empty)
`Success Checkmark`, `Check Pop`, `Toast Slide-In`, `Confetti Burst`, `Fireworks Burst`,
`Like Burst`, `Pulse Radar`

### Image / media treatment
`Image Zoom + Overlay`, `Image Curtain Reveal`, `Scroll Clip Reveal`, `Displacement Wave`

### Text emphasis (inline, sparingly)
`Gradient shimmer`, `Text scramble`, `Typewriter`, `Glitch Text`, `Wave Text`, `Char Lift`

### Marquee / logo strip
`Infinite marquee`, `Seamless Marquee`

### Page-level scroll feel
Smoothness: `Smooth Rail` (Lenis), `Loco Smooth` · Progress: `Scroll progress` · 
Depth: `Parallax Layers`, `Velocity Skew`, `Sticky Stacking Cards`, `Wheel → Horizontal`

---

## 2. Composition Rules

**2.1 Vary section reveals.** Consecutive sections MUST differ: e.g. wipe → stagger → scale →
blur. The uniform fade-up on every section is the #1 "an AI made this" tell.

**2.2 Motion budget — SPEND it.** One *loud focal* moment (usually the hero), yes — but a budget
is meant to be spent, not hoarded. On **expressive** pages (brand, restaurant, campaign, launch,
portfolio) the page must feel **alive**: at least one element in continuous low-key motion at all
times (ambient drift, rising steam, a breathing glow, a slow loop), so it never reads as a static
screenshot. "Restrained" ≠ "still" — it means *one* loud thing, not *zero* living things. Reserve
true stillness for product / checkout / forms / dashboards (§3.4–§3.7), where calm is the point.

**2.3 Consistency where it counts.** All buttons share **one** micro-interaction; all cards
share **one** hover. Vary the *section reveals*, not the *component vocabulary*. Same Save
button must behave the same everywhere.

**2.4 Intensity ∝ importance.** CTA = juicy; body copy = subtle. Match the effect tier to the
element's job.

**2.5 One WebGL hero, max.** WebGL is heavy. One animated 3D/shader background per page; never
stack two. Mid-page ambients (`Film Grain`, `Dot Grid Wave`) used sparingly.

**2.6 Reduced motion is mandatory.** Every effect needs a `prefers-reduced-motion: reduce`
path — typically a crossfade or instant state. Reveal animations must enhance an *already
visible* default (never gate content visibility on a class that may never fire).

**2.7 Performance.** `transform`/`opacity` only for 60fps; lazy-load below-the-fold; one WebGL
context per view; dispose/cleanup on unmount (§4).

**2.8 Aliveness check (anti-flat).** Before shipping an expressive page, ask: *if I took a
screenshot, would I lose anything?* If "no" — it's flat. Entrance animations that fire once +
static decoration = a slideshow, not a living page. The **signature should keep moving** (breathe,
drift, loop, react), not just draw once and freeze. Pick signatures that *live* (shader fields,
particles, steam, flowing gradients, kinetic type) over ones that resolve to a still image, OR
add a dedicated always-on ambient layer. **This is independent of performance** — ambient motion
is facade-loaded + render-on-view, so it costs the Lighthouse score nothing (§5.5). A page that is
"correct" (signature ✓, varied reveals ✓, 95+ ✓) but motionless has failed this rule.

---

## 3. Page Kits

Each kit = a filled slot map + a **section rhythm** (varied reveals, in order). Kits are
starting points; adapt to the real content. Structure assumes Next.js App Router: the `page.tsx`
is a Server Component; each animated section is its own `'use client'` component.

### 3.1 SaaS / Product Landing — *confident, alive, premium*
```
Hero bg       → Aurora gradient (subtle)
Hero headline → Split text reveal            ← the one focal moment
Hero CTA      → Magnetic button
Logos strip   → Seamless Marquee
Features      → reveal: Batch Stagger Reveal + cards 3D tilt card (hover)
How-it-works  → reveal: Scroll Clip Reveal   (different from Features)
Stats         → reveal: Line Mask Reveal + Odometer Counter
Testimonials  → reveal: Zoom-In Reveal
Pricing       → reveal: Fade-Up Stagger; CTA Elastic press
Footer CTA    → reveal: Blur In
Loading       → Skeleton shimmer · page scroll: Smooth Rail
```

### 3.2 Portfolio / Personal — *expressive, characterful*
```
Hero bg       → Particle constellation OR Plasma flow shader (ssr:false)
Hero headline → Decrypt Wipe OR Char Flip 3D
Intro         → reveal: Line Mask Reveal
Work grid     → Grid Pop-In + Image Zoom + Overlay (hover) + custom cursor (Custom Cursor Dot)
Case section  → reveal: Sticky Stacking Cards / Horizontal Track
About         → reveal: Slide-From-Left Sequence
Contact CTA   → Button Shine Sweep
```
Portfolios earn one bold signature (a WebGL hero or glitch text). Use it once.

### 3.3 Marketing / Campaign — *bold, drenched, memorable*
```
Hero bg       → Waves Ocean / Fog Aurora / GPU points wave field (ssr:false)
Hero headline → Word Reveal (big) + Gradient shimmer accent
Sections      → vary hard: Scroll Clip Reveal → Velocity Skew → Pinned Headline Reveal
Interactive   → Cursor Ripple / Pointer Repel / Like Burst
CTA           → Droplet Water-Fill Button
```
Highest motion budget. Still: one hero focal, varied reveals, reduced-motion path.

### 3.4 App UI / Dashboard — *calm, fast, trustworthy* (product register)
```
NO hero WebGL. NO orchestrated page-load. Motion conveys STATE, not decoration.
Data loading  → Skeleton shimmer (not spinners in content)
Async actions → Bouncing dots / Conic Spinner / Radial Progress Ring
Success/error → Success Checkmark / Toast Slide-In
Numbers/KPIs  → Odometer Counter / Count-Up on Scroll (once, on first view)
List/table    → Stagger List Reveal (subtle, fast 150–250ms)
Toggles       → Toggle Switch / Animated Toggle Pill
```
Transitions 150–250ms. Familiarity > surprise. Restraint is the brief.

### 3.5 Content / Blog / Docs — *legible, quiet, focused*
```
Reading       → Scroll progress (top bar) · Smooth Rail
Headings       → reveal: Reveal on scroll (gentle fade-up — consistent here is fine)
Inline accent → Gradient shimmer / Underline Grow (very sparing)
Code/callouts → Copy → Check Morph
Hero (article)→ Line Mask Reveal on title only
```
Lowest motion budget. Motion must never fight reading. (The one place uniform reveals are OK.)

### 3.6 Company Profile / Corporate — *credible, composed, premium-restrained*
```
Hero bg       → Mesh gradient (canvas) / Gradient Orb (calm, low-sat)
Hero headline → Split text reveal (measured, not flashy)
About/Vision  → reveal: Reveal on scroll (gentle)
Stats/Impact  → reveal: Line Mask Reveal + Odometer Counter   ← trust via numbers
Timeline/History → SVG Path Draw (scrub) / Border Draw
Team grid     → Grid Pop-In + subtle 3D tilt card (low max-tilt)
Services      → reveal: Slide-From-Left Sequence
Clients/logos → Seamless Marquee
CTA "Contact" → Magnetic button (subtle)
Loading       → Skeleton shimmer
```
Corporate = trust. Keep WebGL minimal/absent, saturation low, motion measured. Professional
over playful. Variation between sections still applies, but at lower amplitude.

### 3.7 E-commerce — *snappy, product-first, conversion-driven*
```
Hero/promo    → Image Curtain Reveal OR Image Zoom + Overlay (product imagery, not WebGL)
Hero headline → Word Reveal (short, punchy)
Category nav  → Underline Grow / Char Lift
Product grid  → Grid Pop-In (entrance) + Image Zoom + Overlay (hover) + quick badge Pulsing Notification Badge
Add-to-cart   → Like Burst / Check Pop (instant feedback) + cart count Sliding Number Ticker
Sale/urgency  → Gradient shimmer accent / Pulse Radar on deal
Filters/load  → Skeleton shimmer (product cards) · infinite list Stagger List Reveal
Checkout step → Segmented Steps (stepper progress)
Order success → Success Checkmark + Confetti Burst (once)
```
E-commerce motion = **fast feedback**, not spectacle. Every interaction confirms instantly
(add-to-cart, wishlist, filter). Avoid heavy WebGL — it competes with product images and hurts
LCP. Skeletons for every async product load.

---

## 4. Next.js Rules (the wrapper)

The catalog code is vanilla DOM. To use it in Next.js, wrap each effect once with this pattern.

### 4.1 Canonical client-component wrapper
```tsx
'use client'                                   // REQUIRED for any animated effect
import { useRef, useEffect } from 'react'

export function EffectName() {
  const ref = useRef<HTMLDivElement>(null)
  useEffect(() => {
    const el = ref.current
    if (!el) return
    if (window.matchMedia('(prefers-reduced-motion: reduce)').matches) return // §2.6

    // ── paste the effect body from the catalog here, scoped to `el` ──
    // (replace document.querySelector(...) with `el` / el.querySelector(...))

    return () => {
      // REQUIRED cleanup — pick what applies:
      // cancelAnimationFrame(rafId)
      // gsapCtx.revert()                  // if you used gsap.context()
      // ScrollTrigger.getAll().forEach(t => t.kill())
      // renderer.dispose(); renderer.forceContextLoss()   // three.js
      // vantaEffect.destroy()             // Vanta
      // app.destroy(true)                 // PixiJS
      // observer.disconnect()
    }
  }, [])
  return <div ref={ref} className="effect-name" /* effect markup */ />
}
```

### 4.2 SSR-safety (non-negotiable)
- **Never** touch `window`/`document` at module top level — only inside `useEffect` (runs
  client-side only). Otherwise: `ReferenceError: window is not defined` at build/SSR.
- Effects that need DOM measurement run in `useEffect`, after mount.

### 4.3 Heavy / WebGL libs → load client-only
For `three`, `@babylonjs/core`, `pixi.js`, `vanta`, `ogl`, `p5`, `matter-js`, `cannon-es`,
`tsparticles`, `curtainsjs` — never SSR a canvas. Two options:

```tsx
// Option A: dynamic import INSIDE useEffect (keeps the wrapper a normal client component)
useEffect(() => {
  let renderer: any
  ;(async () => {
    const THREE = await import('three')
    // ... build scene on `ref.current`, store renderer for cleanup
  })()
  return () => renderer?.dispose?.()
}, [])

// Option B: next/dynamic with ssr:false for the whole component
import dynamic from 'next/dynamic'
const Hero3D = dynamic(() => import('./Hero3D'), { ssr: false, loading: () => <Skeleton/> })
```
Prefer a `loading:` skeleton so it never flashes an empty box (same lesson as the gallery).

### 4.4 npm imports, not CDN globals
The catalog code uses window globals (`THREE`, `gsap`, `PIXI`…). In Next.js, import from npm:

| Catalog global | Next.js import |
|---|---|
| `THREE` | `import * as THREE from 'three'` |
| `gsap` | `import gsap from 'gsap'` |
| ScrollTrigger/Flip/… | `import { ScrollTrigger } from 'gsap/ScrollTrigger'` → `gsap.registerPlugin(ScrollTrigger)` in effect |
| `PIXI` | `import * as PIXI from 'pixi.js'` |
| `Matter` | `import Matter from 'matter-js'` |
| `BABYLON` | `import * as BABYLON from '@babylonjs/core'` |
| `anime` | `import anime from 'animejs'` |
| `Two` | `import Two from 'two.js'` |
| `CANNON` | `import * as CANNON from 'cannon-es'` |
| Vanta | `import NET from 'vanta/dist/vanta.net.min'` (default = the effect; needs `THREE` passed in) |
| Lenis | `import Lenis from '@studio-freight/lenis'` |
| Splitting / SplitType / Typed / Vivus | default import from `splitting` / `split-type` / `typed.js` / `vivus` |
| Lottie | `import lottie from 'lottie-web'` |

(This mapping is proven in the `design-library-gallery` Vite app's `src/libs.js`.)

### 4.5 GSAP + ScrollTrigger in Next.js
Register plugins inside `useEffect` (client only). Use `gsap.context(() => {...}, ref)` and
`ctx.revert()` in cleanup — this auto-kills tweens + ScrollTriggers and survives React
re-mounts (Strict Mode double-invoke in dev).

### 4.6 Server vs Client split
Keep `page.tsx` a Server Component (fast, SEO). Make **only** the animated sections client
components (`'use client'`) and import them in. Don't mark the whole page client.

---

## 5. Worked examples (one per category)

### 5.1 Button — Magnetic button (vanilla → client)
```tsx
'use client'
import { useRef, useEffect } from 'react'
export function MagneticButton({ children }: { children: React.ReactNode }) {
  const ref = useRef<HTMLButtonElement>(null)
  useEffect(() => {
    const b = ref.current; if (!b) return
    const area = b.parentElement!; const s = 0.4
    const move = (e: MouseEvent) => {
      const r = b.getBoundingClientRect()
      b.style.transform = `translate(${(e.clientX-(r.left+r.width/2))*s}px,${(e.clientY-(r.top+r.height/2))*s}px)`
    }
    const leave = () => { b.style.transform = '' }
    area.addEventListener('mousemove', move); area.addEventListener('mouseleave', leave)
    return () => { area.removeEventListener('mousemove', move); area.removeEventListener('mouseleave', leave) }
  }, [])
  return <button ref={ref} className="mag-btn">{children}</button>
}
```

### 5.2 Scroll reveal — GSAP Batch Stagger (with cleanup)
```tsx
'use client'
import { useRef, useEffect } from 'react'
export function StaggerReveal({ children }: { children: React.ReactNode }) {
  const ref = useRef<HTMLDivElement>(null)
  useEffect(() => {
    const el = ref.current; if (!el) return
    let ctx: any
    ;(async () => {
      const { gsap } = await import('gsap')
      const { ScrollTrigger } = await import('gsap/ScrollTrigger')
      gsap.registerPlugin(ScrollTrigger)
      ctx = gsap.context(() => {
        ScrollTrigger.batch('.rev-item', {
          onEnter: b => gsap.to(b, { y: 0, opacity: 1, stagger: 0.1, duration: 0.7, ease: 'power3.out' }),
          start: 'top 85%',
        })
      }, el)
    })()
    return () => ctx?.revert()
  }, [])
  return <div ref={ref}>{children}</div>  // .rev-item default: opacity:1 in CSS, animate FROM hidden
}
```

### 5.3 Hero WebGL — three.js, client-only via next/dynamic
```tsx
// Hero3D.tsx  ('use client')
'use client'
import { useRef, useEffect } from 'react'
export default function Hero3D() {
  const ref = useRef<HTMLCanvasElement>(null)
  useEffect(() => {
    let raf = 0, renderer: any
    ;(async () => {
      const THREE = await import('three')
      const canvas = ref.current!; const w = canvas.clientWidth, h = canvas.clientHeight
      renderer = new THREE.WebGLRenderer({ canvas, alpha: true, antialias: true })
      // ...scene/camera/mesh from catalog '3D torus knot'...
      const loop = () => { /* rotate; renderer.render(...) */ raf = requestAnimationFrame(loop) }
      loop()
    })()
    return () => { cancelAnimationFrame(raf); renderer?.dispose?.() }
  }, [])
  return <canvas ref={ref} className="hero-canvas" />
}
// page.tsx (Server Component):
import dynamic from 'next/dynamic'
const Hero3D = dynamic(() => import('./Hero3D'), { ssr: false, loading: () => <div className="hero-skeleton" /> })
```

### 5.4 Text — GSAP Split text reveal
```tsx
'use client'
import { useRef, useEffect } from 'react'
export function SplitReveal({ text }: { text: string }) {
  const ref = useRef<HTMLHeadingElement>(null)
  useEffect(() => {
    const el = ref.current; if (!el) return
    let ctx: any
    ;(async () => {
      const { gsap } = await import('gsap')
      el.innerHTML = [...text].map(c => `<span>${c === ' ' ? '&nbsp;' : c}</span>`).join('')
      ctx = gsap.context(() => {
        gsap.from(el.querySelectorAll('span'), { yPercent: 120, opacity: 0, duration: 0.8, ease: 'back.out(1.7)', stagger: 0.04 })
      }, el)
    })()
    return () => ctx?.revert()
  }, [text])
  return <h1 ref={ref} className="split-head">{text}</h1>  // text stays as accessible fallback
}
```

### 5.5 Loading — Skeleton shimmer (pure CSS, simplest, SSR-safe)
```tsx
// No effect hook needed — CSS only, renders on the server fine.
export function Skeleton() {
  return <div className="skeleton" aria-busy="true" aria-live="polite" />
}
/* globals.css:
.skeleton{position:relative;overflow:hidden;background:#1b1b27;border-radius:8px;height:13px}
.skeleton::after{content:"";position:absolute;inset:0;transform:translateX(-100%);
  background:linear-gradient(90deg,transparent,#ffffff17,transparent);animation:skel 1.4s infinite}
@keyframes skel{to{transform:translateX(100%)}}
@media (prefers-reduced-motion:reduce){.skeleton::after{animation:none}} */
```

---

## 5.5 Performance doctrine — 95+ mobile, without sacrificing animation

Non-negotiable target: **Lighthouse mobile Performance ≥ 95**, animation fully intact. The two
only conflict if the animation sits in the critical render path. Keep it out and you get both —
proven: a WebGL hero landing went **54 → 99 mobile** with zero loss of motion.

**Core principle:** the critical path is HTML + CSS; animation is a *deferred enhancement*. The
gate measures the **loaded** page, so a rich animation that loads after interaction **never counts
against the score**. Be as ambitious with motion as you want — just sequence it. The gate
constrains the critical path, NOT how alive the page is.

> **Anti-pattern — animating timidly to "feel safe" about the score.** The single most common way
> this doctrine gets misused: holding back the animation because "we need 95+." Wrong. The gate
> measures load; the animation loads after interaction and is invisible to it. A static-but-correct
> page that scores 98 has *wasted the budget*, not protected the score. If a build feels plain,
> the cause is timid choices, never the perf target. Spend the motion budget (§2.2 / §2.8) — the
> facade architecture already guarantees the score holds.

### Pick the technique by CONTENT (lightest that fits)
| Content | Technique | Why |
|---|---|---|
| abstract / generative / geometric | shader (**OGL ~8KB**, not three.js ~170KB) · canvas2D · CSS | a few KB → infinite frames |
| photoreal / real product / un-renderable | **`frame-scrub`** image sequence (AVIF) | lighter CPU/TBT than a GLTF; control bytes via frame count (24–48) + DIMENSIONS |
| ambient loop (no scrub) | muted autoplay `<video>` | best compression for footage |
| genuinely needs three.js (models, big scenes) | three.js via **OffscreenCanvas + Worker** | renders off the main thread → TBT ~0 |

**Never** `<video>` + `currentTime` scrub on mobile — it janks (that's exactly why Apple ships frames).

### Five load-perf patterns (every animated hero)
1. **Static poster first.** A CSS / image / frame-0 poster paints instantly → it's the LCP, not the
   canvas. The live animation fades in over it.
2. **Facade — load on interaction.** Import the animation lib + assets on the first
   scroll / pointer / touch, never on mount. Off the load/TBT critical path; Lighthouse (which
   never interacts) doesn't pay; a real user gets it the instant they engage.
3. **Self-host fonts** (`next/font`), not a `<link>` to fonts.googleapis.com (big FCP win).
4. **Reveals = IntersectionObserver + CSS**, not a scroll library.
5. **Run only when visible** — rAF paused off-screen + on `visibilitychange`; DPR ≤ 1.5; scrubs
   render on scroll-change only.

### Adaptive fallback (heavy effects only) — "if it can't animate well, ship the picture"
**Scope: heavy effects only** — WebGL/shader, particle canvas, large video/scrub. On data-savers or
low-spec devices, skip the heavy animation and keep the static poster/image; the poster already looks
finished, so the degradation is invisible and the score *rises* (nothing heavy loads).
**Light transform/opacity motion — calm dashboards, micro-transitions, reveals — does NOT need this.**
Those are GPU-cheap on any device; their only fallback is the reduced-motion path (§2.6). Don't gate
ordinary UI motion on device tier — that's over-engineering.
```js
function canAnimate(){
  if (matchMedia('(prefers-reduced-motion: reduce)').matches) return false;
  const c = navigator.connection;
  if (c && (c.saveData || /(^|-)2g$/.test(c.effectiveType || ''))) return false;
  if ((navigator.deviceMemory ?? 8) < 4) return false;          // weak RAM
  if ((navigator.hardwareConcurrency ?? 8) < 4) return false;   // weak CPU
  return true;   // shader heroes: also confirm a webgl2 context before committing
}
// if (!canAnimate()) → keep the poster, never import the animation. else → facade-load on interaction.
```

### Performance is a design PRACTICE, not a design-time gate
At design time your job is **clean, performance-conscious code** — bake in the patterns above
(facade, static poster, deferral, render-on-view, light libs, `canAnimate` fallback). That's the
deliverable. **Do NOT block the design on a hard Lighthouse number, and never flatten the
animation to chase a score.** A live page's real score depends on the real environment (CDN,
network, hosting, caching) that doesn't exist yet — so the strict measurement is a **later / live
check**, re-evaluated when it ships, not a gate the design must clear.

So: design ships clean perf-aware code → *then*, on the live build, run Lighthouse to verify and
tune. The check is available but **optional and informational**, not a pass/fail blocker:
```jsonc
// package.json — run when live to verify; informational, NOT a build blocker
"gate": "lighthouse $URL --form-factor=mobile --only-categories=performance --quiet --chrome-flags=--headless=new --output=json --output-path=lh.json && node -e \"console.log('mobile perf:',Math.round(require('./lh.json').categories.performance.score*100))\""
```
(Lighthouse cold runs are noisy — run against a warm server, take the median of a few, and judge in
the real deployed environment.) The aliveness rules (§2.2 / §2.8) always win over the number: a
page should feel alive first; clean perf practices make that essentially free, and the live number
is tuned afterward.

---

## 5.6 Transition craft — make it feel *expensive*

The premium feeling lives in the **in-between**, not the static frame. A site reads as expensive
because every state change is *resolved* — nothing pops, everything eases, motion has weight and
intention. Cheap = instant state changes + one-property fades. Expensive = layered, physical,
origin-aware transitions on **every** interaction. Apply this to every build, not just heroes.

### Tune every transition by these axes
- **Duration** — feedback short (120–220ms), reveals/spatial longer (300–600ms). Never linger.
- **Easing** — ease-OUT for entrances, ease-IN for exits, **spring** for anything physical. Never
  linear (except loops/scrubs). Standardize ONE curve scale across the whole UI.
- **Distance** — *less travel = more expensive.* Big jumps feel cheap; move things a little.
- **Blur** — a touch of blur on fast motion / focus changes reads as depth and money. Sparingly.
- **Scale** — scale+fade beats fade alone; scale *from the interaction origin*.
- **Spring & momentum** — a hair of overshoot on press / drag / snap (settle, don't stop).
- **Origin / direction awareness** — open from where the user clicked; slide in the direction of
  travel; the active-tab indicator moves *toward* the new tab. Motion that respects cause feels smart.
- **Choreography / stagger** — never reveal a group at once; stagger 30–80ms. The sequence is the craft.
- **Shared-element / layout (FLIP)** — when something moves / resizes / reorders, *animate the layout
  change*, don't cut. This is the single biggest "expensive" tell.

### Premium transition per element (animate the in-between, everywhere)
- **Buttons / CTAs** — layered, not one thing: bg sweep/fill + label shift + icon slide-in + spring
  press (scale .97) + shadow bloom. Magnetic on hero CTAs.
- **Cards** — hover = lift (−4…−6px) + shadow bloom + inner/image scale (~1.03) + a content micro-shift.
  Not just a border-color change.
- **Modals / sheets / popovers** — scale-from-origin (the trigger) + fade + backdrop blur-in; content
  staggers in; exit reverses. Never a hard fade.
- **Menus / dropdowns** — open from the trigger corner (`transform-origin`), items stagger, slight spring.
- **Tabs / segmented / toggles** — the active indicator is a **shared element that SLIDES** between
  options (FLIP / transform); panel content cross-fades in the travel direction.
- **Lists / grids** — add / remove / reorder animate via **FLIP**; entrance staggers; deletion collapses.
  (The Linear / Vercel signature.)
- **Inputs / forms** — focus ring eases + label floats; clear = dissolve; success = check-draw;
  error = a short shake + ring shift.
- **Numbers / prices** — roll / odometer or blur-swap. **Never** an instant text change.
- **Swapped text / labels** — crossfade + slight Y shift (or blur-swap), measured.
- **Images / media** — reveal via clip/scale, lazy fade-in (no pop), ken-burns on hover.
- **Navigation / route or view changes** — the **View Transitions API** for shared-element morphs
  between pages/states; native-app-grade. Progressive enhancement.
- **Tooltips / toasts** — timed (delay-in, quick-out), slide+fade from origin, never instant.

### Toolbox (cheap to build, expensive to feel)
- **CSS transitions** for hover/focus/active — ONE `--ease` + a duration scale
  (`--t-fast:140ms; --t:240ms; --t-slow:480ms`). Consistency is half the premium feel.
- **Spring without a lib** — `transition-timing-function: linear(...)` spring curves, or a keyframe
  with a small overshoot; or a ~1KB spring helper for press/drag.
- **FLIP** — measure first/last rect → invert → play; for reorder / resize / shared-element. The one
  technique that most separates expensive from cheap.
- **View Transitions API** — `document.startViewTransition(...)` + `view-transition-name` on shared
  elements, for state/route morphs. Feature-detect; fall back to a crossfade.
- **Origin-aware** — set `transform-origin` / a CSS var from pointer/click coords so things open and
  scale from where the user acted.
- Respect `prefers-reduced-motion` (crossfade/instant) and stay perf-conscious (transform/opacity, §5.5).

> The bar: if a reviewer can tell where one state ends and the next begins *without* a transition,
> it's not finished. Resolve every change.

---

## 5.7 Modern transition tech — native, zero-lib

Three browser-native APIs that deliver premium §5.6 motion with **no library** and (mostly) no JS.
All three are **progressive enhancement**: content works without them, they enrich where supported.

### A. CSS Scroll-Driven Animations (`animation-timeline`)
Reveals, parallax, and progress bars driven by scroll **on the compositor** — no IntersectionObserver,
no scroll listener, no GSAP. The lightest possible scroll motion. Support: Chromium 115+, Safari 26+,
Firefox behind a flag — so **gate it and keep content visible by default**.
```css
/* reveal as it enters the viewport — visible by default; enhances only where supported */
.reveal{opacity:1}
@supports (animation-timeline: view()){ @media (prefers-reduced-motion: no-preference){
  .reveal{animation:sda-rise linear both; animation-timeline:view(); animation-range:entry 0% entry 45%}
}}
@keyframes sda-rise{from{opacity:0;transform:translateY(30px)}to{opacity:1;transform:none}}

/* page scroll-progress bar — no JS */
.progress{transform-origin:left;transform:scaleX(0);animation:sda-grow linear;animation-timeline:scroll(root)}
@keyframes sda-grow{to{transform:scaleX(1)}}
```
`view()` = element-vs-viewport progress (reveal/parallax). `scroll()` = container scroll progress (bars).

### B. View Transitions API (`document.startViewTransition`)
The browser snapshots before/after the DOM change and crossfades — or **morphs a shared element**
(same `view-transition-name` on the old & new node → it animates position/size between states).
Native-app feel for tabs, list→detail, filtering, route changes.
```js
function update(){ /* mutate the DOM / set state */ }
if (document.startViewTransition) document.startViewTransition(update); else update();
```
```css
::view-transition-old(root),::view-transition-new(root){animation-duration:.32s}
.thumb{view-transition-name:hero}   /* same name on the detail view → morphs */
```
**Next.js App Router page transitions:** simplest is the `next-view-transitions` package (wrap the
app in `<ViewTransitions>`, use its `<Link>`). For same-page state (tabs, filters, sort) use the
native `startViewTransition` call above directly — no package. Gate the `::view-transition`
animations under reduced-motion, or skip `startViewTransition` entirely when reduced.

### C. Theme-switch circular reveal
The on-trend light⇄dark toggle where the new theme wipes in as a circle from the click point —
View Transitions + a clip-path animation, ~12 lines, no lib:
```js
function toggleTheme(e){
  const set = () => document.documentElement.classList.toggle('dark')
  if (!document.startViewTransition || matchMedia('(prefers-reduced-motion: reduce)').matches) return set()
  const x = e.clientX, y = e.clientY
  const r = Math.hypot(Math.max(x, innerWidth - x), Math.max(y, innerHeight - y))
  document.startViewTransition(set).ready.then(() =>
    document.documentElement.animate(
      { clipPath: [`circle(0 at ${x}px ${y}px)`, `circle(${r}px at ${x}px ${y}px)`] },
      { duration: 500, easing: 'ease-in-out', pseudoElement: '::view-transition-new(root)' }))
}
```
```css
::view-transition-old(root),::view-transition-new(root){animation:none;mix-blend-mode:normal}
```

> All three degrade cleanly: no support → content is simply static/instant. Never gate visibility
> or function on them (§2.6). Concrete runnable versions live in `galeri.html` (category
> *UI Transitions* / *Scroll-driven*).

---

## 6. Checklist before shipping a page
- [ ] 3 flavors offered and one chosen BEFORE building — §0 step 0
- [ ] Page commits to ≥1 **signature** effect, rotated (not the safe spine only) — §0.5
- [ ] Page type identified → kit chosen, then adapted to real content
- [ ] Section reveals **varied** (not all fade-up) — §2.1
- [ ] Expressive page feels **ALIVE** — at least one continuous ambient motion, not just one-shot entrances + static decor (the screenshot test) — §2.2 / §2.8
- [ ] **No instant state changes** — every hover / active / open / close / swap eases (the "expensive" test) — §5.6
- [ ] ONE consistent easing + duration scale across the whole UI; hover states are layered (≥2 things move) — §5.6
- [ ] Open/close from origin · tab indicators slide (shared element) · lists FLIP add/remove · numbers roll — §5.6
- [ ] One focal motion (hero); rest restrained — §2.2
- [ ] Buttons/cards consistent; only reveals vary — §2.3
- [ ] ≤1 WebGL background; heavy libs `ssr:false` with a loading skeleton — §2.5 / §4.3
- [ ] Every effect: `'use client'`, cleanup on unmount, no top-level `window` — §4
- [ ] `prefers-reduced-motion` path on every animation — §2.6
- [ ] npm imports, not CDN globals — §4.4
- [ ] Technique matches the content (procedural→shader/OGL · photoreal→frame-scrub · ambient→video) — §5.5
- [ ] Animated heroes: static poster paints first; animation facade-loaded on interaction — §5.5
- [ ] **Heavy effects only** (WebGL/particle/video): `canAnimate()` fallback — save-data / low-spec → static image. Light transform/opacity UIs need only the reduced-motion path (§2.6), not device-gating — §5.5
- [ ] Fonts self-hosted (`next/font`); reveals are IO+CSS (no scroll lib) — §5.5
- [ ] Perf **practices** baked in (facade · poster · defer · render-on-view · light libs · `canAnimate` fallback) — the design-time deliverable. Lighthouse is a later/live check, NOT a design gate — §5.5
