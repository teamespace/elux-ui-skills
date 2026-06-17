# Interaction Reference — Micro-animations & Gestures
*Cross-style. Apply to ALL 6 styles unless overridden by style file.*

---

## Micro-animations

### Screen Transitions
```
Default         : shared-element transition (hero image or card expands to screen)
Fallback        : slide from right (push) — never fade-only
Back gesture    : slide to right (pop)
Modal / sheet   : slide up from bottom
Tab switch      : crossfade content + indicator slides horizontally
Duration        : 300ms push/pop, 250ms tabs, 350ms modal
Easing          : cubic-bezier(0.4, 0, 0.2, 1) for push/pop
                  spring(stiffness: 400, damping: 30) for modals
```

### List & Grid Entrance
```
Stagger delay   : 40ms per item (max 8 items staggered = 320ms cap)
Item animation  : translateY(12px) → translateY(0) + opacity 0→1
Duration        : 280ms per item
Easing          : cubic-bezier(0.0, 0.0, 0.2, 1)
Grid items      : stagger row by row, not item by item
```

### Loading States
```
Skeleton        : ALWAYS before content loads — never spinner alone
Skeleton color  : surface-color with shimmer overlay (animate-pulse)
Shimmer         : gradient moves left→right, 1.4s loop
Content swap    : fade in over skeleton (opacity 0→1, 200ms)
Spinner use     : only for button loading states (inline, never full-screen)
```

### Button / Tap Feedback
```
Press scale     : transform scale(0.96), duration 100ms
Release         : spring back scale(1.0), duration 200ms
Haptic          : light impact on press (iOS: UIImpactFeedbackGenerator .light)
Color shift     : darken bg by ~10% on press (or use :active state)
Disabled state  : opacity 0.4, no interaction, cursor not-allowed
```

### Success States
```
Checkmark       : SVG stroke-dashoffset animation, 400ms
Scale           : scale(0.8)→scale(1.1)→scale(1.0), spring
Color           : accent → emerald-400 (brief flash then settle)
Haptic          : success notification (iOS: .success)
```

### Error States
```
Shake           : translateX animation — 0→-6px→6px→-4px→4px→0
Duration        : 400ms total, 5 keyframes
Haptic          : error notification (iOS: .error)
Color           : input border/bg flashes rose-400 briefly
```

### Pull-to-Refresh
```
Indicator       : custom branded — NOT OS default spinner
Design          : subtle brand icon or simple ring
Threshold       : 60px pull before trigger
Animation       : spring bounce on release
Completion      : smooth fade out, content reloads with stagger
```

### Scroll Behaviors
```
Momentum        : always enabled (native momentum scrolling)
Header          : transparent on top, fills in on scroll (30–60px threshold)
Sticky labels   : section headers stick on scroll (position: sticky)
Parallax        : hero image scrolls at 0.5× content speed (optional per style)
```

---

## Gesture Patterns

### Card / List Gestures
```
Swipe left      : reveal destructive action (delete, archive)
                  Red bg appears, icon + label visible
                  Full swipe = auto-trigger + dismiss
                  Partial swipe = reveal panel, release = snap back
Swipe right     : reveal secondary action (save, pin, mark done)
                  Brand/accent bg appears
Long press      : context menu appears (haptic peek on iOS)
                  Options: max 5 items, destructive always last + red
```

### Bottom Sheet
```
Trigger         : tap CTA or swipe up from bottom
Handle          : 4px × 40px pill, neutral-400, centered top of sheet
Height          : 50% / 75% / 95% snap points
Dismiss         : swipe down past 40% height, or tap outside overlay
Overlay         : black/50 backdrop, tap to dismiss
Animation       : spring(stiffness: 350, damping: 28)
```

### Image Interactions
```
Pinch to zoom   : on detail/gallery screens
Double tap      : toggle zoom (1× → 2×) with spring
Swipe           : next/prev image in gallery
Dismiss         : swipe down from zoomed-out state → close overlay
```

### Navigation Gesture
```
Swipe-back      : screen-edge swipe (left edge, 20px zone) pops screen
                  ALWAYS implement — required for all push screens
Swipe-down      : dismisses modals, bottom sheets, full-screen overlays
Drag-to-refresh : only on list/feed screens at top of scroll
```

---

## State Completeness (always define all 6)

Every interactive component must specify:
```
1. Default   — resting state
2. Hover     — pointer hover (web/iPad) — subtle bg shift
3. Active    — finger pressed — scale + darken
4. Disabled  — opacity 0.4, no gesture response
5. Loading   — spinner or skeleton, preserve layout
6. Error     — shake + color indicator
```
