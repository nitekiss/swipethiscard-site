# SwipeThisCard — marketing site

The public site for the SwipeThisCard app: landing page, support, privacy, and
terms. Static HTML, no build step, no server, no analytics — matches the
app's own privacy stance.

## Served files (repo root — Vercel serves these as-is)

- **`index.html`** — the landing page (`/`). Device claim: iPhone, iPad,
  Apple Watch, per D-170. Includes the Beta sign-up and "tell me when it
  ships" sections.
- **`support.html`** — served at `/support` (clean URL via `vercel.json`).
- **`privacy.html`** — served at `/privacy`. **Draft** — carries bracketed
  placeholders (legal entity name, jurisdiction, effective date) and a
  visible "not yet in effect" notice until those are filled in.
- **`terms.html`** — served at `/terms`. Same draft status as privacy.
- **`favicon.svg`** — the nav/footer brand mark, reused as the tab icon.
- **`robots.txt`** / **`sitemap.xml`** — crawler directives + sitemap.
- **`vercel.json`** — `cleanUrls: true` so `/support`, `/privacy`, `/terms`
  serve without the `.html` extension, matching the site's internal links.

Every page above is a full standalone document (own `<head>`, meta
description, canonical URL). There is no separate build step — edit the
HTML directly and commit.

## Deploy (Vercel, static — no build step)

1. Import this repo in Vercel → **Add New → Project → Import**.
2. Framework preset: **Other**. Build command: **none**. Output dir: repo
   root.
3. Deploy. Every push to `main` redeploys automatically.

## Domain

`swipethiscard.com` is registered and on Cloudflare nameservers. DNS has no
records yet — point it at the Vercel project (apex + `www`) once the
project exists, via the CNAME/A records shown in Vercel's
**Settings → Domains**.

## Still open

- Privacy/Terms bracketed placeholders — need Mehmet's word on legal entity
  name, jurisdiction, and effective date before the draft banner comes off.
