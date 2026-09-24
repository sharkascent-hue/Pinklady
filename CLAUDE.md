# Pink Lady Cleaning — Website Rebuild Brief (for Claude Code)

Read this file first, then everything in `/content`, then look through `/reference/current-site-screenshots`.

## The job
Rebuild **pinklady.ie** from scratch as a fully custom-coded website (no WordPress, no page builder, no templates). Client owns the site outright as files.

The current site is a dated WordPress/Divi build that reads like a generic domestic cleaner (spring cleans, communion party cleans, end of tenancy). **The real business cleans high-end homes — mansions, penthouses, large luxury properties.** The new site must reposition them as a premium, discreet, trusted cleaning service for high-value homes in Dublin — while keeping the brand recognisable (logo, pink, "The cleaning company that cares").

Think: private housekeeping / estate care brand, not "cheap cleaners near me".

## Tech
- Plain HTML + CSS + vanilla JS (or Astro/static if you prefer — must output static files)
- Mobile-first. Current traffic is clearly mobile (screen recording is from an iPhone)
- Fast: optimised images (WebP/AVIF, lazy loading), no heavy libraries
- Subtle, premium motion only (fade/rise on scroll, slow image zoom in hero). Nothing gimmicky
- Contact/quote form → wire up to a simple endpoint (Formspree / Web3Forms / Netlify Forms — leave a clear `TODO` with where to put the key)
- Click-to-call and WhatsApp buttons on mobile (sticky bottom bar)
- SEO: unique titles/meta per page, LocalBusiness + CleaningService JSON-LD schema, sitemap.xml, robots.txt, Open Graph tags
- GDPR: cookie notice only if analytics added; privacy policy page must exist

## Brand
- Logo: `/assets/logo/pinklady-logo-transparent.png` (white removed from the original JPG — check edges; if rough, ask Angelo for the vector/original file). Original in same folder.
- Brand pink (sampled from logo): **#CC4484**
- Logo grey text: **#494949**
- Current site also uses a hot magenta `#C8177A`-ish and bright stripe graphics (orange/mint) — **drop the stripes**, they look cheap
- New palette suggestion (keep the pink, make it feel expensive):
  - Pink `#CC4484` — accents, buttons, small details only (not full pink sections everywhere)
  - Deep ink / charcoal `#1C1A1E` — headings, dark sections
  - Warm ivory `#FAF7F3` — main background
  - Soft blush `#F6E6EE` — section tints
  - Muted gold/champagne `#B8986A` — very sparing, thin lines/icons
- Type: elegant serif for headings (e.g. Cormorant Garamond, Playfair Display) + clean sans for body (e.g. Inter, Manrope). The logo's script font stays in the logo only
- Photography: bright, airy luxury interiors — marble, big windows, staircases, penthouse views, spotless kitchens. No stock photos of people in rubber gloves grinning. Use Unsplash placeholders and list every image in `IMAGES_TODO.md` so Angelo can swap in real ones

## Sitemap (new)
1. **Home**
2. **Services** (overview) + individual pages:
   - Luxury Home Cleaning (regular / housekeeping)
   - Deep Cleaning (one-off)
   - Pre & Post Event Cleaning
   - Move-In / Move-Out Cleaning
   - After Builders & Renovation Cleaning
   - Carpet, Rug & Upholstery Cleaning
   - Office & Commercial Cleaning (keep — they do it, but lower priority)
3. **About / Our Story**
4. **Areas We Serve**
5. **Reviews**
6. **Request a Quote** (main conversion page)
7. **Contact**
8. **Privacy Policy**, **Terms**

Keep URLs close to existing ones where possible for SEO (see `content/current-site-copy.md` for old page names) and add 301 redirect notes in `REDIRECTS.md`.

## Home page structure
1. Top bar: phone + email (small, like now)
2. Nav: logo left, links, "Request a Quote" button
3. **Hero**: full-bleed luxury interior image/video, headline e.g. "Exceptional care for exceptional homes", sub "Discreet, meticulous cleaning for Dublin's finest homes since 2006", two CTAs (Request a Quote / Call Margaret)
4. Trust strip: Since 2006 · Family-run · Fully vetted team · Dublin-wide (only use claims listed in `content/business-info.md` — flag anything else as TODO)
5. Intro / positioning paragraph
6. Services grid (cards with image, short line, link)
7. "The Pink Lady Standard" — how they work (consultation → tailored checklist → same trusted team → final inspection)
8. Discretion & trust section (vetted staff, confidentiality, care with fine finishes) — see TODOs
9. Reviews carousel (Google reviews)
10. Areas served
11. Quote CTA band
12. Footer: address, phone, email, links, socials TODO, legal

## Quote form fields
Name · Email · Phone · Property type (House / Penthouse / Apartment / Estate / Office) · Approx. size (bedrooms or sq ft) · Area · Service needed (multi-select) · One-off or regular · Preferred date · Message · Consent checkbox

## Rules
- Do NOT invent stats, awards, insurance cover, number of clients, or review quotes. Use only what's in `/content`. Put `<!-- TODO: confirm with client -->` where something needs confirming
- Copy tone: calm, confident, understated luxury. No exclamation marks, no "!!!", no "you get the gist"
- British/Irish English spelling (colour, organised, specialise)
- Accessibility: proper contrast (pink on white for small text fails — use ink for body text), alt text, focus states, semantic HTML

## Deliverables
- Complete static site in `/site`
- `IMAGES_TODO.md`, `REDIRECTS.md`, `CLIENT_QUESTIONS.md` (everything that needs confirming)
