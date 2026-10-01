# HCC Holiday Planner Landing Page

Static landing page for The Calm Mom Holiday Planner.

## GitHub upload
Upload `index.html`, the `assets` folder, and this `README.md` to the root of the GitHub repository.

## Vercel
Import the GitHub repository into Vercel and use the `Other` framework preset. No build command is required.

## Checkout
All buy buttons (class `hcc-checkout`) link straight to the Lemon Squeezy checkout page (`?logo=0`; the discount field is shown so promo codes work). The `lemon.js` overlay was removed 2026-10-01 because it was slow to load. Clicks fire GA4 `begin_checkout`; completed purchases are tracked on `/thanks/` (below); Lemon Squeezy is the source of truth for sales.

Suggested custom domain: `planner.halfcupcalm.com`

## Thank-you page (`/thanks/`)
`thanks/index.html` is where Lemon Squeezy sends buyers after checkout. Set the product's redirect URL to
`https://planner.halfcupcalm.com/thanks/?purchased=1`. The page fires GA4 `purchase` ($9) once per checkout:
it uses Lemon Squeezy's order id if one is in the URL, ignores reloads and bookmarked visits, and strips the flag
from the address bar. It is `noindex`, and its styles are copied from `index.html` (re-copy if the header changes).

## Breakpoints
- `> 900px` desktop/landscape iPads: two-column hero.
- `601–900px` iPad portrait: centered hero column, photo up to 380px, 2–3 column sections, header buy button and sticky bar.
- `≤ 600px` phones: headline → page count → value line → CTA → photo (220px) → includes.
