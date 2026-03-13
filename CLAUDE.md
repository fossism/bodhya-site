# CLAUDE.md

This file provides guidance to Claude Code (claude.ai/code) when working with code in this repository.

## Project Overview

Bodhya is a static website built with **Zola** (Rust-based SSG, v0.21.0), deployed on Netlify. It serves two purposes: creating tech opportunities for Bihar students, and offering consulting services for non-profit organizations.

## Common Commands

```bash
# Install Zola (macOS)
brew install zola

# Serve locally with live reload at http://localhost:1111
zola serve

# Build for production (outputs to public/)
zola build
```

There is no package.json, Makefile, or test suite — Zola is the only build tool.

## Architecture

### Template System
Templates use Zola's Tera syntax (Jinja2-like) with block inheritance from `base.html`:

- `templates/base.html` — master layout: sticky header, mobile nav, footer, and **all CSS embedded inline** in a `<style>` tag
- `templates/index.html` — homepage with hero, feature cards, and narrative sections
- `templates/page.html` — generic wrapper for markdown content pages
- `templates/blog.html` / `blog-post.html` — blog listing and article views
- `templates/404.html` — error page

### Content
Markdown files in `content/` with TOML frontmatter. Key pages: `_index.md` (homepage), `about.md`, `join.md`, `consulting.md`. Blog posts live in `content/blog/`, project pages in `content/projects/`.

### Static Assets
`static/` contains images, SVG logos, `main.css`, and `mobile-menu.js` (hamburger menu toggle). The main logo is `static/bodhya-brown.svg`.

### Configuration
- `config.toml` — Zola config: base URL, title, taxonomies (tags, categories), feed generation
- `netlify.toml` — deploy command (`zola build`), publish dir (`public/`), Zola version pin

## Brand & Design

- **Primary color:** `#AD544B` (terracotta)
- **Background:** `#FFF8F3` (floral white)
- **Display font:** Funnel Display (variable, 300–800 weight)
- **Mobile breakpoint:** 768px — desktop nav hidden, replaced by dialog-based slide-in hamburger menu

## CSS Approach

All styles live in the `<style>` block inside `templates/base.html`. `static/main.css` exists but the primary styles are embedded. `sass/` and `themes/` directories are present but empty.

## CI/CD

Two GitHub Actions workflows in `.github/workflows/`:
- `claude.yml` — responds to `@claude` mentions in issues/PRs
- `claude-code-review.yml` — auto-runs Claude code review on every PR

Both require `ANTHROPIC_API_KEY` secret set in GitHub repository settings.

## License

CC BY SA — attribution required, derivatives must share under same license.
