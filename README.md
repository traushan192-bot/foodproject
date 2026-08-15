# Omnifood — Landing Page

A single-page responsive landing page for **Omnifood**, a fictional healthy food delivery service. Built with plain HTML and CSS (no framework, no build step).

## Project Structure

```
.
├── index.html
├── resources/
│   └── css/
│       ├── style.css
│       ├── images1.png        (logo)
│       ├── appstore.png
│       ├── playstore.png
│       ├── img1.avif – img8.avif   (meal showcase photos)
│       ├── lisbon.avif, london.avif, berlin.avif, paris.avif
│       └── cust-1.jpg, cust-2.jpg, cust-3.jpg   (testimonial avatars)
└── vendors/
    └── css/
        ├── normalize.css
        └── grid.css
```

> Note: only `index.html` and `style.css` are included in this handoff. Make sure the image assets and vendor CSS files above exist at the paths referenced in `index.html`, or the page will show broken images/unstyled grid.

## Sections

| Section | Description |
|---|---|
| Header | Full-height hero with background image, headline, and two CTA buttons |
| Features | Four-column icon grid ("Up to 365 days/year", "Ready in 20 minutes", etc.) |
| Meals showcase | 8-image grid of meal photos |
| How it works | Phone mockup + numbered 3-step explainer with app store badges |
| Our cities | City cards (Lisbon, London, Berlin, Paris) with stats and social links |
| Testimonials | Three customer quotes over a fixed background image |
| Plans & pricing | Three pricing tiers (Premium, Pro, Starter) |
| Contact form | Name, email, referral source, newsletter opt-in, message |
| Footer | Footer nav links + social icons + copyright |

## Dependencies

- **[Ionicons](https://ionic.io/ionicons)** (loaded via CDN in `index.html`) — used for all icons (features, cities, footer social links, plan checkmarks).
- **Google Fonts – Lato** (loaded via CDN) — primary typeface across the site.
- **normalize.css** and a custom **grid.css** (expected in `vendors/css/`) — not included here; supply your own or replace with your preferred reset/grid.

## Known Layout Notes

- `.row` is defined **twice** in `style.css`: once for `max-width` + centering, once later as `display: flex`. This is intentional (kept from the original source) but means any element placed alone inside a `.row` will shrink-wrap and left-align unless explicitly given `width: 100%` — see the `.row > h2` rule, which was added specifically to fix this for section headings.
- The contact form uses native `<select>`, `<textarea>`, and `<input type="checkbox">` — no JS validation is wired up; `required` attributes rely on native browser validation only.
- All CTAs (`href="#"`) are placeholders — wire up real links/routes before shipping.

## How to Run

No build tools required. Open `index.html` directly in a browser, or serve the folder with any static server, e.g.:

```bash
npx serve .
```

## Recent Fixes in This Version

- Centered all section `<h2>` headings (previously left-shifted due to the `.row` flex behavior described above).
- Centered the four feature-grid headings and icons.
- Fixed a stray extra `</div>` in the footer markup.
- Added missing footer CSS (nav links, social icons with brand-color hovers, centered copyright line).
- Moved bulky inline `style="..."` attributes out of the "Our cities" section into `style.css` for readability.
