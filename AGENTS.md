# AGENTS.md

Notes for AI coding agents working in this repo.

## What this is

The personal website of Enyce4009, published at https://enyce4009.github.io by GitHub Pages.
It's plain HTML and CSS: no framework, no JavaScript, no build step, no dependencies.
The owner is learning to code, so keep changes simple and easy to read.

## Layout

| Path | Purpose |
| --- | --- |
| `index.html` | The homepage: intro, "What I'm working on", Projects cards, footer |
| `404.html` | Page GitHub Pages shows for missing URLs |
| `style.css` | Entry point every page links to; only `@import`s the files below, in order |
| `css/tokens.css` | Color variables, light and dark mode. Must be imported first |
| `css/base.css` | Reset, page layout, headings, links, footer |
| `css/components.css` | Reusable pieces: `.eyebrow`, `.lead`, `.cards`, `.card` |
| `README.md` | How to preview and publish, and the stylesheet layout |

Pages link only `style.css`. Put new CSS in whichever `css/` file fits, not in `style.css`,
and add a new file to `css/` (plus an `@import` in `style.css`) only when none of them fits.

## Previewing

Open `index.html` in a browser. There are no tests or linters; check changes by looking at the page:

- at desktop width and at phone width (about 375px), with no sideways scrolling
- in both light and dark mode (`css/tokens.css` switches on `prefers-color-scheme`)

`404.html` links `/style.css` with a leading slash so it works at any URL on the live site.
Opened straight from disk it shows unstyled; that's expected. The `@import` paths in `style.css`
are relative to `style.css` itself, so they work from either page; keep them relative.

## Publishing

Every change goes through a pull request. Never commit or push directly to `main`.

1. Create a branch with a short, descriptive name (for example `add-404-page`).
2. Commit there and push the branch.
3. Open a pull request into `main`. Once it's merged, GitHub Pages republishes in a minute or two.

## Rules

- **No build tools or dependencies.** Don't add npm, frameworks, bundlers or CDN scripts unless the owner asks.
- **Colors come from the variables** in `css/tokens.css` (`--bg`, `--surface`, `--text`, `--muted`,
  `--border`, `--accent`). When adding a color, add a variable for it in both the light `:root` block
  and the dark-mode block. Don't hard-code colors in rules.
- **Reuse existing classes** in `css/components.css` (`eyebrow`, `lead`, `cards`, `card`) before adding new ones.
  New reusable classes go there too; page-wide element styles go in `css/base.css`.
- **New pages** copy the `<head>` of `index.html` (charset, viewport, title, description, stylesheet link)
  and wrap content in `<main>`, so they get the same width and padding.
- **Projects** are `<li class="card">` items in the `.cards` list, each with an `<h3>` and a short `<p>`.
- **Keep it accessible:** one `<h1>` per page, headings in order, `alt` text on any image,
  descriptive link text.

## Style

- 2-space indent, lowercase tags and attributes, double quotes in HTML.
- CSS: one property per line; short one-line rules are fine (`a { color: var(--accent); }`).
- Friendly, first-person, plain-language copy, matching the existing text.
- Commit messages: short, imperative, sentence case (for example "Add custom 404 page").
