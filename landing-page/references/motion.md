# Motion Reference — Scroll Animation & Interaction Patterns
*Cross-style. Read when MOTION_INTENSITY > 4 or scroll-driven sections are needed.*

---

## Library Choice

```
Motion (motion/react)    : default for UI/state-change motion, hover physics, reveal-on-scroll
GSAP + ScrollTrigger     : full-page scrolltelling, pin/scrub, horizontal-pan hijacks
Three.js / WebGL         : canvas backgrounds, 3D scenes
```

**NEVER mix GSAP/Three.js with Motion in the same component tree** — they fight
over the same animation frames.

Import Motion from `motion/react` (`import { motion } from "motion/react"`).
The `framer-motion` package alias still works but prefer `motion/react` in new code.

---

## Forbidden Patterns (hard bans)

```
NEVER : window.addEventListener("scroll", ...) — jank-prone, no batching
NEVER : window.scrollY in React state — re-renders every frame
NEVER : requestAnimationFrame loops that touch React state directly
NEVER : layout/layoutId props on static content "for safety" — costs measurement work
```

Use instead: Motion's `useScroll()`, GSAP's `ScrollTrigger`, `IntersectionObserver`,
or CSS `animation-timeline: view()` (scroll-driven animations).

For continuous values driven by user input (mouse position, scroll progress,
pointer physics): use `useMotionValue` / `useTransform`, never `useState`.
`useState` re-renders the React tree every change and collapses performance on mobile.

---

## Sticky-Stack Pattern (GSAP)

For "cards stack and pin on scroll" — must be a REAL sticky-stack, not a
sequential reveal list.

```tsx
"use client";
import { useRef, useEffect } from "react";
import { gsap } from "gsap";
import { ScrollTrigger } from "gsap/ScrollTrigger";
import { useReducedMotion } from "motion/react";

gsap.registerPlugin(ScrollTrigger);

export function StickyStack({ cards }: { cards: React.ReactNode[] }) {
  const ref = useRef<HTMLDivElement>(null);
  const reduce = useReducedMotion();

  useEffect(() => {
    if (reduce || !ref.current) return;
    const ctx = gsap.context(() => {
      const cardEls = gsap.utils.toArray<HTMLElement>(".stack-card");
      cardEls.forEach((card, i) => {
        if (i === cardEls.length - 1) return;
        ScrollTrigger.create({
          trigger: card,
          start: "top top",                  // CRITICAL: pin at viewport top
          endTrigger: cardEls[cardEls.length - 1],
          end: "top top",
          pin: true,
          pinSpacing: false,
        });
        gsap.to(card, {
          scale: 0.92,
          opacity: 0.55,
          ease: "none",
          scrollTrigger: {
            trigger: cardEls[i + 1],
            start: "top bottom",
            end: "top top",
            scrub: true,
          },
        });
      });
    }, ref);
    return () => ctx.revert();
  }, [reduce]);

  return (
    <div ref={ref}>
      {cards.map((card, i) => (
        <div key={i} className="stack-card">{card}</div>
      ))}
    </div>
  );
}
```

**Common failure:** trigger fires halfway through scroll instead of pinning at
viewport top. Fix: `start: "top top"`, never `"top center"` or `"top 80%"`.

---

## Horizontal-Pan Pattern (GSAP)

Vertical scroll converts to horizontal pan within a pinned section.

```tsx
"use client";
import { useRef, useEffect } from "react";
import { gsap } from "gsap";
import { ScrollTrigger } from "gsap/ScrollTrigger";
import { useReducedMotion } from "motion/react";

gsap.registerPlugin(ScrollTrigger);

export function HorizontalPan({ children }: { children: React.ReactNode }) {
  const wrap = useRef<HTMLDivElement>(null);
  const track = useRef<HTMLDivElement>(null);
  const reduce = useReducedMotion();

  useEffect(() => {
    if (reduce || !wrap.current || !track.current) return;
    const ctx = gsap.context(() => {
      const distance = track.current!.scrollWidth - window.innerWidth;
      gsap.to(track.current, {
        x: -distance,
        ease: "none",
        scrollTrigger: {
          trigger: wrap.current,
          start: "top top",                 // pin starts when section top hits viewport top
          end: () => `+=${distance}`,       // scroll distance = horizontal travel needed
          pin: true,
          scrub: 1,
          invalidateOnRefresh: true,
        },
      });
    }, wrap);
    return () => ctx.revert();
  }, [reduce]);

  return (
    <section ref={wrap} className="relative overflow-hidden">
      <div ref={track} className="flex h-[100dvh] items-center">
        {children}
      </div>
    </section>
  );
}
```

**Common failure:** animation starts before the section is pinned, user sees
half a slide. Same fix: `start: "top top"`, pin the wrapper, scrub the inner track.

---

## Scroll-Reveal Stagger (Motion — lighter alternative)

For simple "items appear as they enter viewport" with no pinning, prefer
Motion's `whileInView` over GSAP — lighter, no ScrollTrigger needed.

```tsx
"use client";
import { motion, useReducedMotion } from "motion/react";

export function RevealStagger({ items }: { items: string[] }) {
  const reduce = useReducedMotion();
  return (
    <ul className="grid gap-6">
      {items.map((item, i) => (
        <motion.li
          key={item}
          initial={reduce ? false : { opacity: 0, y: 24 }}
          whileInView={{ opacity: 1, y: 0 }}
          viewport={{ once: true, amount: 0.3 }}
          transition={{ duration: 0.6, delay: i * 0.06, ease: [0.16, 1, 0.3, 1] }}
        >
          {item}
        </motion.li>
      ))}
    </ul>
  );
}
```

Use this for: feature lists, testimonial grids, logo walls, anything that just
needs "enter on scroll." Save GSAP for actual pin/scrub work.

---

## Magnetic Button (Motion)

```tsx
"use client";
import { useRef } from "react";
import { motion, useMotionValue, useSpring } from "motion/react";

export function MagneticButton({ children }: { children: React.ReactNode }) {
  const ref = useRef<HTMLButtonElement>(null);
  const x = useMotionValue(0);
  const y = useMotionValue(0);
  const springX = useSpring(x, { stiffness: 150, damping: 15 });
  const springY = useSpring(y, { stiffness: 150, damping: 15 });

  const handleMouseMove = (e: React.MouseEvent) => {
    const rect = ref.current?.getBoundingClientRect();
    if (!rect) return;
    x.set((e.clientX - rect.left - rect.width / 2) * 0.3);
    y.set((e.clientY - rect.top - rect.height / 2) * 0.3);
  };

  return (
    <motion.button
      ref={ref}
      onMouseMove={handleMouseMove}
      onMouseLeave={() => { x.set(0); y.set(0); }}
      style={{ x: springX, y: springY }}
      className="rounded-full px-8 py-4"
    >
      {children}
    </motion.button>
  );
}
```

Use when `MOTION_INTENSITY > 5` AND brief reads premium/playful/agency.
Implement exclusively via motion values — never `useState` for cursor tracking.

---

## Motion Intensity → Implementation Band

```
1-3 (Static)
  No automatic animations. CSS :hover/:active only.
  prefers-reduced-motion is the default mode anyway.

4-7 (Fluid CSS / Motion whileInView)
  transition: all 0.3s cubic-bezier(0.16, 1, 0.3, 1)
  animation-delay cascades for load-ins
  Focus on transform and opacity only

8-10 (Advanced Choreography)
  Scroll-triggered reveals, parallax, scroll-driven animation
  GSAP ScrollTrigger for pin/scrub work
  Spring physics (type: "spring", stiffness: 100, damping: 20) — no linear easing
```

---

## Reduced Motion (mandatory wrapper pattern)

```tsx
import { useReducedMotion } from "motion/react";

const reduce = useReducedMotion();

<motion.div
  initial={reduce ? false : { opacity: 0, y: 24 }}
  animate={{ opacity: 1, y: 0 }}
/>
```

In CSS: gate behind `@media (prefers-reduced-motion: no-preference)`, or
disable inside `@media (prefers-reduced-motion: reduce)`.

Infinite loops, parallax, scroll-hijack, and magnetic physics MUST collapse
to static/instant under reduced motion — no exceptions.

---

## Performance Rules

```
Animate ONLY transform and opacity — never top, left, width, height
will-change: transform — sparingly, only on elements that WILL animate
Grain/noise filters — fixed pointer-events-none pseudo-elements ONLY,
  never on scrolling containers (destroys mobile FPS)
Lazy-load anything not above-the-fold (Motion isn't tiny, Three.js is large)
```

---

## When Motion Is NOT Motivated (drop it)

Ask before adding any animation: "what does this communicate?"

```
Valid    : hierarchy (draws attention to the right thing)
Valid    : storytelling (reveals content matching a narrative sequence)
Valid    : feedback (acknowledges a user action)
Valid    : state transition (shows something changed)
Invalid  : "it looked cool"
```

GSAP everywhere because GSAP is available is amateur. Each ScrollTrigger,
each marquee, each pinned section needs a one-sentence reason or it gets cut.
