# Flow Reference — Screen Flows & Navigation Patterns
*Cross-style. Apply when building multi-screen flows.*

---

## Navigation Archetypes

### Tab-Based (most common)
```
When to use    : 3–5 top-level sections
Bar position   : bottom (thumb-friendly)
Active state   : defined in style file
Max items      : 5 (4 recommended)
Transition     : crossfade between tabs
Deep nav       : push screens within each tab, each tab remembers its stack
```

### Stack Navigation
```
When to use    : drill-down flows (listing → detail, checkout steps)
Transition     : push right (enter), pop left (back)
Back control   : top-left back button + swipe-back gesture (always both)
Breadcrumb     : not needed on mobile — nav stack is implicit
```

### Modal / Overlay
```
When to use    : temporary task that doesn't change primary context
                 (filters, share sheet, quick edit, confirmation)
NOT for        : full creation flows, settings, complex forms
Transition     : slide up from bottom
Dismiss        : swipe down, tap backdrop, or explicit close button
Close button   : top-right X (32px) or "Done" text button
Max height     : 95vh (leave status bar visible)
```

### Drawer (side nav)
```
Avoid on mobile unless necessary (hamburger menus hide hierarchy)
If needed      : left-side, 80vw width, swipe-right to open
Use instead    : bottom nav, tab bar, or contextual navigation
```

---

## Common Flow Patterns

### Onboarding Flow
```
Screens        : 3–5 max (welcome → value props → permissions → account)
Progress       : dot indicators (top or bottom), NOT numbered steps
CTA            : full-width primary, bottom of screen, in safe zone
Skip           : top-right text link, always available from screen 2
Back           : top-left arrow or swipe-back (not needed on screen 1)
Last screen    : CTA = "Get Started" or "Continue", no skip
Transition     : horizontal slide (push), spring easing
```

### Auth Flow (Login / Signup)
```
Layout         : centered, single field focus per screen
Field order    : email → password (login) | name → email → password (signup)
Keyboard       : input scrolls up when keyboard appears (KeyboardAvoidingView)
CTA            : full-width, 56px, below last field
Error          : inline below field, rose-400 text, shake animation on submit fail
Social auth    : before email/password block, separated by "or" divider
```

### List → Detail Flow
```
Trigger        : tap card / row
Transition     : shared-element (image expands) preferred
                 fallback: push slide
Detail screen  : hero image top, content scrolls under
Sticky CTA     : fixed bottom, always visible on detail
Back           : top-left arrow + swipe-back gesture
Related items  : horizontal scroll section at bottom of detail
```

### Checkout / Multi-Step Form
```
Progress       : step indicator top (not dots — use "Step 2 of 3" text)
One section    : per screen, not all fields at once
Validation     : on blur + on submit, inline errors
CTA label      : "Continue" on steps, "Confirm" on review, "Pay" on final
Back           : always available, preserve previous values
Review screen  : summary of all inputs before final confirmation
```

### Empty States
```
Required       : always design empty state, never just blank
Components     : illustration (optional) + headline + subtext + CTA
Headline       : action-oriented ("Add your first item")
Illustration   : style-consistent (per style file)
CTA            : primary action to fill the empty state
Position       : vertically centered in available space
```

### Error / Offline States
```
Full-page error: illustration + headline + retry CTA
Inline error   : toast / snackbar at bottom, 4s auto-dismiss
Offline banner : persistent top bar, yellow/amber bg
Retry          : always offer explicit retry action
```

---

## Screen Anatomy (consistent across styles)

```
Status bar     : always accounted for (44px iOS / 24px Android)
                 Light or dark icons based on bg color

Navigation     : header bar OR floating back button
                 Header: 56px height, title + optional actions
                 Max 2 action icons in header right

Content area   : status-bar to nav-bar, scrollable
                 Horizontal padding: per style file (usually 16–24px)

Bottom area    : nav bar OR persistent CTA
                 Nav bar: 80px + safe area
                 Persistent CTA: 80px + safe area, white/surface bg
                 Never overlap scrollable content with fixed bottom elements

Safe areas     : ALWAYS respect iOS safe area (notch + home indicator)
                 Use: padding-top: env(safe-area-inset-top)
                      padding-bottom: env(safe-area-inset-bottom)
```

---

## Flow Handoff Notation

When outputting multi-screen flows, annotate each screen with:
```
[Screen name]
→ Trigger: [what causes this screen to appear]
→ Entry: [animation / transition type]
→ Exit to: [next screen + trigger]
→ Back to: [previous screen or dismiss]
→ Special states: [loading / error / empty]
```
