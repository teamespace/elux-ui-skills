# Tables & List Views Reference
*Cross-style. Apply when building any tabular data component.*

---

## Table Anatomy

```
┌──────────────────────────────────────────────────────┐
│ TABLE HEADER (title + controls)                      │
│  "List of Integrations"          [Filter] [Sort] [⋯] │
├──────────────────────────────────────────────────────┤
│ COLUMN HEADERS                                       │
│ □  APPLICATION ↕  TYPE ↕  RATE ↕  PROFIT ↕         │
├──────────────────────────────────────────────────────┤
│ □  [logo] Stripe    Finance    ████── 40%   $650     │
│ □  [logo] Zapier    CRM        ████████ 80% $720     │
│ □  [logo] Shopify   Commerce   ██ 20%       $432     │
├──────────────────────────────────────────────────────┤
│ PAGINATION   ← 1 2 3 ... 8 →          Rows: 10 ▾    │
└──────────────────────────────────────────────────────┘
```

---

## Column Types & Rendering

| Data type        | Render as                                            |
|------------------|------------------------------------------------------|
| Text             | Plain text, truncate with ellipsis if overflow       |
| Number           | Geist Mono / monospace, right-aligned, tabular-nums  |
| Currency         | Geist Mono, right-aligned, "$ 1,234.56" format      |
| Percentage       | Progress bar + text value, or text only              |
| Date             | "Jan 22, 2024" or relative "3 days ago"              |
| Status           | Colored badge pill (see Status Badges below)         |
| Logo/Avatar      | 24–32px circle/square image + name beside it         |
| Progress         | Thin bar `6px height` + optional `%` text right      |
| Boolean          | ✓ check (emerald) or ✗ cross (rose) icon             |
| Actions          | Inline text links or icon buttons — far right column |
| Hash/ID          | Geist Mono, truncate middle: `462a6b…b6ec`           |

---

## Table Specs

**Header row:**
```
Height       : 40px
Background   : neutral-50 (light) / surface-raised (dark)
Font         : 11px 500 UPPERCASE, letter-spacing 0.05em, muted color
Sort icons   : ↕ (unsorted) → ↑ (asc) → ↓ (desc) — click to cycle
Checkbox     : far left, 16px, select-all behavior
```

**Body rows:**
```
Height       : 44–48px (never under 40px)
Font         : 13px 400, primary text color
Border       : 1px bottom separator (subtle)
Hover        : surface-raised bg color
Selected     : accent/10 bg + accent left border (3px)
Alternate    : optional — neutral-50/neutral-800 every other row
```

**Checkbox column:**
```
Width        : 40px
Checkbox     : 16px, accent color when checked
Header       : select-all, indeterminate state when partial
```

---

## Status Badges

```
Open / Active    : emerald-400/20 bg, emerald-400 text, emerald-400/30 border
Pending / Review : amber-400/20 bg, amber-400 text
Closed / Done    : neutral-400/20 bg, neutral-400 text
Error / Failed   : rose-400/20 bg, rose-400 text
Archived         : neutral-600/20 bg, neutral-600 text
New              : sky-400/20 bg, sky-400 text
Beta / Alpha     : violet-400/20 bg, violet-400 text

Dimensions: border-radius 6px, padding 2px 8px, font 11px 500
```

---

## Pagination

**Standard:**
```
[←]  [1]  [2]  [3]  ...  [8]  [→]
Button size: 32×32px, border-radius 6px
Active page: accent bg or darker surface
Arrow: disabled at boundaries (opacity 0.3)
```

**Dense (Cloudflare-style):**
```
[|←]  [←]  [1]  [→]  [→|]
First/Last page jump arrows included
Page count label: "Page 1 of 8"
```

**Rows per page:**
```
Dropdown: "10 ▾" or "25 ▾" or "50 ▾"
Position: far right of pagination bar
```

---

## Filters & Controls (above table)

```
Search input   : pill, 200–280px wide, placeholder "Search..."
Filter button  : icon + "Filter" label, badge count when active
Sort button    : "↑↓ Sort" with active indicator
Column toggle  : "Columns ▾" to show/hide columns
Export         : "↓ Export" or icon button far right
Date range     : if table is time-filtered
```

---

## Expandable Rows

```
Trigger        : ▼ chevron far right, or click anywhere on row
Animation      : accordion expand, 200ms ease
Content        : nested detail view, full-width below parent row
Indicator      : row gets left border accent when expanded
```

---

## Table in a Card

When table is inside a card component:

```
Card header    : table title left, filter/sort controls right
Table          : no extra border (card provides container)
Pagination     : inside card footer, padding matches card
Max height     : set explicit max-height, overflow-y scroll inside card
```

---

## Anti-patterns

```
NEVER  : Truncate data without tooltip on hover showing full value
NEVER  : Right-align text columns (only numbers/currency right-aligned)
NEVER  : More than 8–10 columns without a column toggle
NEVER  : Colorful row backgrounds (only semantic: error=rose tint)
NEVER  : Remove hover state on rows
NEVER  : Pagination with 50+ pages and no jump-to-page
NEVER  : Actions column in first position (always last)
ALWAYS : Show column sort direction clearly
ALWAYS : Provide empty state when 0 results
ALWAYS : Monospace font for all numeric columns
```
