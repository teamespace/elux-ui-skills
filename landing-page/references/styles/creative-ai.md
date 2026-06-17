# CREATIVE-AI — AI & Generative Creative Products
*Reference: Motama.AI (AI portrait generator)*
*Best for: AI image/video tools, generative creative products, visual AI SaaS*

**Theme is independent of this style.** The reference happened to be dark,
but the layout anatomy, font pairing, and component patterns below work in
either mode. Apply whichever theme the user chose in Step 0.5.

---

## Typography

**Font pairing:** `Geist Display` or `PP Neue Montreal` (headline) + `Inter`
(body) — headline rendered in ALL CAPS for maximum visual impact, with a
SINGLE word in the headline rendered in a vibrant gradient/italic treatment
as the focal emphasis point.

```
Hero headline   : 32-44px, weight 700, UPPERCASE, tracking -0.01em, leading-[1.2]
                  ONE word or short phrase gets a gradient-color italic
                  treatment ("STUNNING VISUAL" in the reference) — this is
                  the signature move: emphasis via color+italic on the SAME
                  font family, not a different font
Body            : 14-15px weight 400, leading-relaxed, gray-400 on dark
Section heading : 24-28px weight 600, NOT uppercase (contrast with hero)
Stat callout    : 32-40px weight 700, with the key number in accent color
                  ("7,329,297 Profile Pictures... for 21,434 Happy Users" —
                  the number itself is colored, not the whole sentence)
Card/feature title : 16-18px weight 600
```

**What makes this NOT generic:** the all-caps hero is a deliberate, confident
choice that signals "bold creative tool" — but it's balanced by sentence-case
everywhere else on the page, so the page doesn't read as shouty throughout.
Use this contrast deliberately: ONE uppercase moment, not a page-wide habit.

---

## Color Palette (Tailwind v4) — both modes

### Dark mode
```
Background      : near-black, neutral-950 #0A0A0A, sometimes with a very
                  subtle dot-grid or noise texture
Surface          : neutral-900 #171717
Text             : white #FFFFFF
Text muted        : neutral-400 #A3A3A3
Accent gradient   : violet-500 → fuchsia-500 → cyan-400
```

### Light mode
```
Background      : white #FFFFFF, optionally with a very subtle dot-grid
                  texture in neutral-100
Surface          : neutral-50 #FAFAFA, 1px border neutral-200
Text             : neutral-900 #171717
Text muted        : neutral-500 #737373
Accent gradient   : violet-600 → fuchsia-600 → cyan-500 (slightly deepened
                  from dark-mode values for sufficient contrast on white)
```

In either mode, the gradient is used ONLY for: the emphasized hero word, the
primary CTA button gradient fill, and small icon accents — NEVER as a full-page
background wash.

**Accent solid (alt, either mode):** if a single accent is preferred over
gradient, violet-500 #8B5CF6 (dark) or violet-600 #7C3AED (light) alone.

**Important override of the LILA RULE:** this is the one style category where
a violet/purple gradient is justified BY DESIGN, because the product category
(AI generative art) has a real visual association with "AI magic" that a
violet gradient legitimately communicates — but it must be used with intent
(confined to specific accent moments) not as a default page-wide wash, in
either theme.

---

## Layout Anatomy (section-by-section)

**1. Nav**
```
Logo left, horizontal links center (Home / About / Gallery / Pricing / FAQ),
solid gradient-fill pill CTA right ("Download App")
```

**2. Hero**
```
Centered headline (uppercase, with gradient-italic emphasis word) + subtext
+ a FUNCTIONAL-LOOKING input field (text prompt input with a small icon/avatar
inside it, e.g. "woman_beuty.png" with a generate button) — this single
interactive-looking input is the hero's main visual anchor, more compelling
than a plain CTA button alone for a generative-AI product
Below: a SHOWCASE COLLAGE of 4-6 generated example images at varying sizes/
       crops, arranged asymmetrically (not a clean grid) with a circular
       "shuffle/regenerate" icon button floating in the center overlap
```

**3. Feature Grid (mixed-size bento, NOT equal cards)**
```
2-column asymmetric: one larger cell (with embedded mini-UI showing a model
selector + generate button + sample output image) paired with smaller text
cells describing distinct capabilities — each feature cell that references a
"transformation" capability shows a believable before/after or style-comparison
visual, not just an icon
```

**4. Style/Theme Showcase Gallery**
```
Dense MASONRY-style image grid (8-10+ generated example images at mixed aspect
ratios) — this is the core trust-building device for an AI image product:
showing volume and variety of real output. Grid should feel abundant, not
sparse. NOT a 3-column gallery; use a true masonry/mixed-aspect arrangement.
```

**5. Social Proof Grid (user-generated content style)**
```
A grid of small "social post" style cards mixing: generated images, user
avatar + handle + short quote, arranged in a Pinterest/masonry-like layout —
mimics a social feed rather than a traditional 3-card testimonial row, which
fits the "people are sharing this everywhere" narrative for a viral AI tool
```

**6. Final Showcase Band**
```
A second large image collage (different crop/arrangement from the hero
collage) paired with a closing headline + single CTA — reinforces visual
abundance one more time before the footer
```

**7. Footer**
```
Dark bg, logo + tagline left, link columns (Home/Help/Newsletter), email
input + subscribe button with the gradient-fill button style maintained
```

---

## Component Specifics

```
Buttons          : gradient-fill pill for primary CTA (violet→fuchsia), solid
                   dark with white border for secondary
Input field (hero): pill-shaped, dark surface bg, icon-left, functional-looking
                   placeholder text, small avatar/thumbnail chip inside if
                   referencing an uploaded image
Image showcase    : masonry/mixed-aspect-ratio grids, generous gap (8-12px),
                   rounded corners 8-12px (smaller radius than other styles —
                   images are the content, chrome should be minimal)
Shuffle/regen icon: circular button, gradient or accent-color fill, positioned
                   at the overlap point of a hero collage
```

## Anti-patterns
- No flat 3-column equal galleries — always masonry/mixed-aspect for image showcases
- No gradient wash across the entire page background (confine gradient to
  specific accent moments: hero word, CTA buttons, small icon details)
- No generic "AI sparkle" icon overuse — use it once, deliberately, not on
  every card
- No stock-photo-feeling example images — generated examples should look
  genuinely AI-generated and varied in style, reinforcing the product's range
