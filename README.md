# Minute Jar

A screen-time token system for kids aged about 3 to 10. Kids earn minutes by finishing tasks a parent picks; when they spend them, a big visual timer counts down, warns at one minute and calls time.

- `index.html` – sales page with a working demo in the hero
- `app.html` – the app (kid mode, timer, PIN-locked grown-up area, onboarding)
- `manifest.webmanifest`, `sw.js`, `icon.svg` – installable, offline-capable web app
- `preview/swatches.html` – the palette and font study used to pick the look

No build step and no dependencies. Everything is saved in the browser's `localStorage` on the device; nothing is sent anywhere.

## Run locally

```sh
python3 -m http.server 8000
# open http://localhost:8000
```

## Before selling

1. **Checkout:** set `CHECKOUT_URL` and `PRICE` at the bottom of `index.html` (Stripe Payment Link, Gumroad, Lemon Squeezy, etc.). The price shown is a placeholder.
2. **Host over HTTPS** (GitHub Pages, Netlify, Cloudflare Pages). The offline service worker only registers on HTTPS.
3. **Gate the app** if you want it paid-only: right now `app.html` is openly reachable, which works as a free trial. A paywall needs a licence check or putting the app behind your store's delivery link.
4. **Icons:** some Android/iOS versions want PNG icons (192px and 512px) in the manifest besides the SVG.
5. **Name:** check that "Minute Jar" is free to use as a trademark and domain where you sell.

## Design

- Colors: Sanzo Wada, *A Dictionary of Color Combinations*, No. 290 – Vistoris Lake `#6D4145`, Pale Lemon Yellow `#FFEFAE`, Lincoln Green `#555832`, Cobalt Green `#96D1AA` (values from Matt DesLauriers' open digitization of the book).
- Fonts: Young Serif (headings) and Quicksand (body), both SIL Open Font License, loaded from Google Fonts.
