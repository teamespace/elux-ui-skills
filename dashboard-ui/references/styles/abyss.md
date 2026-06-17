# ABYSS — Dark Premium / Fintech
*Reference: NeuroBank, Nexus dark | Best for: fintech, banking, premium analytics*

---

## Palette (Tailwind v4)

| Role          | Token           | Hex                         | Usage                          |
|---------------|-----------------|------------------------------|--------------------------------|
| Page bg       | slate-950       | #020617                     | App background                 |
| Page bg alt   | —               | #0D1117                     | Slight variation (use sparingly) |
| Sidebar bg    | slate-900       | #0F172A                     | Left nav                       |
| Surface       | slate-900       | #0F172A                     | Cards                          |
| Surface raised| slate-800       | #1E293B                     | Elevated elements, hover       |
| Border        | slate-700/40    | rgba(51,65,85,0.4)          | Card borders                   |
| Border accent | blue-500/30     | rgba(59,130,246,0.3)        | Highlighted card borders       |
| Sidebar active| slate-800       | #1E293B                     | Active nav item bg             |
| Text          | white           | #FFFFFF                     | Primary                        |
| Text secondary| slate-400       | #94A3B8                     | Labels, secondary              |
| Text muted    | slate-600       | #475569                     | Meta, timestamps               |
| Accent        | blue-500        | #3B82F6                     | Primary accent                 |
| Accent bright | blue-400        | #60A5FA                     | Hover states, highlights       |
| Accent glow   | blue-500/20     | rgba(59,130,246,0.2)        | Glow effects, bg tint          |
| Positive      | emerald-400     | #34D399                     | Growth, success                |
| Negative      | rose-400        | #FB7185                     | Decline, error                 |
| Chart 1       | blue-400        | #60A5FA                     | Primary — bars, lines          |
| Chart 2       | violet-400      | #A78BFA                     | Secondary series               |
| Chart 3       | cyan-400        | #22D3EE                     | Third series                   |
| Chart 1 dim   | blue-400/20     | rgba(96,165,250,0.20)       | Bar chart dim variant          |
| Grid line     | white/4         | rgba(255,255,255,0.04)      | Chart grid lines               |
| Grid texture  | —               | `+` pattern white/3         | Optional bg grid texture       |

---

## Typography

Font stack: `"Plus Jakarta Sans"` for display + `"Inter var"` for data
→ Plus Jakarta Sans punya personality lebih dari Inter — terasa premium tapi tetap readable.
→ Enable `font-variant-numeric: tabular-nums` untuk semua angka.

| Role           | Font              | Size  | Weight | Tracking   | Notes                        |
|----------------|-------------------|-------|--------|------------|------------------------------|
| Welcome/hero   | Plus Jakarta Sans | 28px  | 700    | -0.02em    | white, "Welcome back, X"     |
| Page title     | Plus Jakarta Sans | 20px  | 600    | -0.01em    | white                        |
| Section title  | Plus Jakarta Sans | 16px  | 600    | -0.01em    | white                        |
| Date label     | Plus Jakarta Sans | 11px  | 700    | 0.05em     | UPPERCASE, slate-400         |
| KPI number     | Plus Jakarta Sans | 36px  | 700    | -0.03em    | white, tabular-nums          |
| KPI label      | Plus Jakarta Sans | 13px  | 400    | 0          | slate-400                    |
| Chart axis     | Inter             | 10px  | 400    | 0          | slate-500, tabular-nums      |
| Chart value    | Inter             | 11px  | 500    | 0          | white/80                     |
| Table header   | Inter             | 11px  | 500    | 0.06em     | UPPERCASE, slate-500         |
| Table body     | Inter             | 13px  | 400    | 0          | white                        |
| Nav section    | Inter             | 10px  | 600    | 0.08em     | UPPERCASE, slate-600         |
| Nav item       | Plus Jakarta Sans | 13px  | 400    | 0          | slate-400 / white active     |
| Insight text   | Plus Jakarta Sans | 20px  | 600    | -0.01em    | white, AI insight cards      |

---

## Spacing System

| Token | Value | Usage                                    |
|-------|-------|------------------------------------------|
| xs    | 4px   | Icon gap, badge padding                  |
| sm    | 8px   | Between nav icon + text                  |
| md    | 16px  | Card inner padding                       |
| lg    | 20px  | Between cards                            |
| xl    | 24px  | Page padding horizontal                  |
| 2xl   | 32px  | Between major sections                   |

---

## Components

**Background texture (optional)**
- CSS `+` grid pattern: `background-image: radial-gradient(circle, rgba(255,255,255,0.03) 1px, transparent 1px)`
- `background-size: 24px 24px`
- Adds depth without being distracting

**Sidebar**
- `width: 240px`, `background: slate-900`, `border-right: 1px solid slate-700/40`
- Logo: top 20px, 28px height
- User block: avatar 36px circle + name bold + role/email
- Light/dark toggle: icon buttons next to user
- Nav item: 40px height, icon 18px + label, `border-radius: 8px`
- Active: `background: slate-800`, white text + icon
- Upgrade CTA: bottom — gradient card, `border-radius: 12px`

**KPI Cards**
- `background: slate-900`, `border: 1px solid slate-700/40`
- `border-radius: 12px`, `padding: 20px 24px`
- KPI label: 13px slate-400 (top)
- Number: Plus Jakarta Sans 36px 700 white
- Delta: small pill + arrow, emerald-400 or rose-400

**Chart Cards**
- Bar charts: blue-400 bars, dimmed variants at blue-400/20 for inactive
- Grouped bars: pairs per time period
- Bar chart bars: `border-radius: 4px 4px 0 0`, `width: 20–28px`
- Grid lines: `rgba(255,255,255,0.04)` horizontal only
- Chart bg: NO extra bg — inherits card surface

**AI Insights Card**
- Gradient bg: `radial-gradient(ellipse at bottom, blue-500/30, transparent)`
- Dot carousel indicators: 4–5 dots bottom-left
- Insight text: Plus Jakarta Sans 20px 600 white, bottom-left
- Arrow icon: bottom-right, `40px` circle, white/20 bg

**Map Data Card**
- Dark choropleth map, geographic fill by data intensity
- Legend: color scale bar, min/max labels
- Data list below or beside map

**Progress Row**
- Location/category name: Inter 13px white
- Bar: full width minus value, `height: 6px`, `border-radius: 3px`
- Value: Geist Mono 13px right-aligned, white

---

## Anti-patterns
- No light mode
- No warm color palette
- No heavy decorative gradients (use subtle glow only)
- No colorful icon grid
- No sans-serif on everything (Plus Jakarta Sans is the hero)
- No basic chart.js default colors (blue-400/violet-400/cyan-400 only)
