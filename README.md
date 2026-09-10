# Open Source Happy Hour 2026

A technical conference presentation built with [Slidev](https://sli.dev/).

## Develop

```bash
pnpm install
pnpm dev
```

Useful presenter shortcuts:

- `S` opens presenter mode
- `O` opens the slide overview
- `D` toggles dark mode
- `G` opens slide navigation

## Build and export

```bash
pnpm build
pnpm export
```

Edit [`slides.md`](./slides.md) to update the deck. Add static assets to `public/` and reusable Vue components to `components/`.

## REVSYS slide templates

Both layouts use a white background and the logo's navy / blue palette. Styling lives in `style.css`; the logo is bundled locally in `public/revsys-logo.png`.

### Title slide — `revsys-title`

Large logo on the left, talk title and subtitle on the right, with an optional presenter footer:

```md
---
layout: revsys-title
---

# Your talk title

Your subtitle or event name

::footer::

Presenter Name · REVSYS · 2026
```

### Interior slide — `revsys-content`

Small logo anchored bottom-right, with space reserved beneath the content. This is the deck's default layout for new slides:

```md
---
layout: revsys-content
---

# Slide title

- Your first point
- Your second point
```

For two-column content, add `::left::` and `::right::` slots after the heading (see the technical deep-dive example in `slides.md`).
