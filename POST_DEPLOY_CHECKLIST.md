# POST_DEPLOY_CHECKLIST.md
## Paulo Loyo UGC Portfolio — Things to fill in before sharing

Everything marked `[TODO]` or `[PLACEHOLDER]` in the site. Work through this list top-to-bottom before sending the link to brand managers.

---

## 1. SHOWREEL (highest priority)

**File:** `index.html` — Featured Work section, search for `showreel-placeholder`

Replace the grey placeholder block with a real embed:

```html
<!-- Option A: YouTube embed -->
<iframe
  src="https://www.youtube.com/embed/YOUR_VIDEO_ID?autoplay=0&modestbranding=1"
  allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture"
  allowfullscreen
  title="Paulo Loyo UGC Showreel"
  width="100%" height="100%"
  style="border:none;display:block;">
</iframe>

<!-- Option B: Self-hosted video file -->
<video
  src="./videos/showreel.mp4"
  poster="./images/showreel-poster.jpg"
  controls preload="none" playsinline
  style="width:100%;height:100%;object-fit:cover;display:block;">
</video>
```

**If self-hosting:** Upload the file to the repo at `./videos/showreel.mp4` and a poster image at `./images/showreel-poster.jpg`. Keep video under ~30 MB for fast GitHub Pages delivery.

---

## 2. PACKAGES — PRICES AND TERMS

**Files:** `index.html` (packages section) and `rate-card.html`

Search for `[PRICE]`, `[USAGE TERMS]`, `[EXCLUSIVITY TERMS]`, `[REVISION POLICY]`, `[RAW FOOTAGE TERMS]`, `[PAYMENT TERMS]`, and `[X] business days` — replace each with your real rates and terms.

Placeholder locations in `index.html`:
- Single UGC Video price
- 3-Hook Variation Pack price
- Monthly Retainer price/month
- Turnaround time for each package

Placeholder locations in `rate-card.html`:
- All six usage/terms blocks
- All three price cells
- Turnaround columns

---

## 3. TESTIMONIALS

**File:** `index.html` — Testimonials section (three `.testi-card` blocks)

Replace the three placeholder quotes with real quotes from brand managers or agency contacts. Each block needs:
- A real quote (keep it short: 1–3 sentences)
- Full name
- Title and brand (e.g. "Marketing Manager, Pelvini")

Only use quotes you have written permission to publish.

---

## 4. YEAR STARTED

**File:** `index.html` — Footer, and Results section

Currently says `Since 2023`. If you started before or after 2023, update:
- `index.html` → search `Since 2023` → update to correct year
- `results-bar` → the first stat reads "Videos delivered since 2023" → update year

---

## 5. PERFORMANCE METRICS (views, CTR, ROAS)

**File:** `index.html` — Results / Proof section, search `Performance metrics`

Once you have campaign data from brands, add specific numbers here. Suggested format:
```
Campaign: Kismia | Platform: Meta | Spend: $X | CTR: X% | ROAS: X
Campaign: Skillsta | Platform: Meta | 2M+ views | CTR: X%
```

You can also add a second results bar row with these numbers, or simply link to a private PDF deck.

---

## 6. OPEN GRAPH IMAGE

**File:** `index.html` — `<meta property="og:image" ...>`

Currently set to `./images/Cover_selfie.jpg`. For best social sharing results, create a dedicated OG image at 1200×630px with your name, tagline, and a clean background. Upload as `./images/og-image.jpg` and update the meta tag.

---

## 7. FAVICON

No favicon exists yet. Create a 32×32px `.ico` or `.png` and add to `<head>`:
```html
<link rel="icon" href="./images/favicon.png" type="image/png">
```

---

## 8. LOGO WALL (optional upgrade)

The brand marquee currently uses text only. If you want logo images:

1. Collect brand logos (transparent PNG, ~120×48px each)
2. Name them `./images/logos/brandname.png`
3. Update the ticker HTML to use `<img>` tags instead of `<span>` text

Brands worth requesting logos from (highest-profile collabs):
Grammarly, RYOBI, NOCO, Pelvini, Skillsta, Kismia, iGulu, BoxBotl, BZOO

---

## 9. STAT VERIFICATION

The Results section hardcodes counts based on badge counts from the portfolio:

| Stat | Source | Value |
|---|---|---|
| Videos delivered | Card count | 87 ✓ |
| Brand collabs | Brand count | 56 ✓ |
| Active Meta Ads | `badge-meta` count | 16 — **verify this is current** |
| Brand reposts | `badge-repost` count | 14 — **verify this is current** |
| Products live on Amazon | `badge-amazon` count | 4 — **verify which brands** |

Update in `index.html` (results-bar section) if counts change.

---

## 10. PORTFOLIO THUMBNAIL FILENAMES WITH SPACES

Several image filenames contain spaces. They work via URL-encoding (`%20`) but consider renaming for cleaner repo hygiene if you ever reorganize:

- `Harrys1Billo Thumbnail.jpg`
- `Kismia10out10 Thumbnail.jpg`
- `KismiaPOV Thumbnail.jpg`
- `Nertia Snapback 1 Thumbnail.jpg`
- `Nertia Snapback 2 Thumbnail.jpg`
- `PelviniMonarch Thumbnail.jpg`
- `PelviniTitan Thumbnail.jpg`
- `Seraphic thumbnail.jpg`
- `SkillstaENVersion Thumbnail.jpg`

---

## 11. RATE CARD PDF

After filling in `rate-card.html`, save it as a PDF using **File → Print → Save as PDF** in Chrome (or use the system print dialog). Upload the PDF and link it from the Contact section for easy download.

---

## 12. FUTURE VIDEOS

When adding new videos, the schema to use:
```html
<div class="phone-card" data-lang="en">
  <button type="button" class="video-card-btn" role="button"
    aria-label="Play: [Brand] — [Description]"
    data-video-id="[YOUTUBE_SHORT_ID_ONLY]">
    <img src="./images/[ThumbnailFilename].jpg" alt=""
      width="360" height="640" loading="lazy">
    <!-- OPTIONAL BADGES (pick at most one of the first three): -->
    <span class="badge-repost">Reposted ✓</span>
    <span class="badge-meta">Meta Ads ✓</span>
    <span class="badge-amazon">Live on Amazon ✓</span>
    <span class="badge-couple">Couple ✓</span>
    <span class="video-play-btn" aria-hidden="true">▶</span>
  </button>
  <div class="card-desc">
    <div class="card-desc-head">
      <span class="card-desc-num" aria-hidden="true">[NN]</span>
      <span class="card-desc-type">[Category · Subtype]</span>
    </div>
    <p class="card-desc-text">[Short description]</p>
  </div>
</div>
```

Also update:
- `cat-count` span in the category header
- Stats bar (`Videos delivered` count)
- Brand collabs count (if new brand)
- Ticker (both lines)
- SR-only brand list
- Brands grid (bottom of archive)

---

*Generated by Claude Code — spinachfilms.github.io/ugc-portfolio rebuild*
