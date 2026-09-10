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

## Publish to GitHub Pages

The workflow in [`.github/workflows/deploy-pages.yml`](./.github/workflows/deploy-pages.yml) builds and deploys the deck on every push to `main`. It can also be run manually from the Actions tab.

1. Create a GitHub repository and add it as this project's `origin` remote.
2. In the repository's **Settings → Pages → Build and deployment**, select **GitHub Actions** as the source.
3. Commit the project (including `public/` and `.github/workflows/deploy-pages.yml`) and push to `main`.
4. Open **Actions → Deploy slides to GitHub Pages** to follow deployment. The deployment summary links to the published site.

The workflow detects the Pages base path automatically, so no repository name needs to be hardcoded. It also includes a `404.html` fallback for direct links to individual slides (GitHub Pages may return HTTP 404, but the slide app still loads).

To test a repository-path build locally:

```bash
pnpm exec slidev build --base /YOUR-REPO-NAME/
```

The published deck and its assets will be publicly accessible, including any speaker notes bundled by Slidev. Review the content before publishing.

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
