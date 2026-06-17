# PARCHMENT — Editorial & Learning
*Reference: Vocabulary app | Best for: education, wellness, journaling, learning*

---

## Palette (Tailwind v4)

| Role        | Token           | Hex       | Usage                         |
|-------------|-----------------|-----------|-------------------------------|
| Background  | stone-100       | #F5F5F4   | Warm cream page bg            |
| Surface     | white           | #FFFFFF   | Cards                         |
| Border      | neutral-900     | #171717   | Thick card border (2px)       |
| Text        | neutral-900     | #171717   | Headlines, primary            |
| Text muted  | stone-500       | #78716C   | Meta, secondary labels        |
| Text ghost  | stone-400       | #A8A29E   | Placeholder                   |
| Accent A    | emerald-400     | #34D399   | Progress, positive, CTA       |
| Accent B    | orange-400      | #FB923C   | Secondary accent, warnings    |
| Progress bg | neutral-200     | #E5E5E5   | Arc/ring background track     |
| Badge text  | neutral-900     | #171717   | Outlined badge                |

---

## Typography

Font stack: `"Fraunces", "Playfair Display"` for display + `"DM Sans"` for body
→ Fraunces adalah optical size serif yang warm dan modern — terasa editorial bukan template.

| Role         | Font          | Size  | Weight | Line-height | Tracking  |
|--------------|---------------|-------|--------|-------------|-----------|
| Screen title | Fraunces      | 34px  | 700    | 1.1         | -0.02em   |
| Section head | DM Sans       | 11px  | 700    | 1.0         | 0.08em (UPPERCASE) |
| Card title   | Fraunces      | 18px  | 600    | 1.3         | -0.01em   |
| Body         | DM Sans       | 15px  | 400    | 1.6         | 0         |
| Stats/score  | Fraunces      | 24px  | 700    | 1.0         | -0.02em   |
| Caption      | DM Sans       | 12px  | 400    | 1.5         | 0.01em    |
| Button       | DM Sans       | 14px  | 600    | 1.0         | 0.01em    |

Section labels: **ALWAYS uppercase, DM Sans 700 11px, letter-spacing 0.08em**, stone-500 color.

---

## Spacing System

Base unit: `4px`

| Token | Value | Usage                               |
|-------|-------|-------------------------------------|
| xs    | 4px   | Icon gap, internal badge padding    |
| sm    | 8px   | Between inline elements             |
| md    | 16px  | Card inner padding                  |
| lg    | 20px  | Card gap in grid                    |
| xl    | 24px  | Section inner padding               |
| 2xl   | 32px  | Between sections                    |

---

## Components

**Cards**
- `border: 2px solid neutral-900`, `border-radius: 20px`, `background: white`
- Illustration inside (right or centered), not photos
- Title: Fraunces, left-aligned

**2-column grid cards** (challenges)
- Square ratio, illustration top 60%, label bottom
- Same border treatment as cards above

**Wide status card**
- Text + button left side, circular progress arc right side
- Arc: `stroke-width: 8px`, bg track neutral-200, fill accent-A

**Category list rows**
- Full-width card, `border-radius: 16px`, label left bold, illustration bleeds right edge
- `height: 72px`

**Buttons (outlined)**
- `border: 2px solid neutral-900`, `border-radius: 12px`, `background: transparent`
- `height: 44px`, `padding: 0 20px`
- Hover/press: `background: neutral-900`, `color: white`

**Close button (X)**
- Circle `48px`, `border: 2px solid neutral-900`, `border-radius: 50%`
- X icon: 16px, neutral-900

**Progress arc**
- SVG circle, `stroke-linecap: round`
- Score text centered inside (Fraunces 700)

**Bottom nav** — not typical for this style. Prefer tab bar or no persistent nav.

**Section labels**
- ALL CAPS, DM Sans 700 11px, letter-spacing 0.08em, stone-500

---

## Anti-patterns
- No Inter on everything
- No neon or saturated accent colors
- No photo backgrounds in cards
- No flat gradient buttons
- No bottom tab nav with 5 items (use simpler nav)
- No dark mode
