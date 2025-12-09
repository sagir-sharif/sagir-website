# CLAUDE.md

This file provides guidance to Claude Code (claude.ai/code) when working with code in this repository.

## Project Overview

This is a static website for Agence SAGIR, a personnel placement agency specializing in early childhood education services and senior residences in Quebec. The site is hosted on GitHub Pages with a custom domain (new.agencesagir.com).

## Architecture

**HTML with centralized CSS**: The website uses a hybrid CSS approach:
- **Common styles** are in `styles/common.css` - includes navigation, footer, buttons, top bar, and section headers
- **Page-specific styles** remain in each HTML file's `<style>` tag - includes hero sections, galleries, forms, cards, and unique layouts
- No JavaScript frameworks are used

**IMPORTANT**: When creating new pages or modifying existing ones:
1. Always link to `styles/common.css` in the `<head>` section: `<link rel="stylesheet" href="styles/common.css">`
2. Only add page-specific CSS to the `<style>` tag
3. Never duplicate CSS that already exists in common.css

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

**CSS organization**:
- **Common CSS** (`styles/common.css`): Contains universal reset, body styles, navigation, footer, buttons, top bar, section headers, and common responsive breakpoints (@media at 968px and 768px)
- **Page-specific CSS**: Each HTML file's `<style>` tag contains only unique styles for that page (hero sections, galleries, forms, cards, etc.)
- All styles are organized by section with clear comments (e.g., `/* Navigation Menu */`, `/* Hero Section */`)

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

### HTML Pages (13 total)
- `index.html` - Main landing page with service cards linking to landing pages
- `cpe-landing.html` - CPE (early childhood services) landing page
- `residence-aines.html` - Senior residences landing page
- `contact.html` - Contact page with form, contact info, and map
- `regions-desservies.html` - Regions served across Quebec
- `qui-sommes-nous.html` - About us page
- `emplois-cpe.html` - CPE employment opportunities
- `emplois-residences.html` - Residence employment opportunities
- `faq.html` - Frequently asked questions
- `conditions-travail.html` - Working conditions
- `conditions-affectation.html` - Assignment conditions
- `processus-embauche.html` - Hiring process
- `nouveautes.html` - News and updates

### CSS
- `styles/common.css` - **Centralized common styles** (navigation, footer, buttons, top bar, section headers, responsive breakpoints)

### Assets
- `images/logo.jpg` - Company logo
- `images/` - Various images for service cards, galleries, and page backgrounds

### Configuration
- `CNAME` - GitHub Pages custom domain configuration (new.agencesagir.com)
- `.gitignore` - Excludes .claude/ directory from version control
- `CLAUDE.md` - Development guidelines and project documentation

## Important Standards

**Common CSS inclusion**: ALL pages must link to the common stylesheet in the `<head>` section:
```html
<link rel="stylesheet" href="styles/common.css">
```

**Permit number footer**: ALL pages must include the footer with permit number AP-2103464. When creating new pages, always add:
```html
<!-- Footer -->
<footer class="footer">
    <div class="footer-content">
        <p class="footer-permit">Numéro de permis: AP-2103464</p>
    </div>
</footer>
```

Note: Footer CSS is in `styles/common.css` - no need to add CSS for standard footer elements.
