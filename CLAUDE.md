# CLAUDE.md

This file provides guidance to Claude Code (claude.ai/code) when working with code in this repository.

## Project Overview

This is a static marketing website for SecondSet Wallet, an enterprise crypto treasury solution. The entire site is a single-page application built with vanilla HTML, CSS, and JavaScript - no build tools or frameworks required.

## Architecture

**Single-File Structure**: The entire website is contained in `index.html` with:
- Embedded CSS in `<style>` tags (lines 9-632)
- Embedded JavaScript in `<script>` tags (lines 972-998)
- All HTML structure (lines 634-1000)

**Design System**:
- CSS custom properties define the design tokens in `:root` (lines 16-33)
- Primary brand color: `#1DBFA4` (teal/turquoise)
- Gradient backgrounds and hover effects throughout
- Responsive breakpoints at 1024px and 768px

**Sections** (in order):
1. Navigation (fixed header with logo and links)
2. Hero section with CTA buttons
3. Features grid (6 feature cards)
4. How It Works (3-step process)
5. Security section (dark background, security features list)
6. Stats section (gradient background)
7. CTA section
8. Footer with links and social icons

## Development

**Local Testing**: Open `index.html` directly in a browser. No server required since there are no external dependencies or API calls.

**Assets**:
- Logo file: `assets/logo no text.png`
- Referenced in HTML as `logo_no_text.png` (line 639, 693, 913) - note the underscore vs space discrepancy

**Key Issues to Watch**:
- Logo file path inconsistency: file is named `logo no text.png` (with space) but referenced as `logo_no_text.png` (with underscore) in multiple places
- Duplicate feature heading at line 744 ("Instant Setup" followed immediately by "Real-Time Balances")
- Mobile menu toggle exists but nav menu visibility toggle is simplistic (lines 995-997)

## Deployment

Since this is a static site, deployment options:
- GitHub Pages
- Netlify/Vercel (drag-and-drop)
- Any static hosting service
- S3 + CloudFront

No build process needed - just upload the `index.html` and `assets/` folder.

## Maintenance Notes

**To modify styling**: Edit CSS custom properties in `:root` (lines 16-33) to update colors/gradients site-wide.

**To add sections**: Follow the existing pattern of section wrapper > container > content structure. Most sections use max-width: 1280px containers with 2rem padding.

**Responsive design**: Uses CSS Grid that collapses from multi-column to single-column layouts at breakpoints. Media queries start at line 563.
