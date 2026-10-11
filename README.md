# enyce4009.github.io

My personal website, built with plain HTML and CSS and hosted on GitHub Pages.

**Live site:** https://enyce4009.github.io

## Editing locally

Open `index.html` in a browser to preview changes. No build step is needed.

## Styles

`style.css` is the single entry point that both pages load. It imports, in order:

- `css/tokens.css`: color variables, including dark mode. Must load first.
- `css/base.css`: reset, page layout, headings, links, footer.
- `css/components.css`: reusable pieces like `.eyebrow`, `.lead` and the project cards.

## Publishing

Every change goes through a pull request. Once a PR is merged into `main`, GitHub Pages republishes the site within a minute or two.
