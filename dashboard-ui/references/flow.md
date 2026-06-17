# Flow Reference — Dashboard Navigation & Interaction Patterns
*Cross-style. Apply when building multi-page or multi-state dashboard flows.*

---

## Navigation Architecture

### Primary Navigation (Sidebar)
```
Structure      : tree max 2 levels deep
                 Level 1 = section (grouped by label)
                 Level 2 = sub-items (collapsible, indent 12px)
Active state   : highlight current page item — always visible
Deep link      : URL reflects current page (/dashboard/analytics/traffic)
Section groups : labeled dividers ("GENERAL", "TOOLS", "SUPPORT")
                 Max 5 items per group before needing a new group
Collapsed nav  : icon-only mode, tooltip on hover shows label
                 toggle via chevron button at sidebar top edge
```

### Secondary Navigation (Tabs within page)
```
When to use    : same entity, different views (Overview / Metrics / Settings)
Position       : below page title, above content
Style          : underline tabs (not pill) — see style file
URL behavior   : tabs update URL query param (?tab=metrics)
Max tabs       : 6 — if more, use dropdown "More ▾"
Mobile         : horizontal scroll, no wrapping
```

### Breadcrumb
```
When to use    : drill-down pages 2+ levels deep
Format         : "Workers & Pages  >  asm" (icon optional at start)
Font           : 13px muted, separator " > " or "/"
Last item      : current page, not a link, slightly darker
Position       : above page title
```

---

## Page Flow Patterns

### Overview → Detail Drill-down
```
Trigger        : click table row, card, or chart data point
Transition     : page navigate (not modal) — URL changes
Detail page    : full page with own tabs, back breadcrumb top
Back           : breadcrumb link OR browser back
Data context   : carry filter/date state from parent (query params)

Example        : Dashboard → [click Stripe row] → /integrations/stripe
```

### Sidebar → Content Page
```
Trigger        : click sidebar nav item
Transition     : instant content swap (no animation needed)
Scroll reset   : scroll to top on page change
Active state   : sidebar item highlights immediately on click
Loading        : skeleton while data fetches — sidebar stays visible
```

### Filter → Filtered View
```
Trigger        : change date range, dropdown filter, search input
Behavior       : optimistic update — show skeleton immediately, load data
URL update     : reflect filter state in URL (?from=2024-01-01&to=2024-01-31)
Persist        : filters persist when navigating back
Reset          : "Clear filters" link appears when any filter is active
Empty state    : if filters return 0 results — show empty state with reset CTA
```

### Settings / Config Flow
```
Pattern        : side sheet (Sheet component) OR dedicated settings page
Use sheet for  : quick edits, single field changes, toggle settings
Use page for   : complex multi-section settings, billing, team management
Save behavior  : auto-save on change (with subtle toast) OR explicit Save button
Unsaved changes: prompt on navigation away — "You have unsaved changes"
```

### Onboarding / Empty Dashboard
```
First-time user: empty state per section, not blank page
Pattern        : welcome card top + empty sections below with CTAs
Progress       : optional setup checklist (3–5 steps) collapsible top
Dismiss        : always allow dismissing onboarding state
```

---

## Interaction Flows

### Date Range Picker Flow
```
1. User clicks date button → Popover opens (Calendar component)
2. User selects start date → highlighted, awaiting end date
3. User selects end date → range highlighted, popover stays open
4. User clicks "Apply" → popover closes, data refetches with skeleton
5. Button label updates: "Oct 18 – Nov 18 · Monthly"
6. URL updates: ?from=2024-10-18&to=2024-11-18

Preset ranges  : "Today", "Last 7 days", "Last 30 days", "This month",
                 "Last 3 months", "Custom range"
                 Listed as quick-select above calendar
```

### Table Sort Flow
```
1. User clicks column header → column sorts ascending (↑)
2. Click again → sorts descending (↓)
3. Click again → returns to default sort
4. Visual: sort icon in header (↕ → ↑ → ↓)
5. Only one column sorted at a time
6. Sort state persists in URL (?sort=profit&dir=desc)
```

### Table Filter / Search Flow
```
1. User types in search input → debounce 300ms → filter applies
2. Matching text highlighted in results (optional)
3. If 0 results → empty state row with "Clear search" link
4. Filter badge: "3 filters active" pill near table title
5. Click badge → dropdown shows active filters with × to remove each
```

### Export Flow
```
1. User clicks "Export" button → dropdown: CSV / Excel / PDF
2. User selects format → loading state on button (spinner)
3. File downloads → success toast: "Report exported"
4. If error → error toast: "Export failed. Try again."
5. Large datasets: "Preparing export... We'll email you when ready"
```

### Drill-down Chart Flow
```
Trigger        : click bar/point/segment in chart
Behavior       : navigate to filtered detail page
                 OR open side sheet with breakdown
                 OR highlight related table rows below
Hover state    : tooltip shows exact value + % + label
Cursor         : pointer on clickable chart elements
Empty click area: no action (only data points are clickable)
```

### Upgrade / Limit Flow (SaaS)
```
Trigger        : user hits usage limit or tries locked feature
Pattern        : inline banner in affected section (not modal interrupt)
                 "You've reached your limit. Upgrade to Pro+ →"
CTA            : links to billing/upgrade page (not modal)
Dismissible    : yes, but re-shows on next visit if still at limit
```

---

## Toast / Notification Patterns

Use Shadcn `Sonner` or `Toast` for all feedback:

```
Success        : green left border, checkmark icon, 3s auto-dismiss
                 "Integration connected successfully"
Error          : red left border, X icon, persistent until dismissed
                 "Failed to load data. Retry?"
Info           : blue left border, info icon, 4s auto-dismiss
                 "Report is being generated..."
Warning        : amber left border, warning icon, 5s auto-dismiss
                 "API rate limit at 80%. Consider upgrading."

Position       : bottom-right (never top — covers page title)
Stack          : max 3 toasts visible, oldest dismisses first
Action         : optional inline button ("Retry", "Undo", "View")
```

---

## Loading & Error States

### Page-level Loading
```
Pattern        : skeleton layout — sidebar stays visible, content area shows
                 skeleton cards in exact positions of loaded content
Duration       : show skeleton immediately on navigation (no delay)
Transition     : fade in real content over skeleton (200ms)
```

### Section-level Loading
```
Pattern        : skeleton within card — card chrome stays, content skeletons
                 Animated shimmer pulse (Skeleton component)
```

### Error State
```
Full page      : centered — error icon + "Something went wrong" + Retry button
                 Show error code/message in small muted text below
Section        : card shows error inline — "Failed to load" + Retry link
Network        : persistent top banner (amber) "You're offline"
Partial        : load what's available, show inline error for failed sections
```

### Empty States (per section type)
```
KPI card       : "–" value, no delta badge, muted label
Chart          : faint grid + "No data for this period" center-aligned
Table          : single row spanning all columns — icon + message + CTA
                 "No integrations yet" + "Add integration" button
Sidebar section: show section, collapse if 0 items
Activity feed  : "No recent activity" with icon, no CTA needed
```

---

## URL State Management

Always reflect these in URL (enables sharing, bookmarking, back/forward):

```
Current page   : /dashboard/[section]/[page]
Active tab     : ?tab=metrics
Date range     : ?from=YYYY-MM-DD&to=YYYY-MM-DD
Period         : ?period=monthly (daily/weekly/monthly/yearly)
Sort           : ?sort=revenue&dir=desc
Filter         : ?filter=status:active,type:finance
Search query   : ?q=stripe
Pagination     : ?page=2&per_page=25
```
