# SLATE — Marketplace & Discovery
*Reference: Airbnb | Best for: marketplace, booking, travel, e-commerce*

---

## Palette (Tailwind v4)

| Role        | Token           | Hex       | Usage                        |
|-------------|-----------------|-----------|------------------------------|
| Background  | white           | #FFFFFF   | Page bg                      |
| Section div | neutral-50      | #FAFAFA   | Between-section separator    |
| Surface     | white           | #FFFFFF   | Cards, modals                |
| Border      | neutral-200     | #E5E5E5   | Card borders, dividers       |
| Text        | neutral-900     | #171717   | Headlines, primary text      |
| Text muted  | neutral-500     | #737373   | Price, rating, meta          |
| Text ghost  | neutral-400     | #A3A3A3   | Placeholder, disabled        |
| Accent      | rose-500        | #F43F5E   | CTA only — reserve, save     |
| Accent dark | rose-600        | #E11D48   | CTA hover/pressed state      |
| Success     | emerald-500     | #10B981   | Availability, confirmed      |
| Badge bg    | white           | #FFFFFF   | "Guest favorite" pill        |
| Badge text  | neutral-900     | #171717   | Badge label                  |

---

## Typography

Font stack: `"Plus Jakarta Sans", "DM Sans", system-ui`
→ Modern, clean, slightly humanist — tidak AI-generic seperti Inter biasa.

| Role         | Font             | Size  | Weight | Line-height | Tracking |
|--------------|------------------|-------|--------|-------------|----------|
| Screen title | Plus Jakarta Sans | 28px  | 700    | 1.2         | -0.02em  |
| Section head | Plus Jakarta Sans | 20px  | 600    | 1.3         | -0.01em  |
| Card title   | Plus Jakarta Sans | 15px  | 500    | 1.4         | 0        |
| Body         | Plus Jakarta Sans | 14px  | 400    | 1.6         | 0        |
| Price        | Plus Jakarta Sans | 15px  | 600    | 1.4         | 0        |
| Caption/meta | Plus Jakarta Sans | 12px  | 400    | 1.5         | 0.01em   |
| Badge        | Plus Jakarta Sans | 12px  | 600    | 1    | 0        |

---

## Spacing System

Base unit: `4px`

| Token | Value | Usage                            |
|-------|-------|----------------------------------|
| xs    | 4px   | Icon gap, badge padding internal |
| sm    | 8px   | Inline element gap               |
| md    | 12px  | Card content padding             |
| lg    | 16px  | Card gap, list item padding      |
| xl    | 20px  | Section internal padding         |
| 2xl   | 24px  | Section outer padding            |
| 3xl   | 32px  | Between major sections           |

---

## Components

**Cards**
- `border-radius: 16px`
- Photo full-bleed top, `aspect-ratio: 4/3`
- Text block below: title → caption row (price · rating)
- Heart icon: floating top-right of image, `32px` touch target, neutral-900/white fill

**Badge pills**
- `background: white`, `border: 1px solid neutral-200`
- `border-radius: 20px`, `padding: 4px 10px`
- "Guest favorite", "NEW" — always white bg, never colored bg

**Search bar**
- Full-width pill, `border-radius: 40px`
- `background: white`, `border: 1px solid neutral-200`
- `box-shadow: 0 2px 8px rgba(0,0,0,0.08)`
- Icon left, placeholder text muted

**Bottom nav**
- 5 items, icon (24px) + label (10px) below
- Active: rose-500 icon + label
- Inactive: neutral-400 icon + label
- `padding-bottom: safe-area-inset-bottom + 8px`

**CTA Button**
- `background: rose-500`, `color: white`
- `border-radius: 12px`, `height: 56px`, full width
- Font: 16px 600

**Spacing**
- Screen horizontal padding: `24px`
- Section gap: `32px`
- Card gap in scroll: `12px`

---

## Anti-patterns
- No dark mode
- No heavy or colored gradients
- No icon-only nav (always label)
- No dense text walls between card sections
- No colored card backgrounds (photos only)
