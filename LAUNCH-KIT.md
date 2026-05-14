# Fomin Advertorial — Launch Kit

Companion to `index.html`. Use this file for Meta ad campaigns and image generation.

---

## 1. Three Meta Ad Copy Variants

Each variant targets a different psychology. Test all three at $20-30 / day each for 3-5 days, then scale the winner.

### How Meta Ads Are Structured

Meta ads have three text fields:
- **Primary Text** (caption above the image, ~125 chars before "See more" truncation, 2200 max)
- **Headline** (bold text below image, 40 char limit recommended)
- **Description** (smaller text below headline, 30 char limit recommended, optional but increases trust)

All three variants drive to the same landing page:
`https://yoedhistiera-skyvane.github.io/7-reasons-why-fomin-facial-towels/?utm_source=meta&utm_medium=paid_social&utm_campaign=hidden_cause_acne&utm_content=[variant]`

---

### Variant A — "Curiosity / Investigation" Angle

**Hook psychology:** Reader feels like they're being told a secret. Best for cold traffic with no prior awareness of the towel-bacteria problem.

**Primary Text:**
```
I spent six weeks investigating why a friend's $40 cleanser wasn't working.

The answer wasn't her routine. It wasn't her diet. It wasn't even her skin.

It was something hanging right next to her bathroom sink.

University of Arizona research found 90% of bathroom towels carry coliform bacteria within weeks of use, even when washed regularly. And we've been wiping our skincare off with them every night.

Estheticians have been quietly recommending a fix for the last year. Here's what we found 👇
```

**Headline:** `The Hidden Cause of Adult Acne`

**Description:** `New Research · 6 min read`

**Best for:** Women 25-45, interested in skincare, with no prior Fomin awareness. Lookalikes from your buyer list.

---

### Variant B — "Specific Problem / Direct Solution" Angle

**Hook psychology:** Reader recognizes their own situation. Best for retargeting or warm traffic.

**Primary Text:**
```
Your bathroom towel has bacteria on it. Yes — even the clean one.

A 2023 study in Scientific Reports (Nature) found biofilms form on towels within weeks of regular use. Washing doesn't fully remove them. And fabric softener residue is a documented skin irritant.

If your routine has been "perfect on paper" but your skin isn't cooperating, this might be why.

The fix is smaller than you'd think.
```

**Headline:** `Why Your Skincare Isn't Working`

**Description:** `Backed by peer-reviewed research`

**Best for:** Retargeting audiences (people who visited fominsoap.com or your TikTok). Skincare-spending warm audiences.

---

### Variant C — "Personal Story / Soft Sell" Angle

**Hook psychology:** Reader connects emotionally before the pitch. Best for engagement-optimized campaigns.

**Primary Text:**
```
A friend texted me last month: "I don't know what else to do."

She'd done everything. Switched cleansers. Cut dairy. Silk pillowcase. Threw out old makeup. Her cystic acne kept getting worse.

So I started asking estheticians. Five of them. Same question to each: "What would you change first?"

They all said the same thing. And it wasn't a product I'd ever thought about.
```

**Headline:** `What 5 Estheticians Told Me`

**Description:** `The fix nobody talks about`

**Best for:** Discovery-stage cold traffic. Performs best with engagement-optimized campaigns (testimonial / story style).

---

### Creative Notes for All Three

- **Use the hero image** from the advertorial (or a higher-quality real photo of the product on a clean surface). Avoid pure product shots — those underperform vs. lifestyle shots.
- **No medical claims in the ad copy.** "Adult acne" and "skin barrier" are okay; "cures acne," "treats rosacea," "FDA-approved" are not. Meta's policy team will flag medical claim language and reduce delivery.
- **Avoid "before/after" imagery in the ad creative itself.** Meta restricts this for skincare. The evidence comparison image is fine inside the article, but not in the ad.
- **Test thumb-stopping vs. story-driven.** Variant B works as a video ad (15-30 sec). Variants A and C work better as single-image ads with strong primary text.

---

## 2. Nano Banana Image Prompts

For Google Gemini's image generation (Nano Banana). Use these two prompts to replace the placeholder images in `images/hero.webp` and `images/evidence-towels.webp`.

### Important Caveats Before Generating

1. **AI-generated product photography risks brand mismatch.** If the AI invents a "Fomin" package design that doesn't match the real product, readers will notice when they reach the PDP. For the hero image, **strongly consider using a real photo from Fomin's existing product photography** instead. Their lifestyle shots on fominsoap.com are excellent and brand-accurate.
2. **No human faces.** Both prompts intentionally exclude people to avoid AI face-generation legal risk.
3. **Re-generate if results look stocky.** Add the phrase "subtle imperfection, hand-styled" if the output looks too polished/AI-perfect.

---

### Image 1 — Hero Image (`hero.webp`)

**Aspect ratio:** 16:9 horizontal
**Recommended dimensions:** 1600 × 900 pixels
**Save as:** WebP, quality 80-85

**Prompt for Nano Banana:**
```
Editorial product photography, top-down flat lay on a warm cream-colored
linen surface. Composition: a neatly folded stack of three or four pure
white facial towels in the center-left of the frame, with one towel
gently unfolded showing soft cotton-like texture. Upper right: a small
minimalist matte ceramic dish containing a single droplet of clear water.
Lower right: a delicate sprig of fresh eucalyptus, casually placed at a
gentle angle. Soft natural morning light from upper left, creating subtle
warm shadows across the surface. Color palette: cream, soft peach,
muted indigo accent. Style reference: Kinfolk magazine, Cup of Jo,
editorial wellness photography. Shot on medium format camera, shallow
depth of field, slightly desaturated tones, warm undertones. No text,
no logos, no brand markings on any object. No people visible. No hands.
16:9 horizontal composition, high detail, photorealistic, 8K quality.
```

**Negative prompt (if Nano Banana supports it):**
```
no text, no logos, no brand names, no watermarks, no human faces,
no hands, no children, no graphic content, no medical imagery,
no microscope view, no bacteria visualization, no insects, no mold,
no gore, no harsh colors, no studio sterile feel
```

---

### Image 2 — Evidence Comparison (`evidence-towels.webp`)

**Aspect ratio:** 4:3 horizontal
**Recommended dimensions:** 1200 × 900 pixels
**Save as:** WebP, quality 80-85

**Prompt for Nano Banana:**
```
Side-by-side comparison photography, two facial towels laid flat on a
neutral light-gray studio surface, both shot from directly above. Left
side: a worn cotton terry bathroom towel showing visible faint grayish
discoloration, subtle yellowing in patches, small fabric pilling on the
surface, looking authentically used but not extremely dirty. Right side:
a pristine bright white plant-fiber facial towel, perfectly clean, slight
texture visible. Both towels are approximately the same size in frame.
Even diffused studio lighting, soft shadows, no harsh highlights. A
subtle thin dotted vertical line down the exact center of the frame
separating the two halves. Style: clinical but warm, like a beauty
editorial "before and after" feature in a magazine. Color palette muted,
neutral, warm gray undertones. No text, no labels, no brand markings on
either towel. No people. No hands. 4:3 horizontal composition,
photorealistic, high detail.
```

**Negative prompt:**
```
no text, no logos, no brand names, no watermarks, no human faces,
no hands, no children, no graphic content, no medical imagery,
no microscope view, no bacteria visualization, no insects, no mold
visible, no gore, no extreme dirt, no stains, nothing disgusting
```

---

### Notes on the Evidence Image

The "worn towel" needs to look **subtly used**, not gross. The conversion goal is to make readers think "huh, my towel probably looks like that" — not "ew, that's disgusting." If your first generation comes out too gross, regenerate with these adjustments:
- Reduce "yellowing" to "faint discoloration"
- Remove "pilling" if the AI is making it look like mold
- Add "clean but visibly aged"

---

## 3. Post-Launch Checklist

Before going live:

- [ ] Replace 4 placeholder reviews with real verified customer reviews from Fomin's Shopify or Costco
- [ ] Verify $10.80 / $12.00 launch pricing is current on Fomin's PDP
- [ ] Verify 60 towels per box count is accurate (it's the standard Fomin spec but worth confirming)
- [ ] Replace `images/hero.webp` and `images/evidence-towels.webp` with real or generated photos
- [ ] Add Meta Pixel ID to the commented-out tracking block in `<head>`
- [ ] Add GA4 Measurement ID to the commented-out tracking block in `<head>`
- [ ] Consider registering `theskinfiles.co` (or similar) for true third-party feel
- [ ] Test the page on mobile (iPhone Safari + Android Chrome at minimum)
- [ ] Run all 3 CTAs through actual click tests to verify UTM parameters appear in GA4

After launch:

- [ ] Watch scroll heatmap (Hotjar free tier) for drop-off points
- [ ] Watch CTR by CTA position (UTM differentiates them: `cta1_after_research`, `cta2_pricing`, `cta3_final`, `sticky`, `pricing_reveal_link`)
- [ ] If CTR-to-PDP is high but PDP-to-purchase is low, the article's selling well but the PDP needs work
- [ ] If scroll completion is low (<40% reach the final CTA), trim further

---

## 4. Honest Caveats for the Advertorial

Things worth flagging to whoever reviews this:

1. **The hosted URL is on a Fomin-owned domain.** The "Skin Files" branding only fully works if you register a separate domain. On a fominsoap.com subdomain, savvy readers will see through the third-party framing immediately.

2. **The 4 customer reviews are placeholders.** Empty review cards reduce conversion more than no review section at all. Fill them or remove the section before launch.

3. **Maya Ellison is a fictional byline.** The footer disclosure ("Bylines on The Skin Files are illustrative") provides some FTC cover, but the safer long-term move is to either (a) use a real Fomin team member or (b) commission a real licensed esthetician to review and put their real name on it.

4. **The "5 estheticians we interviewed" framing is rhetorical.** It implies primary research that may not have actually happened. If Fomin has talked to any estheticians (even informally, even via DM), this framing is fine. If literally no estheticians were consulted, this becomes a misleading claim and should be softened to "estheticians we follow" or similar.

5. **The 18¢ per use math** assumes 60 towels per box. If the box count is different, the cost-per-use math is wrong. Verify before launch.
