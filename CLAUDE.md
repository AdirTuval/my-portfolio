# CLAUDE.md

This file provides guidance to Claude Code (claude.ai/code) when working with code in this repository.

## Commands

All commands use `pnpm` from the project root:

- `pnpm dev` — start dev server at `localhost:4321`
- `pnpm build` — build production site to `./dist/`
- `pnpm preview` — preview the production build locally
- `pnpm astro check` — run TypeScript and Astro diagnostics

## Architecture

This is an [Astro 5](https://astro.build) static site using the basics starter template, intended to become a personal portfolio. TypeScript is configured in strict mode via `astro/tsconfigs/strict`.

**Routing:** Astro uses file-based routing. Files in `src/pages/` map directly to URL routes. Currently only `index.astro` exists (the homepage).

**Component model:** Astro components (`.astro`) have a frontmatter fence (`---`) for server-side logic/imports, followed by HTML template. Scoped CSS goes in a `<style>` block at the bottom of the file. No JavaScript framework (React, Vue, etc.) is integrated yet.

**Data flow:** `src/layouts/Layout.astro` wraps pages via `<slot />`. Pages import and compose components from `src/components/`. Static assets (SVGs, images) live in `src/assets/` and are imported directly into components for processing by Astro's asset pipeline.

No integrations, content collections, or server-side rendering are configured — `astro.config.mjs` is currently empty.
