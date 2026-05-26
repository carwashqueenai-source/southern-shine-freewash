# Southern Shine — Free Wash landing page

Static landing page deployed to Netlify at
**https://freewash.southernshineexpresswash.com/**.

This is the dedicated landing page for the Free Wash ad campaigns (Meta + Google
Ads). It's intentionally a **separate Netlify site / repo** from the Pollen
Season landing page (`~/dev/southern-shine-landing/`) so the two campaigns can
be deployed and rolled back independently.

## Architecture

- `index.html` — the landing page (was `freewash.html` in the Pollen repo)
- `style.css` — shared design tokens (copied from Pollen repo, kept in sync manually)
- `images/logo.png` — Southern Shine oval logo

## Form posts to

`https://southern-shine-crm.onrender.com/api/text-club/signup` —
CORS-allowed origins are defined in
`southern-shine-app/app.py` → `_PUBLIC_LANDING_ORIGINS`.

## Tracking

- Meta Pixel `26802423279384269` fires `Lead` event on submit
- Google Ads `AW-18036476522` fires conversion `uPv4CMD1jqgcEOqUu5hD` on submit
- UTM / gclid / fbclid attribution captured to `sessionStorage` (first-touch wins)
  and forwarded to the CRM with every submission

## Locations

The form accepts redemptions at all 3 SS locations (CEDAR / SPAR / BENTON).
Ad campaigns themselves only drive traffic to CEDAR + SPAR — BENTON Free Wash
is permanently paused (graduated to mature site). Organic / direct visitors
can still redeem at BENTON.

## Deploy

Auto-deploys from the `main` branch on every push.
