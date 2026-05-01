# Claude Code IL — Landing Page Builder

> AI-generated, conversion-focused landing pages using Claude Code + Emil Kowalski design principles.

---

## 🇮🇱 עברית

### מה זה?

**Claude Code IL Landing Page Builder** הוא כלי שיוצר עמודי נחיתה מקצועיים ומכווני המרה בעברית ובאנגלית — בעזרת Claude Code ועקרונות העיצוב של Emil Kowalski.

כל עמוד נחיתה שנוצר:
- **מותאם RTL מלא** — כולל Heebo font, כיוון נכון, ופריסה עברית מושלמת
- **מכוון המרה** — hero, social proof, CTA, ועדויות אמיתיות
- **עיצוב ברמת production** — Custom easing, animations מדויקות, hover states נכונים
- **Responsive מלא** — 375px עד 1440px

### שימוש

1. פתח `landing-page.html` בדפדפן
2. ערוך את התוכן לפי הצורך
3. שנה את הצבעים ב-CSS Custom Properties (`:root`)
4. deploy על כל hosting סטטי (Vercel, Netlify, GitHub Pages)

### מה כלול

```
landing-page.html   ← עמוד נחיתה מלא, self-contained
README.md           ← תיעוד זה
```

### סטנדרטי עיצוב

הדף בנוי לפי עקרונות **Emil Kowalski Design Engineering**:

| עיקרון | יישום |
|--------|-------|
| Custom easing curves | `cubic-bezier(0.23, 1, 0.32, 1)` על כל transition |
| Hover guards | `@media (hover: hover) and (pointer: fine)` |
| Scroll reveals | `IntersectionObserver` עם stagger delay |
| `prefers-reduced-motion` | ביטול אנימציות לפי הגדרת המשתמש |
| אין `transition: all` | כל property מפורט בנפרד |
| `:active` feedback | `scale(0.97)` על כל כפתור |

---

## 🇬🇧 English

### What is this?

**Claude Code IL Landing Page Builder** generates professional, conversion-focused landing pages in Hebrew and English — powered by Claude Code and Emil Kowalski's design engineering philosophy.

Every generated page is:
- **Fully RTL-ready** — Hebrew Heebo font, correct directionality, proper layout flow
- **Conversion-focused** — Hero, value prop, social proof, CTA, and testimonials
- **Production-grade design** — Custom easing curves, precise animations, correct hover states
- **Fully responsive** — 375px to 1440px

### Usage

1. Open `landing-page.html` in a browser
2. Edit content to match your product
3. Adjust colors via CSS Custom Properties in `:root`
4. Deploy to any static host (Vercel, Netlify, GitHub Pages)

### What's included

```
landing-page.html   ← Full, self-contained landing page
README.md           ← This file
```

### Design Standards Applied

Built to [Emil Kowalski](https://animations.dev/) Design Engineering standards:

| Principle | Implementation |
|-----------|---------------|
| Custom easing curves | `cubic-bezier(0.23, 1, 0.32, 1)` on all transitions |
| Touch-safe hover states | `@media (hover: hover) and (pointer: fine)` guards |
| Scroll-triggered reveals | `IntersectionObserver` with per-sibling stagger delay |
| Reduced motion support | Animations disabled via `prefers-reduced-motion` |
| No `transition: all` | Every animated property explicitly named |
| `:active` press feedback | `scale(0.97)` on all interactive elements |

### Tech Stack

- Pure HTML + CSS + vanilla JS (zero dependencies)
- Google Fonts (Heebo — Hebrew-optimized geometric sans)
- `IntersectionObserver` for scroll reveals
- CSS Custom Properties for theming

### Customization

```css
:root {
  --green:    #00e87a;   /* Primary accent */
  --orange:   #ff7b3a;   /* Secondary accent */
  --bg:       #080812;   /* Page background */
  --surface:  #0e0e1c;   /* Card background */
  --text:     #eeeef6;   /* Primary text */
  --text-2:   #7878a0;   /* Secondary text */
}
```

---

## License

MIT — use freely, attribution appreciated.

---

*Built with [Claude Code](https://claude.ai/code) · Design principles from [Emil Kowalski](https://animations.dev/)*
