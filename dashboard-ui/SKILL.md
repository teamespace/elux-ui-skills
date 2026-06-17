---
name: dashboard-ui
description: >
  Use this skill for ANY dashboard or admin panel design request — KPI overviews,
  analytics pages, data tables, metric cards, chart layouts, or any web-based
  data interface. Triggers on: "buat dashboard", "design admin panel", "bikin
  analytics page", "KPI dashboard", "data visualization", "reporting UI",
  "management panel", or any request producing a data-heavy web interface.

  Picks a named style from the style library, enforces data hierarchy + chart +
  layout rules, runs pre-flight checklist, then builds. Works with all agents:
  Claude, Codex, Cursor, Windsurf.
---

# Dashboard UI Skill

Web-based dashboard — desktop-first, data-driven, scannable.

---

## Step 1 — Set the Dials

```
DATA_DENSITY    : 7   // 1–10 | how much info per viewport (low=airy, high=bento-packed)
CHART_RICHNESS  : 7   // 1–10 | chart complexity (low=sparklines only, high=full viz library)
MOTION_DEPTH    : 5   // 1–10 | animation intensity (dashboards prefer subtle over flashy)
```

---

## Step 2 — Pick a Style

Auto-pick based on context, or user calls by name: `"pakai style OBSIDIAN"`

| Style    | Best for                                              | Reference              |
|----------|-------------------------------------------------------|------------------------|
| CHALK    | Clean SaaS admin, product dashboards, light minimal   | Cursor, ElevenLabs     |
| CANVAS   | Data-dense light, developer/technical, KPI-heavy      | Cloudflare, DisputeFox |
| OBSIDIAN | Dark glassy, AI/tech products, rich widget bento      | Vapi, HRadar           |
| ABYSS    | Dark premium, fintech/banking, dramatic data viz      | NeuroBank, Nexus dark  |

**Auto-pick logic:**
```
Clean SaaS / product admin     → CHALK
Developer / ops / technical    → CANVAS
AI product / dark mode app     → OBSIDIAN
Fintech / banking / premium    → ABYSS
Unknown                        → ask ONE question, then pick
```

After picking → **read `references/styles/[name].md`** before generating.

---

## Step 3 — Load Supporting References

| Need                         | Read                           |
|------------------------------|--------------------------------|
| Always                       | `references/styles/[name].md` |
| Always (components)          | `references/shadcn.md`         |
| Charts & data visualization  | `references/charts.md`         |
| Layout & grid system         | `references/layout.md`         |
| Tables & list views          | `references/tables.md`         |
| Icons                        | `references/icons.md`          |
| Multi-page flows / navigation | `references/flow.md`           |

---

## Step 4 — Pre-Flight Checklist (MANDATORY)

```
□ Style picked (named or auto) + reason stated
□ Dials set
□ Primary metric / KPI visible without scrolling (above the fold)
□ Visual hierarchy: metric size reflects importance (biggest = most critical)
□ Every chart has: title, axis labels (if needed), legend, empty state
□ Data is realistic — no "0", "$0.00", or placeholder values
□ Tables have: sortable columns indicated, row hover state, pagination
□ Left sidebar has: active state, grouped sections with labels
□ Color used semantically: green=positive, red=negative, blue=neutral/info
□ Icon set decided (from references/icons.md)
□ Shadcn CSS variables set in globals.css (from references/shadcn.md)
□ All interactive components use shadcn (Button, Card, Table, Badge, etc)
□ Responsive breakpoint noted (dashboard = 1280px+ primary)
```

---

## Step 5 — Build

Output adapts to request:

| Request              | Default output                                           |
|----------------------|----------------------------------------------------------|
| Full dashboard       | HTML/JSX, 1440px wide, full layout with sidebar          |
| Single page/section  | Isolated section with proper context                     |
| Component            | All states: default, loading, empty, error, hover        |
| Chart component      | Recharts/Chart.js snippet with realistic data            |
| Figma-ready spec     | Token block + spacing annotation + component inventory   |

---

## Layout Anatomy (always apply)

```
Sidebar        : fixed left, 220–260px wide
                 Logo top, nav grouped by section, user/workspace bottom
Top bar        : page title left, actions/filters right (date picker, export, filter)
Content area   : sidebar to right edge, scrollable
                 Padding: 24–32px horizontal, 24px vertical
KPI row        : top of content, 3–4 cards across full width
Chart grid     : below KPI row, 2-col or 3-col grid
Tables         : full width, below charts
```

---

## Data Hierarchy Rules (always apply)

```
Hero metric    : largest number on page — 32–48px, bold
KPI cards      : 24px number, 12px label above, delta badge
Section title  : 14–16px, semibold, with optional icon
Chart title    : 13–14px, medium weight, left-aligned
Table header   : 11–12px UPPERCASE, muted, letter-spaced
Body data      : 13–14px, regular/medium
Muted/meta     : 11–12px, 40–50% opacity
```

---

## Semantic Color Rules (always apply)

```
Positive delta  : emerald-500 / green — "↑ 15.8%"
Negative delta  : rose-500 / red — "↓ 34.0%"
Neutral info    : sky-500 / blue — informational
Warning         : amber-500 — caution states
Active nav      : style-defined accent
Chart colors    : use references/charts.md palette
NEVER           : use red/green for non-semantic purposes
NEVER           : more than 5 distinct colors in one chart
```

---

## Anti-Slop Rules (always enforce)

```
NEVER  : Generic card with just title + number (add sparkline or delta)
NEVER  : Placeholder data — $0, 0 users, empty charts
NEVER  : All charts same type (mix bar, line, donut, area)
NEVER  : Purple-blue gradient background (generic AI dashboard)
NEVER  : Sidebar without active state distinction
NEVER  : Table without hover state or sort indicators
NEVER  : KPI cards all same size regardless of importance
NEVER  : Chart without title or context
ALWAYS : At least one "hero" visual moment (big chart, gauge, heatmap)
ALWAYS : Consistent spacing grid throughout
ALWAYS : Realistic, domain-appropriate data and labels
```
