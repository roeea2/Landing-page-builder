# Landing Page Builder — Claude Code Skill

A Claude Code slash command skill that generates stunning, conversion-focused landing pages through a guided intake process — with full Hebrew/RTL support and Emil Kowalski design engineering standards baked in.

---

## 🇮🇱 עברית

### מה זה?

**Landing Page Builder** הוא skill ל-Claude Code שמייצר עמודי נחיתה מקצועיים ומכווני המרה — בעברית ובאנגלית. הוא מנחה אותך שאלה-שאלה, ואז בונה קובץ HTML מלא, self-contained, שאפשר לפתוח בדפדפן ישר ולראות תוצאה מוכנה.

### תכונות עיקריות

- **תהליך intake מובנה** — שאלות אחת בכל פעם (נושא, קהל יעד, שפה, עיצוב ייחוס)
- **תמיכה מלאה בעברית RTL** — Heebo font, כיוון נכון, כפתורים ופריסה מושלמת
- **עיצוב ברמת Emil Kowalski** — Custom easing, hover guards, scroll reveals, reduced-motion
- **מכוון המרה** — Hero, social proof, CTA, עדויות — הכל עם קופי אמיתי

### התקנה

1. העתק את `generate-landing-page.md` לתיקייה:
   ```
   ~/.claude/commands/
   ```
2. הפעל Claude Code ורשום:
   ```
   /generate-landing-page
   ```
3. עקוב אחרי ה-intake — הקובץ `landing-page.html` יווצר בתיקייה הנוכחית.

### שלבי התהליך

| שלב | תיאור |
|-----|--------|
| **Intake** | 4 שאלות: נושא, קהל יעד, שפה, ייחוס ויזואלי |
| **Design Direction** | Claude בוחר אסתטיקה ספציפית, לא תבנית גנרית |
| **Build** | קובץ HTML מלא, self-contained, עם CSS ו-JS inline |

---

## 🇬🇧 English

### What is this?

**Landing Page Builder** is a Claude Code slash command skill that generates professional, conversion-focused landing pages through a structured intake process. It guides you question-by-question, then outputs a single self-contained HTML file — ready to open in a browser immediately.

### Features

- **Structured intake** — one question at a time (subject, audience, language, visual reference)
- **Full Hebrew / RTL support** — Heebo font, correct layout flow, RTL-safe components
- **Emil Kowalski design standards** — custom easing curves, touch-safe hovers, scroll reveals, `prefers-reduced-motion`
- **Conversion-focused** — real copy, specific CTAs, personas-matched value props

### Installation

1. Copy `generate-landing-page.md` into your Claude commands folder:
   ```
   ~/.claude/commands/
   ```
2. Open Claude Code and type:
   ```
   /generate-landing-page
   ```
3. Answer the 4 intake questions — your `landing-page.html` will be generated in the current directory.

### How It Works

| Phase | Description |
|-------|-------------|
| **Phase 1 — Intake** | Subject, target market, language (Hebrew/English), optional reference image |
| **Phase 2 — Design Direction** | Claude commits to a bold, specific aesthetic before writing any code |
| **Phase 3 — Build** | Single self-contained HTML file with all CSS and JS inline |

### Design Standards Applied

Every generated page follows Emil Kowalski's design engineering philosophy:

| Standard | Implementation |
|----------|---------------|
| Custom easing | `cubic-bezier(0.23, 1, 0.32, 1)` on all transitions |
| Touch-safe hover | `@media (hover: hover) and (pointer: fine)` guards |
| Scroll reveals | `IntersectionObserver` with per-sibling stagger delay |
| Reduced motion | All animations disabled via `prefers-reduced-motion: reduce` |
| No `transition: all` | Every animated property explicitly listed |
| Press feedback | `scale(0.97)` `:active` on all buttons |
| Type scaling | `clamp()` for fluid responsive headlines |
| Hebrew fonts | Heebo, Rubik, or Assistant — never system fonts |

### Output Example

The skill produces pages with these sections (adapted per product):

1. **Hero** — Bold headline + subheadline + primary CTA
2. **For Who** — Persona cards speaking directly to the target audience
3. **Curriculum / Features** — What's included, explained concisely
4. **Social Proof** — Testimonials with names, roles, and specific outcomes
5. **How It Works** — 3-step visual process
6. **Final CTA** — Urgency-driven second conversion moment
7. **Footer** — Minimal, on-brand

---

## File Structure

```
generate-landing-page.md   ← The skill / slash command definition
README.md                  ← This file
```

## Requirements

- [Claude Code](https://claude.ai/code) CLI or desktop app
- No other dependencies

---

*Skill built with [Claude Code](https://claude.ai/code) · Design standards from [Emil Kowalski](https://animations.dev/)*
