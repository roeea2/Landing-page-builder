---
name: generate-landing-page
description: This skill should be used when the user asks to "generate a landing page", "create a landing page", "build a landing page", "make a landing page", or wants a marketing page for a product, service, or idea. Guides the user through a structured intake process before producing a high-quality, production-grade HTML landing page.
---

# Generate Landing Page

Create a stunning, conversion-focused landing page tailored to a specific product, audience, and language. This skill runs a structured intake process first, then produces a single self-contained HTML file.

> **Design standard:** All animation decisions, easing curves, hover states, interaction patterns, and UI polish in this skill are governed by the [`emil-design-eng`](../emil-design-eng/SKILL.md) skill. Before delivering any output, run the full `emil-design-eng` review checklist on the generated code. The design rules in Phase 3 below are landing-page-specific applications of those principles — not a replacement for them.

---

## Phase 1: Intake

Collect the following information from the user via a series of focused questions. Ask questions **one at a time** — do not dump all questions at once. Wait for each answer before asking the next.

### Questions (in order)

1. **Subject** — "What is your landing page about? Describe your product, service, or idea in a few sentences."

2. **Target Market** — "Who is your target audience? Give 2–3 examples of your ideal customer (e.g., 'solo founders who sell on Etsy', 'parents of toddlers in Tel Aviv', 'B2B SaaS teams scaling past 50 people')."

3. **Language** — "Should the landing page be in Hebrew or English?" (If Hebrew: the page must be RTL, use `dir="rtl"`, and all copy including the UI must be in Hebrew with proper typography.)

4. **Reference Image (optional)** — "Do you have a reference image, screenshot, or style inspiration? If yes, share it now. If not, just say 'skip' and I'll design from scratch."

Once all four answers are collected, proceed to Phase 2.

---

## Phase 2: Design Direction

Before writing code, commit to a bold, specific aesthetic direction based on the subject and audience. Apply the following design thinking principles:

**Purpose**: What problem does this product solve and for whom?
**Tone**: Pick a specific aesthetic extreme that fits the audience — e.g., clinical/precision for B2B SaaS, warm/artisanal for food/craft, futuristic/bold for tech, organic/playful for children's products.
**Differentiation**: What single visual or structural choice will make this page memorable?
**Reference**: If the user provided a reference image, extract its dominant color palette, layout density, and typographic mood and incorporate them.

Avoid:
- Generic "startup" aesthetics (purple gradients, Inter, cards with drop shadows on white)
- Template-looking layouts (hero → features → CTA → footer is the floor, not the ceiling)
- Identical design across different generations

---

## Phase 3: Build the Landing Page

Produce a **single self-contained HTML file** that includes all CSS and JS inline. No external dependencies except Google Fonts (which may be loaded via `<link>`).

### Required Sections (adapt creatively, don't be mechanical)

1. **Hero** — Bold headline, subheadline, primary CTA. This is 80% of the page's job.
2. **Value Proposition** — 3–5 reasons why this product/service is worth attention. Not generic. Speak directly to the target personas named by the user.
3. **Social Proof** — Testimonials, numbers, logos, or a "who uses this" section. Use realistic placeholder names if not provided.
4. **How It Works / Features** — Brief, visual explanation of what the product does.
5. **CTA Section** — Final conversion moment. Different from the hero CTA — create urgency or specificity here.
6. **Footer** — Minimal. Brand name, optional links.

---

### Typography

- Choose a distinctive, characterful font pairing from Google Fonts. Display font for headlines, refined serif or geometric sans for body.
- **Never use Inter, Roboto, Arial, or system fonts as the primary font.**
- Scale type with intention: dramatic headline sizes (`clamp()`-based for responsiveness), tight leading, generous tracking on headlines.

### Color

- Commit to a palette. One dominant color, one accent, carefully controlled neutrals.
- Use CSS custom properties (`--color-primary`, `--color-accent`, etc.) throughout.
- Dominant + sharp accent beats timid evenly-distributed palette every time.

### Motion

> See [`emil-design-eng`](../emil-design-eng/SKILL.md) for the full animation decision framework. Summary for landing pages:

- **Hero load**: staggered `fadeUp` with `animation-delay` for each element — orchestrated reveal, not simultaneous appearance.
- **Scroll reveals**: `IntersectionObserver` with per-sibling stagger delay (30–80ms between items). Transition: `opacity` + `translateY(24px)` → `translateY(0)`, `500ms`, `cubic-bezier(0.23, 1, 0.32, 1)`.
- **Cards**: `translateY(-4px)` on hover, guarded with `@media (hover: hover) and (pointer: fine)`.
- **Buttons**: `scale(0.97)` on `:active`. `translateY(-2px)` + box-shadow on hover. Transition: `150ms cubic-bezier(0.23, 1, 0.32, 1)` — never `transition: all`.
- **No `ease-in`** anywhere. Use `ease-out` (custom cubic-bezier) for entries, `ease` for color/opacity only.
- **`prefers-reduced-motion`**: disable all transform-based animations.

### Spatial Composition

- Break the grid at least once — overlapping elements, diagonal sections, or full-bleed edge-to-edge blocks.
- Use generous whitespace in premium zones (hero), controlled density in feature zones.
- Avoid the cookie-cutter 3-column feature card layout unless it's earning its place.

### Backgrounds & Texture

- Create atmosphere — gradient meshes, subtle noise texture (SVG or CSS), geometric line patterns, or layered transparencies.
- Sections should feel distinct from each other, not uniform white boxes.

### Details That Compound

- Custom `::selection` color matching the brand
- `scroll-behavior: smooth`
- Focus styles that are visible and on-brand
- Button `cursor: pointer`
- Images use `loading="lazy"`
- Placeholder images use subtle on-brand gradients, never gray boxes

### Hebrew-Specific Requirements

If the user chose Hebrew:
- `<html dir="rtl" lang="he">`
- All text must be in fluent, natural Hebrew — not literal translation
- Use a Hebrew-compatible Google Font (Heebo, Rubik, Assistant, or Noto Sans Hebrew)
- RTL layout: flexbox and grid directions correct for RTL
- CTA buttons, navigation, and icon placement must respect RTL flow
- Avoid left-aligned decorative elements that break RTL visual balance

### Responsiveness

- Mobile-first. Must look correct at 375px and 1440px.
- CSS Grid and Flexbox only. No fixed pixel widths on containers.
- Typography uses `clamp()` for fluid scaling.
- Touch targets minimum 44×44px.

### Conversion Focus

Every section must push toward the primary CTA:
- Headline addresses a pain point or desire, not just a product name.
- CTA button copy is specific and active ("Start My Free Trial") not generic ("Submit").
- Value proposition speaks to the exact personas the user described.
- Social proof is specific: names, roles, and measurable outcomes.

---

## Output

Deliver:
1. A brief (3–5 sentence) explanation of your design direction and key aesthetic choices.
2. The complete, self-contained `landing-page.html` file.

The file must be ready to open in a browser immediately. No placeholders — fill everything with on-brand copy that fits the user's product and audience.

After delivering the file, offer to refine any section, swap the color palette, adjust the copy tone, or add/remove sections.
