# OBSIDIAN — Dark Glassy
*Reference: Vapi, HRadar | Best for: AI products, dark-mode SaaS, rich bento widget*

---

## Palette (Tailwind v4)

| Role          | Token           | Hex                        | Usage                          |
|---------------|-----------------|----------------------------|--------------------------------|
| Page bg       | neutral-950     | #0A0A0A                    | App background                 |
| Sidebar bg    | neutral-900     | #171717                    | Left nav                       |
| Surface       | neutral-900     | #171717                    | Cards, panels                  |
| Surface raised| neutral-800     | #262626                    | Nested elements, hover state   |
| Border        | white/8         | rgba(255,255,255,0.08)     | Card borders                   |
| Border hover  | white/16        | rgba(255,255,255,0.16)     | Interactive borders on hover   |
| Sidebar active| neutral-800     | #262626                    | Active nav item bg             |
| Text          | white           | #FFFFFF                    | Primary                        |
| Text secondary| neutral-400     | #A3A3A3                    | Labels, descriptions           |
| Text muted    | neutral-600     | #525252                    | Meta, timestamps               |
| Accent        | cyan-400        | #22D3EE                    | Primary accent (teal/cyan)     |
| Accent dim    | cyan-400/15     | rgba(34,211,238,0.15)      | Accent bg, glow                |
| Positive      | emerald-400     | #34D399                    | Growth, success                |
| Negative      | rose-400        | #FB7185                    | Decline, error                 |
| Warning       | amber-400       | #FBBF24                    | Warning                        |
| Chart 1       | cyan-400        | #22D3EE                    | Primary series                 |
| Chart 2       | violet-400      | #A78BFA                    | Secondary series               |
| Chart 3       | emerald-400     | #34D399                    | Third series                   |
| Chart 4       | rose-400        | #FB7185                    | Fourth series                  |
| Chart 5       | amber-400       | #FBBF24                    | Fifth series                   |

---

## Typography

Font stack: `"Geist", "Inter var"` for UI + `"Geist Mono"` for data
→ Geist pada dark bg terasa premium dan cohesive dengan dark-mode SaaS modern.

| Role           | Font       | Size  | Weight | Tracking   | Notes                         |
|----------------|------------|-------|--------|------------|-------------------------------|
| Page title     | Geist      | 22px  | 600    | -0.02em    | white                         |
| Section title  | Geist      | 14px  | 600    | 0          | white                         |
| KPI number     | Geist Mono | 32px  | 700    | -0.03em    | white, tabular-nums           |
| KPI label      | Geist      | 12px  | 400    | 0          | neutral-400                   |
| Delta badge    | Geist Mono | 12px  | 500    | 0          | semantic color                |
| Chart axis     | Geist Mono | 10px  | 400    | 0          | neutral-600                   |
| Chart label    | Geist      | 11px  | 400    | 0          | neutral-400                   |
| Table header   | Geist      | 11px  | 500    | 0.05em     | UPPERCASE, neutral-500        |
| Table body     | Geist      | 13px  | 400    | 0          | white                         |
| Nav section    | Geist      | 10px  | 600    | 0.08em     | UPPERCASE, neutral-600        |
| Nav item       | Geist      | 13px  | 400    | 0          | neutral-400 / white active    |
| Badge          | Geist      | 11px  | 500    | 0          | colored bg + text             |
| Timer/realtime | Geist Mono | 28px  | 700    | 0          | white, monospace critical     |

---

## Spacing System

| Token | Value | Usage                                    |
|-------|-------|------------------------------------------|
| xs    | 4px   | Icon gap, badge padding                  |
| sm    | 8px   | Inline gap, nav item icon-text           |
| md    | 12px  | Compact card padding                     |
| lg    | 16px  | Standard card padding                    |
| xl    | 20px  | Between bento cells                      |
| 2xl   | 24px  | Page padding, section gap                |

---

## Components

**Bento Grid Layout**
- Variable column/row sizes — not all cards same height
- Mix: 1×1 stat, 2×1 chart, 1×2 list, 2×2 main chart
- `gap: 16–20px` between cells
- Each cell: `border: 1px solid white/8`, `border-radius: 16px`, `background: neutral-900`

**Sidebar (icon-only or slim)**
- Icon-only variant: `width: 56px`, icons only, tooltip on hover
- Slim variant: `width: 200px`, icon + label
- `background: neutral-900`, `border-right: 1px solid white/8`
- Active: `background: neutral-800`, accent dot indicator or icon color change
- Section labels: ALL CAPS 10px neutral-600, `margin-top: 20px`
- Bottom: credits/usage indicator + settings

**KPI Cards**
- `background: neutral-900`, `border: 1px solid white/8`, `border-radius: 12px`
- Label: 12px neutral-400
- Number: Geist Mono 32px white
- Delta: pill `background: emerald-400/15` + `color: emerald-400` (or rose variant)
- Sparkline or mini bar chart bottom, accent color at 60% opacity

**Chart Cards**
- Title + optional icon left, controls (filter/expand) right
- Chart: area fills at 15–20% opacity over colored line
- Grid lines: `rgba(255,255,255,0.04)` horizontal only
- Legend: color dot + label, 11px neutral-400

**Activity Calendar (heatmap)**
- `10×10px` cells, `border-radius: 3px`, `gap: 3px`
- Color: neutral-800 → accent/15 → accent/40 → accent/70 → accent
- Column = week, row = day (Mon/Wed/Fri labeled)

**Status Badges**
- `border-radius: 6px`, `padding: 2px 8px`
- Alpha: `background: violet-400/20`, `color: violet-400`, `border: 1px solid violet-400/30`
- Beta: `background: amber-400/20`, `color: amber-400`
- New: `background: emerald-400/20`, `color: emerald-400`

**Real-time / Timer Display**
- Geist Mono 28px 700, white
- Play/pause button: `40px` circle, neutral-800 bg

---

## Anti-patterns
- No light surfaces
- No warm accent colors (this is cool cyan/violet territory)
- No heavy drop shadows (use border instead)
- No colorful sidebar sections (keep sidebar dark and minimal)
- No light mode
- No busy decorative textures
