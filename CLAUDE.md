# CLAUDE.md

This file provides guidance to Claude Code (claude.ai/code) when working with code in this repository.

## About

Personal website for Dor Tzabari at tzabari.dev. Static site — no build tools, no frameworks, just plain HTML/CSS/JS.

## Structure

- `index.html` — Landing page (intro, about, projects, contact links). Has JSON-LD structured data and Open Graph meta tags.
- `blog.html` — Blog listing page (posts are placeholder links for now)
- `resume.json` — Machine-readable resume in JSON Resume format (for ATS and AI agents)
- `llms.txt` — Plain text site summary for LLM agents
- `robots.txt` — Allows all crawlers including AI agents
- `sitemap.xml` — Sitemap for search engines and crawlers

## Design System

- **Font**: JetBrains Mono (monospace, loaded from Google Fonts)
- **Theme**: Light/dark toggle with `data-theme` attribute on `<html>`, persisted via localStorage
- **CSS variables**: `--bg`, `--fg`, `--muted`, `--border`, `--accent`, `--hover` defined in `:root` and `[data-theme="dark"]`
- **Animations**: Staggered `fadeUp` on page load using CSS `animation-delay`
- **Texture**: Subtle SVG noise grain overlay via `body::before`
- **Layout**: Single `.container` at `max-width: 800px`, responsive at 600px breakpoint
- All styles are inline (in `<style>` tags), no external CSS files

## AI/Agent Readability

This site is optimized for AI agents and ATS systems:
- **JSON-LD** (Schema.org `Person`) embedded in `index.html <head>` — structured data for search engines and agents
- **JSON Resume** (`resume.json`) — standard machine-readable resume format
- **llms.txt** — plain text summary following the llms.txt convention for LLM crawlers
- **Semantic HTML** — proper heading hierarchy (`h1` > `h2`), `aria-label` on sections
- **Open Graph + Twitter meta tags** — for social previews and agent extraction
- When adding new content, keep structured data in sync (update JSON-LD, resume.json, and llms.txt)

## Conventions

- Keep the site as plain static HTML — no build step, no bundler, no framework
- Maintain visual consistency: monospace typography, minimal aesthetic, light/dark support
- New pages should reuse the same header/footer pattern and CSS variables
- Blog posts currently link to `#` — future posts will be individual HTML files
- When updating personal info, update it in all locations: index.html (visible + JSON-LD), resume.json, and llms.txt
