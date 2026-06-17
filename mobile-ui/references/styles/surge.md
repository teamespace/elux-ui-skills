# SURGE — Super App & Utility
*Reference: Gojek | Best for: super app, multi-service, ride/food delivery*

---

## Palette (Tailwind v4)

| Role         | Token         | Hex       | Usage                              |
|--------------|---------------|-----------|------------------------------------|
| Background   | white         | #FFFFFF   | Page bg                            |
| Hero banner  | — (brand)     | brand-500 | Full-bleed banner bg (define per brand) |
| Surface      | neutral-50    | #FAFAFA   | Card sections                      |
| Surface alt  | white         | #FFFFFF   | Icon grid cells, wallet card       |
| Border       | neutral-100   | #F5F5F5   | Section separator                  |
| Text         | neutral-900   | #171717   | Primary text                       |
| Text muted   | neutral-500   | #737373   | Meta, secondary                    |
| Accent       | — (brand)     | brand-500 | Active nav, brand CTA              |
| Badge dark   | neutral-900   | #171717   | Discount badge bg                  |
| Badge text   | white         | #FFFFFF   | Discount badge text                |
| Notif dot    | rose-500      | #F43F5E   | Notification badge                 |
| Positive     | emerald-500   | #10B981   | Balance, incoming                  |

**Brand color definition:** Define at project start. Gojek=`emerald-500 #10B981`.
Always use ONE brand primary — never multi-accent.

---

## Typography

Font stack: `"Plus Jakarta Sans", system-ui`
→ Friendly, modern, works at display AND small sizes.

| Role          | Font              | Size  | Weight | Line-height | Notes                     |
|---------------|-------------------|-------|--------|-------------|---------------------------|
| Banner head   | Plus Jakarta Sans | 26px  | 700    | 1.2         | white or dark per bg      |
| Banner sub    | Plus Jakarta Sans | 14px  | 400    | 1.4         | white/80                  |
| Wallet balance| Plus Jakarta Sans | 22px  | 700    | 1.0         | tabular-nums              |
| Wallet label  | Plus Jakarta Sans | 12px  | 400    | 1.0         | neutral-500               |
| Action btn    | Plus Jakarta Sans | 12px  | 600    | 1.0         | brand color               |
| Grid label    | Plus Jakarta Sans | 12px  | 500    | 1.2         | neutral-900, below icon   |
| Section head  | Plus Jakarta Sans | 16px  | 700    | 1.2         | neutral-900               |
| Promo text    | Plus Jakarta Sans | 14px  | 400    | 1.4         | neutral-700               |
| Nav label     | Plus Jakarta Sans | 10px  | 500    | 1.0         | neutral-500 / brand active|

---

## Spacing System

| Token | Value | Usage                                  |
|-------|-------|----------------------------------------|
| xs    | 4px   | Badge internal padding                 |
| sm    | 8px   | Grid cell internal gap                 |
| md    | 12px  | Between grid rows                      |
| lg    | 16px  | Card horizontal padding, promo gap     |
| xl    | 20px  | Section internal padding               |
| 2xl   | 0px   | Banner: full-bleed, no margin          |

---

## Components

**Hero banner**
- Full-width, no border-radius (edge-to-edge)
- `min-height: 160px`, brand bg color
- Bold copy left, product image right (bleed to right edge)
- Carousel dot indicators at bottom, `height: 4px`, rounded pill

**Wallet card row**
- Inline: balance + wallet icon left, action buttons right (Pay, Top Up, More)
- `background: white`, `border-radius: 16px`, `padding: 16px`
- Action buttons: circle icon `36px` + label `10px` below, brand color

**Service icon grid**
- `4×2` grid, each cell: `flex-col align-center`
- Icon container: `72px × 72px`, `border-radius: 16px`, colored bg (brand-tinted)
- Icon: 36px, brand or category color
- Discount badge: overlaid top-right, `background: neutral-900`, `border-radius: 8px`, `padding: 2px 6px`
- Label: Plus Jakarta Sans 12px 500, `margin-top: 6px`

**Promo banners (horizontal scroll)**
- `border-radius: 16px`, full-width image
- `height: 120px`, object-fit cover

**Bottom nav**
- 4 items, icon + label
- Active: brand color icon + label (filled icon variant)
- Inactive: neutral-400
- `height: 64px + safe-area`

**Search bar**
- Full-width pill, neutral-100 bg, neutral-400 icon + placeholder
- `height: 44px`, `border-radius: 22px`

**Avatar**
- Top-right, `44px` circle, `border-radius: 50%`
- Red notification badge: `16px` circle, rose-500, top-right overlay

---

## Anti-patterns
- No monochrome palette (needs brand energy)
- No excessive whitespace (this is dense by design)
- No serif typography
- No minimal/thin icon style
- No dark mode
- No single-service focused layout (always show service grid)
