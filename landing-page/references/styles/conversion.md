# CONVERSION — E-commerce Growth & Upsell SaaS
*Reference: FluxUpsell*
*Best for: e-commerce tools, Shopify apps, conversion-rate-optimization SaaS, growth tools*

**Theme is independent of this style.** The reference happened to be light,
but the layout anatomy, font pairing, and component patterns below work in
dark mode too — see the dark mode palette below. Apply whichever theme the
user chose in Step 0.5.

---

## Typography

**Font pairing:** `Söhne` or `General Sans` (display) + `Inter` (body) +
serif accent for ONE specific use: pull-quote testimonials only.

Why a serif accent here specifically: the reference uses a light editorial
serif exclusively for the large customer testimonial pull-quote ("Flux helped
us increase our AOV by 28%...") — this is justified per the serif discipline
rule because it's marking a genuine "voice of customer" editorial moment, not
used as the page's primary display font.

```
Hero headline   : 40-52px, weight 600-700, tracking -0.02em, leading-[1.1]
                  States a concrete outcome with a number ("Increase AOV By
                  20% Instantly") — headlines in this style ALWAYS contain
                  the core metric/outcome, not abstract benefit language
Eyebrow         : 11-12px weight 600 UPPERCASE tracking-wide, prefixed with a
                  small bullet/dot icon ("● USED BY 500+ HIGH-GROWTH MERCHANTS")
Body            : 14-16px weight 400 leading-relaxed
Stat callout    : 28-36px weight 700, tabular-nums, paired with a plain-language
                  label below (NOT inside a bordered box — sits in open space)
Pull-quote (serif): 20-24px, serif italic, weight 400, leading-relaxed,
                  reserved EXCLUSIVELY for testimonial blockquotes
Pricing number  : 32-40px weight 700
```

---

## Color Palette (Tailwind v4) — both modes

### Light mode (the reference default)
```
Background      : white #FFFFFF, with neutral-50 #FAFAFA alternating sections
Surface          : white, with a soft mesh/blob gradient texture in specific
                  feature sections (very subtle, teal-tinted, never competing
                  with foreground content)
Text             : neutral-900 #171717
Text muted        : neutral-500 #737373
Accent            : teal/emerald-600 #059669 — used for ALL CTAs, checkmarks,
                    active pricing tier, and chart/donut-chart segments
Pricing highlight : the middle/recommended tier gets a solid dark-teal fill
                    (not just a border) — this card inverts to dark bg + white
                    text while the other two tiers stay light, creating strong
                    visual hierarchy
```

### Dark mode
```
Background      : neutral-950 #0A0A0A, neutral-900 alternating sections
Surface          : neutral-900 #171717, with the same subtle mesh/blob
                  texture but teal-tinted at lower opacity against dark
Text             : white #FFFFFF
Text muted        : neutral-400 #A3A3A3
Accent            : teal/emerald-400 #2DD4BF — brightened for contrast on dark
Pricing highlight  : the middle tier inverts the OTHER direction here — it
                    gets a bright teal/white fill while the flanking tiers
                    stay on the dark base, preserving the same "middle tier
                    visually pops" hierarchy regardless of theme
```

---

## Layout Anatomy (section-by-section)

**1. Nav**
```
Logo left, links center (Home / Features / Case Studies / Pricing), solid
accent-color CTA pill right ("Book a Demo")
```

**2. Hero**
```
Centered eyebrow + headline + subtext + single CTA + small trust row (platform
compatibility badge + star rating), all centered and stacked
Below: THREE overlapping/staggered UI screenshot cards at slightly different
       heights (not perfectly aligned in a row — staggered like a loose hand
       of cards), each showing a distinct real product screen (popup builder,
       cart upsell widget, analytics report) — this staggered-height card
       arrangement is the signature hero-asset move for this style
```

**3. Problem Statement Band**
```
Large centered statement (2-3 sentences, slightly larger than body text,
NOT a headline size) framing the core pain point in plain language, followed
by a 3-stat row (no cards, no borders, just number+label in open space)
```

**4. Feature Explanation (text + UI screenshot split)**
```
Left: eyebrow + headline + a checklist (checkmark icon + short label, 3-4
items, NO description text per item, just the label) + ONE item expanded
with a short description (FluxUpsell highlights "Smart Suggestions" with
extra body text while the other 3 checklist items stay label-only)
Right: a single clean UI screenshot in a card frame
```

**5. Case Study / Social Proof**
```
Real product photography (e.g., skincare product flatlay) paired with a
stat callout card overlaid or adjacent (large $ figure + 1-line context) +
a short attributed quote with name+role — this is more concrete/specific
than generic testimonials because it ties to one named case study
Partner/customer logo row sits ABOVE this section, small grayscale logos
```

**6. How It Works (3-step, NOT generic step-1-2-3 labels)**
```
3-column grid, each showing a UI screenshot card + a concrete action title
("Choose Template", "Set Smart Triggers", "Track Real Results") — note these
are VERB-PHRASE titles, never "Step 1/2/3" labels (per universal rules)
```

**7. Pricing**
```
3-column, middle tier inverted to solid dark-teal bg as described in palette
section, each card lists full benefits with checkmarks, CTA button matches
each card's color scheme (light cards get teal CTA, dark middle card gets
white/light CTA for contrast)
```

**8. Testimonial (single large quote)**
```
NOT a grid — one large serif pull-quote centered, with 3-4 small circular
avatar headshots arranged loosely above/around it (not in a perfect row),
small play-button icons on some avatars suggesting video testimonials
```

**9. FAQ**
```
Simple accordion, plain functional question labels, +/- icon toggle right
```

**10. Closing CTA**
```
Centered headline + subtext + single solid CTA button on a clean white or
very subtle textured bg
```

**11. Footer (dark, minimal)**
```
Dark near-black bg, single-line brand statement + link row, no heavy
multi-column structure — this style keeps the footer deliberately lighter/
shorter than other styles, consistent with its clean conversion-focused ethos
```

---

## Component Specifics

```
Buttons         : solid pill, accent teal for primary, dark outline for
                  secondary, height 44-48px
Staggered cards : 3 UI screenshots at different y-offsets and slight rotation,
                  creating depth without a literal 3D effect — achieved via
                  margin-top offsets and 2-4deg rotation per card
Checklist items : checkmark icon (filled circle, accent color) + label,
                  vertical stack, generous line-height between items
Pricing card invert: middle tier swaps text-on-light for light-text-on-dark,
                  everything else (border-radius, padding, structure) stays
                  identical to the other two cards
```

## Anti-patterns
- No equal-height pricing cards (middle tier must be visually distinct via
  color inversion, not just a border or badge)
- No generic step-1-2-3 labels in the "how it works" section
- No fake/abstract icons for the checklist items — use a consistent filled
  checkmark style throughout
- No serif font anywhere except the single testimonial pull-quote use case
- No more than one accent color (teal/emerald only, no secondary color), in either theme
- No silently assuming light mode — confirm theme in Step 0.5 first
