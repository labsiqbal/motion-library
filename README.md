# design-library

A curated, growing library of web **animation / motion** effects — each named, mood-tagged, and shipped with paste-ready code — plus a Next.js application playbook that maps UI context → effect.

It exists because motion has two problems static design doesn't:

1. **You must know the term to ask for it** — "parallax", "magnetic hover", "text scramble". Without the word, you can't summon the effect.
2. **Motion can't be screenshotted** — it lives in time; it must be *run* to be seen.

So this library names every effect (vocabulary) and ships a live gallery where each one runs.

## Contents

| File | Role |
|---|---|
| `SKILL.md` | Skill entry point + usage doctrine |
| `CATALOG.md` | Index of all 217 effects — name · id · when-to-use · library, code included |
| `PLAYBOOK.md` | Application layer — context→effect map, 7 Next.js page kits, perf + transition doctrine |
| `galeri.html` | Live gallery — every effect rendered, filter by category/dependency, copy code |
| `effects/` | Per-category source notes as the library grows |

`CATALOG.md` = *what effects exist*; `PLAYBOOK.md` = *which goes where + how to ship it*.

## Usage

This is a **data provider, not a builder**. It hands a builder (or you directly) the motion vocabulary and code. Open `galeri.html` in a browser to watch the effects; read `CATALOG.md` to grab them.

## License

MIT
