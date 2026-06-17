# Components Reference — Section Block Library
*Cross-style vocabulary. Pick blocks that fit the picked style's layout anatomy
(see references/styles/[name].md for which blocks that style actually uses).*

---

## Landing Page Patterns (overall page structure)

Pick ONE primary pattern per page — this determines section ORDER and emphasis,
distinct from the visual style which determines section APPEARANCE.

```
Hero-Centric          : product has strong visual identity, hero dominates,
                        minimal sections after — short, punchy page
Conversion-Optimized  : every section drives toward one CTA, repeated CTA
                        bands, urgency/stat-driven copy
Feature-Rich Showcase  : SaaS with many capabilities, dense feature grids,
                        deep-dive sections per feature
Minimal & Direct       : simple product, very few sections, large whitespace,
                        one clear value prop
Social-Proof-Focused    : services/B2C, testimonials and trust signals appear
                        multiple times, case studies prominent
Interactive Demo        : software/tools, embedded UI previews and step-flows
                        dominate over copy
Trust & Authority        : B2B/enterprise, logos/certifications/credentials
                        prominent, conservative layout
Storytelling-Driven       : brand/agency/nonprofit, narrative arc across
                        sections, mission statement prominent
```

Match to style: SERVICE↔Trust&Authority or Social-Proof, WARM-SAAS↔Feature-Rich
or Minimal, INFRA↔Interactive Demo, CREATIVE-AI↔Hero-Centric, CONVERSION↔
Conversion-Optimized, TECHNICAL↔Feature-Rich or Interactive Demo.

---

## Hero Paradigms (vocabulary)

```
Asymmetric Split Hero    : text one side, asset other side, generous whitespace
Centered Stack Hero       : eyebrow+headline+subtext+CTA centered, asset below
                           (used by SERVICE, CREATIVE-AI, TECHNICAL styles)
Editorial Manifesto Hero   : large type, no asset, near-poster
Video/Media Mask Hero      : type cut out as mask over video background
Device Mockup Hero          : real phone/laptop frame showing actual app UI
                           beside or below text (INFRA signature)
Floating Card Collage Hero  : 3-5 UI mockup cards scattered at angles
                           (WARM-SAAS signature)
Staggered Screenshot Hero    : 3 screenshots at different heights/rotations
                           in a loose hand-of-cards arrangement (CONVERSION)
```

---

## Feature Section Layouts

```
Asymmetric 2-Col Grid    : alternating image/text cells, never 3-equal
                          (SERVICE signature)
1-Hero+3-Plain Grid       : one cell gets solid accent fill + larger icon,
                          other 3 stay plain white cards (WARM-SAAS signature)
Paired-Widget Grid         : every feature cell shows a small functional UI
                          widget alongside copy (TECHNICAL signature)
Zig-Zag Deep-Dive            : alternating text-left/image-right then flips,
                          MAX 2-3 instances before switching layout family
Bento Grid                    : mixed cell sizes, CSS grid with fractional
                          units, at least 2-3 cells with real visual variety
Checklist + Screenshot         : checkmark list left, single UI screenshot
                          right, one item gets expanded description (CONVERSION)
```

---

## Social Proof Patterns

```
3-Card Testimonial Grid    : standard — star rating + quote + avatar + name/role
Radial Testimonial          : one large central quote, satellite quotes/avatars
                           around the edges (INFRA signature)
Map/World Testimonial        : world map texture bg, floating avatars at
                           "locations," single navigable quote card (WARM-SAAS)
Single Pull-Quote             : one large serif italic quote, no grid, small
                           avatar cluster above (CONVERSION signature)
Logo-Forward Quote Cards       : company logo prominent alongside quote, suits
                           B2B-technical audiences who recognize brand names
Social-Feed Grid                : masonry mix of generated content + user posts,
                           mimics a social feed (CREATIVE-AI signature)
```

---

## Pricing Patterns

```
3-Tier Equal Cards         : standard, middle tier elevated via border/badge only
3-Tier Color-Invert          : middle tier fully inverts to dark/accent bg
                           while flanking tiers stay light (CONVERSION signature)
2-Tier Focused                : simpler product, fewer choices, less decision
                           fatigue (TECHNICAL signature)
Toggle Monthly/Yearly          : switch above cards, savings badge per card
```

---

## How-It-Works Patterns

```
Numbered Circle Connector    : filled circles with digits, dotted connector
                           line, real action-verb label below each (TECHNICAL)
Verb-Phrase Steps              : no numbering at all, just sequential verb-led
                           titles with screenshots ("Choose Template", "Set
                           Triggers", "Track Results") (CONVERSION)
```

Never use generic "Step 1 / Step 2 / Step 3" text labels — see universal-rules.md.

---

## CTA Band Patterns

```
Simple Centered CTA           : headline + subtext + single button, clean bg
Photo-Background CTA            : full-width dark-overlay photo, headline+CTA
                           left, value-prop mini-card right (SERVICE signature)
Gradient Band CTA                : warm or accent gradient fill, 2 CTAs
                           (primary + secondary), optional UI peek (WARM-SAAS)
Globe/Network Visual CTA          : large network/globe graphic, suits
                           geographically-distributed products only (INFRA)
```

---

## Integration/Ecosystem Patterns

```
Radial Node Diagram    : central logo, thin connector lines to surrounding
                        partner-tool logo chips, lines fade toward edges
                        (TECHNICAL signature) — legitimate, not decorative,
                        when product genuinely has integrations to show
Logo Wall                : simple grayscale logo row, lives UNDER hero never
                        inside it, real SVG logos only
```

---

## Anti-Pattern Cross-Reference (see universal-rules.md for full list)

The most commonly violated ones, repeated here for visibility while building blocks:
```
NEVER : 3-equal feature cards with identical icon+title+body structure
NEVER : Generic step-1/2/3 labels
NEVER : Fake div-based product screenshots — use real or generated images
NEVER : More than one marquee per page
NEVER : Section-number eyebrows (00/INDEX, 001 · Capabilities)
```
