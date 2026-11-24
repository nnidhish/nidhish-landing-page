# Nidhish Karkera — Personal Landing Page

A single-file, dependency-free personal landing page for a Test Engineer specialising in
banking and payments QA.

## Contents

| File | Purpose |
| --- | --- |
| `index.html` | The entire site — markup, styles and a little vanilla JS. No build step, no dependencies. |
| `vercel.json` | Vercel config: clean URLs plus a few security headers. |

## Local preview

Open the file directly:

```sh
open index.html
```

Or serve it over HTTP:

```sh
npx serve .
# then visit http://localhost:3000
```

## Deploy to Vercel

### Option A — from this machine (CLI)

```sh
npm i -g vercel   # once
vercel login      # once
vercel --prod     # deploy
```

The first `vercel` run asks a few questions (scope, project name, directory). Accept the
defaults: no framework, no build command, root directory as the output.

### Option B — from Git (recommended for updates)

1. Push this folder to a GitHub repository (`main` branch).
2. Go to [vercel.com/new](https://vercel.com/new) and import the repository.
3. Framework preset: **Other**. Build command: none. Output directory: `.`.
4. Every push to `main` then redeploys automatically.

## Editing

All content lives in `index.html` and is grouped by section, so it is easy to update:

- `<!-- HERO -->`, `<!-- ABOUT -->`, `<!-- EXPERIENCE -->`, `<!-- SKILLS -->`,
  `<!-- EDUCATION -->`, `<!-- CONTACT -->`
- Theme colours are the CSS custom properties at the top of the `<style>` block
  (`--accent`, `--accent-2`, `--bg`, …).

## Notes

- The scroll-reveal animation is a progressive enhancement: content is only hidden when
  JavaScript is running, and there is a fallback if the observer never fires, so the page
  never renders blank. `prefers-reduced-motion` is respected and a print stylesheet is included.
- No external fonts, CDNs or trackers — the page is fully self-contained and works offline.
