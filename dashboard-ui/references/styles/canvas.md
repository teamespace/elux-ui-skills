# CANVAS — Data-Dense Light
*Reference: Cloudflare, DisputeFox | Best for: developer/ops tools, technical KPI, data-heavy*

---

## Palette (Tailwind v4)

| Role          | Token          | Hex       | Usage                            |
|---------------|----------------|-----------|----------------------------------|
| Page bg       | white          | #FFFFFF   | App background                   |
| Surface       | white          | #FFFFFF   | Cards, panels                    |
| Surface alt   | neutral-50     | #FAFAFA   | Alternate row bg in tables       |
| Border        | neutral-200    | #E5E5E5   | Card borders, table lines        |
| Border strong | neutral-300    | #D4D4D4   | Section dividers, prominent borders |
| Sidebar bg    | white          | #FFFFFF   | Left nav                         |
| Sidebar active| neutral-100    | #F5F5F5   | Active nav item bg               |
| Text          | neutral-900    | #171717   | Primary                          |
| Text secondary| neutral-600    | #525252   | Labels, secondary                |
| Text muted    | neutral-400    | #A3A3A3   | Meta, timestamps                 |
| Accent        | orange-500     | #F97316   | Brand accent (Cloudflare orange) — adapt |
| Positive      | emerald-600    | #059669   | Positive delta, success          |
| Negative      | rose-500       | #F43F5E   | Error, negative                  |
| Warning       | amber-500      | #F59E0B   | Warning states                   |
| Chart 1       | sky-500        | #0EA5E9   | Primary data series              |
| Chart 2       | violet-500     | #8B5CF6   | Secondary series                 |
| Chart 3       | emerald-500    | #10B981   | Third series                     |
| Chart 4       | orange-400     | #FB923C   | Fourth series                    |
| Chart 5       | rose-400       | #FB7185   | Fifth series                     |

---

## Typography

Font stack: `"Geist Mono", "JetBrains Mono"` for data + `"Inter var"` for UI
→ Mono font untuk semua angka/metrics = terasa technical, presisi, developer-grade.

| Role           | Font       | Size  | Weight | Tracking   | Notes                      |
|----------------|------------|-------|--------|------------|----------------------------|
| Page title     | Inter      | 20px  | 600    | -0.01em    |                            |
| Section title  | Inter      | 14px  | 600    | 0          |                            |
| KPI number     | Geist Mono | 28px  | 700    | -0.02em    | tabular-nums always        |
| KPI label      | Inter      | 12px  | 400    | 0          | neutral-600                |
| Delta text     | Geist Mono | 12px  | 500    | 0          | with ↑↓ arrow prefix      |
| Chart axis     | Geist Mono | 10px  | 400    | 0          | neutral-400                |
| Table header   | Inter      | 11px  | 600    | 0.06em     | UPPERCASE, neutral-500     |
| Table body     | Inter      | 13px  | 400    | 0          | neutral-900                |
| Table mono     | Geist Mono | 13px  | 400    | 0          | For IDs, hashes, numbers   |
| Nav item       | Inter      | 13px  | 400    | 0          |                            |
| Nav section    | Inter      | 10px  | 600    | 0.08em     | UPPERCASE, neutral-400     |
| Tab label      | Inter      | 13px  | 500    | 0          | Active underline accent    |
| Badge/pill     | Inter      | 11px  | 500    | 0          |                            |
| Caption        | Inter      | 11px  | 400    | 0          | neutral-400                |

---

## Spacing System

| Token | Value | Usage                                    |
|-------|-------|------------------------------------------|
| xs    | 4px   | Badge padding, tight gaps                |
| sm    | 8px   | Between inline elements                  |
| md    | 12px  | KPI card padding (compact)               |
| lg    | 16px  | Card padding standard                    |
| xl    | 20px  | Between card rows                        |
| 2xl   | 24px  | Page padding, section gap                |

---

## Components

**Top Navigation (tab-style)**
- `border-bottom: 1px solid neutral-200`
- Tabs: 13px Inter 500, `padding: 12px 16px`, active = accent underline `2px`
- Right side: filter dropdown + date range + icon buttons (refresh, expand)
- Global date range: pill dropdown, always visible

**KPI Row (mini-cards with sparklines)**
- 4–6 cards across full width
- `border: 1px solid neutral-200`, `border-radius: 8px`, `padding: 16px`
- Label: Inter 12px neutral-600 (top)
- Number: Geist Mono 28px 700
- Delta: Geist Mono 12px + ↑↓ arrow, semantic color
- Sparkline: bottom 40px, chart color, area fill at 10% opacity

**Dense Data Table**
- `border: 1px solid neutral-200`, `border-radius: 8px`
- Header: neutral-50 bg, Inter 11px 600 UPPERCASE, neutral-500
- Row height: 44px, `border-bottom: 1px solid neutral-100`
- Alternate row: neutral-50 bg
- Hover: neutral-100 bg
- Sort indicator: ↑↓ arrows on header
- Progress bar cells: `height: 6px`, `border-radius: 3px`, accent color fill
- Status badges: `border-radius: 4px`, semantic bg/text colors

**Tab Navigation (within content)**
- Underline style — no pill/bg
- Active: accent color text + `2px bottom border`
- Inactive: neutral-500 text
- `gap: 0`, tabs flush together with `padding: 0 16px`

**Gauge / Radial Chart**
- Multi-color arc (rainbow for credit score range)
- Large number center: Geist Mono 48–64px 700
- Range labels: left/right of arc, Geist Mono 12px

**Progress Indicator**
- Horizontal bar: `height: 4px`, `border-radius: 2px`
- Fill: accent or semantic color
- Value label: right-aligned, Geist Mono 13px

---

## Anti-patterns
- No heavy card shadows
- No colored sidebar backgrounds
- No decorative gradient backgrounds
- No large illustrations
- No dark mode
- No playful/rounded aesthetic
