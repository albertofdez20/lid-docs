# Apply Lid styling in GitBook dashboard

This file is for the human. GitBook publishes from this GitHub repo, but a few
visual settings only live in the GitBook dashboard. Work through the list
below once, then the site matches the Lid design system.

---

## 1. Paste the custom CSS

1. Open GitBook dashboard.
2. Go to **Site** → **Customization** → **Custom CSS**.
3. Open `custom.css` in the root of this repo.
4. Copy the entire file.
5. Paste into the Custom CSS panel.
6. Save.

If you don't see a Custom CSS panel, you're on a plan that doesn't include it.
Upgrade to Premium, or live with the built-in brand controls (which the next
steps cover).

---

## 2. Set the primary color

**Dashboard** → **Site** → **Customization** → **Colors**.

- Primary color (light): `#8B5CF6`
- Primary color (dark): `#8B5CF6`

Leave every other swatch at default. The custom.css file overrides the rest.

---

## 3. Force dark mode as default

**Dashboard** → **Site** → **Customization** → **Appearance**.

- Default appearance: **Dark**
- Allow user to toggle: **Off**

Lid is dark by default. Light mode isn't in scope for docs.lid.pro.

---

## 4. Typography

**Dashboard** → **Site** → **Customization** → **Typography**.

- Heading font: **Space Grotesk** (if in the picker). Otherwise, leave default.
- Body font: **Inter** (if in the picker). Otherwise, leave default.

The custom.css file imports both from Google Fonts and applies them site-wide,
so even if GitBook doesn't offer them natively, the site will still render
Space Grotesk + Inter once CSS is pasted.

---

## 5. Logo and favicon

The Lid logo lives in the repo at `/Gitbook Lid/lid-logo.svg` and is also
inlined as a base64 data URL inside `custom.css`. That means the header logo
renders from the CSS alone, even if you skip the dashboard upload.

For the cleanest result, upload both in the dashboard too:

- **Logo (light, for dark backgrounds):** `lid-logo.svg` from the repo root.
- **Favicon:** `lid-favicon.svg` from the repo root. This is the square violet
  mark, cropped for tab icons.

All uploads go in **Dashboard** → **Site** → **Customization** → **Logo & favicon**.

Dashboard uploads take precedence over the CSS inline logo, so the site works
either way. The CSS version is a safety net.

---

## 6. Header layout

**Dashboard** → **Site** → **Customization** → **Header**.

- Header style: **Minimal** or **Sticky**. Avoid "Bold" or "Centered" which
  fight the Lid layout.
- Navigation links (right side of the header):
  - Product → `https://app.lid.pro`
  - Site → `https://lid.pro`
- Primary CTA: `Open the app` → `https://app.lid.pro`

---

## 7. Social preview image

**Dashboard** → **Site** → **SEO & social** → **Open Graph image**.

Upload `lid-og-image.svg` from the repo root. It's a 1200×630 card with the
Lid logo, tagline ("Your customers are your sales team."), and docs.lid.pro
URL on the dark purple ground.

If the dashboard requires PNG instead of SVG, open the SVG in Preview or
Figma and export at 1200×630 PNG. The SVG is the source of truth.

---

## 8. Custom domain

**Dashboard** → **Site** → **Domain**.

- Connect `docs.lid.pro`.
- Follow GitBook's CNAME instructions.
- Wait for DNS propagation.

---

## 9. Search

**Dashboard** → **Site** → **Search**.

- Enable AI search if on your plan.
- Prompt (optional): "Ask about how LID works, pricing, attribution, or the
  affiliate system."

---

## 10. Analytics

**Dashboard** → **Integrations** → **Analytics**.

Connect whichever analytics tool is set up for `lid.pro`. Keep docs and
marketing site on the same analytics property so funnel data is unified.

---

## What the repo controls vs. what the dashboard controls

| Repo (GitHub sync)                        | Dashboard only                                |
|-------------------------------------------|------------------------------------------------|
| Page content (.md files)                  | Primary color value                            |
| Page order (SUMMARY.md)                   | Logo and favicon files                         |
| Redirects (.gitbook.yaml)                 | Custom domain binding                          |
| Custom CSS (custom.css → paste manually)  | Search config, analytics, OG image             |
| README.md                                 | Header layout and navigation links             |

The CSS file lives in the repo for version control. It still needs to be
pasted into the dashboard once. Re-paste any time it changes.

---

## Quick sanity check after going live

Open `docs.lid.pro` and check:

- [ ] Dark purple background across every page
- [ ] Headlines render in Space Grotesk
- [ ] Body text renders in Inter
- [ ] Links are violet (`#8B5CF6`)
- [ ] Active TOC item has a purple left-rail
- [ ] Tables have uppercase headers and muted borders
- [ ] Code blocks are dark with violet inline code
- [ ] No white flashes between pages (appearance locked to dark)
- [ ] Header shows the Lid logo (from CSS or your dashboard upload)

If any of these fails, the CSS did not apply. Re-paste `custom.css` and save.
