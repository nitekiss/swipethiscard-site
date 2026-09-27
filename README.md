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
- **`fonts/`** — Archivo and IBM Plex Mono, self-hosted (OFL 1.1, licences
  beside them) and declared in `fonts/fonts.css`, so a visit reaches no host
  but ours. The Privacy Policy (§9) says so; keep it true — no Google Fonts,
  CDNs or third-party scripts.
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

`swipethiscard.com` is registered, on Cloudflare nameservers, and live on
Vercel: `www` serves the site and the apex 308-redirects to it (check with
`curl -sL`). The card-facts catalog lives separately on Cloudflare Pages at
`swipethiscard.app/catalog/v1/`.

## Still open

- Privacy/Terms bracketed placeholders — need Mehmet's word on legal entity
  name, jurisdiction, and effective date before the draft banner comes off.
