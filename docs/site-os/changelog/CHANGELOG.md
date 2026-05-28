# AIRONE Site Changelog

All notable changes to the AIRONE Heating and Cooling website. Newest first.

---

## 2026-05-27 — Owner Decision Implementation (4 changes)

### Decision 1: Pricing Removed Site-Wide
**Reason:** Owner elected not to publish any prices on service pages until pricing strategy is finalized and quoted in writing per job.

- Removed every `<span class="price-ph">…</span>` body usage across all service pages (zero remain in page bodies; inert `.price-ph` CSS class definitions left in stylesheets as harmless dead code).
- Replaced each removed pricing section with a unified **"Pricing Available on Request"** CTA block (white card on light section background) containing the headline, a one-paragraph explainer, and a dark phone-CTA button: `tel:+13234711037` — `Call (323) 471-1037 for a Free Quote`.
- Pages affected (13 total): all batch 1–4 service pages that previously contained a price-table or tune-up-cost section.
- Special handling:
  - **ac-maintenance.html** — entire `<section id="tune-up-cost">` (table of 5 plan/visit prices + supporting prose) replaced wholesale with the unified CTA block. Maintenance-plans comparison table retained (it lists *features*, not prices).
  - **services.html** — Silver/Gold plan-card pricing spans removed surgically; feature comparison table and plan feature `<ul>` lists retained intact.

### Decision 2: GBP Placeholder Removed Site-Wide
**Reason:** Owner has not yet set up the AIRONE Google Business Profile; publishing a placeholder URL or empty link is worse than directing visitors straight to the phone line.

- Removed every `GBP_URL_PLACEHOLDER` block from the reviews-section of every page (35 instances site-wide → 0 remain).
- Replaced each with a clean static block on the existing light-cream section background reading:
  > AIRONE serves Los Angeles County, South Bay, and Orange County. Google reviews coming soon — call (323) 471-1037 to speak with a customer directly.
- When GBP is live, this block can be reverted to a CTA pointing at the live profile URL.

### Decision 3: Dual GHL Form ID Pattern (Documentation Only — No HTML Changes)
**Reason:** Site QA flagged two distinct GoHighLevel form IDs embedded on the same page and asked whether this was a bug. It is intentional — a single GHL form widget cannot render twice on the same page (the second iframe loads blank). Two distinct form IDs are required to render the hero form and the mid/end-of-page CTA form on the same page.

| Form ID | Position | Purpose |
| --- | --- | --- |
| `Ob9DKlQhU1Ny9UHalpm9` | Hero (top-of-page) | Primary lead capture above the fold |
| `fr0tqZYW0y2Z0p5PsulY` | CTA (mid/bottom-of-page) | Secondary lead capture after content review |

Both submit to the same GHL location and feed the same lead pipeline; the IDs only differ to satisfy the widget's "one ID per page render" constraint. **Do not consolidate these IDs.** Both forms load via the shared script `connect.siriussys.io/js/form_embed.js`.

### Decision 4: CTA Background Image Unified
**Reason:** Visual consistency across the site; the unified image is on-brand and works across heating, cooling, IAQ, and utility pages without looking out of place.

- All `.cta-split-bg` background images normalized to `assets/images/Final_CTA_image.webp`.
- Applied to 6 Batch 4 pages (IAQ + ac-refrigerant-recharge) and to all Batch 1–3 pages that previously used a page-specific CTA image (5 furnace pages, heating-installation).
- Per-page hero `split-bg` images (above the fold) were **not** changed — those remain page-specific to communicate the service.

---

### Verification (run at completion)
- `grep "price-ph" *.html | grep -v "\.price-ph{"` → **0 body matches** (CSS rule definitions only)
- `grep "GBP_URL_PLACEHOLDER" *.html` → **0 matches**
- `grep "cta-split-bg.*background-image" *.html | grep -v Final_CTA_image` → **0 matches**
- `grep -l "Pricing Available on Request" *.html` → **13 files**
- `grep -l "Google reviews coming soon" *.html` → **35 files**
