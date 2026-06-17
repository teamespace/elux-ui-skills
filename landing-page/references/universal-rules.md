# Universal Rules — Landing Page Anti-Slop Discipline
*Applies to EVERY style, EVERY page, EVERY time. Non-negotiable. Adapted from
production-tested LLM design-tell research.*

---

## Typography Discipline

**Display / Headlines:** `text-4xl md:text-6xl tracking-tighter leading-none` as baseline.
**Body / Paragraphs:** `text-base text-gray-600 leading-relaxed max-w-[65ch]`.

**Sans font choice:**
- Discouraged as default: Inter. Reach for the style file's named font pairing first.
- Override: Inter is acceptable when the brief explicitly asks for neutral/Linear-style,
  or the brief is public-sector/accessibility-first.

**SERIF DISCIPLINE (very discouraged as default):**
Serif is NOT a default reach for "creative brief." Serif is only acceptable when:
- The brand brief literally names a serif font, OR
- The aesthetic is genuinely editorial/luxury/publication/heritage AND you can
  articulate why this specific serif fits this specific brand.
For everything else, default to sans display fonts named in the style file.
**Banned as defaults regardless of style:** Fraunces, Instrument Serif (the two
LLM-favorite display serifs — overused to the point of being a tell).

**Emphasis rule:** to emphasize a word in a headline, use italic or bold of the
SAME font family. Never inject a different font family mid-headline for "visual interest."

**Italic descender clearance (mandatory):** italic words containing descenders
(y g j p q) need `leading-[1.1]` minimum + `pb-1` reserve, or the descender clips.

---

## Color Calibration

- Max 1 accent color per page. Saturation < 80% by default.
- **THE LILA RULE:** "AI purple/blue glow" aesthetic is banned as default. No
  automatic purple button glows, no random neon gradients. Use neutral bases
  (zinc/slate/stone) with high-contrast singular accents.
- Override: if the brand explicitly calls for purple/violet, embrace it — but
  with intent: consistent palette, harmonized neutrals, restrained gradients.
- **One palette per project.** Don't fluctuate warm/cool grays within one project.
- **COLOR CONSISTENCY LOCK (mandatory):** once an accent is chosen, it's used
  identically on the WHOLE page. No surprise blue CTA in section 7 of a
  warm-grey site. Audit every component before shipping.

**PREMIUM-CONSUMER PALETTE BAN:** for premium-consumer briefs (cookware, wellness,
artisan, luxury, DTC home goods), the LLM default is warm beige/cream + brass/clay/
oxblood + espresso dark text. This exact family is BANNED as default:
```
Banned backgrounds : #f5f1ea, #f7f5f1, #fbf8f1, #efeae0, #ece6db, #faf7f1, #e8dfcb
Banned accents      : #b08947, #b6553a, #9a2436, #9c6e2a, #bc7c3a, #7d5621
Banned text          : #1a1714, #1a1814, #1b1814
```
**Default alternatives (rotate, never reuse twice in a row):**
Cold Luxury (silver-grey + chrome + smoke), Forest (deep green + bone + amber),
Black and Tan (off-black + warm tan, no beige), Cobalt + Cream, Terracotta + Slate,
Olive + Brick + Paper, Pure monochrome + single saturated pop.

---

## Layout Diversification

- **Anti-center bias:** centered hero/H1 avoided when `DESIGN_VARIANCE > 4`. Force
  split-screen (50/50), left-content/right-asset, or asymmetric whitespace.
  Override OK for editorial/manifesto/launch-announcement briefs.
- **NO 3-column equal feature cards.** The generic identical-three-card row is
  banned. Use 2-column zig-zag, asymmetric grid, scroll-pinned, or horizontal-scroll.
- **SHAPE CONSISTENCY LOCK:** pick ONE corner-radius scale for the whole page
  (all-sharp / all-soft 12-16px / all-pill for interactive) and stick to it.
- **Section-Layout-Repetition check:** no two sections share the same layout
  family. At least 4 different layout families across 8 sections.
- **Zigzag Alternation Cap:** no 3+ consecutive sections with the same
  image+text-split layout.

---

## Materiality & Cards

- Use cards ONLY when elevation communicates real hierarchy. Otherwise group
  with `border-t`, `divide-y`, or negative space.
- Shadow tint matches background hue. No pure-black drop shadows on light bg.
- For `VISUAL_DENSITY > 7`: generic card containers are banned.

---

## Interactive States (full cycle, always)

- **Loading:** skeletal loaders matching final layout shape. No generic spinners.
- **Empty states:** beautifully composed, indicate how to populate.
- **Error states:** clear, inline for forms, contextual toasts for transient.
- **Tactile feedback:** `:active` uses `-translate-y-[1px]` or `scale-[0.98]`.
- **BUTTON CONTRAST CHECK (mandatory a11y):** every CTA text readable against
  its bg. White-on-white, transparent-no-border CTAs — banned. WCAG AA min
  (4.5:1 body, 3:1 large text 18px+). Same for ghost buttons over photos (use
  scrim or stroke).

---

## Copy Discipline

**Banned filler verbs:** "Elevate", "Seamless", "Unleash", "Next-Gen", "Revolutionize" → use concrete verbs instead.
**Banned generic names:** "John Doe", "Sarah Chan" → use creative, realistic, locale-appropriate names.
**Banned generic avatars:** SVG "egg" or default user icons → use believable photo placeholders.
**Banned fake-perfect numbers:** `99.99%`, `50%`, `1234567` → use organic messy data (`47.2%`, real-looking figures).
**Banned startup-slop names:** "Acme", "Nexus", "SmartFlow", "Cloudly" → invent contextual names that sound real.

**Fake-precise numbers** (92%, 4.1x, 48k) must either come from real data, be
explicitly labeled as mock, or be skipped. Don't fake engineering precision
the brand doesn't claim.

**One copy register per page.** Don't mix technical mono, editorial prose, and
marketing punch in one composition unless the brand voice explicitly calls for it.

**Quotes & testimonials:** max 3 lines of quote body. Never 6. Cut longer quotes
down to a snippet. Attribution: name + role + company. Never name only.

---

## Page Theme Lock

Theme (light / dark / mixed) is decided once, in `SKILL.md` Step 0.5, before
any code is written — never inferred silently from the picked style or the
brief's vibe words. Once decided, the page has ONE theme. Sections do not invert.
- If dark mode, ALL sections are dark. No warm-light section sandwiched in a
  dark page (or vice versa).
- Exception: a deliberate mixed mode (e.g. dark hero / light body) is allowed
  ONLY when the user explicitly chose "mixed" in Step 0.5 — max one full
  theme-switch moment, never alternating further down the page.
- Section-level tint within the same theme family is fine
  (`bg-zinc-950` next to `bg-zinc-900`); flipping to `bg-amber-50` mid-page is broken.

---

## Motion Discipline

- **MOTION MUST BE MOTIVATED.** Before any animation, ask: "what does this
  communicate?" Valid: hierarchy, storytelling, feedback, state transition.
  Invalid: "it looked cool." If you can't articulate the reason in one
  sentence, drop the animation.
- **"Motion claimed, motion shown."** If `MOTION_INTENSITY > 4`, the page must
  actually move: hero entry, scroll-reveal, hover physics on CTAs minimum.
  Never half-build motion that breaks.
- **MARQUEE MAX-ONE-PER-PAGE.** Horizontal scrolling text/logo marquees appear
  at most once. Two+ marquees = lazy filler.
- See `references/motion.md` for canonical GSAP/Motion code patterns and the
  full forbidden-pattern list (no `window.addEventListener('scroll')`, etc).

---

## AI Tells — Forbidden Patterns (the production-tested list)

### Visual & CSS
- NO neon/outer glows by default. Use inner borders or subtle tinted shadows.
- NO pure black `#000000`. Use off-black, zinc-950, or charcoal.
- NO oversaturated accents — desaturate to blend with neutrals.
- NO excessive gradient text on large headers.
- NO custom mouse cursors.

### Hero & Top-of-Page
- NO version labels in hero (`V0.6`, `BETA`, `INVITE-ONLY`, `EARLY ACCESS`)
  unless the brief is genuinely a product launch.
- NO "Brand · No. 01"-style sub-eyebrows.

### Section Numbering & Labels
- NO section-number eyebrows (`00 / INDEX`, `001 · Capabilities`, `06 · how it works`).
  Eyebrows name the topic in plain language, not enumerate.
- NO `01 / 4`-style pagination labels on images/bento tiles.
- NO generic step labels (`Stage 1`, `Step 1`, `Phase 01`) — use the verb-noun
  directly ("Install", "Configure", "Ship").

### Separators & Decoration
- Middle-dot (`·`) max 1 per line in metadata strips, not the default separator everywhere.
- NO decorative colored status dots on every list/nav/badge — only for real semantic state.
- NO vertical rotated text ("INDEX OF WORK, 2018-2026") unless agency/Awwwards brief.
- NO crosshair/hairline grid lines purely as decoration.
- NO decoration text strip at hero bottom (`BRAND. MOTION. SPATIAL.`).
- NO floating top-right sub-text in section headings (corner-floating paragraph Tell).

### Fake Product Previews
- NO div-based fake product UI in hero (fake task list, fake terminal, fake
  dashboard from styled divs) — the #1 LLM-design tell. Use real screenshot,
  generated image, real component preview, or skip the preview.
- NO fake version footers (`v0.6.2-rc.1`, `last sync 4s ago`) inside fake screenshots.

### Marketing-Copy Tells
- NO "Quietly in use at / Quietly trusted by" social-proof headers. Use "Trusted by",
  "Used at", "Customers include" — or skip the heading.
- NO "Field notes / Currently on the bench / Loose plates"-style poetic labels —
  use plain functional labels.
- NO locale/weather strips (`LIS 14:23 · 18°C`) unless brief is genuinely place-focused.
- NO micro-meta-sentences under eyebrows ("Each of these is a feature we ship today...").

### Pills, Captions, Footers
- NO pills/labels overlaid on images (`Brand · 02`, `Field notes - journal`).
- NO photo-credit captions as decoration unless crediting a real photographer.
- NO version footers on marketing pages (`v1.4.2`, `Build 0048`).
- NO "Reservation 412 of 800"-style fake live-stock counters.

### Lists & Comparisons
- NO `border-t` + `border-b` on every row of a long list — pick one, sparingly.
- NO scoring bars with filled background tracks as comparison visuals on a
  landing page — that's dashboard-UI clutter. Use number + icon, or thin
  inline bar without track.

### Scroll & Locale Cues
- **Scroll cues are banned.** No "Scroll", "↓ scroll to explore", animated
  mouse-wheel icons. If the user hasn't scrolled, they're looking at the hero —
  they know what scroll is.
- NO locale/city/time strips for 99% of briefs (agency-portfolio decoration tell).

---

## EM-DASH BAN (the single most-violated tell — zero tolerance)

**Em-dash (—) is COMPLETELY banned.** No "limited use," no "body copy is fine"
exception. None.

- Banned in headlines → use period or comma.
- Banned in eyebrows/labels/pills/buttons/captions/nav → use line breaks, columns, hairlines.
- Banned in body copy → restructure with two sentences, a comma, parentheses, or a colon.
- Banned in quote attribution → use a normal hyphen with spaces ( - ).
- Banned in en-dash form (–) as separator too. Date ranges use a hyphen (2018-2026).

The ONLY permitted dash characters: regular hyphen `-`, minus sign in math (`-5°C`).

If a single `—` or `–` appears anywhere visible, the output fails pre-flight
and must be rewritten. This has historically been ignored when phrased as
"use sparingly" — the rule here is binary: zero em-dashes.

---

## Accessibility & Performance Guardrails

- Animate ONLY `transform` and `opacity`. Never `top`, `left`, `width`, `height`.
- **Reduced motion (mandatory):** any motion above `MOTION_INTENSITY > 3` MUST
  honor `prefers-reduced-motion`. Infinite loops, parallax, scroll-hijack
  collapse to static under reduced motion.
- **Dark mode:** design for both modes from the start unless brief says light-only.
  No pure `#000000`/`#ffffff` — use off-black/off-white for depth.
- **Core Web Vitals targets:** LCP < 2.5s, INP < 200ms, CLS < 0.1. Hero image
  uses `next/image priority` or preload.
- **Z-index restraint:** never spam arbitrary `z-50`/`z-10`. Use systemic layer
  contexts only (sticky nav, modals, overlays).
- **Viewport stability:** NEVER `h-screen` for full-height hero. ALWAYS
  `min-h-[100dvh]` to prevent mobile layout jumping.

---

## FINAL PRE-FLIGHT CHECK

Run this before outputting any code. Not optional — every box must be honestly
checkable, or the output is not done.

- [ ] Design Read declared (Step 0 one-liner)?
- [ ] Theme question asked or already answered by the user (Step 0.5) — never silently assumed?
- [ ] Dial values explicit and reasoned, not silently defaulted?
- [ ] Style picked and named, file read before generating?
- [ ] **ZERO em-dashes anywhere** — headlines, eyebrows, pills, body, quotes, captions, buttons?
- [ ] Page Theme Lock: ONE theme for the whole page, no mid-page flip?
- [ ] Color Consistency Lock: one accent used identically across all sections?
- [ ] Shape Consistency Lock: one corner-radius system throughout?
- [ ] Button Contrast Check: every CTA readable against its bg (WCAG AA 4.5:1)?
- [ ] CTA label never wraps to 2+ lines at desktop?
- [ ] Serif discipline: not Fraunces/Instrument Serif unless explicitly justified?
- [ ] Premium-consumer palette check: not the banned beige+brass+espresso family?
- [ ] Italic descender clearance on every italic word with y/g/j/p/q?
- [ ] Hero fits viewport: headline ≤ 2 lines, subtext ≤ 20 words/4 lines, CTA visible without scroll?
- [ ] Hero top padding max `pt-24`, content not floating mid-viewport?
- [ ] Hero stack ≤ 4 text elements (eyebrow, headline, subtext, CTAs)?
- [ ] No 3-equal-column generic feature cards?
- [ ] No section-number eyebrows (`00/INDEX`, `001 · Capabilities`)?
- [ ] No generic step labels (`Step 1`, `Stage 1`)?
- [ ] No decorative status dots without real semantic meaning?
- [ ] No scroll cues (`Scroll`, `↓ scroll to explore`)?
- [ ] No fake div-based product screenshots in hero?
- [ ] No version footers (`v1.4.2`) on marketing pages?
- [ ] No locale/time/weather strips unless brief is place-focused?
- [ ] Logo wall uses real SVG logos, lives under hero (not inside it)?
- [ ] Copy self-audit: no AI-hallucinated or grammatically broken strings?
- [ ] Motion motivated: every animation justified in one sentence?
- [ ] Marquee max-one-per-page?
- [ ] No `window.addEventListener('scroll')` — Motion/GSAP/IntersectionObserver only?
- [ ] Reduced motion wrapped for everything `MOTION_INTENSITY > 3`?
- [ ] Dark mode tokens defined and tested in both modes (if applicable)?
- [ ] Viewport stability: `min-h-[100dvh]`, never `h-screen`?
- [ ] Section-Layout-Repetition: at least 4 layout families across 8 sections?
- [ ] Icons from Phosphor only, no hand-rolled SVG paths?
- [ ] Core Web Vitals plausibly hit?

If a single checkbox cannot be honestly ticked, fix it before delivering.
