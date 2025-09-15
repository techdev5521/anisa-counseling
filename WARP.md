# WARP.md

This file provides guidance to WARP (warp.dev) when working with code in this repository.

## Project Overview

This is the website for Anisa Counseling Group in West Lafayette, Indiana. It's built using Astro 5 with TailwindCSS 4 for styling and uses TypeScript with strict configuration.
The website should be responsive, have an automatic light and dark mode switch via CSS and be themes with earth tones.

## Development Commands

### Core Development
```bash
npm run dev       # Start development server at http://localhost:4321
npm run build     # Build for production (outputs to dist/)
npm run preview   # Preview production build locally
```

### Astro CLI
```bash
npm run astro     # Access Astro CLI directly
npx astro add     # Add integrations (e.g., npx astro add react)
```

## Architecture Overview

### Project Structure
- **`src/pages/`** - File-based routing. Each `.astro` file becomes a route
- **`src/components/`** - Reusable Astro components
- **`src/styles/`** - Global styles and CSS imports
- **`public/`** - Static assets served directly (images, favicon, etc.)
- **`dist/`** - Production build output (generated)

### Key Files
- **`src/components/Page.astro`** - Base layout component that wraps all pages
- **`src/siteDetails.json`** - Site configuration and metadata
- **`src/styles/global.css`** - Global styles with TailwindCSS import
- **`astro.config.mjs`** - Astro configuration with TailwindCSS Vite plugin

### Technology Stack
- **Astro 5** - Static site generator with island architecture
- **TailwindCSS 4** - Utility-first CSS framework (integrated via Vite plugin)
- **TypeScript** - Type checking with strict configuration extending `astro/tsconfigs/strict`

### Component Architecture
The project follows a simple layout pattern:
1. **Base Layout**: `Page.astro` provides the HTML structure, imports global styles, and uses site configuration from `siteDetails.json`
2. **Pages**: Individual pages import and wrap content in the `Page` component
3. **Slot Pattern**: Components use Astro's slot system for content composition

### Configuration Notes
- TailwindCSS is integrated via the Vite plugin rather than as an Astro integration
- TypeScript configuration extends Astro's strict preset
- No additional integrations or frameworks are currently installed

### Development Patterns
- Site-wide configuration is centralized in `src/siteDetails.json`
- Global styles are imported through the base `Page` component
- Static assets go in `public/` and are served from the root path
- All pages should use the `Page` component wrapper for consistency