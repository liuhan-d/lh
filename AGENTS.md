# AGENTS.md

## Project

Student coursework for 《高级网页设计》 (Advanced Web Design). A collection of standalone HTML/CSS exercise pages — no framework, no build system, no package manager, no tests.

## Running

Open any `.html` file directly in a browser. No dev server, no build step, no dependencies.

## Structure

- `index.html` — navigation hub linking all exercise pages
- `N-M*.html` — individual exercise pages (e.g., `6-1 flex.html`, `9-1 transiton.html`)
- `css.css` — minimal shared styles (only used by some pages)
- `img/` — image assets referenced by exercise pages

## Conventions

- All vanilla HTML/CSS/JS — no CDN, no external dependencies
- Some filenames contain Chinese characters and spaces; links in `index.html` use URL-encoded hrefs (e.g., `5-1%20层叠与继承.html`)
- Pages are self-contained with inline `<style>` blocks
- New exercise pages must be added as card entries in `index.html` (but pages themselves do NOT link back to `index.html`)
- When creating a new HTML page, also add a card link to it in `index.html`
- Every HTML page must include a link back to `index.html` (e.g., a "返回首页" link in header or footer)
