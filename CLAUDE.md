# CLAUDE.md

This file provides guidance to Claude Code (claude.ai/code) when working with code in this repository.

## Commands

```sh
npm run dev       # Start dev server at localhost:4321
npm run build     # Build production site to ./dist/
npm run preview   # Preview production build locally
npm run astro ... # Run Astro CLI commands (e.g., astro add, astro check)
```

## Architecture

This is an **Astro 6** static site for **NEXO Estudio**, a Spanish-language digital production agency.

**Structure:**
- `src/layouts/Layout.astro` — Base HTML shell; accepts `title` and optional `description` props; imports global CSS and Google Fonts (Inter + Outfit)
- `src/components/` — Reusable Astro components (Navigation, Hero, etc.)
- `src/pages/index.astro` — Single-page layout composing Navigation, Hero, and inline section content
- `src/styles/global.css` — All shared design tokens and utility classes (no CSS framework)

**Design system (CSS custom properties in `global.css`):**
- Dark theme: `--color-bg: #050801`, primary emerald `--color-primary: #10b981`, accent amber `--color-secondary: #f59e0b`
- Fonts: `--font-sans` (Inter) for body, `--font-display` (Outfit) for headings
- Utility classes: `.glass` (glassmorphism cards), `.container` (max-width `--layout-max-width` 1480px), `.section` (vertical padding; anchor offset via `scroll-padding-top` on `html` only), `.section-title`/`.section-subtitle` (global), `.btn`/`.btn-primary`/`.btn-outline`, `.text-gradient`, `.animate-in`

All component-scoped styles live in `<style>` blocks within each `.astro` file. Global/shared styles belong in `src/styles/global.css`.

The site is Spanish-language (`lang="es"`) with sections: Inicio (Hero), Servicios, Proyectos, Contacto.
