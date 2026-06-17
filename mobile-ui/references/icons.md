# Icons Reference — Mobile UI
*Cross-style. Defines which icon set to use per style + rules.*

---

## Why This Matters

Icon choice adalah salah satu perbedaan paling visible antara "AI generic" dan "crafted UI".
Heroicons + Feather on white bg = instant sign of AI-generated slop.
Icon set harus match visual weight dan personality dari style.

---

## Icon Set per Style

| Style      | Primary Icon Set         | Style variant  | Why                                        |
|------------|--------------------------|----------------|---------------------------------------------|
| SLATE      | Phosphor Icons           | Regular (2px)  | Friendly, rounded, matches lifestyle vibe   |
| PARCHMENT  | Phosphor Icons           | Bold (2.5px)   | Heavier stroke matches thick card borders   |
| COBALT     | Phosphor Icons           | Light (1.5px)  | Thin on dark bg = elegant, fintech feel     |
| VOID       | Phosphor Icons           | Thin (1px)     | Ultra-light on black = premium data feel    |
| SURGE      | Phosphor Icons           | Fill           | Filled icons = bold, consumer-friendly      |
| ARGON      | Phosphor Icons           | Thin (1.5px)   | Monochrome thin = luxury premium            |

**Why Phosphor?** — 9,000+ icons, multiple weights (thin/light/regular/bold/fill/duotone),
free, works in React Native + Flutter + SVG + web. Consistent visual system across weights.
CDN: `https://unpkg.com/@phosphor-icons/web`
React: `npm install @phosphor-icons/react`

---

## Icon Sizing Rules

| Usage                  | Size  | Touch target |
|------------------------|-------|--------------|
| Nav bar icons          | 24px  | 44×44px      |
| Action buttons (inline)| 20px  | 44×44px      |
| Card icons             | 18px  | N/A          |
| List row icons         | 20px  | 44×44px if tappable |
| Hero / decorative      | 32px+ | N/A          |
| Badge / indicator      | 12px  | N/A          |
| Input prefix/suffix    | 18px  | N/A          |
| FAB                    | 24px  | 56×56px      |

Min touch target always 44×44px — pad with invisible area if icon is smaller.

---

## Icon Color Rules

### Per-style color:

**SLATE**
- Nav active: `rose-500`
- Nav inactive: `neutral-400`
- Card actions: `neutral-700`
- CTA icons: `white`

**PARCHMENT**
- Nav (if present): `neutral-900`
- Card icons: `neutral-800`
- Action icons: `neutral-900`
- Accent icons: `emerald-400`

**COBALT**
- All icons: `white`
- Active state: `white` (no color change — rely on bg highlight)
- Muted icons: `white/50`

**VOID**
- All icons: `white`
- Muted icons: `neutral-400`
- Category icon bg: per-category tinted circle

**SURGE**
- Nav active: `brand-500`
- Nav inactive: `neutral-400`
- Service grid icons: per-service color (as defined by brand)
- Action icons: `brand-500`

**ARGON**
- All icons: `white` (monochrome only — no colored icons)
- Muted icons: `neutral-400`
- Active indicator: accent color DOT below icon, not colored icon

---

## Common Icon Names (Phosphor)

Map these UI needs to Phosphor icon names:

| Need              | Phosphor name          |
|-------------------|------------------------|
| Home              | `House`                |
| Search            | `MagnifyingGlass`      |
| Profile / User    | `User`                 |
| Settings          | `GearSix`              |
| Notifications     | `Bell`                 |
| Heart / Save      | `Heart`                |
| Bookmark          | `Bookmark`             |
| Share             | `ShareNetwork`         |
| Back arrow        | `ArrowLeft`            |
| Close / X         | `X`                    |
| Add / Plus        | `Plus`                 |
| More (3 dots)     | `DotsThree`            |
| Chevron right     | `CaretRight`           |
| Chevron down      | `CaretDown`            |
| Filter            | `Funnel`               |
| Edit              | `PencilSimple`         |
| Delete            | `Trash`                |
| Check / Success   | `CheckCircle`          |
| Warning           | `Warning`              |
| Camera            | `Camera`               |
| Image / Photo     | `Image`                |
| Chat / Message    | `ChatCircle`           |
| Location          | `MapPin`               |
| Calendar          | `CalendarBlank`        |
| Clock / Time      | `Clock`                |
| Star / Rating     | `Star`                 |
| Cart              | `ShoppingCart`         |
| Wallet / Payment  | `Wallet`               |
| Eye / View        | `Eye`                  |
| Upload            | `UploadSimple`         |
| Download          | `DownloadSimple`       |

---

## Anti-patterns

```
NEVER  : Mix icon sets in one screen (e.g. Heroicons + Phosphor)
NEVER  : Use emoji as functional icons
NEVER  : Inconsistent stroke widths within one style
NEVER  : Colored icons in ARGON (monochrome only)
NEVER  : Filled icons in COBALT or VOID (too heavy on dark bg)
NEVER  : Different sizes for same-role icons (nav icons always same size)
NEVER  : Icon without label in bottom nav (unless space absolutely forces it)
ALWAYS : Maintain visual weight consistency throughout one screen
ALWAYS : Use same icon set variant throughout one screen
```
