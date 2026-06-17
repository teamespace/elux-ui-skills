# COBALT — Fintech Hero
*Reference: Revolut home | Best for: fintech home screen, wallet, payments*

---

## Palette (Tailwind v4)

| Role         | Token            | Hex                                      | Usage                      |
|--------------|------------------|------------------------------------------|----------------------------|
| Hero bg      | —                | linear-gradient(180deg, #1A3BF0, #0A0A2E)| Full-bleed hero area       |
| Page bg      | slate-950        | #020617                                  | Below-fold background      |
| Surface      | slate-900        | #0F172A                                  | Cards, transaction list    |
| Border       | slate-700/30     | rgba(51,65,85,0.3)                       | Card borders               |
| Glass btn    | white/15         | rgba(255,255,255,0.15)                   | Action buttons bg          |
| Text         | white            | #FFFFFF                                  | All primary text           |
| Text muted   | slate-400        | #94A3B8                                  | Date, secondary labels     |
| Text ghost   | white/40         | rgba(255,255,255,0.4)                    | Placeholders               |
| Accent       | blue-400         | #60A5FA                                  | Active nav, links          |
| Positive     | emerald-400      | #34D399                                  | Incoming transactions      |
| Negative     | rose-400         | #FB7185                                  | Outgoing transactions      |
| Nav bg       | slate-950        | #020617                                  | Bottom nav bar             |

---

## Typography

Font stack: `"Inter var", "Inter"` — but used at intentional sizes with tabular nums.
→ Inter dipakai disini karena fintech butuh numerik yang tepat dan presisi, bukan estetik.
→ Enable `font-variant-numeric: tabular-nums` untuk semua angka/amounts.

| Role           | Font  | Size  | Weight | Line-height | Notes                         |
|----------------|-------|-------|--------|-------------|-------------------------------|
| Balance hero   | Inter | 52px  | 700    | 1.0         | tabular-nums, white           |
| Balance label  | Inter | 13px  | 400    | 1.0         | white/60, "Personal · All"    |
| Action label   | Inter | 12px  | 500    | 1.0         | white/80, below icon buttons  |
| List item name | Inter | 15px  | 500    | 1.4         | white                         |
| List meta      | Inter | 12px  | 400    | 1.4         | slate-400                     |
| Amount +       | Inter | 15px  | 600    | 1.4         | emerald-400, tabular-nums     |
| Amount −       | Inter | 15px  | 600    | 1.4         | white/80, tabular-nums        |
| Nav label      | Inter | 10px  | 500    | 1.0         | white/60 inactive, white active|
| Section head   | Inter | 13px  | 600    | 1.0         | white/60, uppercase tracking  |

---

## Spacing System

| Token | Value | Usage                               |
|-------|-------|-------------------------------------|
| xs    | 4px   | Dot indicator, micro gaps           |
| sm    | 8px   | Between action icon + label         |
| md    | 12px  | Between transaction rows            |
| lg    | 16px  | Card internal padding               |
| xl    | 20px  | Between card sections               |
| 2xl   | 24px  | Hero section padding top            |
| hero  | 60px  | Hero area top padding (status bar)  |

---

## Components

**Hero section**
- Full-bleed gradient, no border, no card chrome
- Balance centered, `padding-top: 60px`
- "Personal · All accounts" label above balance (muted)
- Pagination dots (3) below balance for account swipe
- `padding-bottom: 32px`

**Action row**
- 4 circular buttons, `width: 56px height: 56px`
- `background: rgba(255,255,255,0.15)`, `border-radius: 50%`
- Icon: 22px, white
- Label: 12px Inter 500, white/80, `margin-top: 8px`
- Row: `justify-content: space-around`, `padding: 0 24px`

**Avatar + search bar (header)**
- Avatar: 40px circle, top-left, notification red dot 8px
- Search: pill, `background: rgba(255,255,255,0.12)`, flex-grow
- Icon buttons right: 36px each

**Transaction list card**
- `background: slate-900`, `border-radius: 20px`
- Rows: flag/logo avatar 40px left, name + date center, amount right
- `padding: 16px`, `row-gap: 0`, divider line `1px slate-700/20`
- "See all" text: centered, 14px, white/50, `padding: 16px 0`

**Bottom nav**
- `background: slate-950`, no border, `height: 80px`
- 5 items, icon only (24px), label optional (10px)
- Active: white icon + label; inactive: white/40
- `padding-bottom: safe-area + 8px`

---

## Anti-patterns
- No light mode
- No colorful multi-accent (stays blue/dark)
- No photo cards
- No heavy drop shadows (use bg contrast instead)
- No rounded pill tab bars
- No warm colors (this is cool blue territory)
