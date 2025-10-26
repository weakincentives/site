# WARP.md

This file provides guidance to WARP (warp.dev) when working with code in this repository.

## Project Overview

This is a static landing page for Weak Incentives, an open source project focused on developing and optimizing side effect free background agents. The repository contains a single-file website with no build system or dependencies.

## Repository Structure

This is a minimal static site repository with:
- `public/index.html` - Single page with embedded CSS
- `wrangler.toml` - Cloudflare Workers deployment configuration
- `LICENSE` - Apache License 2.0
- No package manager, build tools, or dependencies

## Development Commands

Since this is a static HTML site with no dependencies:

**Preview the site:**
```bash
# Using Python's built-in server (from project root)
python3 -m http.server 8000 -d public

# Or using PHP
php -S localhost:8000 -t public
```

Then open http://localhost:8000 in your browser.

**Deploy to Cloudflare Workers:**
```bash
npx wrangler deploy
```

The site is configured to deploy the `public/` directory via `wrangler.toml`.

## Architecture

This is a single-page static website with:
- **No JavaScript**: Pure HTML and CSS implementation
- **No build process**: Files can be deployed as-is
- **Embedded styles**: CSS is inline in the `<style>` tag within index.html
- **Responsive design**: Uses clamp() for fluid typography and viewport-based sizing
- **Dark theme**: Fixed dark background (#0a0a0a) with gradient text effects

## Code Style

When modifying `public/index.html`:
- Maintain the minimalist aesthetic with dark background and gradient text
- Use system font stack for performance
- Keep responsive design using clamp() and viewport units
- Preserve the fixed GitHub link in the top-right corner
- Follow the existing 4-space indentation for HTML and CSS
