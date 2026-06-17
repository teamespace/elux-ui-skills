---
name: mobile-ui
description: >
  Use this skill for ANY mobile UI design request — screens, flows, components,
  or full apps. Triggers on: "buat mobile app", "design screen", "bikin tampilan
  mobile", "mobile UI", "app screen", "bikin onboarding", "home screen", "detail
  page", "flow mobile", or any request producing a mobile interface.

  Cross-platform agnostic (React Native / Flutter vibe). Picks a named style
  from the style library, enforces thumb-zone + gesture + micro-animation rules,
  runs pre-flight checklist, then builds.

  Always use this skill even for single-screen requests. Works with all agents:
  Claude, Codex, Cursor, Windsurf.
---

# Mobile UI Skill

---

## Step 1 — Set the Dials

```
TOUCH_FIDELITY  : 8   // 1–10 | strictness of thumb-zone + tap target rules
MOTION_DEPTH    : 7   // 1–10 | micro-animation intensity
GESTURE_LAYER   : 7   // 1–10 | swipe/drag/haptic cue density
```

---

## Step 2 — Pick a Style

Auto-pick based on context, or user calls by name: `"pakai style VOID"`

| Style      | Best for                                      | Reference      |
|------------|-----------------------------------------------|----------------|
| SLATE      | Marketplace, booking, travel, e-commerce      | Airbnb         |
| PARCHMENT  | Education, wellness, journaling, learning     | Vocabulary app |
| COBALT     | Fintech home, wallet, payments hero           | Revolut (home) |
| VOID       | Portfolio, analytics, crypto, data tracking   | Revolut wealth |
| SURGE      | Super app, multi-service, ride/food delivery  | Gojek          |
| ARGON      | Premium dark consumer, fitness, luxury        | —              |

**Auto-pick logic:**
```
Marketplace / booking      → SLATE
Education / wellness       → PARCHMENT
Fintech home / payments    → COBALT
Portfolio / analytics      → VOID
Super app / multi-service  → SURGE
Premium / exclusive        → ARGON
Unknown                    → ask ONE focused question, then pick
```

After picking → **read `references/styles/[style-name].md`** before generating any UI.

---

## Step 3 — Load Supporting References

Load based on what the request needs:

| Need                              | Read                          |
|-----------------------------------|-------------------------------|
| Always                            | `references/styles/[name].md` |
| Animation / micro-interaction     | `references/interaction.md`   |
| Multi-screen flow / transitions   | `references/flow.md`          |
| Icon decisions                    | `references/icons.md`         |
| Typography system deep-dive       | inside style file (self-contained) |

---

## Step 4 — Pre-Flight Checklist (MANDATORY)

```
□ Style picked (named or auto) + reason stated
□ Dials set
□ Thumb zone: primary CTA in bottom 60% of screen
□ Min tap target 44×44px on all interactive elements
□ Skeleton loader state defined (not just loaded state)
□ At least 2 gesture interactions specified
□ Micro-animation noted: entrance, CTA press, screen transition
□ Bottom nav present if 3+ sections exist
□ Realistic content — no Lorem Ipsum, no placeholder numbers
□ Icon set decided (from references/icons.md)
```

---

## Step 5 — Build

Output adapts to request:

| Request              | Default output                                         |
|----------------------|--------------------------------------------------------|
| Single screen        | HTML/JSX mockup, 390×844px                             |
| Multi-screen flow    | Annotated set with transition notes                    |
| Component            | All states: default, hover, active, disabled, loading, error |
| React Native         | RN StyleSheet + Animated API                           |
| Flutter              | Widget + AnimationController                           |
| Handoff spec         | Token block + spacing annotation                       |

---

## Thumb Zone (always apply)

```
SAFE ZONE    : bottom 60% → primary actions, nav, CTAs
STRETCH ZONE : middle 30% → secondary interactions
DEAD ZONE    : top 10%   → decorative / status only

Primary CTA  : always within 80px of bottom edge
Back button  : top-left, but prefer swipe-back gesture
FAB          : bottom-right, 72px above nav
Min target   : 44×44px — hard limit, no exceptions
```

---

## Anti-Slop Rules (always enforce)

```
NEVER  : Purple-blue gradient on white (default AI output)
NEVER  : Inter Regular 16px on white for everything
NEVER  : Uniform 8px border-radius across all elements
NEVER  : Heroicons / Feather on everything without style rationale
NEVER  : Center-aligned body text blocks
NEVER  : Empty state = icon + "No items yet"
NEVER  : Modal for simple confirmation (use bottom sheet)
NEVER  : Three-dot menu as primary action
ALWAYS : One distinctive visual moment per screen
ALWAYS : Style-consistent spacing system, not arbitrary px values
ALWAYS : At least one delight detail per screen
```
