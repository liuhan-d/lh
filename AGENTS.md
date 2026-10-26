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
- `font/` — iconfont icon assets (`iconfont.css`, `iconfont.js`, `demo_index.html` lists available glyphs)
- `cdn/` — legacy local icon assets (Font Awesome, Lucide), used only by exercise pages 13-1 / 13-2

## Conventions

- All vanilla HTML/CSS/JS — no CDN, no external dependencies
- Some filenames contain Chinese characters and spaces; links in `index.html` use URL-encoded hrefs (e.g., `5-1%20层叠与继承.html`)
- Pages are self-contained with inline `<style>` blocks
- New exercise pages must be added as card entries in `index.html` (but pages themselves do NOT link back to `index.html`)
- When creating a new HTML page, also add a card link to it in `index.html`
- Every HTML page must include a link back to `index.html` (e.g., a "返回首页" link in header or footer)

## Icons & Data Fetching

- Pages must be implemented with native HTML, CSS, and JavaScript only — no third-party libraries, no CDN resources
- Icons must use the local iconfont icons from the `font/` directory: link `font/iconfont.css` and use `<i class="iconfont">&#xe6xx;</i>` style markup; check `font/demo_index.html` or `font/iconfont.json` for available glyph codes
- When a page needs server-side data, request it with the native `fetch` API (run a local server such as `python -m http.server` to test); do not add any ajax/fetch library

## Naming & Comment Rules

- All JavaScript variable names, CSS class names, and element `id` names must start with the `lh_` prefix (e.g., `lh_count`, `lh_card`, `lh_btn_submit`)
- Every newly created HTML page must include the following comment right after `<!DOCTYPE html>`:
  `<!-- 姓名：刘晗，建立时间：YYYY-MM-DD，使用的大模型：<model name>，功能名称：<页面功能描述> -->`
- 建立时间 is the page's creation date in `YYYY-MM-DD` format; 使用的大模型 records the AI model that assisted in creating the page (e.g., GLM-5.3-Flash); 功能名称 is a short description of what the page demonstrates
