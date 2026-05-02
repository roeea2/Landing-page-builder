# Landing Page Builder — Claude Code Skills

Two composable Claude Code skills for generating production-grade, conversion-focused landing pages. `generate-landing-page` handles the full build process; `emil-design-eng` is its design foundation — a standalone skill encoding Emil Kowalski's UI engineering philosophy.

---

## 🇮🇱 עברית

### מה יש פה?

שני skills ל-Claude Code:

| Skill | תפקיד |
|-------|--------|
| [`generate-landing-page`](skills/generate-landing-page/SKILL.md) | מנחה אותך שאלה-שאלה ובונה עמוד נחיתה מלא |
| [`emil-design-eng`](skills/emil-design-eng/SKILL.md) | כל עקרונות העיצוב — animations, easing, hover states, accessibility |

`generate-landing-page` **מסתמך על** `emil-design-eng` — הוא מפנה אליו לכל החלטת עיצוב ומריץ את ה-checklist שלו על הקוד לפני הפלט.

### התקנה

העתק את שני ה-skills לתיקיית הפקודות שלך:

```bash
cp skills/generate-landing-page/SKILL.md ~/.claude/commands/generate-landing-page.md
cp skills/emil-design-eng/SKILL.md ~/.claude/commands/emil-design-eng.md
```

### שימוש

```
/generate-landing-page
```

ענה על 4 שאלות (נושא, קהל יעד, שפה, ייחוס ויזואלי) — הקובץ `landing-page.html` יווצר ישר.

לסקירת עיצוב בלי בנייה:
```
/emil-design-eng
```

### מה שנבנה

- תמיכה מלאה בעברית RTL — Heebo font, כיוון נכון, כל ה-UI בעברית
- 6 סקשנים: Hero, Value Prop, Social Proof, Features, CTA, Footer
- HTML self-contained אחד — אפשר לפרוס ב-Vercel / Netlify / GitHub Pages ישר

---

## 🇬🇧 English

### What's in this repo?

Two composable Claude Code skills:

| Skill | Role |
|-------|------|
| [`generate-landing-page`](skills/generate-landing-page/SKILL.md) | Guided intake → full landing page build |
| [`emil-design-eng`](skills/emil-design-eng/SKILL.md) | Design foundation — animations, easing, hover, accessibility |

`generate-landing-page` **depends on** `emil-design-eng`. It explicitly references it for all design decisions and runs the full Emil checklist on generated code before output.

### Installation

Copy both skills into your Claude commands folder:

```bash
cp skills/generate-landing-page/SKILL.md ~/.claude/commands/generate-landing-page.md
cp skills/emil-design-eng/SKILL.md ~/.claude/commands/emil-design-eng.md
```

### Usage

**Generate a landing page:**
```
/generate-landing-page
```

Answer 4 intake questions (subject, target market, language, visual reference) and receive a ready-to-open `landing-page.html`.

**Design review only:**
```
/emil-design-eng
```

Use this skill standalone to review any UI code against Emil Kowalski's principles — returns a Before/After table of issues found.

### How the skills relate

```
generate-landing-page
        │
        └── depends on ──▶  emil-design-eng
                             (animation framework, easing curves,
                              hover guards, review checklist)
```

`generate-landing-page` references `emil-design-eng` inline and instructs Claude to run its review checklist on every generated page. You can use `emil-design-eng` independently for any other UI work.

### What gets built

- Single self-contained HTML file — inline CSS and JS, one Google Fonts `<link>`
- Full Hebrew RTL support — Heebo font, correct layout flow, fluent Hebrew copy
- 6 sections: Hero, Value Proposition, Social Proof, Features, How It Works, CTA + Footer
- Deploy-ready: static file works on Vercel, Netlify, GitHub Pages, or any CDN

### Design standards enforced

| Standard | Rule |
|----------|------|
| Easing | `cubic-bezier(0.23, 1, 0.32, 1)` — no built-in `ease` on motion |
| Hover | `@media (hover: hover) and (pointer: fine)` guard on all hover effects |
| Transitions | No `transition: all` — every property listed explicitly |
| Entry animations | `opacity` + `translateY` from non-zero start — never `scale(0)` |
| Scroll reveals | `IntersectionObserver` + per-sibling stagger (30–80ms) |
| Reduced motion | Full `prefers-reduced-motion` block disabling transform-based motion |
| Press feedback | `scale(0.97)` on `:active` for every button |
| Typography | `clamp()` for fluid scaling — never fixed `px` font sizes on headings |

---

## Repo Structure

```
landing-page-builder/
├── README.md
└── skills/
    ├── generate-landing-page/
    │   └── SKILL.md          ← landing page builder (references emil-design-eng)
    └── emil-design-eng/
        └── SKILL.md          ← design engineering foundation (standalone)
```

## Requirements

- [Claude Code](https://claude.ai/code) CLI or desktop app
- No other dependencies

---

*Skills built with [Claude Code](https://claude.ai/code) · Design principles from [Emil Kowalski](https://animations.dev/)*
