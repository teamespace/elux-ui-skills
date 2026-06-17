# Charts & Data Visualization Reference
*Cross-style. Apply when building any chart or data viz component.*

---

## Chart Type Selection

Pick chart type based on the data story:

| Data story                     | Chart type              | Never use instead     |
|--------------------------------|-------------------------|-----------------------|
| Trend over time                | Line or Area            | Bar (unless comparing periods) |
| Comparison across categories   | Bar (vertical)          | Pie (too many cats)   |
| Part-to-whole (≤5 categories)  | Donut                   | Pie (prefer donut)    |
| Distribution / frequency       | Histogram / Area        | Line                  |
| Two variables correlation      | Scatter                 | Line                  |
| Activity over time             | Heatmap calendar        | Bar                   |
| Geographic distribution        | Choropleth map          | Bar                   |
| Progress toward goal           | Gauge / Radial bar      | Donut                 |
| Rankings / leaderboard         | Horizontal bar          | Vertical bar          |
| Grouped comparison (multi-cat) | Grouped bar             | Stacked (unless showing total) |

**Mixing rule:** Never use the same chart type more than twice per page. Vary.

---

## Color Palette per Style

### CHALK (light minimal)
```
Primary   : neutral-900  #171717
Secondary : neutral-400  #A3A3A3
Positive  : emerald-500  #10B981
Negative  : rose-500     #F43F5E
Info      : sky-500      #0EA5E9
Area fill : primary at 8–12% opacity
```

### CANVAS (dense light)
```
Series 1  : sky-500      #0EA5E9
Series 2  : violet-500   #8B5CF6
Series 3  : emerald-500  #10B981
Series 4  : orange-400   #FB923C
Series 5  : rose-400     #FB7185
Area fill : series color at 10% opacity
Grid line : neutral-100  #F5F5F5
```

### OBSIDIAN (dark glassy)
```
Series 1  : cyan-400     #22D3EE
Series 2  : violet-400   #A78BFA
Series 3  : emerald-400  #34D399
Series 4  : rose-400     #FB7185
Series 5  : amber-400    #FBBF24
Area fill : series color at 15–20% opacity
Grid line : rgba(255,255,255,0.04)
```

### ABYSS (dark premium)
```
Series 1  : blue-400     #60A5FA
Series 2  : violet-400   #A78BFA
Series 3  : cyan-400     #22D3EE
Dim bars  : blue-400/20  rgba(96,165,250,0.20)
Area fill : series color at 15% opacity
Grid line : rgba(255,255,255,0.04)
```

---

## Chart Anatomy Rules

### Every chart MUST have:
```
□ Title: left-aligned, section-title size
□ Optional subtitle or time range
□ Legend: if multiple series — color dot + label, bottom or right
□ Empty state: placeholder illustration + "No data for this period"
□ Loading state: skeleton bars/lines animated
```

### Grid lines:
```
Horizontal only (never vertical in line/area/bar charts)
Opacity: 4–8% on dark, neutral-100 on light
No border around chart area
```

### Axes:
```
Y-axis: left side, labels right-aligned, Geist Mono / monospace
X-axis: bottom, labels centered under tick
Tick count: max 6 Y-axis labels, max 8 X-axis labels
Zero line: slightly more visible than regular grid lines
```

### Tooltips:
```
Background: surface color + 1px border + shadow
Content: date/label, series name, value (bold), delta if relevant
Font: Geist Mono for numbers, style body font for labels
Position: follow cursor, never clip off screen edge
```

---

## Specific Chart Patterns

### KPI Sparkline (inline in KPI card)
```
Height     : 40–60px
Width      : full card width
Line       : 1.5px stroke, chart primary color
Area fill  : 8% opacity
No axes    : no labels, no grid
No tooltip : decorative only
```

### Area Chart (trend)
```
Line       : 2px stroke
Fill       : gradient — 20% at top → 0% at bottom
Smooth     : monotone curve (not jagged)
Data points: show dots only on hover
```

### Bar Chart (comparison)
```
Bar width  : 60–70% of available band width
Radius     : 4px top corners only (border-radius: 4px 4px 0 0)
Hover      : brighten bar, show tooltip
Grouped    : 4px gap between bars in same group
```

### Donut Chart
```
Stroke width : 14–20px
Inner radius : 60% of outer (creates readable donut hole)
Segments     : 2px gap between segments (stroke-dashoffset)
Center text  : total value + label
Hover        : segment lifts slightly, tooltip appears
Max segments : 6 (use "Other" for remainder)
```

### Heatmap Calendar
```
Cell size  : 10–12px square
Gap        : 3px
Radius     : 2–3px
Color scale: 5 steps — empty → lightest → mid → high → darkest
             Use style accent color for filled cells
Labels     : month letters top (M A M J J A S O N D J F)
             Day letters left (M W F only)
Legend     : "Fewer ○ ○ ● ● ● More" bottom-right
```

### Gauge / Radial
```
Arc range  : 180° or 270° (never 360° — that's a donut)
Stroke     : 12–16px
Track      : muted version of accent at 20% opacity
Fill       : gradient from negative (red) → neutral → positive (green)
Needle     : thin line or marker at current value
Value      : large centered below or inside arc
```

---

## Chart Library Recommendations

```
Recharts    : React default — good for line, bar, area, donut
Chart.js    : HTML/vanilla — good all-rounder
D3.js       : Complex custom viz (heatmap, gauge, map, custom)
Tremor      : React + Tailwind — pre-styled, fastest to implement
```

For agent output:
- React artifacts → use Recharts (imported in Claude artifacts)
- HTML artifacts → use Chart.js via CDN
- Complex/custom → use D3 with explicit SVG paths
