# VOID — Data & Wealth
*Reference: Revolut wealth | Best for: portfolio, analytics, crypto, data tracking*

---

## Palette (Tailwind v4)

| Role         | Token         | Hex       | Usage                           |
|--------------|---------------|-----------|---------------------------------|
| Background   | neutral-950   | #0A0A0A   | Page bg (near-pure black)       |
| Surface      | neutral-900   | #171717   | Cards, list containers          |
| Surface 2    | neutral-800   | #262626   | Tab toggle active bg            |
| Border       | neutral-800   | #262626   | Subtle card separation          |
| Text         | white         | #FFFFFF   | All primary text, amounts       |
| Text muted   | neutral-400   | #A3A3A3   | Subtitles, percentages          |
| Text ghost   | neutral-600   | #525252   | Placeholder, disabled           |
| Accent cyan  | cyan-400      | #22D3EE   | Primary data arc, cash          |
| Accent purple| violet-500    | #8B5CF6   | Secondary arc, invest           |
| Accent amber | amber-400     | #FBBF24   | Crypto category                 |
| Accent teal  | teal-400      | #2DD4BF   | Interest / savings              |
| Negative     | rose-400      | #FB7185   | Loss, liabilities               |
| Tab active   | neutral-800   | #262626   | Pill toggle active bg           |

---

## Typography

Font stack: `"Inter var", "Inter"` with `font-variant-numeric: tabular-nums`
→ Data legibility adalah prioritas. Setiap digit harus occupy same width.

| Role           | Font  | Size  | Weight | Line-height | Notes                    |
|----------------|-------|-------|--------|-------------|--------------------------|
| Total amount   | Inter | 52px  | 700    | 1.0         | center, tabular-nums     |
| Total label    | Inter | 14px  | 400    | 1.0         | neutral-400, center      |
| Tab label      | Inter | 15px  | 600    | 1.0         | active white, inactive neutral-400 |
| Category name  | Inter | 16px  | 500    | 1.4         | white                    |
| Category sub   | Inter | 13px  | 400    | 1.4         | neutral-400              |
| Amount value   | Inter | 16px  | 600    | 1.4         | white, tabular-nums, right|
| Amount percent | Inter | 13px  | 400    | 1.4         | neutral-400, right       |
| Back nav       | Inter | 14px  | 500    | 1.0         | white                    |
| Screen title   | Inter | 28px  | 700    | 1.1         | white, left-aligned      |

---

## Spacing System

| Token | Value | Usage                                  |
|-------|-------|----------------------------------------|
| xs    | 4px   | Arc gap between segments               |
| sm    | 8px   | Between icon and text in list row      |
| md    | 16px  | List row internal padding              |
| lg    | 20px  | Between cards                          |
| xl    | 24px  | Screen outer padding                   |
| chart | 240px | Donut chart diameter                   |

---

## Components

**Donut chart (center-stage)**
- SVG, `diameter: 240px`, `stroke-width: 14px`
- `stroke-linecap: round`
- Small gap between segments (`stroke-dashoffset` trick)
- Total label + amount centered inside
- Animate: arc draws in on enter, spring ease 600ms

**Tab toggle (Assets / Liabilities)**
- Pill container: `background: neutral-900`, `border-radius: 50px`, `padding: 4px`
- Active pill: `background: neutral-800`, `border-radius: 46px`
- Text: 15px Inter 600
- `height: 44px` total

**Category list rows**
- Container card: `background: neutral-900`, `border-radius: 18px`
- Row: icon pill left (48px circle, category-specific bg), name + subtitle center, value + percent right
- Icon pill colors: cash=cyan-400/20, invest=violet-500/20, crypto=amber-400/20
- Divider: none — use `gap: 0`, row separator via `padding: 16px 0`
- Last row: no separator

**Standalone link cards** (Interest, Linked)
- Same card style, with `>` chevron right
- Subtitle: teal-400 for rates, muted for others

**Back nav**
- `←` arrow, top-left, 44px touch target
- White, no border, no bg

**Screen title**
- Inter 700 28px, white, left-aligned, `margin-top: 16px`

---

## Anti-patterns
- No light bg surfaces
- No illustrative decorations
- No colorful gradient backgrounds (black only)
- No crowded navigation
- No warm tones (red, orange, yellow) except for crypto/negative
- No card drop shadows (use bg contrast)
