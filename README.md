# Pink Lady — Claude Code handoff pack

Unzip, open the folder in Claude Code, and say:

> Read CLAUDE.md and everything in /content and /reference, then build the site in /site.

## What's in here
- `CLAUDE.md` — full build brief (positioning, design, sitemap, tech, rules)
- `content/business-info.md` — verified facts, contact details, areas, questions for the client
- `content/current-site-copy.md` — everything transcribed from the current pinklady.ie (from the screen recording)
- `content/new-copy.md` — draft luxury copy for every page
- `assets/logo/` — original logo JPG + transparent PNG (auto-cut, check edges)
- `reference/current-site-screenshots/` — 17 frames from the recording (current site, mobile)

---

## The built site (`site/`)
Plain static HTML/CSS/JS with no framework and no runtime dependencies. Upload the contents of `site/` to any host (Netlify, Cloudflare Pages, GitHub Pages, Apache).

- **Edit copy:** everything lives in `build.mjs`. Run `node build.mjs` (Node 18+) to regenerate every page, plus `sitemap.xml`, `robots.txt` and `site.webmanifest`.
- **Styles / motion:** `site/assets/css/style.css`, `site/assets/js/main.js` (hand-written, not generated).
- **Fonts:** Cormorant Garamond + Manrope, self-hosted in `site/assets/fonts` (no Google Fonts calls, so no GDPR concern).
- **Before launch:** see `CLIENT_QUESTIONS.md`, `IMAGES_TODO.md`, `REDIRECTS.md`, and search `build.mjs` for `TODO`.

### Motion
- **Intro** (first visit per browser session): the logo's circle opens, the "Pink Lady" script is written across, then an ivory curtain lifts to reveal the hero. Click anywhere to skip.
- **Hero:** photo settles from a slight zoom into a slow Ken Burns drift. The headline rises word by word from behind a mask.
- **Scroll:** fade/rise reveals, curtain-wipe image reveals, staggered lists, gold rules drawing in, a count-up of years since 2006, a "Pink Lady Standard" timeline that fills as you scroll, eased parallax, and an areas marquee.
- **Chrome:** header goes frosted on scroll and hides on scroll down, returning on scroll up. Also a pink reading-progress hairline, a full-screen mobile menu with staggered links, a mobile Call/WhatsApp/Quote bar, fill-sweep and (on desktop) magnetic buttons.
- **Page changes:** cross-document View Transitions (Chrome/Edge/Safari 18.2+), with a fade fallback elsewhere.
- **Reduced motion:** all of it switches off under `prefers-reduced-motion`.
