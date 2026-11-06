# Security · אבטחה

## מה יש כאן ומה אין

- הריפו **לא מכיל קוד-מוצר, נתוני-לקוחות או סודות**. הוא מכיל workflow אחד שבונה את `maor-system` ומפרסם קבצים סטטיים.
- ה-workflow משתמש **רק ב-`GITHUB_TOKEN`** האוטומטי של GitHub Actions, בהרשאת `contents: write` — כדי לדחוף לענף `gh-pages` של הריפו הזה. אין בו סודות נוספים.
- כל מה שבענף `gh-pages` **ציבורי** — זה האתר החי. אסור שיגיע לבנייה (`dist/`) מפתח, טוקן או קובץ `.env`. הגנה על זה נמצאת בריפו `maor-system`, שממנו נבנה האתר.
- `CNAME` נכתב בכל ריצה ל-`orbit-il.com`. שינוי שלו, או של הגדרות Pages, עלול להפנות את הדומיין למקום אחר — רק באישור הבעלים.

## מי יכול להפעיל פריסה

כל מי שיכול לדחוף ל-`main` או להריץ workflow בריפו הזה מפעיל בנייה ופריסה של האתר החי. לכן: עבודה בענפים ו-PR, ומיזוג ל-`main` רק באישור הבעלים.

## דיווח על בעיית אבטחה

אל תפתחו issue ציבורי. דווחו באופן פרטי לבעלי הריפו דרך GitHub (**Security → Report a vulnerability**, אם מופעל), עם תיאור, צעדים לשחזור והשפעה.

---

## In English

- No product code, customer data or secrets live here — one workflow that builds `maor-system` and publishes static files.
- The workflow uses only the built-in `GITHUB_TOKEN` with `contents: write`, to push this repo's `gh-pages` branch. No other secrets.
- Everything on `gh-pages` is **public** (it is the live site). Keys, tokens and `.env` files must never reach the build output; that is guarded in `maor-system`.
- `CNAME` is rewritten to `orbit-il.com` on every run; changing it or the Pages settings can point the domain elsewhere — owner approval only.
- Anyone who can push to `main` or run the workflow deploys the live site: branches + PRs, owner-approved merges.

**Reporting:** please don't open a public issue. Report privately to the repo owner through GitHub (**Security → Report a vulnerability**, if enabled) with a description, steps to reproduce and impact.
