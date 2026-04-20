# HANGOVR 180 — Brand Site

**Live URL:** Deployed on Vercel
**Version:** 5.3
**Last updated:** April 20, 2026

## Changelog

### 5.3 (April 20, 2026)

**All pages with hero images — Landscape Phone Fix**
- Bumped landscape hero `min-height` from `50vh`/`40vh` to `80vh`/`70vh` on index, doa180, whos-in, inside, find-us
- Stock-up unchanged (text-only hero, no image)
- Fixes hero framing on iPhone landscape where images were too short to tell the story

### 5.2 (April 19, 2026)

**inside.html — Clinical Ingredient Cards**
- Rewrote card scaling system: cards are content-height stacked columns below 1200px, square 3-col grid at 1200px+
- Added `min-width: 0` on grid children to prevent overflow
- Capped `.clinical__name` at `2.75rem` max so "FULVIC ACID" stays on one line at all widths
- Removed `overflow: hidden` — `aspect-ratio: 1` acts as minimum, cards grow if content needs it
- Added font-size math documentation to PROJECTNOTES.md

**inside.html — Product/Protocol Section**
- Changed image from `min-height: 24rem` to `max-height: 24rem` when stacked (mobile)
- Brought side-by-side layout from 1400px down to 768px
- Image and text visible together across nearly all viewport widths

**inside.html — Real Science Section**
- Centered content vertically: equalized padding to `6rem` all around (was 4rem top / 6-8rem bottom)

**whos-in.html — Identity Section (S2)**
- Moved CTA button below both columns, centered — eliminates height mismatch between left and right text blocks
- Changed grid from `align-items: center` to `align-items: start` — both text blocks share top edge
- Bumped headline font to `clamp(2.5rem, 5.5vw, 3.75rem)`
- "Tomorrow People know" restyled as uppercase label (0.875rem → clamp(1.5rem, 3vw, 2rem), 900-weight, tracked)
- Dropped all italic from body text — uses weight contrast instead (500 base, 700 strong)
- Bumped body font to `clamp(1.375rem, 2.5vw, 1.625rem)`

**whos-in.html — Copy Changes**
- Body text: "The smart move is: If you are doing UBER later, Do a 180 now."
- Body text: "That's how you be the one who shows up for everything"
- Sarah quote: "SHE'S MY LITTLE ALARM CLOCK, BUT LOUDER!"
- Dr. Fumi quote: "I QUESTION EVERYTHING, THIS ONE WAS SO EASY."

**index.html — Hero Section (S1)**
- Changed `object-position` from `center left` to `50% 25%` — anchors vertically toward the top to prevent head cropping at ultrawide viewports
- Landscape override set to `50% 35%`
- Mobile portrait uses a separate image file via `<picture>` source swap, so `object-position` only affects desktop/tablet views

**index.html — Tension Section (S2)**
- Restructured from 2-col grid to flex layout: headline + image in `.tension__top` row
- Added JS font-fitter: binary-searches for largest font size that fills container without overflow (768px+ only)
- Image square at 35% width on desktop, 4:3 full-width on mobile
- Sub text `max-width: calc(65% - 3rem)` aligns right edge with image left edge
- Headline scaled to `clamp(3.5rem, 12vw, 4.5rem)` for equal visual weight with image on mobile
- Padding set to `3rem` on mobile matching pack section rhythm
- Removed "But" from sub text: "We're still looking to keep the life we love..."

**index.html — Pack Section (S3)**
- Removed `<picture>` mobile source — always uses desktop image
- Changed to `object-fit: cover` with `object-position: center top`
- Mobile: `max-height: 20rem`, square removed
- Desktop: image fills grid row height set by text content

**index.html — Email Section (S4)**
- Changed to "Austin, in the whole country," / "we tell you first." with weight ramp on second line
- "we tell you first." set to 800-weight transitioning into headline

**Global — Em Dash Removal**
- Replaced all `&mdash;` with `-` across whos-in.html and find-us.html
- Rule: no em dashes in any visible content, regular hyphens only

**Global — Footer Trademark**
- Added `®` symbol next to footer logo on all six pages
- Styled via `.footer__tm` in global.css: yellow, 2rem, 900-weight, top-aligned

**doa180.html — Review Card Stars**
- Removed `overflow: hidden` from `.review-card__stars` — was clipping the 5th star on narrow mobile
- Replaced with `flex-wrap: wrap` for safety

**New: PROJECTNOTES.md**
- Added project knowledge base with brand system reference, responsive text-in-box scaling method, image scaling patterns, Montserrat character width reference, and punch list tracking

### 5.1 (April 18, 2026)
- Fixed Category 3 image references to use -desktop/-mobile variants matching repo filenames

### 5.0
- Initial release

## Overview
Static marketing site for HANGOVR 180, a pre-alcohol supplement brand based in Austin, TX.

## Tech Stack
- Static HTML/CSS (no framework, no build tools)
- Font: Montserrat (Google Fonts)
- Hosting: Vercel (auto-deploys from this repo)
- Images: WebP with `<picture>` art direction
- JS: Font-fitter on index.html tension headline (vanilla, no dependencies)

## Button System
- `.btn-cta-light` — red CTA on light backgrounds, hovers to dark/yellow
- `.btn-cta-dark` — red CTA on dark backgrounds, hovers to yellow/dark
- `.btn-signup` — black/yellow default, red/white hover (signup + cart forms)
- `.card__btn` — full-width black/yellow, red/white hover (product cards)

## Deployment
Push to main branch. Vercel auto-deploys. No vercel.json.
