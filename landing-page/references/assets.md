# Assets Reference — Images, Mockups & Illustration Strategy
*Cross-style. Read before generating any visual asset (hero image, UI mockup,
product photo, illustration).*

---

## Execution Order (mandatory)

```
1. BUILD with placeholders filled in immediately — every image slot on the
   page ships with a real, rendered fallback (SVG illustration, picsum photo,
   styled initials avatar, or hand-built UI mockup). NEVER leave an empty
   slot, a broken link, or a "[image here]" comment. The page must look
   complete and presentable the moment it's delivered.

2. DELIVER the page. Do not append image-gen prompts unprompted at this stage.

3. ASK, once, after delivery: offer the upgrade path in one short line, e.g.
   "Want me to generate prompts for real photography to replace the
   placeholders?" — then WAIT for a yes before producing any prompt.

4. ONLY AFTER explicit confirmation, output the prompt template(s) for the
   specific slots the user wants upgraded (all of them, or just the hero,
   whichever they specify).
```

This mirrors how the mobile and dashboard skills handle assets: ship something
real-looking first, treat photoreal generation as an opt-in upgrade, never a
blocking step.

---

## Priority Order (for what fills the placeholder)

```
1. SVG inline generation    → decorative graphics, icons, line-art illustration,
                              backgrounds, the isometric/diagram motifs named
                              in style files (radial node diagram, globe graphic,
                              gauge widget, topographic texture)
2. Smart placeholder         → product photos, people, real-world scenes that
                              can't be represented as clean SVG
3. Image gen prompt template → upgrade path when the user wants real-feeling
                              generated photography (GPT Image, Midjourney, Veo)
```

Never default straight to a generic gray box or a broken Unsplash link. Every
visual slot on the page should have an intentional fallback even before final
assets exist.

---

## 1. SVG Inline Generation (build this directly in code)

Use for anything that's fundamentally a diagram, icon, or abstract graphic
rather than a photograph. This is zero-dependency and renders immediately.

**What qualifies for SVG:**
```
- Score/gauge widgets (TECHNICAL style)             → arc + number, pure SVG
- Network/integration node diagrams (TECHNICAL)       → circles + connector lines
- Globe/world connection graphics (INFRA)          → wireframe sphere + arc paths
- Isometric line-art motifs (TECHNICAL)                 → folded-box/accordion shapes
- Topographic/mountain silhouette textures (INFRA)   → layered path silhouettes
- Sketch/wireframe transition illustrations (SERVICE)      → outline-only 3D-ish renders
- Icon badges, feature icons                                 → always Phosphor Icons,
                                                              never hand-rolled SVG paths
  for FUNCTIONAL icons — hand-rolled SVG is reserved ONLY for the bespoke
  diagram/texture graphics listed above, never for generic icon needs
- Decorative dot-grid or noise textures                       → CSS radial-gradient
  pattern or a single repeated SVG pattern, fixed/pointer-events-none
```

**Quality bar for hand-built SVG diagrams:** every line should connect to
something real (a feature, a data point, a logo). Never add hairline grids
or connector lines as pure decoration with no informational purpose — that's
banned under universal-rules.md.

---

## 2. Smart Placeholder (when SVG isn't appropriate)

For photography slots (hero product photo, team photo, customer photo,
testimonial avatar) where no real asset exists yet:

```
Product/scene photos  : use https://picsum.photos/seed/{descriptive-string}/{w}/{h}
                        — ALWAYS use a descriptive seed string tied to the
                        actual content ("solar-rooftop-install", "eyecare-exam-room")
                        so re-renders stay visually consistent, never a random/numeric seed

Avatar placeholders    : NEVER use a generic SVG "egg" icon or default Lucide/
                        Heroicons user silhouette — these are an instant tell.
                        Use https://picsum.photos/seed/{realistic-name}/200/200
                        cropped to a circle, OR a styled initials avatar:
                        colored circle bg (derived from the style's accent
                        palette) + 2-letter initials in the style's display font

UI screenshot mockups   : build a REAL, fully-designed mini-interface in actual
                        HTML/CSS matching the brand's exact color tokens —
                        never a vague gray-box "fake dashboard." If the
                        product genuinely doesn't have a UI yet, render a
                        believable one using the page's own design tokens
                        (this satisfies "real component preview" from the
                        anti-fake-screenshot rule)

Logo wall placeholders   : use real SVG logos from Simple Icons
                        (https://simpleicons.org) or devicon for known tools/
                        platforms (Zapier, WordPress, HubSpot, etc). For
                        fictional/example company logos, generate a simple
                        wordmark SVG (text in a distinct weight + a small
                        geometric mark), never a plain text string pretending
                        to be a logo
```

---

## 3. Image Generation Prompt Templates (ONLY after user confirms the upgrade)

Do not produce these unless the user has explicitly said yes to the offer in
Step 3 of the Execution Order above. When confirmed, output a ready-to-use
prompt per requested slot, matched to the picked landing page style:

**SERVICE style prompt template:**
```
"[Subject: e.g. modern house with rooftop solar panels / medical clinic
 examination room], photorealistic, natural daylight, [accent color] sky
 or color grading, professional architectural/medical photography style,
 clean composition, shot on full-frame camera, shallow depth of field,
 trustworthy and approachable mood, no people looking at camera unless
 specified, 16:9 or 4:3 aspect ratio"
```

**WARM-SAAS style prompt template:**
```
"[Subject: e.g. person working on laptop in bright modern workspace],
 warm golden-hour lighting, soft peach/coral color cast, candid lifestyle
 photography style, shallow depth of field, genuine smile or focused
 expression, modern minimal interior, shot on 35mm, 4:5 or 1:1 aspect ratio"
```

**INFRA style prompt template:**
```
"[Subject: e.g. laptop or phone displaying app interface on dark textured
 surface like stone or concrete], dramatic low-key lighting, single accent
 color rim light in teal/mint, dark moody atmosphere, product photography
 style, sharp focus on device screen, 16:9 aspect ratio"
```

**CREATIVE-AI style prompt template:**
```
"[Subject: stylized portrait or creative scene], vibrant saturated colors,
 violet-to-cyan gradient lighting, digital art / AI-generated aesthetic,
 high contrast, dramatic, painterly or hyperreal finish, square or 4:5
 aspect ratio, varied art style per image to show range"
```

**CONVERSION style prompt template:**
```
"[Subject: e.g. product flatlay like skincare or e-commerce goods], clean
 bright studio lighting, minimal styled props, soft shadows, editorial
 product photography style, neutral or teal-tinted background, 1:1 or 4:5
 aspect ratio"
```

**TECHNICAL style prompt template:**
```
"[Subject: e.g. abstract data/network visualization or workspace with
 multiple monitors showing dashboards], cool blue color grading, clean
 modern tech-editorial photography style, sharp focus, professional
 B2B SaaS marketing aesthetic, 16:9 aspect ratio"
```

When outputting a prompt, append the target tool's note:
```
For GPT Image / Midjourney: paste the prompt directly.
For Veo (if animated hero is needed): add motion direction, e.g.
  "slow push-in, 4 second loop, no camera shake"
```

---

## Asset Checklist (run alongside the main pre-flight check)

```
□ Every image slot ships with a real, rendered placeholder — zero empty slots,
  zero "[image here]" comments, zero broken links
□ No generic gray-box placeholders shipped without intent (SVG, picsum, or
  styled avatar used instead)
□ No broken Unsplash links — picsum.photos with descriptive seeds, or generated
□ No SVG "egg" or default user-icon avatars
□ UI mockups are fully designed in the page's own tokens, not vague gray boxes
□ Logo wall uses real SVG logos (Simple Icons/devicon) or generated wordmarks
□ Hand-rolled SVG reserved for diagrams/textures only, never generic icons
  (Phosphor Icons for all functional icon needs)
□ Image-gen prompts were NOT produced unless the user explicitly confirmed
  the upgrade offer first
□ If prompts were confirmed and produced, they match the picked style's
  visual language
```
