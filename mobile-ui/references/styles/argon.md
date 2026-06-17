# ARGON — Premium Dark Consumer
*Best for: premium fitness, luxury, exclusive membership, high-end consumer*

---

## Palette (Tailwind v4)

| Role         | Token           | Hex                        | Usage                         |
|--------------|-----------------|----------------------------|-------------------------------|
| Background   | neutral-950     | #0A0A0A                    | Page bg                       |
| Surface      | neutral-900     | #171717                    | Cards                         |
| Border       | white/8         | rgba(255,255,255,0.08)     | 1px card borders              |
| Border hover | white/16        | rgba(255,255,255,0.16)     | Card hover/active border      |
| Text         | white           | #FFFFFF                    | Primary                       |
| Text muted   | neutral-400     | #A3A3A3                    | Secondary, descriptions       |
| Text ghost   | neutral-600     | #525252                    | Placeholder, disabled         |
| Accent       | — (brand)       | Define per project          | Gold #C9A84C / neon #39FF14  |
| Accent dim   | accent/15       | accent at 15% opacity      | Glow, inner light             |
| Icon color   | white           | #FFFFFF                    | Always monochrome             |

**Accent guidance:** Gold `#C9A84C` for luxury/wealth. Neon green `#39FF14` for fitness/sport.
Electric blue `sky-400 #38BDF8` for tech premium. Pick ONE and commit.

---

## Typography

Font stack: `"Clash Display", "Cabinet Grotesk"` for display + `"DM Sans"` for body
→ Clash Display adalah geometric modern yang terasa premium tapi tidak seperti Inter.
→ Tidak ada di Google Fonts standard — gunakan CDN dari fontshare.com.

| Role           | Font           | Size  | Weight | Line-height | Tracking  |
|----------------|----------------|-------|--------|-------------|-----------|
| Hero title     | Clash Display  | 40px  | 700    | 1.0         | -0.03em   |
| Screen title   | Clash Display  | 28px  | 600    | 1.1         | -0.02em   |
| Card title     | Clash Display  | 18px  | 600    | 1.2         | -0.01em   |
| Section label  | DM Sans        | 11px  | 700    | 1.0         | 0.08em UPPERCASE |
| Body           | DM Sans        | 15px  | 400    | 1.6         | 0         |
| Stats / metric | Clash Display  | 36px  | 700    | 1.0         | -0.02em   |
| Caption        | DM Sans        | 12px  | 400    | 1.5         | 0.01em    |
| Button         | DM Sans        | 15px  | 600    | 1.0         | 0.02em    |
| Nav label      | DM Sans        | 10px  | 500    | 1.0         | 0.02em    |

---

## Spacing System

| Token | Value | Usage                                    |
|-------|-------|------------------------------------------|
| xs    | 4px   | Icon internal gap                        |
| sm    | 8px   | Between label + value in row             |
| md    | 16px  | Card inner padding                       |
| lg    | 20px  | Card gap                                 |
| xl    | 32px  | Section outer padding                    |
| hero  | 48px  | Hero area top padding                    |

---

## Components

**Hero area**
- Full-bleed dark image or gradient
- `background: linear-gradient(180deg, transparent 40%, #0A0A0A 100%)`
- Overlay text: white, left-aligned, bottom-anchored
- `min-height: 56vh`

**CTA Button**
- Solid accent bg, white text
- `border-radius: 12px`, `height: 56px`, full width
- DM Sans 600 15px, letter-spacing 0.02em
- Glow on idle: `box-shadow: 0 0 20px accent/30` (subtle)

**Cards**
- `border: 1px solid rgba(255,255,255,0.08)`
- `border-radius: 20px`, `background: neutral-900`
- Inner accent glow: `box-shadow: inset 0 0 0 1px accent/05`
- On hover/press: border brightens to `white/16`

**Stat block**
- Clash Display 700 36px metric, DM Sans 12px label below
- Accent color on metric value, white/60 on label
- Often in 2-column grid

**Icon style**
- Thin stroke, `stroke-width: 1.5px`, white, `24px`
- No fill icons. No colored icons. Monochrome only.
- Prefer: Phosphor icons (thin variant) or custom SVG

**Section labels**
- DM Sans 700 11px UPPERCASE, letter-spacing 0.08em, neutral-400

**Bottom nav**
- `background: neutral-950`, `border-top: 1px solid white/08`
- Icon only (24px), accent dot indicator on active (not filled icon)
- 4–5 items

---

## Anti-patterns
- No colorful icon grids
- No multi-accent palette (one accent only)
- No flat/filled icon style
- No light surface cards
- No system default animations
- No Inter as primary typeface
- No light mode version
