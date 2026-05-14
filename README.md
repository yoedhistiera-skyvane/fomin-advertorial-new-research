# Fomin — Clean Facial Towels Advertorial

A high-converting advertorial landing page for Fomin Clean Facial Towels, designed to run as the pre-landing page for Facebook and Instagram ad traffic. Brand-adapted styling (colors, fonts, voice matched to fominsoap.com), single self-contained HTML file, no build step required.

**Live target product:** https://fominsoap.com/products/clean-facial-towels

---

## Table of contents

1. [Quick start (deploy in 5 minutes)](#quick-start)
2. [Connect to a Fomin subdomain](#connect-to-a-fomin-subdomain)
3. [Replace the 12 image placeholders](#replace-the-12-image-placeholders)
4. [Replace the 4 customer reviews](#replace-the-4-customer-reviews)
5. [Add tracking pixels (Meta + GA4)](#add-tracking-pixels)
6. [Edit copy, prices, or links](#edit-copy-prices-or-links)
7. [A/B testing setup](#ab-testing-setup)
8. [Compliance checklist before launch](#compliance-checklist)
9. [Page anatomy reference](#page-anatomy-reference)
10. [Brand tokens (for future edits)](#brand-tokens)

---

## Quick start

You have three deployment options. Pick the one that matches your situation.

### Option A — Push to GitHub, deploy via Vercel (recommended)

```bash
# 1. Create a new GitHub repo (private or public, doesn't matter)
# 2. Clone it locally, then:
git add index.html README.md vercel.json images/
git commit -m "Initial advertorial"
git push origin main

# 3. Go to vercel.com → "Add New..." → "Project"
# 4. Import your GitHub repo
# 5. Click "Deploy" (no settings to change — vercel.json handles it)
```

Vercel will give you a URL like `your-project.vercel.app` within ~60 seconds. The page will render with placeholder images already in place — replace them at your own pace by uploading real images to the `images/` folder with the same filenames. Then connect the Fomin subdomain (next section).

### Option B — Drag and drop into Vercel

```bash
# 1. Go to vercel.com → "Add New..." → "Project" → "Deploy a template"
# 2. Or use the CLI:
npm install -g vercel
cd fomin-advertorial
vercel
```

Follow the prompts. No GitHub needed.

### Option C — Any static host

The file is plain HTML with zero dependencies. Drop `index.html` on any static host:
- Netlify (drag-and-drop)
- Cloudflare Pages
- GitHub Pages
- AWS S3 + CloudFront
- The Fomin Shopify "Custom Page" if you want to host it on their existing infrastructure

---

## Connect to a Fomin subdomain

Since you're hosting on a Fomin-owned subdomain (e.g. `learn.fominsoap.com`), here's the DNS setup.

### On Vercel
1. Project Settings → Domains → "Add"
2. Enter `learn.fominsoap.com` (or whatever subdomain you choose)
3. Vercel will show you a CNAME record to add

### On Fomin's DNS (Shopify or wherever fominsoap.com is managed)
Add this CNAME record:

```
Type:   CNAME
Name:   learn (or whatever subdomain)
Value:  cname.vercel-dns.com.
TTL:    3600 (or default)
```

DNS propagation takes 5 min – 24 hours. SSL/HTTPS is automatic via Vercel.

**Subdomain naming suggestions:**
- `learn.fominsoap.com` ✅ recommended — feels editorial
- `read.fominsoap.com` ✅
- `skin.fominsoap.com` ✅ topical
- `guide.fominsoap.com` ✅
- Avoid `shop.`, `buy.`, `deal.` — Meta classifies these as commercial intent and may push up your CPMs

---

## Replace the 12 image placeholders

The HTML already references `/images/` paths — you just need to upload your real images with matching filenames to the `images/` folder, commit, and push. The page works the moment files land in place.

### Image map

| Filename in `/images/` | Used for | Recommended size | Format |
|---|---|---|---|
| `hero.webp` | Top of page, above intro paragraphs | 1600×900 (16:9) | WebP |
| `reason-01-bacteria.webp` | Reason 01 right column | 800×1000 (4:5) | WebP |
| `reason-02-residue.webp` | Reason 02 left column | 800×1000 | WebP |
| `reason-03-laundry.webp` | Reason 03 right column | 800×1000 | WebP |
| `reason-04-friction.webp` | Reason 04 left column | 800×1000 | WebP |
| `reason-05-environment.webp` | Reason 05 right column | 800×1000 | WebP |
| `reason-06-chemicals.webp` | Reason 06 left column | 800×1000 | WebP |
| `reason-07-solution.webp` | Reason 07 right column | 800×1000 | WebP |
| `reviews/customer-1.webp` | First review card avatar | 160×160 (1:1) | WebP |
| `reviews/customer-2.webp` | Second review card avatar | 160×160 | WebP |
| `reviews/customer-3.webp` | Third review card avatar | 160×160 | WebP |
| `reviews/customer-4.webp` | Fourth review card avatar | 160×160 | WebP |

> The product image in the inline product card uses Fomin's own Shopify CDN URL — no upload needed there.

### How to replace an image

**Method 1 — GitHub web interface (no terminal):**
1. Go to your repo on github.com
2. Click into the `images/` folder
3. Click the filename you want to replace (e.g. `hero.webp`)
4. Click the pencil icon, then "Choose your file" or drag your new file in with the same name
5. Commit changes — Vercel will redeploy in ~30 seconds

**Method 2 — Git command line:**
```bash
# Replace the placeholder hero with your real image
cp /path/to/your/real-hero.webp images/hero.webp
git add images/hero.webp
git commit -m "Replace hero image"
git push
```

### Image optimization is critical

Raw camera photos are 4–8 MB each. Uploaded unoptimized, your page will be 50+ MB and crawl on mobile. Run images through one of these before uploading:

- **[Squoosh.app](https://squoosh.app)** (Google) — drop in image, choose WebP, slide quality to ~80, download. 30 seconds per image. ⭐ Recommended.
- **[TinyPNG.com](https://tinypng.com)** — batch optimize up to 20 images at once.
- **[Cloudinary](https://cloudinary.com)** — automated bulk optimization with a free tier.

**Target file sizes:**
- Hero: under 150 KB
- Reason images: under 100 KB each
- Customer avatars: under 20 KB each

**Total target page weight (all images combined): under 1.5 MB**. Test with [PageSpeed Insights](https://pagespeed.web.dev) — aim for "Largest Contentful Paint" under 2 seconds on mobile.

### Placeholder files included

The repo ships with tiny WebP placeholder images (~6 KB each) so the page renders correctly before you upload real photos. They show "Reason 01 — Bacteria" etc. on a cream background — clearly visible-as-placeholder but not broken images. Replace them as you go.

---

## Replace the 4 customer reviews

Open `index.html` and search for `REPLACE: Real review`. You'll find 4 spots. Each looks like this:

```html
<div class="review-card">
  <div class="img-placeholder review">...</div>
  <div class="stars">★★★★★</div>
  <p class="quote">"REPLACE: Real review quote here..."</p>
  <div class="name">— Customer name</div>
  <div class="meta-r">Verified buyer · 2026</div>
</div>
```

### Where to source real reviews

Pull from these — in order of preference:
1. **Fomin's Shopify product reviews** (the 106 reviews on the Clean Facial Towels page)
2. **Costco reviews** for the 100-pack
3. **Amazon reviews** for the FOMIN listings (`B0BS42M5RV`, `B0BFJGPKBW`)
4. **Walmart product reviews**

### What makes a high-converting review

Pick reviews that mention:
- A **specific outcome** ("acne cleared," "redness gone," "no more breakouts")
- A **specific timeframe** ("within a week," "after a month")
- A **specific use case** ("for travel," "after working out," "for makeup removal")
- A **competitor comparison** ("better than Clean Skin Club," "switched from Neutrogena")

### Authenticity rules

- ✅ Use real reviews verbatim or with minor edits for typos/grammar
- ✅ Use real first names or "Sarah M." style initials
- ❌ Don't fabricate reviews — FTC violation and Meta will flag it
- ❌ Don't claim "verified" if you can't substantiate
- ✅ Keep `Verified buyer · 2026` only if true

---

## Add tracking pixels

The file has Meta Pixel and GA4 pre-wired but commented out. Find them near the top of `index.html`.

### Meta Pixel

1. Get your Pixel ID from Meta Business Manager → Events Manager
2. In `index.html`, find this block (around line 24):

```html
<!--
<script>
  !function(f,b,e,v,n,t,s){...
  fbq('init', 'PIXEL_ID'); fbq('track', 'PageView');
</script>
...
-->
```

3. Remove the `<!--` at the top and `-->` at the bottom to uncomment
4. Replace both instances of `PIXEL_ID` with your real ID (e.g. `1234567890123456`)

### GA4

1. Get your Measurement ID from Google Analytics → Admin → Data Streams (looks like `G-XXXXXXXXXX`)
2. Find this block (around line 40):

```html
<!--
<script async src="https://www.googletagmanager.com/gtag/js?id=MEASUREMENT_ID"></script>
...
-->
```

3. Remove `<!--` and `-->`
4. Replace both instances of `MEASUREMENT_ID` with your real ID

### Track CTA clicks (optional but recommended)

To track clicks on each "Shop now" button, add `onclick` handlers:

```html
<a href="https://fominsoap.com/products/clean-facial-towels"
   class="btn btn-ocean btn-large"
   onclick="fbq('track', 'AddToCart'); gtag('event', 'cta_click', {location: 'final_cta'});">
  Shop Clean Facial Towels →
</a>
```

Different `location` values for each CTA help you see which one converts best:
- Header button → `header`
- Inline product card → `inline_card`
- Final CTA → `final_cta`
- Mobile sticky → `sticky_cta`

---

## Edit copy, prices, or links

### Price changes

Search for `$10.80` and `$12.00` — they appear in 3 spots (inline product card, final CTA, sticky CTA). Update all three to stay consistent.

### Product link

The Fomin product URL appears in 5 spots. Search for `fominsoap.com/products/clean-facial-towels` to find all instances if the product URL ever changes.

### Headline

Find this line:

```html
<h1 class="headline">7 reasons your bathroom towel may be sabotaging your skin (and the small change that fixes it)</h1>
```

Also update the `<title>`, `og:title`, and meta description tags up top to match.

### Discount badge

The "10% off" badge appears next to the price. Search for `10% off` to update all instances.

---

## A/B testing setup

The single biggest performance lever is testing. Here's how to set it up.

### Option 1 — Vercel split testing (advanced)

Use Vercel Edge Middleware to split traffic 50/50 between `/a` and `/b` paths. Requires writing a `middleware.ts` file. Best if you have a developer.

### Option 2 — Two URLs, Meta ads split

Easiest method. Duplicate the file:

```bash
cp index.html index-b.html
```

Edit `index-b.html` with one specific change (different headline, different CTA copy, different first reason). Push both to Vercel.

In Meta Ads Manager:
1. Create two ad sets with identical targeting
2. Set the destination URL of one to `learn.fominsoap.com/`
3. Set the other to `learn.fominsoap.com/b`
4. Split budget 50/50
5. Run for 3–5 days minimum (need ~100 conversions per variant for statistical significance)
6. Keep the winner

### What to test first (priority order)

1. **Headline** — biggest impact, easiest to swap. Try: "What dermatologists are quietly saying about your towel" vs. current "7 reasons..."
2. **Number of reasons** — try 5 vs. 7 vs. 3
3. **Hero image** — lifestyle vs. product-only
4. **Price framing** — "$10.80" vs. "Under $11"
5. **CTA copy** — "Shop now" vs. "Try them risk-free" vs. "Get 10% off"

---

## Compliance checklist

Run this list before turning on ads. Most ad-account bans come from skipping one of these.

### Meta ad policy
- [ ] No "before/after" personal attribute claims ("your acne," "your sensitive skin" — second person is risky)
- [ ] No medical claims ("cures acne," "treats eczema") — we use "may help" / "supports" instead ✅
- [ ] No body shaming or insecurity-amplifying language ✅
- [ ] FDA disclaimer in footer ✅
- [ ] Privacy Policy link present and working ✅

### FTC
- [ ] All cited stats are real and sourceable (Scientific Reports 2023, Gerba/University of Arizona) ✅
- [ ] Customer reviews are real, not fabricated — **DO before launch**
- [ ] "Trusted at Costco, Anthropologie..." retailer claims are accurate — confirm with Fomin team
- [ ] No false scarcity ("only 3 left!" if untrue)
- [ ] Price savings ("10% off") reflect actual list price

### Legal
- [ ] Confirm you have written permission from Fomin to publish on their subdomain
- [ ] Confirm Walknoice font is NOT being self-hosted (we use Google Fonts only — Outfit + Assistant) ✅
- [ ] All linked product pages, policies, and footer URLs work

### Performance
- [ ] Page loads in under 2 seconds on 4G mobile (test with Vercel Analytics or PageSpeed Insights)
- [ ] Real images optimized to WebP, under 200KB each
- [ ] Pixel fires correctly (test with Meta Pixel Helper Chrome extension)

---

## Page anatomy reference

Top to bottom, here's what's on the page:

1. **Lavender→peach gradient strip** (6px brand accent)
2. **Announcement bar** — "Free shipping on orders over $47 →"
3. **Header** — Fomin logo (left) + "Shop now →" CTA button (right, blue)
4. **Breadcrumb** — "Suds & Stories · Skincare"
5. **H1 headline** — "7 reasons your bathroom towel may be sabotaging your skin..."
6. **Dek** (sub-headline)
7. **Byline row** — date, 7 min read, star rating, 15,000+ reviews
8. **Hero image** (16:9 placeholder)
9. **Lead paragraph** with drop-cap
10. **Intro paragraphs** (2)
11. **Reason 01** — Bacterial science + 90% stat callout
12. **Reason 02** — Makeup transfer ("look at your towel right now")
13. **Reason 03** — Washing doesn't fix it
14. **Reason 04** — Friction wrecks skin barrier
15. **Inline lifestyle image** (3:2 placeholder)
16. **Reason 05** — Bathroom environment + 20-minute stat callout
17. **Reason 06** — Fabric softener residue
18. **Pull-quote** (verified customer)
19. **Reason 07** — The fix
20. **Inline product card** with price, stars, "Shop now" button
21. **USP section** — 8 differentiators in a grid
22. **Comparison table** — Your old towel vs. Fomin (8 rows)
23. **"How is this different from face wipes?"** section
24. **"How to actually use them"** section
25. **Certifications strip** — Leaping Bunny, Vegan, TÜV, OEKO-TEX, Plastic Neutral
26. **"Trusted at" retailer logos** — Costco, Anthropologie, Bristol Farms, Thrive Market, Lassen's
27. **Reviews grid** — 4 customer cards (placeholders)
28. **FAQ section** — 7 expandable questions
29. **Final CTA block** — Big ocean-blue button + guarantee row
30. **Ocean wave SVG divider**
31. **Footer** — Links, copyright, FDA disclaimer
32. **Mobile sticky CTA bar** — Appears after 600px of scroll on mobile

---

## Brand tokens

All colors and fonts are CSS variables at the top of `index.html`. To rebrand or theme, edit these:

```css
:root {
  --cream: #FFF5EF;        /* Page background — Fomin signature warm cream */
  --cream-dark: #F5E8DD;   /* Card/pullquote backgrounds */
  --ink: #121212;          /* Main heading text — near-black */
  --body: #383434;         /* Body copy — warm dark brown */
  --muted: #6B6463;        /* Secondary text */
  --indigo: #545084;       /* Brand accent — links, kickers */
  --indigo-soft: #BFC9E9;  /* Lavender accent (announcement bar) */
  --peach: #F4BF8B;        /* Peach gradient end */
  --ocean: #2885C6;        /* Primary CTA + footer */
  --ocean-dark: #1F6A9E;   /* CTA hover */
  --teal: #1FA67A;         /* Success/check marks, discount badges */
  --gold: #C89B3F;         /* Star ratings */
}
```

**Typography:**
- Body: `Outfit` (Google Fonts) — matches Fomin's body font
- Headings: `Assistant` (Google Fonts) — matches Fomin's blog article headings

Both load from Google Fonts CDN — no licensing concerns, fast global delivery.

---

## Questions / issues

If something breaks or you need help customizing further, the file is fully self-contained and human-readable. Open `index.html` in any text editor and you'll find clear comments throughout marking each section.

**File size:** ~52 KB (under 100 KB load goal)
**Dependencies:** 0 (no JS frameworks, no CSS frameworks, no build step)
**Browser support:** Modern browsers (Chrome 90+, Safari 14+, Firefox 88+, Edge 90+)
**Mobile-optimized:** Yes, responsive breakpoints at 720px and 480px

Good luck with the launch.
