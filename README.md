# Lioness Beauty Studio

Lioness Beauty Studio is a responsive, two-page website built with plain HTML, CSS, and JavaScript. No paid libraries, no build step, no external image assets — the gallery uses the beauty portfolio photos provided for this project.

## Files

- `index.html` — home page: hero, featured work, about, price list, reviews, booking
- `gallery.html` — full portfolio gallery (13 photos, filling a 4×4 grid)
- `styles.css` — all styling (mobile-first, responsive)
- `script.js` — mobile nav toggle, footer year
- `assets/` — logo, hero photo, favicon set, social share image, `gallery/` portfolio photos

## Preview locally

```bash
cd ~/lioness-beauty-studio
python -m http.server 8765 --bind 127.0.0.1
```

Then open http://127.0.0.1:8765/ in a browser. Google Fonts are optional; fallback fonts are used if they cannot load.

## Business details on the site

- Phone and WhatsApp: 0772782712
- Area: Pierre van Raynveld, Centurion
- Hours: Monday–Friday, 8:00 AM–5:00 PM
- Email: emmarentia96@gmail.com
- Prices: supplied price ranges; braiding is listed as quote-on-request
- TikTok: https://www.tiktok.com/@lionesbeautystudio

## Finished

- Full responsive layout, verified with no horizontal overflow at 1249px and 390px widths
- Text-only hero (no background photo); the hero panel and its overlay styles were removed and the heading rebalanced to a max-width column
- All internal links and image references resolve (verified against the filesystem — 0 missing)
- Favicon set (`favicon.ico`, `favicon-32.png`, `apple-touch-icon.png`), cropped from the supplied logo
- Open Graph + Twitter share card (`assets/og-image.jpg`, 1200×630), so shared links show a preview
- Accessibility: skip link, alt text on every image, `aria-current` on the active nav item, keyboard-usable mobile menu
- Reviews section restored as "04 / Kind words, real feel-good moments" (3 client testimonials, styled cards). Customer confirmed the testimonials come from real clients.
- Section order: 01 Real work, real style · 02 About · 03 Price list · 04 Reviews · 05 Booking
- The old "03 / The good stuff" service-card section was removed at the owner's request. Its braiding note was moved into the price list so the quote-on-request detail isn't lost. The `.services-section` / `.service-grid` / `.service-card` CSS was deliberately left in `styles.css` (currently unused) so the section can be restored from the backup if wanted — strip it once the content is final.

## Before publishing

1. **Confirm remaining content.** Prices and portfolio image permissions should still be checked by the owner. The testimonials are confirmed real, but they carry no client names ("A returning client") — add a first name or initial only with that client's permission.
2. **Make share URLs absolute.** Once the hosting address is known, `og:image` / `twitter:image` in both HTML files should become full `https://...` URLs (crawlers prefer absolute paths), and an absolute `og:url` plus a `canonical` link can be added.
3. **Get explicit approval**, then publish to a free host.

No hosting account, domain, paid service, or public site has been created.
