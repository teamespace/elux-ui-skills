# Layout & Grid Reference
*Cross-style. Apply when structuring any dashboard page.*

---

## Core Layout Structure

```
┌─────────────────────────────────────────────────┐
│ SIDEBAR (220–260px fixed)   │ MAIN CONTENT       │
│                             │ ┌─────────────────┐│
│ Logo                        │ │ TOP BAR         ││
│ Search (optional)           │ │ Title + Actions ││
│                             │ └─────────────────┘│
│ NAV SECTIONS                │ ┌─────────────────┐│
│  Section Label              │ │ KPI ROW (3–4)   ││
│  • Nav Item                 │ └─────────────────┘│
│  • Nav Item (active)        │ ┌────────┐ ┌──────┐│
│                             │ │ CHART  │ │CHART ││
│ Section Label               │ │ 2/3 w  │ │1/3 w ││
│  • Nav Item                 │ └────────┘ └──────┘│
│  • Nav Item                 │ ┌─────────────────┐│
│                             │ │ TABLE (full w)  ││
│ USER / WORKSPACE (bottom)   │ └─────────────────┘│
└─────────────────────────────────────────────────┘
```

---

## Sidebar Widths

| Variant       | Width   | Use case                              |
|---------------|---------|---------------------------------------|
| Full          | 260px   | Many nav items, labels + icons        |
| Standard      | 220px   | Default — icon + label                |
| Compact       | 200px   | Tight space, still readable           |
| Icon-only     | 56–64px | Collapsed state, tooltips on hover    |

Sidebar is always fixed (not sticky) — content scrolls behind it.

---

## Content Area Grid

**12-column grid** within content area.

Common card spans:
```
Full width      : 12 cols
Two-thirds      : 8 cols
Half            : 6 cols
One-third       : 4 cols
One-quarter     : 3 cols
```

**KPI row patterns:**
```
3 KPI cards     : 4 cols each
4 KPI cards     : 3 cols each
5 KPI cards     : mixed (2+2+2+2+4 or scroll)
6 KPI cards     : 2 cols each (dense)
```

**Chart grid patterns:**
```
2 equal charts  : 6 + 6
Main + sidebar  : 8 + 4
Three equal     : 4 + 4 + 4
Main + two small: 8 + (4+4 stacked)
Full width      : 12 (main hero chart)
```

---

## Spacing Constants

```
Page padding H  : 24–32px (from sidebar right edge to content)
Page padding V  : 24px top
Section gap     : 24–32px between major sections
Card gap        : 16–20px between cards in same row
Card padding    : 20–24px internal
Top bar height  : 56–64px
Sidebar padding : 16–20px horizontal
```

---

## Top Bar Anatomy

```
Left side:
  - Page title (20–24px bold)
  - Optional breadcrumb above title (12px muted)

Right side (left to right):
  - Date range picker
  - Filter button
  - Export button  
  - Optional: search icon, notification bell, user avatar
```

---

## Bento Grid (OBSIDIAN style)

Free-form grid with intentionally varied card sizes:

```
Row 1: [1×1 stat] [1×1 stat] [2×1 chart] [1×1 stat]
Row 2: [1×2 profile] [2×1 chart] [1×1 stat] [1×1 list]
Row 3: [3×1 full chart] [1×1 stat]
```

Rules:
- No two adjacent cards same height AND width (vary deliberately)
- At least one card 2× wider than others per row
- At least one card 2× taller than others overall
- Gap: 16–20px uniform

---

## Responsive Breakpoints

Dashboard is desktop-first:

```
1440px+   : Full layout, all columns visible
1280px    : Sidebar 200px, content slightly compressed
1024px    : Sidebar collapses to icon-only (64px)
768px     : Single-column content, burger menu
< 768px   : Not recommended for complex dashboards
             Show mobile-optimized summary view instead
```

---

## Scroll Behavior

```
Sidebar     : fixed, does not scroll
Top bar     : sticky — stays visible on scroll (optional: hide on down, show on up)
Content     : scrolls freely
Tables      : horizontal scroll on overflow (never truncate data)
Charts      : fixed height — do not grow with content
```

---

## Empty & Loading States

Every section must define:

**Loading:**
```
KPI cards   : skeleton — gray animated pulse, same dimensions as loaded state
Charts      : gray animated area where chart will be, no axes
Tables      : 5 skeleton rows, same column structure
```

**Empty:**
```
Charts      : faint placeholder grid + "No data for selected period" center
Tables      : "No results found" center row, with optional filter reset action
KPI cards   : "–" or "0" with no delta badge
```
