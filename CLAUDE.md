# CLAUDE.md

This file provides guidance to Claude Code (claude.ai/code) when working with code in this repository.

## Project Overview

This is a static website for Agence SAGIR, a personnel placement agency specializing in early childhood education services and senior residences in Quebec. The site is hosted on GitHub Pages with a custom domain (new.agencesagir.com).

## Architecture

**Single-page HTML with embedded CSS**: The main landing page ([index.html](index.html)) contains all styles in a `<style>` tag within the `<head>`. There are no external CSS files or JavaScript frameworks.

**Navigation structure**:
- Main navigation bar with logo (images/logo.jpg) in top-left
- Dropdown menus for "Intervenant(e)s", "Gestionnaires", and "Qui sommes nous?"
- Links to contact.html for contact functionality
- Sticky navigation that remains visible on scroll

**Page sections** (in order):
1. Top bar with phone/email contact info
2. Main navigation with logo
3. Hero section (split: left text, right service cards)
4. About section with stats
5. Trust badges section
6. Services overview (2-column grid)
7. How it works (4-step process)
8. Why choose us section
9. CTA section with contact buttons

**Color scheme**:
- Primary blue: #002B5C (main brand color)
- Secondary green: #7CB342 (early childhood services)
- Secondary teal: #00838F (senior residences)
- Neutral backgrounds: #f8f9fa, white

**Images**:
- Logo: images/logo.jpg (used in navigation at 50px height)
- Service card images use Unsplash URLs embedded in CSS
- Icons are emoji characters

## Key Implementation Details

**CSS organization**: Styles are organized by section with clear comments (e.g., `/* Navigation Menu */`, `/* Hero Section */`). Mobile responsive breakpoints at 968px and 768px.

**Logo usage**: The navigation uses `<img src="images/logo.jpg">` with CSS styling `.nav-logo img { height: 50px; width: auto; }`. Do not use text-based logos in the navigation.

**Language**: All content is in French (lang="fr").

## Development Workflow

**Testing locally**: Open index.html directly in a browser, or use a local server:
```bash
python -m http.server 8000
# Visit http://localhost:8000
```

**Deployment**: The site auto-deploys via GitHub Pages when changes are pushed to the main branch. Custom domain configured via CNAME file.

**Git workflow**:
```bash
git add .
git commit -m "Description"
git push origin main
```

## File Structure

- `index.html` - Main landing page (all-in-one with embedded CSS)
- `contact.html` - Contact page placeholder (content to be added)
- `images/logo.jpg` - Company logo
- `CNAME` - GitHub Pages custom domain configuration
- `.gitignore` - Excludes .claude/ directory from version control
