# Icons Reference — Dashboard UI
*Cross-style. Defines icon set, sizing, and usage rules.*

---

## Icon Set: Phosphor Icons

Same icon system as mobile-ui skill — consistency across products.

```
Package  : @phosphor-icons/react (React) or unpkg CDN (HTML)
CDN      : https://unpkg.com/@phosphor-icons/web
```

**Weight per style:**

| Style    | Phosphor weight | Why                                        |
|----------|-----------------|--------------------------------------------|
| CHALK    | Regular (2px)   | Clean, neutral, matches minimal aesthetic  |
| CANVAS   | Regular (2px)   | Technical but readable                     |
| OBSIDIAN | Light (1.5px)   | Thin on dark bg = elegant                  |
| ABYSS    | Light (1.5px)   | Premium dark = lighter stroke              |

---

## Sizing by Context

| Context               | Size  | Notes                              |
|-----------------------|-------|------------------------------------|
| Sidebar nav icons     | 18px  | With text label beside             |
| Top bar icon buttons  | 18px  | Refresh, expand, filter            |
| KPI card icon         | 16px  | Optional — in label row            |
| Table action icons    | 16px  | Edit, delete, view — in row        |
| Chart control icons   | 16px  | Bar/line toggle, fullscreen        |
| Section title icon    | 16px  | Left of section heading            |
| Badge/pill icon       | 12px  | Inside status badges               |
| Empty state icon      | 32px  | Center of empty state              |
| Notification          | 20px  | Top bar bell icon                  |
| User avatar fallback  | 20px  | When no photo available            |

Min touch target: not applicable for most dashboard interactions (mouse-driven), but keep clickable icons at least 28×28px including padding.

---

## Common Icon Map (Phosphor names)

| UI element              | Phosphor name           |
|-------------------------|-------------------------|
| Dashboard / overview    | `SquaresFour`           |
| Analytics / chart       | `ChartBar`              |
| Payments / billing      | `CreditCard`            |
| Customers / users       | `Users`                 |
| Settings / gear         | `GearSix`               |
| Integrations            | `PlugsConnected`        |
| Members / team          | `UsersThree`            |
| Usage / consumption     | `ChartLineUp`           |
| Spending                | `Money`                 |
| Invoices                | `Receipt`               |
| Products                | `Package`               |
| Automation              | `Lightning`             |
| Security                | `ShieldCheck`           |
| Help / support          | `Question`              |
| Search                  | `MagnifyingGlass`       |
| Notifications           | `Bell`                  |
| Filter                  | `Funnel`                |
| Sort                    | `ArrowsDownUp`          |
| Export / download       | `DownloadSimple`        |
| Refresh / reload        | `ArrowCounterClockwise` |
| Calendar / date         | `CalendarBlank`         |
| Expand / fullscreen     | `ArrowsOut`             |
| More options (3-dot)    | `DotsThree`             |
| Close / X               | `X`                     |
| Add / new               | `Plus`                  |
| Edit / pencil           | `PencilSimple`          |
| Delete / trash          | `Trash`                 |
| View / eye              | `Eye`                   |
| External link           | `ArrowSquareOut`        |
| Check / success         | `CheckCircle`           |
| Warning / caution       | `Warning`               |
| Error / danger          | `XCircle`               |
| Info                    | `Info`                  |
| Copy                    | `Copy`                  |
| Upload                  | `UploadSimple`          |
| API / code              | `Code`                  |
| Webhook                 | `Webhooks` / `ArrowsLeftRight` |
| Cloud / deploy          | `Cloud`                 |
| Storage / database      | `Database`              |
| Compute / server        | `Desktop`               |
| AI / model              | `Brain` / `Sparkle`     |
| Message / chat          | `ChatCircle`            |
| Voice / audio           | `SpeakerHigh`           |
| Media / video           | `Video`                 |

---

## Icon Color Rules

### CHALK
```
Sidebar inactive  : neutral-400
Sidebar active    : neutral-900
Section icon      : neutral-500
CTA icon          : white (on dark button)
Status icons      : semantic (emerald/rose/amber)
```

### CANVAS
```
Sidebar inactive  : neutral-400
Sidebar active    : neutral-900 or accent
Table actions     : neutral-400, hover → neutral-900
Status            : semantic colors
```

### OBSIDIAN
```
All icons         : neutral-400 default
Active/hover      : white
Accent elements   : cyan-400
Status            : emerald/rose/amber (400 variants)
```

### ABYSS
```
All icons         : slate-400 default
Active/hover      : white
Accent elements   : blue-400
Status            : emerald/rose/amber (400 variants)
```

---

## Anti-patterns

```
NEVER  : Mix icon weights within one page
NEVER  : Colored icons in OBSIDIAN/ABYSS sidebars (monochrome only)
NEVER  : Emoji as functional icons
NEVER  : Icons without consistent sizing in same context
NEVER  : Different icon sets for nav vs content
ALWAYS : Hover state on clickable icons (color change)
ALWAYS : Tooltip on icon-only buttons (no label)
```
