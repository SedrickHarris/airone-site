# AIRONE Site Changelog

All notable changes to the AIRONE Heating and Cooling website. Newest first.

---

## 2026-06-04 — Maintenance Plans Suite: Level 5 Builds + Reconciliation (4 commits + pre-build audit)

### Summary
Full Level 5 Site Master workflow executed for both maintenance plan detail pages. Both pages built from scratch with research-informed content, GEO targeting, E-E-A-T signals, full schema suite, and AEO FAQ blocks. Overview page reconciled to match verified feature set. All three pages in the maintenance plans suite are now internally consistent and GSC-ready. Sitemap pretty-URL 404 risks resolved.

---

### Commit 41101d7 — maintenance-plans-silver.html Level 5 Build

**Type:** feat (rebuild)
**File:** `maintenance-plans-silver.html`
**Sitemap:** `sitemap.xml` — `/maintenance-plans/silver` removed, `/maintenance-plans-silver` added, lastmod `2026-06-04`

**What changed:**
- Rebuilt from scratch as a Level 5 core revenue page following full Site Master workflow (Prompts 01–08): business intake, keyword research, SERP/competitor gap analysis, page strategy, full on-page content, schema planning, QA, and Claude Code build prompt.
- Flat canonical URL: `/maintenance-plans-silver`
- 10-section layout: Hero, What's Included (5 feature cards), Visit Checklist (8-step), Silver vs Gold (comparison table), Warranty Protection, Why SoCal, Why AIRONE, Social Proof, FAQ, Final CTA
- GEO targeting: Burbank, Van Nuys, Glendale, Woodland Hills, Pasadena, Manhattan Beach, Torrance, South Bay, Orange County
- 4 JSON-LD schema blocks: BreadcrumbList, Service, FAQPage (8 Q&A), SpeakableSpecification
- E-E-A-T signals: License #114807, CSLB verification link, no subcontractors, written condition report, since 2020, manufacturer warranty protection section
- Internal links: `/maintenance-plans`, `/maintenance-plans-gold`, `/ac-maintenance`, `/furnace-maintenance`, `cslb.ca.gov`
- Hero bg: `HVAC_Maintenance_Plans_AIRONE_Save_Energy_And_Prevent_Repairs.webp`
- CTA bg: `Final_CTA_image.webp`
- GHL Hero form: `Ob9DKlQhU1Ny9UHalpm9` | CTA form: `fr0tqZYW0y2Z0p5PsulY`
- All 24 QA checks passed

**Content accuracy note:** S5 (Why SoCal) and S6 (Why AIRONE) required Silver-specific adaptation from Gold copy during build. Adaptations approved by project owner before commit. Key change: "Written Documentation" (one report/year) vs Gold's "Two Written Reports Per Year."

---

### Commit 0c5cfa8 — maintenance-plans-gold.html Level 5 Build

**Type:** feat (rebuild)
**File:** `maintenance-plans-gold.html`
**Sitemap:** `sitemap.xml` — `/maintenance-plans/gold` removed, `/maintenance-plans-gold` added, lastmod `2026-06-04`

**What changed:**
- Rebuilt from scratch as a Level 5 core revenue page following full Site Master workflow (Prompts 01–08).
- Flat canonical URL: `/maintenance-plans-gold`
- 11-section layout: Hero, What's Included (10 feature cards — 5 foundation + 5 Gold exclusives), Two Visits (spring/fall checklists), Gold Exclusive Features (deep dive), Is Gold Right For You, Comparison Table (12 rows), Why SoCal, Why AIRONE, Social Proof, FAQ, Final CTA
- Gold-exclusive features: bi-annual visits (spring AC + fall furnace), refrigerant top-off included, 10% off all parts & labor on repairs, emergency priority response, annual duct inspection
- GEO targeting: Burbank, Van Nuys, Glendale, Woodland Hills, Pasadena, Manhattan Beach, South Bay, Orange County, San Fernando Valley, Inland Empire
- 4 JSON-LD schema blocks: BreadcrumbList, Service, FAQPage (8 Q&A), SpeakableSpecification
- E-E-A-T signals: License #114807, CSLB verification link, EPA Section 608 certification (refrigerant), no subcontractors, two written condition reports per year, since 2020
- Internal links: `/maintenance-plans`, `/maintenance-plans-silver`, `/ac-maintenance`, `/furnace-maintenance`, `/duct-cleaning`, `cslb.ca.gov`
- Hero bg: `HVAC_Maintenance_Plans_AIRONE_Save_Energy_And_Prevent_Repairs.webp`
- CTA bg: `Final_CTA_image.webp`
- GHL Hero form: `Ob9DKlQhU1Ny9UHalpm9` | CTA form: `fr0tqZYW0y2Z0p5PsulY`
- All 27 QA checks passed

**Content accuracy note:** S3/S4/S5 content reconstructed from verified in-prompt data (S1 cards + S9 FAQ + Silver page) after "Prompt 05" reference was confirmed not to exist in prior context. All reconstructed copy reviewed and approved by project owner before commit.

---

### Commit ba832a4 — maintenance-plans.html Gold Plan Reconciliation Pass 1

**Type:** fix
**File:** `maintenance-plans.html`

**What changed:** Surgical correction of Gold Plan feature data that conflicted with the verified feature set now live on `maintenance-plans-gold.html`. No structural changes. No Silver content touched.

| Location | Old value | New value |
| --- | --- | --- |
| Schema OfferCatalog — Gold offer (line 103) | Two AC visits per year, two furnace visits per year | Two visits per year — one spring AC tune-up and one fall furnace inspection |
| Schema OfferCatalog — Gold offer (line 103) | 15 percent member discount | 10 percent member discount |
| Schema OfferCatalog — Gold offer (line 103) | refrigerant top-off up to 1 lb per year | refrigerant top-off included |
| Schema FAQPage a2 + visible FAQ a2 (lines 112, 702) | same three errors | same three corrections (replace_all — schema ≡ visible) |
| Schema FAQPage a4 + visible FAQ a4 (lines 114, 712) | Gold Plan members receive two visits for each system per year | Gold Plan members receive two visits per year |
| Comparison table — discount row Gold cell (line 562) | 15% | 10% |
| Comparison table — AC tune-up row Gold cell (line 558) | 2 visits per year | Included (spring) |
| Comparison table — furnace row Gold cell (line 559) | 2 visits per year | Included (fall) |
| Comparison table — refrigerant row label (line 565) | Refrigerant top-off up to 1 lb per year | Refrigerant top-off included |
| Body copy line 522 | The Gold Plan adds a second AC visit and a second furnace visit | The Gold Plan provides two visits per year — one spring AC tune-up and one fall furnace inspection |

All 9 Step 3 verification checks passed. FAQ schema ≡ visible text confirmed.

---

### Commit ec0dc5a — maintenance-plans.html Gold Plan Reconciliation Pass 2

**Type:** fix
**File:** `maintenance-plans.html`

**What changed:** Follow-up surgical correction. "Annual whole-system performance verification" replaced with verified Gold feature "annual duct inspection" across 4 locations.

| Location | Old value | New value |
| --- | --- | --- |
| Schema OfferCatalog — Gold offer (line 103) | annual whole-system performance verification | annual duct inspection |
| Schema FAQPage a2 (line 112) | an annual whole-system performance verification | an annual duct inspection |
| Comparison table — row label (line 564) | Annual whole-system performance verification | Annual duct inspection |
| Visible FAQ a2 (line 702) | an annual whole-system performance verification | an annual duct inspection |

All Step 3 verification checks passed. FAQ schema ≡ visible text confirmed.

---

### Repo Audit + Sitemap Fix (2026-06-04, pre-build)

**Type:** fix + audit
**Files:** `sitemap.xml`
**Context:** Prior to the Level 5 builds, a full repo audit was conducted using Claude Code. Key findings and fixes:

- **128 HTML files** confirmed in repo; **125 sitemap URLs** confirmed
- `city-template.html` correctly excluded from sitemap (build artifact)
- `thank-you-contact.html` and `thank-you-quote.html` correctly excluded (noindex pages)
- **Pretty-URL 404 risk identified and resolved:** `/maintenance-plans/silver` and `/maintenance-plans/gold` were in the sitemap with no matching `.html` files and no rewrite rules in `_redirects`. Both corrected to flat slugs during respective Level 5 builds.
- `robots.txt` confirmed correct: points to `https://aironeheatingandcoolinginc.com/sitemap.xml`
- Repo confirmed in sync with `origin/main` at audit time

---

### GSC Submission Status

Sitemap is now clean, flat-URL, and content-consistent across all three maintenance plan pages. Ready to submit to Google Search Console and Bing Webmaster Tools.

Submit: `https://aironeheatingandcoolinginc.com/sitemap.xml`

---

### Verification commands (run to confirm suite consistency)

```bash
grep "maintenance-plans" sitemap.xml
# Expected: /maintenance-plans, /maintenance-plans-silver, /maintenance-plans-gold
# Must NOT contain: /maintenance-plans/silver or /maintenance-plans/gold

grep -c "15%" maintenance-plans.html
# Expected: 0

grep "annual duct inspection" maintenance-plans.html
# Expected: ≥4

grep "maintenance-plans-silver\|maintenance-plans-gold" maintenance-plans.html
# Expected: ≥1 each (internal links to detail pages)
```

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
