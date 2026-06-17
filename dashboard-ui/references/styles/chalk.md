# CHALK — Clean SaaS Admin
*Reference: Cursor, ElevenLabs | Best for: product dashboards, SaaS admin, light minimal*

---

## Palette (Tailwind v4)

| Role          | Token          | Hex       | Usage                          |
|---------------|----------------|-----------|--------------------------------|
| Page bg       | neutral-50     | #FAFAFA   | App background                 |
| Surface       | white          | #FFFFFF   | Cards, sidebar, panels         |
| Surface raised| neutral-50     | #FAFAFA   | Nested sections inside cards   |
| Border        | neutral-200    | #E5E5E5   | Card borders, dividers         |
| Border subtle | neutral-100    | #F5F5F5   | Subtle separators              |
| Sidebar bg    | white          | #FFFFFF   | Left nav                       |
| Sidebar active| neutral-100    | #F5F5F5   | Active nav item bg             |
| Text          | neutral-900    | #171717   | Page titles, primary data      |
| Text secondary| neutral-600    | #525252   | Labels, descriptions           |
| Text muted    | neutral-400    | #A3A3A3   | Meta, timestamps, captions     |
| Accent        | neutral-900    | #171717   | CTAs, active states (high contrast) |
| Positive      | emerald-600    | #059669   | Growth, success, positive delta|
| Negative      | rose-500       | #F43F5E   | Decline, error, negative delta |
| Info          | sky-500        | #0EA5E9   | Neutral metrics, sparklines    |
| Chart 1       | neutral-900    | #171717   | Primary data series            |
| Chart 2       | neutral-400    | #A3A3A3   | Secondary data series          |
| Heatmap low   | emerald-100    | #D1FAE5   | Activity heatmap low           |
| Heatmap high  | emerald-600    | #059669   | Activity heatmap high          |

---

## Typography

Font stack: `"Geist", "Inter var", system-ui`
→ Geist adalah font Vercel — modern, technical, extremely clean. Terasa crafted bukan generic.

| Role           | Font  | Size  | Weight | Tracking   | Notes                      |
|----------------|-------|-------|--------|------------|----------------------------|
| Page title     | Geist | 24px  | 600    | -0.02em    | Left-aligned, neutral-900  |
| Section title  | Geist | 15px  | 600    | -0.01em    | With optional icon left    |
| KPI number     | Geist | 32px  | 600    | -0.03em    | tabular-nums               |
| KPI label      | Geist | 12px  | 400    | 0          | neutral-500, above number  |
| Delta badge    | Geist | 12px  | 500    | 0          | positive/negative color    |
| Table header   | Geist | 11px  | 500    | 0.05em     | UPPERCASE, neutral-400     |
| Table body     | Geist | 13px  | 400    | 0          | neutral-900                |
| Nav item       | Geist | 13px  | 400    | 0          | neutral-600, active=900    |
| Nav section    | Geist | 11px  | 500    | 0.05em     | UPPERCASE, neutral-400     |
| Button         | Geist | 13px  | 500    | 0          |                            |
| Caption        | Geist | 11px  | 400    | 0          | neutral-400                |

---

## Spacing System

| Token | Value | Usage                                    |
|-------|-------|------------------------------------------|
| xs    | 4px   | Icon-text gap, badge padding             |
| sm    | 8px   | Between nav items, inline gap            |
| md    | 12px  | Card inner padding (compact sections)    |
| lg    | 16px  | Card inner padding (standard)            |
| xl    | 24px  | Between cards, content padding           |
| 2xl   | 32px  | Section gap, page padding                |

---

## Components

**Sidebar**
- `width: 220px`, `background: white`, `border-right: 1px solid neutral-200`
- Logo: top 20px, 32px height
- User block: avatar 28px + name + role, top section
- Nav sections: label ALL CAPS 11px neutral-400, `margin-top: 24px`
- Nav item: 36px height, icon 16px + label, `border-radius: 6px`
- Active item: `background: neutral-100`, `color: neutral-900`
- Inactive: `color: neutral-600`, no bg
- Bottom section: settings, user, workspace switcher

**KPI Cards**
- `border: 1px solid neutral-200`, `border-radius: 10px`, `padding: 20px`
- Label: 12px neutral-500 (top)
- Number: 32px Geist 600, tabular-nums
- Delta: pill badge — `background: emerald-50` + `color: emerald-600` (or rose variant)
- Sparkline: small (60px height), bottom of card, neutral-300 line

**Top Bar**
- Page title left: 24px Geist 600
- Right: date picker + filter + export buttons
- `padding: 24px 32px`, `border-bottom: 1px solid neutral-100`

**Activity Heatmap** (Cursor-style)
- Square cells `10×10px`, `border-radius: 2px`, `gap: 3px`
- Color scale: neutral-100 → emerald-100 → emerald-300 → emerald-500 → emerald-700
- Row labels left (M/W/F), column labels top (month letters)
- Legend: "Fewer ○○●●●● More" bottom

**Buttons**
- Primary: `background: neutral-900`, `color: white`, `border-radius: 8px`, `height: 36px`
- Secondary: `border: 1px solid neutral-200`, `background: white`, `border-radius: 8px`
- Ghost: no border, no bg, `color: neutral-600`

---

## Anti-patterns
- No colored sidebar bg (white only)
- No heavy chart gradients
- No multiple accent colors
- No large decorative illustrations
- No dark mode (this is light-only)
- No colorful pill nav sections
