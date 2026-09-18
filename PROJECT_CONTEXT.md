# TapIQ — Project Context (handoff)

A one-page brief so any AI assistant or developer can pick this up with full context.

## What it is
**TapIQ** — a local **San Diego drinking-water screening & filter guidance** service for
renters, families, and bottled-water users. Tagline: *"Test your tap. Find your filter."*
The core product is a **same-day in-home water screening** that produces a plain-English
**water analysis report** and an honest filter recommendation (which may be "you don't need one").

Founder: **Eduardo Martinez**, water scientist (6+ yrs, global water-treatment experience).

## Live URLs
- Site: **https://tapiqwater.com**
- Example report: **https://tapiqwater.com/report.html** (add `?tier=starter|kit|advanced`)
- Repo (public): **https://github.com/21eddiemartinez-lab/TapIQ**

## Tech stack
- **Plain standalone HTML** — no framework, no build step, no bundler.
- Two pages: `index.html` (landing) and `report.html` (customer deliverable, JS-rendered
  from a `REPORTS` data object at the bottom of the file).
- Vanilla `<script>` blocks; a `<canvas>` globe on the landing hero (pure JS).
- Google Fonts only. All other assets local in `assets/`.
- Hosted on **GitHub Pages**; every `git push` to `main` auto-deploys in ~1 min.
- Custom domain via `CNAME` file + DNS at Network Solutions. `.nojekyll` present.

## File structure
```
index.html        landing page
report.html       example water analysis report (3 tiers via tabs)
assets/
  tapiq-mark.png        drop logo mark (nav/footer/favicon)
  tapiq-logo-light.png  full wordmark lockup, dark text (light bg)
  tapiq-logo-dark.png   full wordmark lockup, white text (dark bg)
  og-image.png          1200x630 social share card
CNAME, .nojekyll  GitHub Pages config
```

## Design system — "Bold Utilitarian" (do not drift from this)
- **Palette:** ink `#101010`, bone `#F2F1EC` / `#E7E5DB`, brand **blue** `#1668D8`
  (bright `#3B9BF5`, dark `#0E4FA8`), vermilion accent `#E4572E` (sparing).
  Semantic status (report only): good `#0F7A3D`, watch `#A65A0B`, action `#B4231C`.
- **Type:** Archivo Expanded (display, heavy), Archivo (body), Archivo Narrow (labels),
  IBM Plex Mono (report data readouts).
- **Rules:** flat color blocks, **2px hard black borders, zero border-radius**, offset
  "hard shadows" (`5px 5px 0`). **No gradients, no glows, no glassmorphism, no emoji icons,
  no rounded pill badges, no em-dashes in copy.** Design tokens live in `:root` in each file's
  `<style>` (note: the token names still read `--teal*`/`--sky*` but hold blue values).

## Key features
- Hero **canvas globe**: dotted lat/long sphere, people-nodes light up blue as connections
  complete, then smoothly resets and loops. Respects `prefers-reduced-motion`.
- Sections: Hero, Problem, **Bottled-water savings band** (~$1,000/yr), Service (Clean Water
  Starter Kit), Packages (3 tiers, "See a sample report" links), How It Works, Why TapIQ,
  **Founder**, FAQ, Lead form, Footer.
- **Lead form → Formspree** (`https://formspree.io/f/mwledqol`), AJAX submit, emails to
  `hello@tapiqwater.com`. Keeps branded success state + error fallback.
- **Mobile hamburger menu**, Open Graph/Twitter share tags, SEO titles.
- Report tiers: Starter Check ($49–$79), Clean Water Starter Kit ($149), Advanced Water
  Profile (Custom, adds a certified-lab results table). Each has a savings estimate.

## Email
Google Workspace on `tapiqwater.com`; MX = `smtp.google.com` (priority 1).
Public address: `hello@tapiqwater.com`.

## How to edit & deploy
1. Edit `index.html` / `report.html` directly (report copy/prices live in the `REPORTS`
   object and the `PACKAGES`/price markers — search `UPDATE ... HERE`).
2. `git add -A && git commit -m "..." && git push` → live in ~1 min.
> An external AI (e.g. ChatGPT) can READ the public repo and live site but cannot push.
> Its workflow: it proposes edited code → you paste it into the file → commit & push.

## Open / optional (not blockers)
- Founder headshot (currently an "EM" monogram placeholder — swap into `.founder-portrait`).
- Privacy one-liner near the lead form.
- Instagram / social links in footer.
- Planned: a **"San Diego Water, Explained"** page using real, cited Consumer Confidence
  Report (CCR) data from local providers (City of SD, Sweetwater, Helix, Otay, etc.).
  Rule: never publish an un-sourced number; cite source + year; educational tone.
