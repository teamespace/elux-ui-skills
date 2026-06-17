# INFRA — Security, Privacy & Infrastructure Products
*Reference: Lumba VPN*
*Best for: VPN, security tools, privacy products, infrastructure/networking SaaS*

**Theme is independent of this style.** The reference happened to be dark,
but the layout anatomy, font pairing, and component patterns below work in
either mode. Apply whichever theme the user chose in Step 0.5.

---

## Typography

**Font pairing:** `Geist` (display) + `Geist Mono` (technical data: speeds,
IPs, connection times) + `Inter` (body)

Why: the reference uses a clean modern grotesque for headlines but switches
to monospace for ANY live/technical data (connection timer "01:25:49",
bandwidth "12.0 mb/s", IP addresses) — this monospace-for-data discipline is
what makes the product feel technically credible rather than marketing-fluffy.
This holds in both light and dark mode.

```
Hero headline   : 40-52px, weight 600, tracking -0.02em, leading-[1.15]
                  3 lines acceptable here (more than other styles) because
                  the headline doubles as a value-prop list
Eyebrow/tagline : two short feature claims side by side under headline
                  ("Fast Reliable and Easy-to-Use VPN" · "Strict no-logs
                  Policy") separated by a small icon, NOT a single eyebrow line
Body            : 14-15px, weight 400, leading-relaxed
Live data       : Geist Mono, 14-20px, weight 500, ALWAYS tabular-nums
                  (connection timers, speed counters, IP addresses)
Price           : 32-40px weight 700, with Geist Mono for the decimal/currency
Feature card title : 16-18px weight 600
```

---

## Color Palette (Tailwind v4) — both modes

### Dark mode
```
Background      : near-black with subtle texture — neutral-950 #0A0A0A with
                  a faint topographic/mountain silhouette graphic bleeding
                  in from the hero, NOT flat black
Surface          : neutral-900 #171717, sometimes with a 1px lighter border
Surface elevated : neutral-800 #262626 (pricing card highlight, mockup frames)
Text             : white #FFFFFF
Text muted        : neutral-400 #A3A3A3
Border            : white/8 rgba(255,255,255,0.08)
Accent            : teal/emerald-400 #2DD4BF or mint-400
```

### Light mode
```
Background      : white #FFFFFF, with a faint topographic line-art texture
                  in neutral-100 bleeding in from the hero (same motif as
                  dark mode, inverted contrast)
Surface          : neutral-50 #FAFAFA, 1px border neutral-200
Surface elevated  : white with a colored border (pricing highlight, mockup frames)
Text             : neutral-900 #171717
Text muted        : neutral-500 #737373
Border            : neutral-200 #E5E5E5
Accent            : teal-600 #0D9488 or emerald-600 (darker shade than the
                  dark-mode accent, for sufficient contrast on white)
```

In either mode, the accent is used sparingly and deliberately: the literal
"connect" power button (a circular glowing element), toggle switches, and
the "Most Popular" pricing card border. It never appears as a large background
fill; it stays as a precise, small, glowing accent.

### Mixed/split option
If the user explicitly asked for a dark-hero / light-body split (a legitimate
one-time Page Theme Lock exception), use dark mode tokens for the hero only,
then light mode tokens for everything below it — never alternate further.

---

## Layout Anatomy (section-by-section)

**1. Nav**
```
Logo left, horizontal links center (Features ▾ / Pricing / Testimonial /
Resources ▾), Log In ghost link + solid accent-color pill CTA right
("Create Account")
```

**2. Hero**
```
Left: headline (can be 3 lines) + two short feature-claim lines with small
check/shield icons + single CTA button
Right: a REAL DEVICE MOCKUP — phone showing the actual app UI (connection
timer, speed graph, country selector) — this is a legitimate device-mockup
use case, NOT a fake div-screenshot, because it's framed as an actual phone
silhouette with a believable, fully-designed app screen inside
Background: faint topographic/mountain-range silhouette, very subtle, never
            competing with the foreground content — render in whichever
            theme's neutral tone is appropriate
```

**3. Trust/Partner Strip**
```
"Our partners have confidence in the safety of our services" — small
grayscale/monochrome logo row directly under hero, standard pattern
```

**4. Feature Grid (2x2 or 2x3, asymmetric sizing allowed)**
```
Each cell: icon/small graphic + title + 1-2 line body, paired with a SMALL
embedded UI widget showing the relevant live data (a mini server-location
selector, a mini speed graph, a toggle switch demo) — features are not just
text+icon, they show a believable miniature of the actual interface
```

**5. Open-Source / Trust Signals band**
```
This section uses a deliberate ONE-TIME contrast moment regardless of the
page's chosen theme: if the page is dark, this band can flip to a light
card section to signal "transparency" (this is the legitimate Page Theme
Lock exception, used intentionally, not randomly). If the page is already
light, this band can use a subtly different surface tone instead of an
actual theme flip.
3-column: Open Source / High-speed servers / Strict no-logs, icon + title + body
```

**6. Product Showcase (hero asset, large)**
```
Full laptop mockup sitting on a textured surface (rock/stone texture in
reference, can be lighter wood/marble texture for light mode) showing the
FULL app dashboard UI — this is the "money shot" that proves the product
is real; surrounding negative space and subtle lighting/shadow make it feel
premium rather than like a flat screenshot paste
```

**7. Pricing**
```
3-column cards, middle card elevated with accent-colored border + "Most
Popular" badge + slightly larger scale, each card shows the FULL feature list
(not abbreviated), savings badge top-right of each card ("Save 87%")
```

**8. Testimonials**
```
Circular/radial layout: large central quote card surrounded by smaller
satellite quote snippets at the edges, avatars are small circles — this
radial arrangement is more distinctive than a flat 3-card row
```

**9. Closing CTA + Globe Visual**
```
Centered headline + subtext + single CTA, followed by a large globe/earth
graphic with connection-line arcs (signature "world coverage" visual for VPN/
network products) — render as a dark wireframe sphere with glowing arcs in
dark mode, or a lighter line-art sphere with accent-colored arcs in light
mode. This graphic only makes sense for geographically-distributed service
products, don't reuse for unrelated SaaS.
```

**10. Footer**
```
Bg matches the page's chosen theme, multi-column link groups (product,
resources, platforms, connect), logo top-left, standard structure
```

---

## Component Specifics

```
Buttons         : solid accent pill for primary, ghost/outline for
                  secondary, height 44-48px
Device mockups  : phone/laptop frames with REAL believable app screens inside
                  — connection timer, speed graphs, server selector UI, all
                  styled consistently with the brand's actual accent palette
Toggle switches : pill-shaped, accent color when active, neutral when inactive
Live data widgets: small embedded cards showing timer/speed/location — Geist
                  Mono for all numbers, small accent-colored live-indicator dot
                  (this IS an acceptable use of a decorative dot — it's real
                  semantic state: "connection active")
Globe graphic   : wireframe/dotted sphere with glowing connection arcs,
                  tone matched to the chosen theme
```

## Anti-patterns
- No warm colors anywhere (stays in cool teal/mint + neutral grays, in either theme)
- No fake div-based UI mockups — device mockups must show a fully fleshed-out,
  believable app interface, not placeholder boxes
- No decorative dots except the one legitimate "connection active" indicator
- No flat pure black `#000000` or pure white `#FFFFFF` for backgrounds —
  always near-black/near-white with subtle texture or tone variation
- Do not assume this style means dark mode — confirm theme in Step 0.5 first
