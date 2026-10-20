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
| `style.css` | The only stylesheet, shared by every page |
| `README.md` | How to preview and publish |

## Previewing

Open `index.html` in a browser. There are no tests or linters; check changes by looking at the page:

- at desktop width and at phone width (about 375px), with no sideways scrolling
- in both light and dark mode (`style.css` switches on `prefers-color-scheme`)

`404.html` links `/style.css` with a leading slash so it works at any URL on the live site.
Opened straight from disk it shows unstyled; that's expected.

## Publishing

Every change goes through a pull request. Never commit or push directly to `main`.

1. Create a branch with a short, descriptive name (for example `add-404-page`).
2. Commit there and push the branch.
3. Open a pull request into `main`. Once it's merged, GitHub Pages republishes in a minute or two.

## Rules

- **No build tools or dependencies.** Don't add npm, frameworks, bundlers or CDN scripts unless the owner asks.
- **Colors come from the variables** at the top of `style.css` (`--bg`, `--surface`, `--text`, `--muted`,
  `--border`, `--accent`). When adding a color, add a variable for it in both the light `:root` block
  and the dark-mode block. Don't hard-code colors in rules.
- **Reuse existing classes** (`eyebrow`, `lead`, `cards`, `card`) before adding new ones.
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
