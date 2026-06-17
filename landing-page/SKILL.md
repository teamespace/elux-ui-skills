---
name: landing-page
description: >
  Use this skill for ANY landing page, marketing site, or promotional web page
  request. Triggers on: "buat landing page", "design marketing site", "bikin
  homepage produk", "landing page untuk SaaS/produk/jasa", "promotional page",
  or any request producing a conversion-focused web page.

  This skill enforces brief inference, anti-slop universal rules (typography,
  color, layout, copy, motion discipline), picks a named style from the style
  library based on visual reference DNA, then builds. Works with all agents:
  Claude, Codex, Cursor, Windsurf.

  ALWAYS read references/universal-rules.md before generating any code — these
  rules apply regardless of which style is picked and are non-negotiable.
---

# Landing Page Skill

Mixed-purpose landing pages — SaaS, service business, e-commerce, AI products,
agency, consumer. Style adapts to the brief; universal rules never do.

---

## Step 0 — Brief Inference (Read the Room First)

Before touching code or dials, infer what the user actually wants.

**Read these signals:**
1. Page kind — SaaS, professional service, e-commerce, AI/creative tool, agency/portfolio
2. Vibe words used — "clean", "premium", "playful", "technical", "trustworthy", "bold"
3. Reference signals — URLs, screenshots, named competitors
4. Audience — B2B buyer, consumer, technical user, trust-sensitive (medical/finance)
5. Existing brand assets (for redesigns)

**State a one-line Design Read before any code:**
> "Reading this as: [page kind] for [audience], leaning toward [style name]."

Example: *"Reading this as: B2B SaaS landing for technical buyers, leaning toward TECHNICAL style with isometric illustration and step-flow."*

If the page kind/audience/style is ambiguous, ask **exactly one** clarifying
question about it. If you can confidently infer it, do not ask.

---

## Step 0.5 — Theme Question (ALWAYS ASKED, no exceptions)

**Theme (light / dark / both) is independent of style.** No named style is
locked to a theme — every style in the library must work in either mode, or
as a deliberate light-to-dark split across sections. Never silently default
to dark just because the brief sounds "techy," "AI," or "infra" — that
association is a bias to actively resist, not a rule to follow.

Unless the user has already stated a theme preference explicitly in their own
words (e.g. "make it dark mode", "light and clean please", "dark hero with a
light body"), **always ask this one question before generating anything**:

> "Should this be light mode, dark mode, or a mix (e.g. dark hero, light body)?"

This question is asked even when the Design Read in Step 0 was fully
confident and no other clarifying question was needed. Theme is a separate
axis from page-kind/audience/style inference and does not get inferred
silently.

Once answered (or already stated), lock it per `references/universal-rules.md`
Page Theme Lock: one theme for the whole page, with at most one deliberate
full theme-switch moment if the user explicitly asked for a mixed/split theme.

---

## Step 1 — Set the Dials

```
DESIGN_VARIANCE  : 7   // 1–10 | 1=symmetric grid, 10=asymmetric/masonry chaos
MOTION_INTENSITY : 6   // 1–10 | 1=static, 10=cinematic scroll-driven
VISUAL_DENSITY   : 4   // 1–10 | 1=airy/gallery, 10=packed/dense
```

**Dial inference from brief signals:**

| Signal                                          | VARIANCE | MOTION | DENSITY |
|--------------------------------------------------|----------|--------|---------|
| Trust-first / professional service / medical     | 4-5      | 3-4    | 3-4     |
| SaaS mainstream / productivity                   | 6-7      | 5-6    | 4-5     |
| AI / creative / vibrant showcase                  | 8-9      | 7-8    | 4-5     |
| Technical / developer / step-flow                | 6-7      | 4-5    | 4-5     |
| Conversion-focused e-commerce SaaS                | 6-7      | 5-6    | 5-6     |
| Dark tech / security / privacy                    | 6-7      | 6-7    | 3-4     |

---

## Step 2 — Pick a Style

Six named styles, each derived from real reference DNA — layout anatomy,
font pairing, and component patterns. **None of these names imply a theme.**
"INFRA" does not mean dark, "SERVICE" does not mean light. Theme was already
decided in Step 0.5; apply it on top of whichever style fits the brief.

Auto-pick based on brief, or user calls by name: `"use the TECHNICAL style"`.

| Style       | Best for                                          | Reference DNA              |
|-------------|----------------------------------------------------|-----------------------------|
| SERVICE     | Professional service, healthcare, trust-first B2C  | Solar, eyecare, healthcare staffing |
| WARM-SAAS   | Productivity tools, consumer SaaS, playful growth  | Task management, referral marketing |
| INFRA       | Security, privacy, VPN, infrastructure products    | VPN product                |
| CREATIVE-AI | AI tools, creative/generative products             | AI image generator         |
| CONVERSION  | E-commerce SaaS, upsell/growth tools                | Shopify upsell app          |
| TECHNICAL   | Technical AI SaaS, dev tools, step-flow products    | AI SEO tool                |

**Auto-pick logic (page kind only, theme is separate — see Step 0.5):**
```
Trust-first service / medical / finance      → SERVICE
Productivity / growth / consumer SaaS        → WARM-SAAS
Security / privacy / VPN / infra             → INFRA
AI / creative / generative tool              → CREATIVE-AI
E-commerce / conversion / upsell SaaS         → CONVERSION
Technical AI SaaS / dev tool / SEO            → TECHNICAL
Unknown page kind                             → ask ONE question, then pick
```

After picking → **read `references/styles/[name].md`** before generating.
This file contains the FULL font pairing rationale and section-by-section
layout anatomy, with token tables for BOTH light and dark mode — apply
whichever the user chose in Step 0.5.

---

## Step 3 — Load Supporting References

| Need                                  | Read (MANDATORY ORDER)              |
|----------------------------------------|--------------------------------------|
| Always, first                          | `references/universal-rules.md`      |
| Always, second                         | `references/styles/[name].md`        |
| Scroll animation / GSAP / Motion       | `references/motion.md`               |
| Section blocks (hero, pricing, FAQ)    | `references/components.md`           |
| Images, illustrations, mockups         | `references/assets.md`               |

`universal-rules.md` is non-negotiable and applies on top of every style —
it contains the anti-slop tells, em-dash ban, color/typography discipline,
and the final pre-flight checklist.

---

## Step 4 — Pre-Flight Check

Run `references/universal-rules.md` Section "FINAL PRE-FLIGHT CHECK" in full
before shipping any output. Every box must be honestly checkable. This is
not optional — if a single box fails, the output is not done.

---

## Step 5 — Build

| Request               | Default output                                          |
|------------------------|-----------------------------------------------------------|
| Full landing page      | Next.js/React, RSC default, Tailwind v4, Motion for interactivity |
| Single section          | Isolated component matching picked style's tokens          |
| Redesign                | Audit first per universal-rules.md Section 11 (Redesign Protocol) |
| Static HTML              | Tailwind CDN + vanilla JS, same style rules apply           |

**Stack defaults** (from universal-rules.md, summarized):
```
Framework  : React / Next.js, Server Components default
Styling    : Tailwind v4
Animation  : Motion (motion/react) for UI; GSAP+ScrollTrigger for scroll-hijack
Icons      : Phosphor Icons (consistent with mobile/dashboard skills)
Fonts      : next/font or self-hosted — never <link> Google Fonts in prod
```

**Asset flow (mandatory order, see `references/assets.md`):**
```
1. Ship the page with every image slot already filled — SVG illustration,
   smart placeholder, or hand-built UI mockup. Never an empty slot.
2. Deliver. Do not push image-gen prompts unprompted.
3. Offer once: "Want prompts to generate real photography for these
   placeholders?" Wait for a yes.
4. Only after confirmation, produce style-matched prompts for the
   requested slots.
```
