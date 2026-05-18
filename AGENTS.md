# Agent Notes

## Project Shape
- This repo is a static single-page landing page for LAF Avvocati; the deployable entrypoint is `index.html` in the project root.
- There is no `package.json`, lockfile, build step, test runner, linter, formatter, or CI config in this workspace.
- `stitch/screen.png` is the original Google Stitch visual reference; `stitch/` is reference material, not the deployable page.
- Target hosting is static HTML/CSS/JavaScript on Linux hosting at Aruba.it; do not introduce Node.js, server-side code, or build-only runtime assumptions.

## Working On The Page
- Edit `index.html` directly; Tailwind is loaded at runtime from `https://cdn.tailwindcss.com?plugins=forms,container-queries`.
- The Tailwind theme is inline in the `tailwind-config` script near the top of `index.html`; keep color and font changes there when adding reusable tokens.
- The page uses root assets `logo-laf.png` and `lorusso.jpg`; keep paths relative to `index.html` for static hosting.
- The page depends on network-loaded Google Fonts, Material Symbols, and some remote image URLs; offline rendering will not fully match production.
- Content is Italian (`<html lang="it">`); current copy is placeholder until the customer provides final texts.
- The contact form uses a small inline JavaScript `mailto:` handler; there is no backend wiring.

## Verification
- For visual changes, open `index.html` in a browser and compare desktop and mobile layouts against the intent and `stitch/screen.png`.
- Check the browser console/network panel after edits because missing CDN fonts, Material icons, or remote images are the most likely runtime issues.
