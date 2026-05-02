<div dir="rtl">

# בונה עמודי נחיתה — Skills ל-Claude Code

> עמוד נחיתה מקצועי, מכוון המרה, בעברית מלאה — תוך דקות. עם עקרונות העיצוב של Emil Kowalski.

[🇬🇧 English version](README.md)

---

## מה זה?

שני skills ל-Claude Code שעובדים יחד:

**[`generate-landing-page`](skills/generate-landing-page/SKILL.md)** — מנחה אותך בארבע שאלות ואז בונה קובץ HTML מלא, self-contained, שאפשר לפתוח בדפדפן ולראות תוצאה מוכנה לפרסום.

**[`emil-design-eng`](skills/emil-design-eng/SKILL.md)** — ה-skill של עיצוב שעומד מאחורי הכל. מכיל את כל עקרונות ה-UI של Emil Kowalski: easing curves, hover states, animations, accessibility. `generate-landing-page` מסתמך עליו ומריץ את ה-checklist שלו על כל קוד לפני שהוא מוסר אותך.

```
generate-landing-page
        │
        └── מסתמך על ──▶  emil-design-eng
                           (easing, animations, hover guards, checklist)
```

אפשר להשתמש ב-`emil-design-eng` גם לבד — לסקירת כל קוד UI.

---

## התקנה

שכפל את הריפו והעתק את שני ה-skills לתיקיית הפקודות:

```bash
git clone https://github.com/roeea2/Landing-page-builder.git
cd Landing-page-builder

cp skills/generate-landing-page/SKILL.md ~/.claude/commands/generate-landing-page.md
cp skills/emil-design-eng/SKILL.md ~/.claude/commands/emil-design-eng.md
```

זהו. פתח Claude Code ותוכל להריץ:

```
/generate-landing-page
```

---

## שימוש

### בניית עמוד נחיתה

```
/generate-landing-page
```

ה-skill ישאל אותך ארבע שאלות, אחת בכל פעם:

| שאלה | לדוגמה |
|------|---------|
| על מה העמוד? | "קורס Claude Code למפתחים מתחילים" |
| מי קהל היעד? | "מפתחים, מנהלי מוצר, פרילנסרים" |
| עברית או אנגלית? | עברית |
| יש עיצוב ייחוס? | תמונה / skip |

אחרי ארבע שאלות — קובץ `landing-page.html` מוכן.

### סקירת עיצוב בלבד

```
/emil-design-eng
```

תן לו קוד CSS/HTML — יחזיר טבלת Before/After עם כל הבעיות שמצא לפי עקרונות Emil Kowalski.

---

## מה מקבלים

עמוד נחיתה עם שישה סקשנים (מותאם לפי המוצר):

| סקשן | תפקיד |
|------|--------|
| **Hero** | כותרת, כותרת משנה, CTA ראשי |
| **For Who** | כרטיסי פרסונות שמדברות ישר לקהל היעד |
| **Features** | מה כלול, בשפה ישירה |
| **Social Proof** | עדויות עם שם, תפקיד, ותוצאה מדידה |
| **How It Works** | תהליך ויזואלי של 3 שלבים |
| **CTA** | רגע המרה שני עם דחיפות ספציפית |

**הפלט:** קובץ HTML אחד — כל ה-CSS וה-JS בפנים. אפשר לפרוס ב-Vercel, Netlify, GitHub Pages, או כל CDN סטטי.

---

## סטנדרטי עיצוב

כל עמוד שנוצר עובר את ה-checklist של `emil-design-eng` לפני הפלט:

| סטנדרט | כלל |
|---------|-----|
| **Easing** | `cubic-bezier(0.23, 1, 0.32, 1)` — לא `ease` מובנה על motion |
| **Hover** | `@media (hover: hover) and (pointer: fine)` על כל hover effect |
| **Transitions** | אין `transition: all` — כל property מפורט בנפרד |
| **כניסת אלמנטים** | `opacity` + `translateY` — לעולם לא `scale(0)` |
| **Scroll reveals** | `IntersectionObserver` עם stagger של 30–80ms בין פריטים |
| **Reduced motion** | ביטול כל motion-based animation ב-`prefers-reduced-motion` |
| **לחיצה על כפתורים** | `scale(0.97)` ב-`:active` על כל כפתור |
| **טיפוגרפיה** | `clamp()` לסקיילינג fluid — אין `px` קבוע על כותרות |

---

## מבנה הריפו

```
landing-page-builder/
├── README.md           ← English
├── README.he.md        ← עברית (זה הקובץ)
└── skills/
    ├── generate-landing-page/
    │   └── SKILL.md    ← skill הבנייה (מפנה ל-emil-design-eng)
    └── emil-design-eng/
        └── SKILL.md    ← תשתית העיצוב (אפשר להשתמש גם לבד)
```

---

## דרישות

- [Claude Code](https://claude.ai/code) — CLI, desktop app, או תוסף VS Code
- כלום אחר

---

## רישיון

MIT — חופשי לשימוש, attribution מוערך.

---

*נבנה עם [Claude Code](https://claude.ai/code) · עקרונות עיצוב מ-[Emil Kowalski](https://animations.dev/)*

</div>
