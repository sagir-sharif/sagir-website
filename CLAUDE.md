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
10. Footer with permit number

**Color scheme**:
- Primary blue: #002B5C (main brand color)
- Secondary green: #7CB342 (early childhood services)
- Secondary teal: #00838F (senior residences)
- Neutral backgrounds: #f8f9fa, white

**Images**:
- Logo: images/logo.jpg (used in navigation at 50px height)
- Service card images: CPE uses Unsplash URL, Résidences uses images/residences.jpg
- Icons are emoji characters

**Footer**: All pages include a footer with the agency permit number (AP-2103464). The footer uses:
- Background: #f8f9fa
- Border-top: 1px solid #e0e0e0
- Text: "Numéro de permis: AP-2103464" in brand color (#002B5C)
- Centered layout with 24px vertical padding

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

- `index.html` - Main landing page with service cards linking to landing pages
- `cpe-landing.html` - CPE (early childhood services) landing page with navigation
- `residence-aines.html` - Senior residences landing page (no navigation menu)
- `contact.html` - Contact page with form, contact info, and map placeholder
- `images/logo.jpg` - Company logo
- `images/residences.jpg` - Background image for residence service card
- `CNAME` - GitHub Pages custom domain configuration (new.agencesagir.com)
- `.gitignore` - Excludes .claude/ directory from version control

## Important Standards

**Permit number footer**: ALL pages must include the footer with permit number AP-2103464. When creating new pages, always add:
```html
<!-- Footer -->
<footer class="footer">
    <div class="footer-content">
        <p class="footer-permit">Numéro de permis: AP-2103464</p>
    </div>
</footer>
```

And the corresponding CSS:
```css
/* Footer */
.footer {
    background: #f8f9fa;
    padding: 24px 40px;
    text-align: center;
    border-top: 1px solid #e0e0e0;
}

.footer-content {
    max-width: 1400px;
    margin: 0 auto;
    color: #666;
    font-size: 14px;
}

.footer-permit {
    font-weight: 500;
    color: #002B5C;
}
```
