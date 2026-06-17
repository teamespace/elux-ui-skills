# TECHNICAL — Technical AI SaaS & Developer-Adjacent Tools
*Reference: Seospace/Seio (AI SEO platform, light + dark variants)*
*Best for: AI SaaS with a clear workflow/process, dev-adjacent tools, B2B technical products*

**Theme is independent of this style — and was already decided in Step 0.5,
not inferred here.** The reference itself shipped two real variants (a fully
light build and a dark-hero/light-body build), so this style is the most
flexible in the library on this axis. Do not default to dark just because
the brief mentions "AI" or "infrastructure" — apply whichever theme the user
chose.

---

## Typography

**Font pairing:** `Geist` (display + body) + `Geist Mono` (scores, metrics,
keyword data tables)

Why: the reference is data/workflow-heavy (SEO scores, keyword tables,
step sequences) so the monospace-for-data discipline matters even more here
than in INFRA — every numeric score, percentage, and data-table cell
uses tabular monospace, while headlines and body stay in the clean grotesque.

```
Hero headline   : 36-48px weight 600, tracking -0.02em, leading-[1.15]
                  States the product category clearly ("Your Always On AI
                  SEO Growth Engine") — functional and descriptive, not
                  abstract/poetic
Eyebrow/badges  : small inline star-rating + review-count badges directly
                  under the CTA buttons (NOT a separate eyebrow line above
                  headline) — trust signals sit close to the action point
Body            : 14-15px weight 400 leading-relaxed
Score/gauge number: Geist Mono, 28-36px weight 700, paired with a small
                  "/100" suffix in muted weight
Data table cells : Geist Mono, 13-14px, tabular-nums, right-aligned for numbers
Section heading  : 24-30px weight 600, centered (this style centers section
                  headlines, unlike SERVICE/WARM-SAAS which lean left-aligned)
Step label       : the literal action verb ("Enter Keyword", "Generate",
                  "Publish") in 14-16px weight 600, never "Step 1"
```

---

## Color Palette (Tailwind v4) — both modes

### Light mode (fully light build)
```
Background       : white #FFFFFF, soft blue-tinted neutral-50 for
                  alternating sections
Surface          : white, with 1px border neutral-200
Text             : neutral-900 #171717
Text muted        : neutral-500 #737373
Accent            : blue-600 #2563EB or sky-500 #0EA5E9
```

### Dark mode (hero can stay dark even if body is light — see Mixed option)
```
Background        : slate-950 #020617
Surface            : slate-900 #0F172A, 1px border white/8
Text               : white #FFFFFF
Text muted          : slate-400 #94A3B8
Accent              : blue-500 #3B82F6 or sky-400 #38BDF8 (brightened for
                    sufficient contrast on dark)
```

### Mixed (dark hero / light body — a real reference variant, not an
### improvisation)
```
Hero section only : dark mode tokens above
Everything below   : light mode tokens above
This is the ONE style in the library where a dark-hero/light-body split is
part of its native reference DNA, not just a generic Page Theme Lock
exception — but it is still only used when the user picked "mixed" in
Step 0.5, never assumed by default.
```

**Gauge colors (same in any mode):**
```
multi-stop gradient arc (red→amber→emerald) ONLY for the score gauge widget
specifically — this is the one legitimate multi-color use case (representing
a literal range), not used elsewhere on the page in any theme
```

---

## Layout Anatomy (section-by-section)

**1. Nav**
```
Logo left, links center (Features / Pricing / Testimonial / Blog), Sign In
ghost link + solid accent Sign Up button right
```

**2. Hero**
```
Left: headline + subtext + dual CTA (solid primary "Automate My SEO" + ghost
secondary "See a Demo" with small play-icon) + star-rating/review badges row
Right OR below: a SCORE GAUGE WIDGET (circular gauge showing "90/100" with
       the multi-color arc) paired with a small functional-looking keyword
       input card — this gauge widget is the hero's visual anchor, more
       compelling for a "scoring" product than abstract illustration
Background transition: an ISOMETRIC LINE-ART illustration (folded paper/box
       shapes in an accordion arrangement) bridges the hero into the next
       section — this isometric motif recurs as a section-divider device,
       not just a one-off hero decoration
```

**3. Feature Grid (2-column, paired UI widgets)**
```
2x3 or 2x2 grid where EVERY cell pairs a short title+description with a
SMALL embedded functional UI widget specific to that feature (keyword
research table, article generation toggle, export-to-platform checklist,
inline AI editing preview) — every single feature claim is backed by a
believable mini-interface, this is denser/more proof-heavy than other styles
```

**4. How It Works (numbered circles, NOT number-prefix text labels)**
```
3-step horizontal flow: each step is a FILLED CIRCLE containing just the
digit (1, 2, 3) as a small visual marker, connected by a dotted line, with
the actual step name as a separate bold label below the circle ("Enter
Keyword", "Generate", "Publish") — the numbering is a visual connector
device, not a text-label crutch; this is allowed under universal rules
because the number lives in a graphic element, not as a text eyebrow
Below: 3 screenshot cards showing each step's actual interface
```

**5. Audience Segmentation Grid**
```
2x3 icon-grid (SEO Agencies / Affiliate Marketers / Bloggers / Startups /
Niche Site Owners) — small icon + title + 1-line body, no heavy cards, just
icon+text pairs in a clean grid, helps technical buyers self-identify quickly
```

**6. Pricing**
```
2-column (simpler than 3-tier patterns in other styles — fits a more focused
product), recommended tier has accent-colored border + "Most Popular" badge,
full checklist of features per tier
```

**7. Testimonials**
```
3-column cards OR dark-bg logo+quote cards (Seospace shows quotes paired
directly with a large company logo on a dark card background, rather than
a person's avatar) — this logo-forward testimonial style suits B2B-technical
audiences who recognize company names more than individual names
```

**8. Integration Diagram**
```
A NODE-CONNECTOR diagram: central product logo with thin connector lines
radiating out to partner-tool logos (WordPress, Notion, Zapier, HubSpot) —
this radial integration map is a recognizable, legitimate pattern for
positioning a product within a tool ecosystem
```

**9. Content/Blog Showcase**
```
3-column article preview cards (image + date/author meta + title + 1-line
excerpt + "Read Article" link) — standard blog-teaser pattern, kept simple
```

**10. Closing CTA**
```
Centered headline + subtext + single CTA, paired with a small score-gauge
widget repeated from the hero (visual bookend/callback)
```

**11. Footer**
```
Dark near-black bg, logo + 1-line tagline left, 3-column link groups
(Product / Resource / Company) right, standard structure
```

---

## Component Specifics

```
Score gauge      : circular arc widget, multi-stop gradient fill (red→amber→
                  emerald), large number center, "/100" suffix muted, small
                  label below ("Your Score is Excellent")
Step connector   : numbered filled circles connected by a dotted/dashed line,
                  horizontal on desktop, can stack vertical on mobile
Integration map  : central node + radiating thin lines (1-1.5px) to surrounding
                  small logo chips, lines fade in opacity toward the edges
Isometric illustration: folded-box/paper-accordion line-art shapes, used as
                  a section-transition graphic device (not random decoration —
                  it should feel like it represents "structured content" or
                  "workflow steps" conceptually)
Data table        : Geist Mono numbers, right-aligned, subtle row hover state,
                  small colored difficulty/score badges inline
```

## Anti-patterns
- No abstract/poetic headline — this audience wants to know exactly what the
  product does in the first line
- No "Step 1/2/3" text labels — use numbered circles as a graphic device plus
  a real action-verb label
- No single flat-color icons without function — pair feature claims with
  actual mini-UI widgets wherever possible
- No silently picking light, dark, or mixed mode — that choice belongs to
  Step 0.5, not to this style's defaults
- No multi-color usage anywhere except the literal score-gauge arc, in any theme
