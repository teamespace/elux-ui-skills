# SERVICE — Trust-First Professional Service
*Reference: Sunfold (solar), Visiona (eyecare), Clinicare (healthcare staffing)*
*Best for: healthcare, professional services, B2C trust-sensitive brands, consultancies*

**Theme is independent of this style.** All three references happened to be
light, but the layout anatomy, font pairing, and component patterns below
work in dark mode too — see the dark mode palette below. Apply whichever
theme the user chose in Step 0.5.

---

## Typography (the part that actually prevents generic output)

**Font pairing:** `Geist` (display + body) or `General Sans` + `Geist Mono` (stats only)

Why this pairing: all three references use a clean, slightly-rounded grotesque
sans for headlines that reads as approachable-professional, not corporate-cold
and not Inter-generic. The key differentiator from generic SaaS is the
**headline weight + size discipline**: headlines are confident but never shouty.

```
Hero headline   : 44-56px, weight 600 (NOT 700/800), tracking -0.02em, leading-[1.1]
                  Two lines max, breaks naturally at a clause boundary
Eyebrow         : 12-13px, weight 500, UPPERCASE, tracking 0.08em, muted color
                  Often prefixed with a small dot/icon (Sunfold: "● Top Solar
                  Energy Company"), NOT a section-number
Body / subtext  : 15-16px, weight 400, leading-relaxed, max-w-[60ch], muted color
Stat numbers    : Geist Mono or tabular-nums sans, 28-36px, weight 600
                  ("10+ Years", "200+ Projects", "5000+ Patients")
Card title      : 18-20px, weight 600
Card body       : 14-15px, weight 400, muted
Nav links       : 14px, weight 400, regular case (never uppercase)
```

**What makes this NOT generic:** the eyebrow + headline + single subtext pattern
is disciplined to exactly 3 elements before the CTA — references never stack
a tagline AND a subtext AND trust badges all in the hero. Pick one supporting
line, not three.

---

## Color Palette (Tailwind v4) — both modes

### Light mode (the reference default)
```
Background     : white #FFFFFF, or very soft tinted sky (Sunfold: pale blue-grey gradient)
Surface         : white #FFFFFF, neutral-50 #FAFAFA for alternating sections
Text            : neutral-900 #171717
Text muted      : neutral-500 #737373
Accent          : ONE saturated color tied to industry — sky-500 (#0EA5E9) for
                  solar/tech-adjacent, blue-600 (#2563EB) for healthcare/medical,
                  emerald-600 for eco/sustainability
Dark section    : slate-900 #0F172A or near-black, used ONLY for the closing
                  CTA band before footer (never the whole page, in this mode)
Card border     : neutral-200 #E5E5E5, very subtle
```

### Dark mode
```
Background     : neutral-950 #0A0A0A, or a very soft dark-tinted variant
                 (deep slate-blue gradient echoing the light mode's sky tint)
Surface         : neutral-900 #171717, neutral-800 #262626 for alternating sections
Text            : white #FFFFFF
Text muted       : neutral-400 #A3A3A3
Accent           : same industry-tied hue, brightened — sky-400 #38BDF8,
                 blue-400 #60A5FA, or emerald-400, for sufficient contrast
Light section    : white or neutral-50, can be used for ONE contrasting trust/
                 stat band (the inverse of the light-mode dark CTA band)
Card border      : white/8 rgba(255,255,255,0.08)
```

One accent color in either mode, used identically in buttons, links, icon
backgrounds, and the active nav state. Never introduce a second saturated color.

---

## Layout Anatomy (section-by-section, in observed order)

**1. Nav**
```
Logo left, link group center-left (Home / About / Services / Why Us),
two CTAs right: ghost "Contact" + solid "Get Started"
Height: 64-72px, white bg, no border or very subtle border-b
Links: regular case, 14px, no underline until hover
```

**2. Hero**
```
Centered text block (eyebrow + 2-line headline + 1 subtext + 1-2 CTAs)
followed by a FULL-WIDTH photo-real product/service image below the fold line
(not beside the text — Sunfold and Visiona both stack hero text ABOVE a large
image, not side-by-side split)
Image: real photography or photo-real 3D render, rounded corners 16-24px,
       no overlay text/badges on top of the image
CTA: one primary solid button, label is an action ("Book a Call", "Schedule
     Your Visit") with a small arrow icon, never "Learn More" alone
```

**3. Mission/Vision Statement Band**
```
Large centered serif-weight statement (still sans font, just bigger/lighter)
broken into a multi-line sentence, sometimes with inline emoji or icon accents
(Sunfold uses inline emoji as a deliberate warmth device — only use this if
the brief explicitly wants approachable/non-corporate tone)
Followed immediately by a 3-stat row (number + label, no cards, no borders)
```

**4. Services / Expertise Grid**
```
Asymmetric 2-column grid where one cell is text+CTA and the adjacent cell is
a full-bleed image — alternating which side has the image (Sunfold pattern)
NOT a 3-equal-card row. Each text cell: small eyebrow + title + 2-line body
+ small "Learn More" link with arrow, dark pill button style
```

**5. Why Choose Us**
```
3-column icon-row UNDER a centered headline — this is the one place a 3-column
grid is acceptable, because items are icon+label only (not full cards with
shadows), kept minimal: colored icon square (8-10px radius) + title + 1-line body
```

**6. Trust/Process strip (optional, Clinicare-style)**
```
Numbered sections using "001 —", "002 —" prefixes are used in Clinicare
specifically because it's a process/journey narrative (this is one of the
few legitimate uses of number-prefixed eyebrows — only when describing an
actual sequential process, not decorative section numbering)
```

**7. Testimonials (if present)**
```
3-column card grid, each card: 5-star icon row + headline quote (1 short line)
+ 2-3 line body + avatar + name + role/location
Real-sounding location-specific roles ("Elderly nurse - Frankfurt") not generic
```

**8. Closing CTA band**
```
Full-width dark section (the ONE place page theme can shift to dark within an
otherwise light page) — large photo background (solar panels, medical equipment)
with dark overlay, headline + subtext left, a small "what to expect" card
(3 bullet points with icons) right — this is the booking-call value prop card
pattern seen in Sunfold
```

**9. Footer**
```
Logo + tagline left, contact info + hours in a 2-column data block,
newsletter input + subscribe button top-right
Large faded brand wordmark sometimes bleeds off the bottom edge (Sunfold) —
optional flourish, not required
```

---

## Component Specifics

```
Buttons       : solid dark pill (border-radius: full) for primary, ghost/outline
                for secondary, height 44-48px
Cards         : border-radius 16-20px, 1px border neutral-200, no shadow OR
                very subtle shadow tinted to bg
Icon badges   : 40-48px square, border-radius 10-12px, accent-tinted bg (10-15%
                opacity), icon in full accent color
Image treatment: real photography or photoreal 3D renders ONLY — never
                illustration-only for this style. Rounded corners 16-24px.
```

## Anti-patterns
- No silently assuming light mode — confirm theme in Step 0.5 first
- No 3-equal feature cards with icons+shadows (use the asymmetric grid pattern)
- No SaaS dashboard-style UI mockups in hero (this is service/consumer-facing, not product UI)
- No more than one accent color
- No generic stock-photo feel — images should look specific to the actual service
