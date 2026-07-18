# Mkahawa — Restaurant Website

A warm, image-led one-page website for **Mkahawa**, a neighborhood Kenyan kitchen run by Josh & Aisha. Built as a single self-contained HTML file covering the full customer journey — hero, story, menu, gallery, hours, and reservations.

## Project Description

Mkahawa's site is designed to sell the food first and the space second, then make it dead simple to find and book a table. It's a single `Mkahawa.html` file with all CSS and JavaScript inlined, so it can be opened directly in a browser or dropped onto any static host with zero setup.

**Sections included:**
1. Hero — full-bleed image, name, tagline, primary CTAs
2. About — the restaurant's story and philosophy
3. Menu Preview — signature dishes with imagery + category pills
4. Full Menu — tabbed, scannable "order ticket" cards by Breakfast / Lunch / Dinner / Drinks
5. Signature Dishes — editorial spread on ingredients and seasonality
6. The Space — photo gallery of the dining room, bar, and grill
7. Visit Us — address, hours, phone, embedded map, parking/access notes
8. Reservations — booking form + walk-in/group/private dining notes
9. What's Happening — recurring events and specials
10. Newsletter + Footer

**Stack:** plain HTML5, CSS (custom properties, no framework), vanilla JS (tab switching, mobile nav, scroll header state). Font is Google Fonts' Lato; imagery is hotlinked from Unsplash as placeholders.

## Diagram / Preview

```
┌─────────────────────────────┐
│  Sticky Nav                 │
├─────────────────────────────┤
│  Hero (full-bleed image)    │
├─────────────────────────────┤
│  About        │  About image│
├─────────────────────────────┤
│  Menu Preview (4-up grid)   │
├─────────────────────────────┤
│  Full Menu (tabbed tickets) │
├─────────────────────────────┤
│  Signature Dishes (editorial│
│  image grid)                │
├─────────────────────────────┤
│  The Space (photo gallery)  │
├─────────────────────────────┤
│  Visit Us       │    Map    │
├─────────────────────────────┤
│  Reservations (form)        │
├─────────────────────────────┤
│  What's Happening (events)  │
├─────────────────────────────┤
│  Newsletter                 │
├─────────────────────────────┤
│  Footer                     │
└─────────────────────────────┘
```
Open `Mkahawa.html` in a browser to see the actual rendered layout — there's no separate diagram/image asset in this repo yet. If you add real photography, a good next step is dropping a `/screenshots` folder in here with a full-page capture for anyone browsing the repo on GitHub.

## Installation Instructions (for users)

No build tools, no `npm install`, no server required.

1. Download or clone the project folder.
2. Locate `Mkahawa.html`.
3. Double-click it, or open it in any modern browser (Chrome, Firefox, Safari, Edge).

**To host it live**, upload `Mkahawa.html` to any static host and point your domain at it — for example:
- Drag-and-drop onto [Netlify Drop](https://app.netlify.com/drop)
- Push to a GitHub repo and enable **GitHub Pages**
- Upload via FTP/SFTP to any standard web host

No environment variables, database, or backend are required for the site to render.

## Instructions for Contributors

1. Fork or clone the repository.
2. Make your changes directly in `Mkahawa.html` — all markup, styles, and scripts live in that one file.
3. Test by opening the file locally in a browser; check both desktop and mobile widths (the layout has a breakpoint at `900px` and `560px`).
4. Keep the three layers organized as you edit:
   - `<style>` block in `<head>` — all CSS, using the `:root` custom properties for color/spacing
   - HTML body — organized top to bottom by section, each with a clear `id`
   - `<script>` block near the bottom — nav toggle, scroll state, menu tab switching
5. Open a pull request describing what changed and why. Include a screenshot if the change is visual.

## How to Tweak This Project for Your Own Use

This template is easy to reskin for a different restaurant, cuisine, or brand:

- **Colors:** edit the CSS custom properties at the top of the `<style>` block (`--white`, `--chili`, `--char`, `--gold`, `--cream`, `--ember`). Every color in the site references these variables.
- **Font:** swap the Google Fonts `<link>` tags and the `font-family` value in `body{}` to change typography sitewide.
- **Copy:** all restaurant name, tagline, story, and menu text is plain HTML — search and replace directly in the file.
- **Menu items:** each dish is a `.dish-card` (preview grid) or `.ticket` (full menu). Copy an existing block and edit the name, description, price, and tag to add a new item.
- **Images:** every `<img>` has a direct `src` URL and descriptive `alt` text — replace the URLs with your own photography (hosted anywhere) or local image paths.
- **Map:** the embedded map in the Visit Us section uses a generic Google Maps embed URL — replace the `q=` parameter with your real address, or swap in your own map embed code.
- **Sections:** every section is a `<section>` with its own `id` and class — delete or reorder sections by cutting/pasting whole blocks; update the nav links to match.

## Expectations from Contributors

- Keep the site framework-free and dependency-free unless there's a strong reason to add one — the point of this project is that anyone can open and edit a single file.
- Preserve accessibility basics: meaningful `alt` text on images, working keyboard navigation, and sufficient color contrast against the chili-red/cream/ember palette.
- Test responsive behavior before submitting — the layout should hold up from small phones to wide desktops.
- Don't hardcode real personal data (phone numbers, addresses) in example/demo commits — use placeholders unless you're deploying a real instance.
- Match the existing code style: 2-space indentation, BEM-ish flat class names, CSS custom properties over hardcoded colors.

## Known Issues

- **Placeholder imagery:** all photos are hotlinked from Unsplash for demonstration. They are not the restaurant's actual food or space and should be replaced with real photography before going live. Hotlinked images can also change or go offline since they're not hosted locally.
- **Forms are not wired to a backend:** the Reservation and Newsletter forms currently only show a confirmation `alert()` in the browser — no email, database, or booking service is connected yet.
- **Map is a placeholder:** the embedded map points to a generic search, not the restaurant's real address.
- **No CMS:** menu prices, hours, and events are hardcoded in HTML. Frequent updates (e.g., weekly specials) require editing the file directly rather than through an admin panel.
- **Single-file structure:** great for portability, but as the site grows, splitting CSS/JS into separate files may become worth the added complexity.
