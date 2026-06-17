# WARM-SAAS — Playful Productivity & Growth SaaS
*Reference: Todolux (task management), Smartrefer (referral marketing)*
*Best for: productivity tools, consumer SaaS, growth/marketing tools, approachable B2B*

**Theme is independent of this style.** Both references happened to be
light with a warm gradient bloom, but the same gradient-bloom device works
darkened too — see the dark mode palette below. Apply whichever theme the
user chose in Step 0.5.

---

## Typography

**Font pairing:** `Cabinet Grotesk` (display) + `Inter Tight` (body) — or
`Switzer` (display) + `General Sans` (body) as an alternate pairing.

Why: both references use a confident geometric-grotesque for headlines at
fairly large size, but keep body copy in a more neutral, smaller-x-height
font. This prevents the "everything is the same weight" generic SaaS look.
The headline font has slightly tighter, more characterful letterforms than Inter.

```
Hero headline   : 48-64px, weight 700, tracking -0.02em, leading-[1.05]
                  Can be 2-3 lines, left-aligned, NOT centered (both refs
                  left-align hero text even though asset sits beside or below)
Eyebrow         : 12px, weight 600, "WHY TODOLUX?" / "OUR FEATURES" style —
                  often paired with a small emoji or icon, UPPERCASE optional
                  (Todolux uses sentence-case eyebrows with an emoji suffix)
Body            : 14-15px, weight 400, leading-relaxed, muted gray
Feature card title : 16-18px, weight 600
Stat/price numbers : weight 700, large (32-48px for pricing), tabular-nums
Nav             : 14px weight 500, pill-shaped active state background
```

**What makes this NOT generic:** the eyebrow uses a playful marker (emoji or
small icon) rather than a plain uppercase label — this is the visual signature
that separates WARM-SAAS from corporate SaaS. Don't skip this detail.

---

## Color Palette (Tailwind v4) — both modes

### Light mode (the reference default)
```
Background gradient : warm radial/linear gradient, light at edges, saturated
                       at one focal point — Todolux uses peach-to-coral
                       (orange-50 → orange-200 → transparent), Smartrefer uses
                       pale yellow-to-cream (amber-50 → yellow-100)
Surface              : white #FFFFFF for cards sitting on the gradient
Text                  : neutral-900 #171717
Text muted            : neutral-500 #737373
Accent                : ONE warm saturated color — orange-500 #F97316 (Todolux)
                        or amber-400/yellow-500 (Smartrefer) — used for ALL
                        CTAs, active states, and chart/icon accents
Card bg (feature)     : the accent color used as a SOLID fill card (not just
                        outline) for exactly ONE "hero feature" card per grid —
                        this creates visual hierarchy (Todolux's orange "Fast
                        & Light Experience" card sits among otherwise white cards)
```

### Dark mode
```
Background gradient : the same warm radial bloom, but darkened — a deep
                       near-black base (neutral-950) with the warm gradient
                       glow appearing as a muted, desaturated bloom at one
                       focal point (orange-950/40 → transparent, NOT a bright
                       orange-200 wash, which would clash with a dark page)
Surface               : neutral-900 #171717 for cards
Text                   : white #FFFFFF
Text muted             : neutral-400 #A3A3A3
Accent                 : the same warm hue, brightened for contrast —
                        orange-400 #FB923C or amber-400 #FBBF24
Card bg (feature)      : the accent color as a solid fill for the one hero
                        feature card, same 1-special+3-plain pattern, just on
                        a dark base for the plain cards instead of white
```

The gradient background is the single biggest differentiator of this style —
it's not a flat color, it's a soft radial bloom that fades to the base color
by mid-page, in either light or dark mode.

---

## Layout Anatomy (section-by-section)

**1. Nav**
```
Logo + wordmark left, horizontal links center (with dropdown chevrons for
"Made For ▾" / "Resources ▾"), solid pill CTA button right ("Start for Free")
Login link as plain text before the CTA button
```

**2. Hero**
```
Left-aligned text block (eyebrow optional, headline 2-3 lines, subtext 1-2
lines, single CTA button) — RIGHT side or BELOW: floating/scattered UI card
mockups at slight rotation angles (Todolux shows 3-4 small task-card mockups
overlapping at different rotations, not in a clean grid)
Partner/trust logo strip directly below hero, small grayscale logos in a row
Background: the warm gradient bloom described above, concentrated behind the
            floating UI cards
```

**3. Feature Grid (asymmetric, NOT 3-equal)**
```
2x2 or mixed grid where ONE cell is the solid-accent-color "hero" card
(larger icon, bold white text) and the other 3 cells are white cards with
icon + title + 2-line body — this 1-special+3-plain pattern is the signature
move, avoid making all 4 cells visually identical
```

**4. Feature Deep-Dive (alternating zig-zag, max 2-3 instances)**
```
Text left / UI screenshot mockup right, then flips to mockup left / text right
on the next instance — each screenshot mockup shows a believable in-context
UI (task cards, form fields) styled to match the product's actual brand colors,
NOT generic gray wireframes
```

**5. Testimonial (map/world variant)**
```
Smartrefer/Todolux pattern: world map illustration (dotted/outline style) as
background texture, with floating avatar circles positioned at different
"locations," and ONE large centered quote card in the middle with arrow
navigation (prev/next) to cycle testimonials — this is a more illustrative
take than a standard 3-card testimonial grid
```

**6. Pricing**
```
3-column pricing cards, MIDDLE card visually elevated (slight scale-up,
colored border, "Most Popular" badge) — standard SaaS pricing pattern, but
keep the accent color consistent with the rest of the page
Toggle: Monthly/Yearly switch above the cards, accent-colored when active
```

**7. FAQ**
```
Accordion list, left-aligned questions with a +/- icon right, paired beside
a small stat block (Active Users / Reviews / Teams) — this combo of FAQ +
stats side-by-side is more interesting than a standalone FAQ accordion
```

**8. Closing CTA**
```
Full-width gradient or solid-accent band, headline + subtext centered or left,
2 CTA buttons (primary solid + secondary outline "Download App" style),
sometimes with a final UI mockup screenshot peeking from the bottom edge
```

**9. Footer**
```
Dark bg (near-black, NOT pure black), brand statement top-left ("Join millions
who organize..."), multi-column link groups right, social icons bottom
```

---

## Component Specifics

```
Buttons        : solid pill for primary (accent color), outline pill for
                 secondary, height 44-48px
UI mockup cards: white bg, border-radius 12-16px, soft shadow, shown at a
                 slight rotation (2-6deg) when floating in hero, perfectly
                 straight when used in feature deep-dive sections
Feature icons  : simple line icons in colored circle/square badges, OR small
                 custom illustrated icons (Smartrefer uses small 3D-ish icon
                 illustrations for multi-channel/AI features)
Stat chips     : small pill badges showing live-feeling numbers ("82%", "832",
                 "750") next to mini sparkline charts inside mockup cards
```

## Anti-patterns
- No silently assuming light mode — confirm theme in Step 0.5 first
- Never apply the gradient as a flat full-page wash in either mode; it must
  fade out from one focal point by mid-page
- No flat solid-color background for the whole page (must be a gradient bloom, fading out)
- No generic gray dashboard mockups — UI previews must be brand-colored and believable
- No 3-identical-cards feature grid (use the 1-hero+3-plain asymmetric pattern)
- No more than one warm accent hue (don't mix orange AND yellow AND red)
