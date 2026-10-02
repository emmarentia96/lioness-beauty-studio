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

## Published

- **Custom domain: https://lionessbeauty.co.za** (registered at HOSTAFRICA, renews 2 Oct 2027)
- Fallback address that always works: https://emmarentia96.github.io/lioness-beauty-studio/
- Gallery: https://lionessbeauty.co.za/gallery.html
- Source repo: https://github.com/emmarentia96/lioness-beauty-studio (public)
- Host: GitHub Pages, free tier, built from `main` at the repo root. `.nojekyll` is present so Pages serves the files as-is.
- Account: `emmarentia96`. The GitHub CLI lives at `~/bin/gh.exe` (and `~/tools/gh.exe`).

### DNS at HOSTAFRICA

The apex must have exactly these four A records and nothing else:

```
185.199.108.153
185.199.109.153
185.199.110.153
185.199.111.153
```

Plus `www` CNAME to `lionessbeauty.co.za`. HOSTAFRICA auto-creates an A record pointing at `169.239.180.4` (their parked server) — it MUST be deleted, or roughly one visitor in five gets a 404 and the HTTPS certificate never gets issued.

### Pending / optional cleanup

- **HTTPS enforcement** — switch on once GitHub issues the certificate for the custom domain.
- **TTLs of 1, 2, 3 and 4 seconds** on the four A records (row numbers were typed into the TTL field). Harmless and useful during setup, but change to `3600` once things are settled.
- The auto-created `MX 0 lionessbeauty.co.za` record points mail at itself, so mail to the domain would not deliver. Harmless while the business uses Gmail, but remove it or point it at a real mail host if a domain email address is ever wanted.

### Updating the live site

Edit the files, then:

```bash
cd ~/lioness-beauty-studio
git add -A && git commit -m "describe the change"
git push
```

Pages rebuilds automatically in about a minute. A local preview server can run alongside at `python -m http.server 8765`.


## Remaining content checks (owner's call)

1. **Prices** — the owner reviewed the list, but the Full glam combo (R900–R1,200) is priced below the sum of its four parts. Deliberate bundle discount or typo?
2. **Testimonials** — confirmed real, but carry no client names ("A returning client"). Add a first name or initial only with that client's permission.
3. **Portfolio permissions** — the gallery now includes photos of clients (lash application, frontal detail). Confirm each person is happy for their photo to appear on a public site.
4. **Custom domain** (optional, paid) — a `.co.za` domain would replace the github.io address. Nothing purchased; the owner must approve first.

## Assets not published

Two files were moved out of the site to `~/lioness-beauty-originals/`:

- `lash-look.jpg` — a phone screenshot (status bar, `1 of 2` counter, letterbox bars), not a usable photo. A cropped version is published as `assets/gallery/lash-volume.jpg`.
- `welcoming-hero.jpg` — the old homepage hero background, removed with the hero photo.
