# Shadcn/ui Reference — Dashboard
*Component system untuk semua dashboard styles. Phosphor = icons, Shadcn = components.*

---

## Setup

```bash
# Init shadcn di project
npx shadcn@latest init

# Install komponen yang dipakai dashboard
npx shadcn@latest add button card badge table tabs select dropdown-menu
npx shadcn@latest add dialog sheet tooltip skeleton separator avatar
npx shadcn@latest add input command popover calendar progress
```

---

## CSS Variable Mapping per Style

Paste ke `globals.css` sesuai style yang dipilih.

### CHALK — Clean SaaS Light

```css
:root {
  --background:         250 250 250;   /* neutral-50  */
  --foreground:          23  23  23;   /* neutral-900 */
  --card:               255 255 255;   /* white       */
  --card-foreground:     23  23  23;   /* neutral-900 */
  --popover:            255 255 255;
  --popover-foreground:  23  23  23;
  --primary:             23  23  23;   /* neutral-900 */
  --primary-foreground: 255 255 255;
  --secondary:          245 245 245;   /* neutral-100 */
  --secondary-foreground: 23 23  23;
  --muted:              245 245 245;   /* neutral-100 */
  --muted-foreground:   163 163 163;   /* neutral-400 */
  --accent:             245 245 245;
  --accent-foreground:   23  23  23;
  --destructive:        244  63  94;   /* rose-500    */
  --border:             229 229 229;   /* neutral-200 */
  --input:              229 229 229;
  --ring:                23  23  23;
  --radius:             0.5rem;        /* 8px — clean, not too round */
}
```

### CANVAS — Dense Light / Technical

```css
:root {
  --background:         255 255 255;   /* white       */
  --foreground:          23  23  23;   /* neutral-900 */
  --card:               255 255 255;
  --card-foreground:     23  23  23;
  --primary:             23  23  23;
  --primary-foreground: 255 255 255;
  --secondary:          245 245 245;   /* neutral-100 */
  --secondary-foreground: 82 82  82;   /* neutral-600 */
  --muted:              250 250 250;   /* neutral-50  */
  --muted-foreground:   163 163 163;   /* neutral-400 */
  --accent:             249 115  22;   /* orange-500 — adapt per brand */
  --accent-foreground:  255 255 255;
  --destructive:        244  63  94;   /* rose-500    */
  --border:             212 212 212;   /* neutral-300 */
  --input:              229 229 229;
  --ring:               249 115  22;   /* accent ring */
  --radius:             0.375rem;      /* 6px — tighter for dense UI */
}
```

### OBSIDIAN — Dark Glassy

```css
:root {
  --background:          10  10  10;   /* neutral-950 */
  --foreground:         255 255 255;
  --card:                23  23  23;   /* neutral-900 */
  --card-foreground:    255 255 255;
  --popover:             23  23  23;
  --popover-foreground: 255 255 255;
  --primary:             34 211 238;   /* cyan-400    */
  --primary-foreground:  10  10  10;
  --secondary:           38  38  38;   /* neutral-800 */
  --secondary-foreground: 163 163 163; /* neutral-400 */
  --muted:               38  38  38;
  --muted-foreground:   115 115 115;   /* neutral-500 */
  --accent:              34 211 238;   /* cyan-400    */
  --accent-foreground:   10  10  10;
  --destructive:        251 113 133;   /* rose-400    */
  --border:             255 255 255 / 0.08;
  --input:              255 255 255 / 0.08;
  --ring:                34 211 238;
  --radius:             0.75rem;       /* 12px — softer on dark bg */
}
```

### ABYSS — Dark Premium Fintech

```css
:root {
  --background:           2   6  23;   /* slate-950   */
  --foreground:         255 255 255;
  --card:                15  23  42;   /* slate-900   */
  --card-foreground:    255 255 255;
  --popover:             15  23  42;
  --popover-foreground: 255 255 255;
  --primary:             59 130 246;   /* blue-500    */
  --primary-foreground: 255 255 255;
  --secondary:           30  41  59;   /* slate-800   */
  --secondary-foreground: 148 163 184; /* slate-400   */
  --muted:               30  41  59;
  --muted-foreground:    71  85 105;   /* slate-600   */
  --accent:              96 165 250;   /* blue-400    */
  --accent-foreground:    2   6  23;
  --destructive:        251 113 133;   /* rose-400    */
  --border:              51  65  85 / 0.4;  /* slate-700/40 */
  --input:               51  65  85 / 0.4;
  --ring:                59 130 246;
  --radius:             0.625rem;      /* 10px        */
}
```

---

## Component Usage per Dashboard Element

### KPI Cards → `<Card>`

```tsx
import { Card, CardContent, CardHeader } from "@/components/ui/card"
import { Badge } from "@/components/ui/badge"

// Usage
<Card>
  <CardHeader className="pb-2">
    <span className="text-xs text-muted-foreground uppercase tracking-wide">
      Total Revenue
    </span>
  </CardHeader>
  <CardContent>
    <div className="text-3xl font-semibold tabular-nums">$9,257.51</div>
    <Badge variant="outline" className="mt-2 text-emerald-500 border-emerald-500/30 bg-emerald-500/10">
      ↑ 15.8%
    </Badge>
  </CardContent>
</Card>
```

### Data Tables → `<Table>`

```tsx
import {
  Table, TableBody, TableCell, TableHead,
  TableHeader, TableRow
} from "@/components/ui/table"
import { Badge } from "@/components/ui/badge"
import { Button } from "@/components/ui/button"

// Usage
<Table>
  <TableHeader>
    <TableRow>
      <TableHead className="w-[200px]">Application</TableHead>
      <TableHead>Type</TableHead>
      <TableHead>Rate</TableHead>
      <TableHead className="text-right">Profit</TableHead>
    </TableRow>
  </TableHeader>
  <TableBody>
    <TableRow>
      <TableCell className="font-medium">Stripe</TableCell>
      <TableCell><Badge variant="secondary">Finance</Badge></TableCell>
      <TableCell>
        <div className="flex items-center gap-2">
          <div className="h-1.5 w-24 rounded-full bg-muted overflow-hidden">
            <div className="h-full w-[40%] rounded-full bg-primary" />
          </div>
          <span className="text-xs tabular-nums">40%</span>
        </div>
      </TableCell>
      <TableCell className="text-right tabular-nums">$650.00</TableCell>
    </TableRow>
  </TableBody>
</Table>
```

### Page Tabs → `<Tabs>`

```tsx
import { Tabs, TabsList, TabsTrigger, TabsContent } from "@/components/ui/tabs"

<Tabs defaultValue="overview">
  <TabsList>
    <TabsTrigger value="overview">Overview</TabsTrigger>
    <TabsTrigger value="metrics">Metrics</TabsTrigger>
    <TabsTrigger value="settings">Settings</TabsTrigger>
  </TabsList>
  <TabsContent value="overview">...</TabsContent>
</Tabs>
```

### Date Range Picker → `<Popover>` + `<Calendar>`

```tsx
import { Popover, PopoverContent, PopoverTrigger } from "@/components/ui/popover"
import { Button } from "@/components/ui/button"
import { Calendar } from "@/components/ui/calendar"
import { CalendarBlank } from "@phosphor-icons/react"

<Popover>
  <PopoverTrigger asChild>
    <Button variant="outline" className="gap-2">
      <CalendarBlank size={16} />
      Oct 18 – Nov 18
    </Button>
  </PopoverTrigger>
  <PopoverContent className="w-auto p-0" align="end">
    <Calendar mode="range" />
  </PopoverContent>
</Popover>
```

### Filter / Sort Dropdown → `<DropdownMenu>`

```tsx
import {
  DropdownMenu, DropdownMenuContent, DropdownMenuItem,
  DropdownMenuTrigger, DropdownMenuSeparator, DropdownMenuLabel
} from "@/components/ui/dropdown-menu"
import { Button } from "@/components/ui/button"
import { Funnel } from "@phosphor-icons/react"

<DropdownMenu>
  <DropdownMenuTrigger asChild>
    <Button variant="outline" size="sm" className="gap-1.5">
      <Funnel size={14} /> Filter
    </Button>
  </DropdownMenuTrigger>
  <DropdownMenuContent align="end">
    <DropdownMenuLabel>Filter by</DropdownMenuLabel>
    <DropdownMenuSeparator />
    <DropdownMenuItem>This week</DropdownMenuItem>
    <DropdownMenuItem>This month</DropdownMenuItem>
    <DropdownMenuItem>Last 90 days</DropdownMenuItem>
  </DropdownMenuContent>
</DropdownMenu>
```

### Status Badges → `<Badge>` variants

```tsx
import { Badge } from "@/components/ui/badge"

// Extend with custom variants in badge.tsx or use className overrides:
<Badge className="bg-emerald-500/10 text-emerald-500 border-emerald-500/20">Active</Badge>
<Badge className="bg-amber-500/10 text-amber-500 border-amber-500/20">Pending</Badge>
<Badge className="bg-rose-500/10 text-rose-500 border-rose-500/20">Failed</Badge>
<Badge className="bg-violet-500/10 text-violet-500 border-violet-500/20">Alpha</Badge>
<Badge className="bg-sky-500/10 text-sky-500 border-sky-500/20">Beta</Badge>
<Badge variant="secondary">Archived</Badge>
```

### Loading Skeletons → `<Skeleton>`

```tsx
import { Skeleton } from "@/components/ui/skeleton"

// KPI card skeleton
<Card>
  <CardHeader><Skeleton className="h-3 w-24" /></CardHeader>
  <CardContent>
    <Skeleton className="h-8 w-32 mb-2" />
    <Skeleton className="h-4 w-16" />
  </CardContent>
</Card>

// Table row skeleton
<TableRow>
  <TableCell><Skeleton className="h-4 w-32" /></TableCell>
  <TableCell><Skeleton className="h-4 w-20" /></TableCell>
  <TableCell><Skeleton className="h-2 w-24 rounded-full" /></TableCell>
  <TableCell><Skeleton className="h-4 w-16 ml-auto" /></TableCell>
</TableRow>
```

### Sidebar Nav Item → `<Button>` ghost variant

```tsx
import { Button } from "@/components/ui/button"
import { Tooltip, TooltipContent, TooltipTrigger } from "@/components/ui/tooltip"
import { ChartBar } from "@phosphor-icons/react"

// Full sidebar item
<Button
  variant="ghost"
  className="w-full justify-start gap-2.5 text-muted-foreground
             hover:text-foreground data-[active=true]:bg-secondary
             data-[active=true]:text-foreground"
  data-active={isActive}
>
  <ChartBar size={18} />
  Analytics
</Button>

// Icon-only collapsed sidebar
<Tooltip>
  <TooltipTrigger asChild>
    <Button variant="ghost" size="icon">
      <ChartBar size={18} />
    </Button>
  </TooltipTrigger>
  <TooltipContent side="right">Analytics</TooltipContent>
</Tooltip>
```

### Search Command → `<Command>`

```tsx
import {
  Command, CommandInput, CommandList,
  CommandItem, CommandGroup
} from "@/components/ui/command"

<Command className="rounded-lg border">
  <CommandInput placeholder="Quick search... ⌘K" />
  <CommandList>
    <CommandGroup heading="Navigation">
      <CommandItem>Dashboard</CommandItem>
      <CommandItem>Analytics</CommandItem>
    </CommandGroup>
  </CommandList>
</Command>
```

### Confirmation Dialog → `<Dialog>`

```tsx
import {
  Dialog, DialogContent, DialogHeader,
  DialogTitle, DialogFooter
} from "@/components/ui/dialog"
import { Button } from "@/components/ui/button"

<Dialog>
  <DialogContent>
    <DialogHeader>
      <DialogTitle>Delete integration?</DialogTitle>
    </DialogHeader>
    <p className="text-sm text-muted-foreground">
      This action cannot be undone.
    </p>
    <DialogFooter>
      <Button variant="outline">Cancel</Button>
      <Button variant="destructive">Delete</Button>
    </DialogFooter>
  </DialogContent>
</Dialog>
```

### Settings Panel → `<Sheet>`

```tsx
import { Sheet, SheetContent, SheetHeader, SheetTitle } from "@/components/ui/sheet"

// Side panel for filter/detail — better than modal for dashboards
<Sheet>
  <SheetContent side="right" className="w-[400px]">
    <SheetHeader>
      <SheetTitle>Filter Options</SheetTitle>
    </SheetHeader>
    {/* filter content */}
  </SheetContent>
</Sheet>
```

---

## Component → Shadcn Mapping (quick ref)

| Dashboard element        | Shadcn component                    |
|--------------------------|-------------------------------------|
| KPI metric card          | `Card` + `Badge`                    |
| Data table               | `Table`                             |
| Page/section tabs        | `Tabs`                              |
| Date range picker        | `Popover` + `Calendar` + `Button`   |
| Filter dropdown          | `DropdownMenu` + `Button`           |
| Status badge             | `Badge` (className override)        |
| Loading state            | `Skeleton`                          |
| Sidebar nav item         | `Button` ghost + `Tooltip`          |
| Search / command palette | `Command`                           |
| Confirmation modal       | `Dialog`                            |
| Side filter panel        | `Sheet`                             |
| Progress bar             | `Progress`                          |
| Avatar / user image      | `Avatar`                            |
| Section divider          | `Separator`                         |
| Form inputs              | `Input` + `Select` + `Label`        |
| Notification count       | `Badge` absolute positioned         |
| Expandable section       | `Collapsible`                       |
| Tooltip on hover         | `Tooltip`                           |

---

## Rules

```
ALWAYS  : Use shadcn components for all interactive elements
ALWAYS  : Override via CSS variables (globals.css) — never hardcode colors
ALWAYS  : Pair Phosphor icons with shadcn buttons (size={16} or size={18})
ALWAYS  : Use className overrides for semantic badge colors (not custom variants)
NEVER   : Mix shadcn with other component libraries (Radix direct, MUI, etc)
NEVER   : Hardcode hex colors in component props — use Tailwind tokens only
NEVER   : Create custom modal/dropdown from scratch when shadcn has it
```
