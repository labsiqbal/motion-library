# CATALOG.md — design-library effects index (all 202)

The **AI-facing index** of every effect in the library. Use it to discover, verify, and pick —
then grab the runnable code from **`galeri.html`** (search the effect's `id` in `data-fx="<id>"`)
or the Vite app `design-library-gallery/`. This file is the *map*; `galeri.html` is the *code*.

Each entry: **Name** `id` — *istilah* · when-to-use `[library]`. A ⭐ marks a **signature**
effect (the long-tail that gives a page character — rotate these per PLAYBOOK §0.5); unmarked
entries are **workhorses** (the safe spine).

> Counts: 217 effects · 131 signature ⭐ · 86 workhorse · across 29 libraries.

---

## Signature palette by family (for the §0 flavor menu)

When building the 3-flavor menu, pull each flavor's signature from a **different family** below,
and make ≥1 flavor reach a heavy family (shader / 3d / physics / hand-made).

- **shader** — Particle Sphere, Vanta 3D net, Cube Wave Grid, Morphing Point Cloud, Plasma flow shader, GPU points wave field, Particle galaxy spiral, Repelling points grid, Swirling particle sphere, Fresnel glow sphere, Particle Fountain, Displacement Wave, Orbiting Swarm, Hue-Rotate Pulse, Pointer Repel, Bloom Glow Text, Wave Field, Waves Ocean, Fog Aurora, Plasma Triangle, Raymarch Blob, GPU Particles, Noise Field Plane, Fresnel Box, Noise Blob, Starfield, Displacement Plane, Ripple Plane
- **3d** — 3D torus knot, Wavy Plane, Breathing Icosahedron, Glowing Knot Halo, Edge Dodecahedron, Spiral Tube, Torus Knot Glow, Glow Icosphere, Orbiting Instances, Edged Polyhedra, DNA Helix, Equalizer Ring, Tumbling Ring, Torus Aura, Pita Mengalir, Bentang Bergulir, Bola Kaca, Awan Tetrahedron, Cincin Giro, Bola Kubus, Scroll-Dolly 3D World, Pinned Product Scrub
- **generative** — Mesh gradient (canvas), Particle constellation, Starfield Warp, Link constellation, Flow Field Drift, Generative Wave Lines, Morphing Polygon, Animated Gradient, Confetti Burst, Themed Snowfall, Flow Field Streams, Liquid Metaballs, Cursor Network
- **cyber** — Glitch Text, Cube Words, Decrypt Wipe, Char Flip 3D, Neon Flicker Sign, Perspective Grid Floor, Digital Rain
- **organic** — Aurora gradient, Floating blobs, Blur In, Wave Text, Blob Morph, Gradient Orb, Coin Flip, Mesh Drift
- **physics** — Gravity Rain Pile, Newton's Cradle, Drag &amp; Toss, Hyper Bounce, Wobble Tower, Cube Stack Drop, Bounce Box, Domino Chain, Constraint Pendulum
- **hand-made** — Film Grain, Self-Drawing Text, Hand-Drawn Sketch, Signature Draw
- **kinetic-type** — Text scramble, Stroke Fill, Elastic letters, Char Index Reveal, Per-Word Rotate-In, Typewriter Phrases, Line + Char Mask Reveal, Elastic Char Bounce, Scramble Headline, Morphing Counter
- **micro** — Grid wave stagger, Spring Grid, Spring Settle Card, Keyframe Pulse, Stagger Rise, Mix Morph
- **scroll** — Smooth Rail, Fade-Up Stagger, Zoom-In Reveal, Slide-From-Left Sequence, Parallax Layers, Loco Smooth, Loco Parallax
- **feedback** — Confetti Burst, Fireworks Burst
- **hero** — Dot Grid Wave, Cursor Ripple, SVG line draw, SVG Path Morph, Timeline Shapes, Origami Folding Card, Rotating Gallery Cube

---

## Full index (by category)

### Micro-interaction (36)

- · **Magnetic button** `magnetic` — *magnetic hover / cursor-following* · premium · playful — CTA hero, portfolio. Hindari: form padat. `[vanilla]`
- · **3D tilt card** `tilt` — *3d tilt / pointer perspective* · modern · depth — product card, showcase. Hindari: konten teks panjang. `[vanilla]`
- · **Ripple click** `ripple` — *material ripple / ink* · tactile · responsif — tombol, list item. Cocok hampir di mana saja. `[vanilla]`
- · **Spotlight hover** `spotlight` — *cursor spotlight / radial glow* · premium · dark-UI — pricing card, feature grid. `[vanilla]`
- · **Animated gradient border** `gborder` — *conic gradient border / rotating glow* · futuristik · berani — highlight card, badge "baru". `[vanilla]`
- · **Elastic press** `elastic` — *squash & stretch / elastic ease* · playful · juicy — CTA utama, game-y UI. Butuh GSAP buat ease elastic. `[gsap]`
- · **Button Shine Sweep** `btn-shine` — *shine sweep / specular gleam / hover gloss* · premium · CTA & pricing buttons · hindari di tombol sekunder `[vanilla]`
- · **Border Draw** `border-draw` — *stroke-dashoffset draw / outline trace / SVG line draw* · elegan, teknikal · kartu & ikon fitur · hindari kalau radius berubah `[vanilla]`
- · **Custom Cursor Dot** `cursor-dot` — *custom cursor / trailing ring / pointer follower* · playful, terarah · portfolio & hero interaktif · hindari di mobile/form `[vanilla]`
- · **Like Burst** `like-burst` — *particle burst / confetti pop / like explosion* · dopamine, reward · like/upvote/save · hindari aksi destruktif `[vanilla]`
- · **Toggle Switch** `toggle-switch` — *toggle / switch / squish slide* · tactile, jelas · setting on/off & dark mode · hindari aksi non-binary `[vanilla]`
- · **3D Flip Card** `flip-card` — *flip card / 3D rotateY / backface reveal* · playful, informatif · profil tim & fitur dua-sisi · hindari konten yang harus terbaca `[vanilla]`
- · **Image Zoom + Overlay** `img-zoom` — *ken-burns zoom / hover overlay / caption reveal* · editorial, rapi · galeri & kartu produk · hindari kalau caption harus selalu tampak `[vanilla]`
- · **Copy → Check Morph** `copy-check` — *state morph / icon swap / copy feedback* · memuaskan, jelas · tombol copy code/link · hindari kalau copy bisa gagal diam-diam `[vanilla]`
- · **Grid Pop-In** `grid-pop` — *staggered grid burst* · playful · loading galeri/dashboard · hindari di list panjang `[gsap]`
- · **Flip Layout Swap** `flip-swap` — *FLIP state transition* · satisfying · grid↔list toggle · hindari kalau state sering berubah `[gsap]`
- · **Orbit Path** `orbit-path` — *MotionPath follow* · hypnotic · loader, hero accent · hindari sebagai elemen fungsional `[gsap]`
- · **Odometer Counter** `odometer` — *tween-driven count up* · credible · stats block, KPI · hindari angka real-time `[gsap]`
- · **Drag &amp; Snap-Back** `drag-snap` — *inertia draggable* · tactile · swipe card, reorder · hindari kalau drag punya konsekuensi destruktif `[gsap]`
- ⭐ **Grid wave stagger** `anime-grid-wave` — *grid stagger / ripple-from-center* · playful · loaders, dashboards · anime.js v3 (~16KB) — stagger({grid,from}) `[anime.js]` _(micro)_
- ⭐ **Spring Grid** `motion-spring-grid` — *spring stagger reveal* · playful · grid/dashboard load-in · Motion One (~18kb) `[Motion One]` _(micro)_
- ⭐ **Confetti Burst** `tsp-confetti-burst` — *emitter celebration burst* · celebratory · success/checkout/win · tsParticles (~80kb) `[tsParticles]` _(generative)_
- · **Stagger List Reveal** `waapi-stagger-list` — *staggered reveal · element.animate* · terstruktur · onboarding / list pertama muncul `[WAAPI]`
- · **Morph Card Loop** `waapi-morph-card` — *keyframe morph* · playful · empty state / hero accent `[WAAPI]`
- · **Equalizer Bars** `equalizer-bars` — *audio equalizer / VU bars* · alive · audio/media UI, "live" status `[vanilla]`
- · **Menu Morph** `menu-morph` — *hamburger-to-close morph* · crisp · nav toggle, mobile header `[vanilla]`
- · **Underline Grow** `underline-grow` — *directional underline wipe* · elegan · nav links, footer menu `[vanilla]`
- · **Drag-Rotate Card** `drag-rotate-card` — *observer drag / 3D tilt* · tactile · product showcase `[gsap]`
- · **Toss &amp; Settle** `toss-inertia` — *physics2D / inertia bounce* · playful · success ping `[gsap]`
- · **Morph Loader** `morph-loader` — *sequenced dots-to-bar* · calm · loading state `[gsap]`
- ⭐ **Spring Settle Card** `spring-settle-card` — *spring physics / drag-to-settle* · playful · kartu interaktif · Popmotion (~12kb) `[Popmotion]` _(micro)_
- ⭐ **Keyframe Pulse** `keyframe-pulse` — *keyframes / multi-stop loop* · hypnotic · loader / beacon · Popmotion (~12kb) `[Popmotion]` _(micro)_
- ⭐ **Stagger Rise** `stagger-rise` — *staggered reveal / cascade* · crisp · list / menu · Popmotion (~12kb) `[Popmotion]` _(micro)_
- ⭐ **Mix Morph** `mix-morph` — *value mixer / interpolation* · organic · brand mark / idle shape · Popmotion (~12kb) `[Popmotion]` _(micro)_
- · **Pulsing Notification Badge** `notif-badge` — *badge ping · attention dot* · alert-friendly · navbars/inbox `[vanilla]`
- · **Sliding Number Ticker** `number-ticker` — *number ticker · odometer roll* · satisfying-counter · stats/metrics `[vanilla]`

### Scroll (28)

- · **Reveal on scroll** `reveal` — *scroll reveal / fade-up stagger* · clean · editorial — section masuk viewport. IntersectionObserver, no lib. `[vanilla]`
- · **Parallax layers** `parallax` — *parallax depth / multi-layer* · imersif · spasial — hero berlapis. Di sini pakai kursor (teknik sama). `[vanilla]`
- · **Scroll progress** `progress` — *scroll progress / reading indicator* · fungsional · clean — artikel, long page. `[vanilla]`
- · **Count-Up on Scroll** `scroll-countup` — *count up · animated stats · number ticker · IntersectionObserver* · bangga, faktual · landing stats / metrics band `[vanilla]`
- · **Scroll Clip Reveal** `scroll-clip` — *clip-path reveal · scroll-linked mask · image wipe · scrub* · sinematik · hero image / case study `[vanilla]`
- · **Sticky Stacking Cards** `scroll-stack` — *sticky stack · card stack · pinned cards · position:sticky* · rapi, naratif · proses / langkah-langkah `[vanilla]`
- · **Velocity Skew** `scroll-skew` — *scroll velocity · skew · momentum · inertia distortion* · enerjik, playful · list panjang / portofolio `[vanilla]`
- · **Wheel → Horizontal** `scroll-horizontal` — *horizontal scroll · wheel hijack · sideways gallery* · galeri, showcase · portofolio / produk `[vanilla]`
- · **Line Mask Reveal** `scroll-textmask` — *text mask · scroll fill · line reveal · highlight wipe* · puitis, premium · manifesto / about `[vanilla]`
- · **Pinned Headline Reveal** `gsap-pin-headline` — *pin · scrub · char stagger · headline build* · sinematik · hero / opening · hindari di teks panjang `[gsap]`
- · **Parallax Layers (scrub)** `gsap-parallax-layers` — *parallax · depth · multi-layer scrub* · imersif · hero / storytelling · hindari saat butuh teks tajam `[gsap]`
- · **Batch Stagger Reveal** `gsap-batch-reveal` — *ScrollTrigger.batch · stagger · enter reveal* · rapi · galeri / fitur grid · hindari kalau item &lt; 4 `[gsap]`
- · **Horizontal Track (scrub)** `gsap-horizontal-track` — *pin · horizontal scroll · scrub x* · showcase · portofolio / produk · hindari di mobile sempit `[gsap]`
- · **SVG Path Draw (scrub)** `gsap-path-draw` — *stroke-dashoffset · line draw · scroll scrub* · teknis · diagram / proses · hindari di path super panjang `[gsap]`
- · **Scale + Spin + Color** `gsap-scale-spin` — *scrub transform · rotate · color tween* · tegas · CTA / aksen · hindari kalau sekitarnya ramai `[gsap]`
- ⭐ **Smooth Rail** `lenis-smooth-rail` — *smooth scroll / lerp momentum* · cair & mewah · long-form landing · Lenis (~8kb) `[Lenis]` _(scroll)_
- ⭐ **Fade-Up Stagger** `aos-fade-up-stagger` — *animate on scroll / fade-up* · renyah · daftar fitur, timeline · AOS (~14kb, normal pakai page-scroll) `[AOS]` _(scroll)_
- ⭐ **Zoom-In Reveal** `aos-zoom-in` — *animate on scroll / zoom-in* · punchy · galeri, kartu produk · AOS (~14kb) `[AOS]` _(scroll)_
- ⭐ **Slide-From-Left Sequence** `sr-slide-left-seq` — *reveal on scroll / origin-left* · tegas & berurutan · langkah proses · ScrollReveal (~10kb) `[ScrollReveal]` _(scroll)_
- ⭐ **Parallax Layers** `lenis-parallax-layers` — *smooth scroll + parallax depth* · sinematik · hero, storytelling · Lenis (~8kb) `[Lenis]` _(scroll)_
- ⭐ **Loco Smooth** `loco-smooth` — *smooth / inertia scroll* · premium · landing body / editorial · Locomotive (~20kb) `[Locomotive]` _(scroll)_
- ⭐ **Loco Parallax** `loco-parallax` — *scroll-speed / depth parallax* · cinematic · hero / story section · Locomotive (~20kb) `[Locomotive]` _(scroll)_
- ⭐ **Pinned Product Scrub** `pinned-product-scrub` — *apple-style product scrub / pinned 3D reveal / scroll-rotate* · premium · sinematik — product hero, launch page · komposisi three.js + ScrollTrigger pin+scrub (± Lenis) `[three.js]` _(3d)_
- · **Frame Sequence Scrub** `frame-scrub` — *image-sequence scrub / apple-style frame scrub / photoreal turntable* · premium · sinematik — hero produk photoreal yang ga bisa di-shader · paling ringan di CPU (cuma drawImage); kontrol bytes via AVIF + jumlah frame + dimensi `[vanilla]`
- ⭐ **Scroll Reveal (native)** `sda-reveal` — *CSS scroll-driven / animation-timeline:view() / no-JS reveal* · modern, ringan · reveal saat masuk viewport — zero JS/IO, jalan di compositor · Chromium/Safari; fallback: tampil `[vanilla]` _(scroll)_
- · **Scroll Progress Bar (native)** `sda-progress` — *animation-timeline:scroll() / reading progress* · techy, ringan · progress baca artikel/halaman, no scroll listener `[vanilla]`
- ⭐ **Parallax (native)** `sda-parallax` — *scroll-driven parallax / view()* · sinematik, ringan · section depth, murni CSS `[vanilla]` _(scroll)_
- · **Image Clip Reveal (native)** `sda-clip` — *scroll-driven clip-path / image wipe / view()* · editorial, ringan · reveal banner/gambar saat masuk `[vanilla]`

### Text (25)

- ⭐ **Text scramble** `scramble` — *text scramble / decode / glitch-in* · techy · futuristik — heading hero, judul section. `[vanilla]` _(kinetic-type)_
- · **Typewriter** `typewriter` — *typewriter / typing rotator* · naratif · ramah — tagline "kami bikin ___". `[vanilla]`
- · **Split text reveal** `split` — *split text / per-char stagger* · premium · editorial — judul besar masuk. GSAP timeline + stagger. `[gsap]`
- · **Gradient shimmer** `shimmer` — *text shine / shimmer sweep* · mewah · halus — logo wordmark, label premium. CSS murni. `[vanilla]`
- · **Infinite marquee** `marquee` — *marquee / infinite ticker* · berani · brutalist — strip brand, logo wall. CSS loop. `[vanilla]`
- · **Char Lift** `char-lift` — *per-character hover · letter lift · playful nav* · ceria · menu/header interaktif · hindari di body text panjang `[vanilla]`
- ⭐ **Glitch Text** `glitch-text` — *RGB split · datamosh · chromatic aberration* · edgy/cyberpunk · hero gaming/tech · hindari konteks korporat tenang `[vanilla]` _(cyber)_
- ⭐ **Blur In** `blur-in` — *defocus reveal · soft focus · letter cascade* · elegan/dreamy · hero editorial · hindari kalau butuh keterbacaan instan `[vanilla]` _(organic)_
- ⭐ **Cube Words** `cube-words` — *3D flip · rotating words · word carousel* · teknis/dinamis · headline "kami bikin X" `[vanilla]` _(cyber)_
- ⭐ **Stroke Fill** `stroke-fill` — *outline to fill · text-stroke wipe · ink fill* · premium/bold · hero kata tunggal besar · hindari teks kecil `[vanilla]` _(kinetic-type)_
- ⭐ **Wave Text** `wave-text` — *sine wave · bouncing letters · staggered float* · ramah/main-main · banner playful · hindari nada serius `[vanilla]` _(organic)_
- ⭐ **Decrypt Wipe** `decrypt-wipe` — *cascade decrypt · left-to-right lock-in · matrix wipe* · techy/misterius · loading/reveal hacker-ish `[vanilla]` _(cyber)_
- · **Seamless Marquee** `marquee-wrap` — *infinite wrap ticker* · energetic · logo wall, ticker · hindari teks yang harus dibaca penuh `[gsap]`
- · **Word Reveal** `word-reveal` — *word-split stagger* · elegant · hero headline, section intro · hindari di paragraf panjang `[gsap]`
- ⭐ **Elastic letters** `anime-elastic-text` — *elastic ease / spring stagger text* · bouncy · headline pop, CTA · anime.js v3 — easeOutElastic `[anime.js]` _(kinetic-type)_
- ⭐ **Char Index Reveal** `char-index-reveal` — *staggered char cascade* · crisp · hero entrance · Splitting.js (~3kb) `[Splitting.js]` _(kinetic-type)_
- ⭐ **Per-Word Rotate-In** `word-rotate-in` — *word-level flip stagger* · playful · headline reveal · Splitting.js (~3kb) `[Splitting.js]` _(kinetic-type)_
- ⭐ **Typewriter Phrases** `typed-phrases` — *rotating typewriter* · conversational · taglines · Typed.js (~10kb) `[Typed.js]` _(kinetic-type)_
- ⭐ **Self-Drawing Text** `vivus-draw` — *SVG stroke draw-on* · technical · logo intro · Vivus (~8kb) `[Vivus]` _(hand-made)_
- ⭐ **Line + Char Mask Reveal** `mask-line-reveal` — *masked char rise* · editorial · paragraph intro · SplitType+gsap (~30kb) `[SplitType]` _(kinetic-type)_
- ⭐ **Elastic Char Bounce** `elastic-bounce` — *elastic char loop* · bouncy · playful badge · SplitType+gsap (~30kb) `[SplitType]` _(kinetic-type)_
- · **Character Wave** `waapi-char-wave` — *per-char stagger* · ceria · hero word / playful header `[WAAPI]`
- ⭐ **Scramble Headline** `scramble-headline` — *text-scramble / decode reveal* · techy · hero load-in · butuh ScrambleTextPlugin `[gsap]` _(kinetic-type)_
- ⭐ **Char Flip 3D** `char-flip-3d` — *per-char 3D rotateX stagger* · snappy · section title `[gsap]` _(cyber)_
- ⭐ **Morphing Counter** `anime-counter` — *number odometer* · data-proud · stats &amp; KPI · anime.js (~17KB) `[anime.js]` _(kinetic-type)_

### Hero / WebGL / ambient (90)

- ⭐ **Aurora gradient** `aurora` — *aurora / animated mesh glow* · dreamy · modern — background hero SaaS. CSS blur + keyframes. `[vanilla]` _(organic)_
- ⭐ **Mesh gradient (canvas)** `mesh` — *animated mesh gradient / flowing blobs* · organik · premium — hero bg yang lebih hidup dari CSS. `[vanilla]` _(generative)_
- ⭐ **Particle constellation** `constellation` — *particle network / constellation* · techy · futuristik — hero startup/AI. Canvas 2D, no lib. `[vanilla]` _(generative)_
- ⭐ **3D torus knot** `three` — *webgl / three.js wireframe object* · wow · 3D — hero teknikal, landing produk. Butuh three.js (~600KB CDN). `[three.js]` _(3d)_
- ⭐ **Floating blobs** `blobs` — *floating blobs / ambient shapes* · playful · ramah — bg section, empty state. CSS keyframes. `[vanilla]` _(organic)_
- ⭐ **Particle Sphere** `particle-sphere` — *point cloud · fibonacci sphere · slow spin · additive glow* · cosmic · hero/loading/AI · hindari di teks padat `[three.js]` _(shader)_
- ⭐ **Wavy Plane** `wavy-plane` — *wireframe mesh · vertex displacement · sine ripple* · retro-future · hero/footer/divider `[three.js]` _(3d)_
- ⭐ **Blob Morph** `blob-morph` — *organic shape · path interpolation · gooey · gradient fill* · playful · avatar/hero accent/empty state `[vanilla]` _(organic)_
- ⭐ **Film Grain** `film-grain` — *noise · grain · analog texture · overlay blend* · cinematic · texture over hero/photo · hindari di teks kecil `[vanilla]` _(hand-made)_
- ⭐ **Dot Grid Wave** `dot-grid` — *grid · radial pulse · size/opacity wave · background pattern* · techy-calm · section bg/dashboard hero `[vanilla]` _(hero)_
- ⭐ **Gradient Orb** `gradient-orb` — *conic gradient · glow · spinning sphere · pure CSS* · premium-AI · hero focal/logo halo/CTA accent `[vanilla]` _(organic)_
- ⭐ **Starfield Warp** `starfield-warp` — *hyperspace · perspective projection · streaking stars · z-rush* · energetic-scifi · hero/loading/transition `[vanilla]` _(generative)_
- ⭐ **Cursor Ripple** `cursor-ripple` — *interactive · expanding rings · mousemove spawn · water surface* · tactile-delight · hero/interactive bg/playground `[vanilla]` _(hero)_
- ⭐ **SVG line draw** `anime-line-draw` — *stroke-dashoffset / self-drawing path* · elegant · logo reveal, diagram · anime.js v3 — setDashoffset `[anime.js]` _(hero)_
- ⭐ **Link constellation** `ts-constellation` — *particle network / hover-reactive links* · techy · hero SaaS, footer bg · tsParticles v2 (~180KB) — links + grab `[tsParticles]` _(generative)_
- ⭐ **Vanta 3D net** `vanta-net` — *webgl net / animated 3D mesh background* · wow · hero landing, login bg · Vanta.NET + three.js `[Vanta]` _(shader)_
- ⭐ **Breathing Icosahedron** `breathing-ico` — *wireframe polyhedron · vertex noise · pulsing breath* · organik · hero/AI-idle/loading · hindari saat butuh teks tajam `[three.js]` _(3d)_
- ⭐ **Cube Wave Grid** `cube-wave` — *instanced mesh · grid · travelling sine wave* · tech · hero/data/dashboard · hindari kalau performa HP lemah `[three.js]` _(shader)_
- ⭐ **Morphing Point Cloud** `morph-cloud` — *point cloud · position lerp · sphere ⇄ torus* · hipnotis · hero/AI/transisi · hindari di latar yang sudah ramai `[three.js]` _(shader)_
- ⭐ **Glowing Knot Halo** `glow-knot-halo` — *torusknot · additive points halo · pulse glow* · premium · hero/landing/AI · hindari di UI yang harus tenang `[three.js]` _(3d)_
- ⭐ **Edge Dodecahedron** `edge-dodeca` — *dodecahedron · EdgesGeometry · neon line segments* · crisp tech · hero/logo/loader · hindari kalau ingin lembut `[three.js]` _(3d)_
- ⭐ **Spiral Tube** `spiral-tube` — *CatmullRom curve · TubeGeometry · helix ribbon* · dinamis · hero/transisi/branding · hindari di kartu kecil `[three.js]` _(3d)_
- ⭐ **Plasma flow shader** `plasma-flow` — *fragment plasma / sin-based color flow* · psychedelic · hero bg, loader · hindari di belakang teks padat `[three.js]` _(shader)_
- ⭐ **GPU points wave field** `points-wave` — *vertex-displaced point grid / ocean of dots* · techy · hero produk, data viz · hindari layout statis `[three.js]` _(shader)_
- ⭐ **Particle galaxy spiral** `galaxy-spiral` — *spiral galaxy / per-particle vertex colors* · kosmik · hero space/AI · hindari UI sibuk `[three.js]` _(shader)_
- ⭐ **Repelling points grid** `repel-grid` — *raycaster repel / pointer-reactive field* · interaktif · hero CTA, 404 · hindari mobile tanpa pointer `[three.js]` _(shader)_
- ⭐ **Swirling particle sphere** `swirl-sphere` — *additive particle sphere / size attenuation* · elegan · hero AI, avatar, loader · hindari low-end mobile `[three.js]` _(shader)_
- ⭐ **Fresnel glow sphere** `fresnel-sphere` — *fresnel rim light / atmospheric glow* · sci-fi · hero produk, planet/orb · hindari bg terang `[three.js]` _(shader)_
- ⭐ **Particle Fountain** `pixi-fountain` — *particle emitter* · energik · hero/celebration · PixiJS (~400KB) `[PixiJS]` _(shader)_
- ⭐ **Displacement Wave** `pixi-displace` — *displacement filter* · liquid · background hero · PixiJS (~400KB) `[PixiJS]` _(shader)_
- ⭐ **Orbiting Swarm** `pixi-swarm` — *additive orbit* · kosmik · hero/loader · PixiJS (~400KB) `[PixiJS]` _(shader)_
- ⭐ **Hue-Rotate Pulse** `pixi-huepulse` — *color matrix filter* · psikedelik · accent/loader · PixiJS (~400KB) `[PixiJS]` _(shader)_
- ⭐ **Pointer Repel** `pixi-repel` — *interactive repel field* · playful · interaktif/hero · PixiJS (~400KB) `[PixiJS]` _(shader)_
- ⭐ **Bloom Glow Text** `pixi-bloomtext` — *blur bloom pulse* · neon · hero headline · PixiJS (~400KB) `[PixiJS]` _(shader)_
- ⭐ **Gravity Rain Pile** `matter-rain-pile` — *rigid-body rain* · playful · hero/empty-state · Matter.js (~90KB) `[Matter.js]` _(physics)_
- ⭐ **Newton's Cradle** `matter-cradle` — *conservation pendulum* · mesmerizing · hero/loader · Matter.js (~90KB) `[Matter.js]` _(physics)_
- ⭐ **Drag &amp; Toss** `matter-drag` — *mouse constraint* · interactive · hero/playground · Matter.js (~90KB) `[Matter.js]` _(physics)_
- ⭐ **Hyper Bounce** `matter-bounce` — *elastic restitution* · energetic · hero/404 · Matter.js (~90KB) `[Matter.js]` _(physics)_
- ⭐ **Wobble Tower** `matter-tower` — *rigid stack* · tense · hero/game · Matter.js (~90KB) `[Matter.js]` _(physics)_
- ⭐ **Flow Field Drift** `flow-field` — *flow field* · hypnotic · hero bg / loaders · p5.js (~900KB) `[p5.js]` _(generative)_
- ⭐ **Generative Wave Lines** `wave-lines` — *waveform field* · calm · section dividers · p5.js (~900KB) `[p5.js]` _(generative)_
- ⭐ **Morphing Polygon** `poly-morph` — *vertex morph* · meditative · logo idle / badges · two.js (~150KB) `[two.js]` _(generative)_
- ⭐ **Hand-Drawn Sketch** `rough-sketch` — *sketchy redraw* · playful · doodle headers · rough.js (~40KB) `[rough.js]` _(hand-made)_
- ⭐ **Animated Gradient** `granim-gradient` — *gradient crossfade* · premium · hero / CTA panels · Granim.js (~18KB) `[Granim.js]` _(generative)_
- ⭐ **SVG Path Morph** `path-morph` — *shape morph* · slick · feature icons / logo reveals · KUTE.js (~30KB) `[KUTE.js]` _(hero)_
- ⭐ **Torus Knot Glow** `bjs-torusknot-glow` — *emissive PBR knot* · hypnotic · hero centerpiece · Babylon.js (~4MB, berat) `[Babylon.js]` _(3d)_
- ⭐ **Particle Fountain** `bjs-particle-fountain` — *emitter spray* · energetic · celebratory header · Babylon.js (~4MB, berat) `[Babylon.js]` _(shader)_
- ⭐ **Glow Icosphere** `bjs-glow-icosphere` — *neon wireframe* · techy · data/AI hero · Babylon.js (~4MB, berat) `[Babylon.js]` _(3d)_
- ⭐ **Orbiting Instances** `bjs-instanced-orbit` — *instanced orbit* · cosmic · loading/portfolio hero · Babylon.js (~4MB, berat) `[Babylon.js]` _(3d)_
- ⭐ **Wave Field** `bjs-wave-ground` — *vertex displacement* · calm · ambient background hero · Babylon.js (~4MB, berat) `[Babylon.js]` _(shader)_
- ⭐ **Edged Polyhedra** `bjs-edged-polyhedra` — *edge-rendered solids* · crystalline · premium product hero · Babylon.js (~4MB, berat) `[Babylon.js]` _(3d)_
- ⭐ **Timeline Shapes** `motion-timeline-shapes` — *orchestrated keyframe timeline* · confident · hero accents/logo reveal · Motion One (~18kb) `[Motion One]` _(hero)_
- ⭐ **Waves Ocean** `vanta-waves-ocean` — *3D animated wave plane* · immersive · hero background · Vanta+THREE (~120kb) `[Vanta]` _(shader)_
- ⭐ **Fog Aurora** `vanta-fog-aurora` — *animated gradient fog field* · dreamy · soft hero/section bg · Vanta+THREE (~115kb) `[Vanta]` _(shader)_
- ⭐ **Themed Snowfall** `tsp-snowfall-theme` — *ambient falling particle field* · calm · seasonal/ambient bg · tsParticles (~80kb) `[tsParticles]` _(generative)_
- ⭐ **Coin Flip** `coin-flip` — *3D Y-axis coin flip* · delightful · badge/reward reveal, logo play `[vanilla]` _(organic)_
- ⭐ **Mesh Drift** `mesh-drift` — *animated gradient mesh* · atmospheric · hero bg, auth screens `[vanilla]` _(organic)_
- ⭐ **Plasma Triangle** `ogl-plasma-tri` — *fullscreen plasma* · hipnotis · hero/landing · OGL (~50KB, ringan) `[OGL]` _(shader)_
- ⭐ **Raymarch Blob** `ogl-blob-march` — *sdf metaball* · organik · hero/produk · OGL (~50KB, ringan) `[OGL]` _(shader)_
- ⭐ **GPU Particles** `ogl-particles` — *point cloud* · galaksi · hero/intro · OGL (~50KB, ringan) `[OGL]` _(shader)_
- ⭐ **Noise Field Plane** `ogl-noise-plane` — *displaced plane* · tenang · hero/background · OGL (~50KB, ringan) `[OGL]` _(shader)_
- ⭐ **Fresnel Box** `ogl-fresnel-box` — *rim-light cube* · futuristik · hero/produk · OGL (~50KB, ringan) `[OGL]` _(shader)_
- ⭐ **DNA Helix** `dna-helix` — *double helix* · organik · sains/bio/data genetik `[three.js]` _(3d)_
- ⭐ **Equalizer Ring** `eq-ring` — *audio bars* · energik · musik/podcast/live audio `[three.js]` _(3d)_
- ⭐ **Noise Blob** `noise-blob` — *vertex displacement* · cair · brand playful/AI/abstrak `[three.js]` _(shader)_
- ⭐ **Tumbling Ring** `cube-ring` — *phase rotation* · ritmis · loader/loop/teknis `[three.js]` _(3d)_
- ⭐ **Starfield** `starfield` — *z-loop warp* · imersif · intro/space/kecepatan `[three.js]` _(shader)_
- ⭐ **Torus Aura** `torus-aura` — *normal-mat + points* · futuristik · produk tech/hero `[three.js]` _(3d)_
- ⭐ **Cube Stack Drop** `cannon-cube-stack` — *rigid-body 3D stacking* · playful · hero/empty-state · cannon.js (~140KB) `[cannon.js]` _(physics)_
- ⭐ **Bounce Box** `cannon-bounce-box` — *elastic 3D ricochet* · energetic · hero/404 · cannon.js (~140KB) `[cannon.js]` _(physics)_
- ⭐ **Domino Chain** `cannon-domino` — *chain-reaction tumble* · mesmerizing · hero/storytelling · cannon.js (~140KB) `[cannon.js]` _(physics)_
- ⭐ **Constraint Pendulum** `cannon-pendulum` — *point-to-point swing* · hypnotic · hero/loader · cannon.js (~140KB) `[cannon.js]` _(physics)_
- ⭐ **Displacement Plane** `curtains-displace` — *vertex-displacement shader* · liquid · background hero · curtains.js (~50KB) `[curtains.js]` _(shader)_
- ⭐ **Ripple Plane** `curtains-ripple` — *radial wave/ripple shader* · dreamy · interaktif/background · curtains.js (~50KB) `[curtains.js]` _(shader)_
- ⭐ **Signature Draw** `signature-draw` — *stroke-dashoffset draw-on* · elegant · hero/logo intro `[gsap]` _(hand-made)_
- ⭐ **Pita Mengalir** `ribbon-trail` — *flowing ribbon trail* · hipnotis · hero gerak lambat `[three.js]` _(3d)_
- ⭐ **Bentang Bergulir** `terrain-scroll` — *low-poly terrain scroll* · sinematik · hero lanskap `[three.js]` _(3d)_
- ⭐ **Bola Kaca** `glass-orb` — *glass refractive orb* · premium · hero produk `[three.js]` _(3d)_
- ⭐ **Awan Tetrahedron** `tetra-cloud` — *instanced spinning tetrahedra* · enerjik · hero teknologi `[three.js]` _(3d)_
- ⭐ **Cincin Giro** `gyro-rings` — *concentric rotating torus rings* · presisi · hero futuristik `[three.js]` _(3d)_
- ⭐ **Bola Kubus** `cube-sphere` — *pulsing sphere of cubes* · teknis · hero data/AI `[three.js]` _(3d)_
- ⭐ **Neon Flicker Sign** `neon-flicker` — *neon flicker · faulty-tube glow* · retro-electric · bar/club/arcade hero `[vanilla]` _(cyber)_
- ⭐ **Origami Folding Card** `origami-fold` — *origami fold · 3D crease* · crafted-3D · feature reveal hero `[vanilla]` _(hero)_
- ⭐ **Rotating Gallery Cube** `gallery-cube` — *3D cube · rotating showcase* · showcase-bold · portfolio/feature hero `[vanilla]` _(hero)_
- ⭐ **Perspective Grid Floor** `grid-floor` — *grid floor · synthwave horizon* · retro-futurist · landing/hero backdrop `[vanilla]` _(cyber)_
- ⭐ **Flow Field Streams** `flow-streams` — *flow field / vector noise* · hypnotic · hero &amp; loaders `[vanilla]` _(generative)_
- ⭐ **Digital Rain** `digital-rain` — *matrix code rain* · techy · hero &amp; 404 `[vanilla]` _(cyber)_
- ⭐ **Liquid Metaballs** `metaballs` — *metaballs / scalar field* · organic · hero &amp; backgrounds `[vanilla]` _(generative)_
- ⭐ **Cursor Network** `cursor-network` — *proximity graph / plexus* · interactive · hero &amp; tech landing `[vanilla]` _(generative)_
- ⭐ **Scroll-Dolly 3D World** `scroll-dolly-3d` — *scroll-linked camera dolly / fly-through / depth tunnel* · sinematik · imersif — hero scrollytelling, intro brand, product reveal · di produksi pakai ScrollTrigger scrub kamera (composed) `[three.js]` _(3d)_

### Feedback / loaders (27)

- · **Skeleton shimmer** `skeleton` — *skeleton loader / shimmer placeholder* · profesional · halus — loading state. CSS murni. `[vanilla]`
- · **Liquid progress** `liquid` — *liquid fill / wave progress* · delightful · organik — loader, stat. CSS rotate trick. `[vanilla]`
- · **Bouncing dots** `dots` — *dot loader / bouncing dots* · ramah · ringan — inline loading, chat typing. CSS delay. `[vanilla]`
- · **Success Checkmark** `checkmark` — *checkmark draw-in / stroke confirm* · lega · konfirmasi sukses, submit beres · hindari di error state `[vanilla]`
- ⭐ **Confetti Burst** `confetti` — *confetti burst / particle celebration* · gembira · checkout sukses, milestone · hindari di flow serius `[vanilla]` _(feedback)_
- · **Pulse Radar** `radar` — *ping / pulse / expanding rings* · hidup · status live, notif baru · hindari kalau perlu fokus tenang `[vanilla]`
- · **Conic Spinner** `conic-spin` — *conic-gradient loader / mask spinner* · modern · loading singkat, fetch data `[vanilla]`
- · **Segmented Steps** `steps` — *segmented / stepper progress fill* · terukur · onboarding, checkout, wizard `[vanilla]`
- · **Toast Slide-In** `toast` — *toast / snackbar notification* · informatif · konfirmasi singkat, auto-dismiss · hindari error kritis `[vanilla]`
- · **Radial Progress Ring** `ring-progress` — *radial / circular progress ring* · presisi · upload, skor, completion % `[vanilla]`
- · **Breathing Loader** `waapi-breathe-loader` — *pulse / breathe* · tenang · indeterminate loading `[WAAPI]`
- · **Composite Glow Ring** `waapi-composite-glow` — *composite: 'add'* · energik · sync / processing `[WAAPI]`
- · **Eased Rate Spinner** `waapi-rate-spinner` — *playbackRate easing* · hidup · long task feedback `[WAAPI]`
- · **Conic Ring** `conic-ring` — *conic-gradient spinner* · modern · loading states, async fetch `[vanilla]`
- · **Check Pop** `check-pop` — *draw-on checkbox tick* · satisfying · todo/forms, consent `[vanilla]`
- · **Segment Clock** `segment-clock` — *12-segment radial loader* · tenang · loading, "memproses…" `[vanilla]`
- · **Animated Toggle Pill** `toggle-pill` — *toggle · stateful switch* · tactile-clean · settings/forms `[vanilla]`
- · **Image Curtain Reveal** `curtain-reveal` — *curtain reveal · split-open* · theatrical · gallery/portfolio `[vanilla]`
- · **Radar Sweep** `radar-sweep` — *radar sweep · scanning loop* · techy-monitoring · live/scanning state `[vanilla]`
- · **Droplet Water-Fill Button** `water-fill` — *water fill · liquid rise* · playful-fluid · primary CTA `[vanilla]`
- · **Equalizer Bars (canvas)** `audio-bars` — *spectrum / VU bars* · energetic · player &amp; live status `[vanilla]`
- ⭐ **Fireworks Burst** `fireworks` — *particle burst / celebration* · celebratory · sukses &amp; milestone `[vanilla]` _(feedback)_
- · **Lottie Glow Loop** `lottie-glow` — *vector micro-loop* · hypnotic · loaders &amp; empty states · Lottie (asset+lib); warna ikut asset `[Lottie]`
- · **Lottie Pulse Mark** `lottie-pulse` — *animated illustration* · friendly · success &amp; status · Lottie (asset+lib); warna ikut asset `[Lottie]`
- · **Ring Pulse Grid** `anime-ring` — *radial stagger* · rhythmic · loaders &amp; ambient · anime.js (~17KB) `[anime.js]`
- · **Checkmark Draw** `anime-check` — *line-draw confirm* · reassuring · success &amp; form confirm · anime.js (~17KB) `[anime.js]`
- · **Bouncing Balls** `anime-balls` — *keyframe bounce* · playful · loaders &amp; waiting · anime.js (~17KB) `[anime.js]`

---

### UI Transitions (11)

State transitions that make app UI feel *expensive* (PLAYBOOK §5.6 / §5.7). Functional motion — the
in-between of every state change. All vanilla; the View-Transition ones degrade to instant where unsupported.

- · **Tab Slide** `tab-slide` — *sliding indicator / shared-element tab / pill slide* · premium · crisp — tabs, segmented, filter. Indikator geser, bukan loncat `[vanilla]`
- ⭐ **FLIP Reorder** `flip-reorder` — *FLIP / list reorder / shared-element move* · satisfying · add/remove/reorder list — item meluncur ke posisi baru (signature Linear/Vercel) `[vanilla]` _(ui-transitions)_
- · **Popover from Origin** `modal-origin` — *origin-aware / scale-from-trigger / popover* · premium · menu/popover/modal membuka dari titik klik `[vanilla]`
- · **Error Shake** `error-shake` — *invalid shake / form validation / wobble* · jelas · input gagal validasi `[vanilla]`
- · **Input Clear Dissolve** `input-clear` — *clear dissolve / blur-out / field reset* · halus · tombol clear search/field `[vanilla]`
- · **Tooltip Timing** `tooltip-timing` — *delayed-in / quick-out / intent tooltip* · pro · tooltip (anti-flicker) `[vanilla]`
- ⭐ **Toast Stack** `toast-stack` — *stacking toast / FLIP push / notification queue* · hidup · notifikasi sukses, lama terdorong naik `[vanilla]` _(ui-transitions)_
- · **Accordion (smooth height)** `accordion-smooth` — *grid-rows 0fr→1fr / auto-height transition* · mulus · FAQ/collapse, TANPA JS ukur tinggi `[vanilla]`
- ⭐ **View Transition Crossfade** `vt-crossfade` — *View Transitions API / startViewTransition / state crossfade* · native-app · ganti panel/tab/filter `[vanilla]` _(ui-transitions)_
- ⭐ **Shared-Element Morph** `vt-morph` — *view-transition-name / shared element / list→detail* · mewah · thumbnail→detail, grid→halaman `[vanilla]` _(ui-transitions)_
- ⭐ **Theme Switch (circular reveal)** `theme-reveal` — *theme toggle / circular clip reveal / View Transitions* · high-delight · light↔dark nyebar dari titik klik `[vanilla]` _(ui-transitions)_

## How to use an entry
1. Pick by *istilah* (the technical term) + when-to-use, filtered by your dependency budget (`[library]`).
2. For a whole page, go through **PLAYBOOK.md** first (flavor menu → kit → slot map).
3. Grab the code: open `galeri.html`, find `data-fx="<id>"`; the `<script type="text/plain" class="src">` next to that card (or the inline `init('<id>', …)`) is the recipe. The Vite app's `src/main.js` has the same, npm-import ready.
4. Always add a `prefers-reduced-motion` fallback; prefer `transform`/`opacity`.

## Dependency tiers
- **vanilla** — zero deps, default. **gsap** / **three** — Tier 2 focused libs. **[other lib]** — Tier 3, flag the cost.

## Growth
New effects enter via galeri.html (verified running) → re-run the extractor to refresh this index. Curation gate = Iqbal.
