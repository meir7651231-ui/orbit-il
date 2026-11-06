<p align="left"><a href="#contributing-english">English</a> · <b>עברית</b></p>

# תרומה לריפו

הריפו הזה **מגיש את האתר החי orbit-il.com**. כל מיזוג ל-`main` — גם של תיעוד — מפעיל בנייה ופריסה מחדש מ-`maor-system@main`.

## איפה משנים מה

| רוצים לשנות… | איפה |
|---|---|
| משהו באתר / באפליקציה | בריפו `maor-system`, לא כאן |
| תיעוד, איורים, תבניות | כאן — ענף + PR |
| ה-workflow, `CNAME`, הגדרות Pages | רק באישור מפורש של הבעלים |

## הכללים

1. עובדים בענף, פותחים PR (עדיף טיוטה). **אף פעם לא דוחפים ישירות ל-`main`.**
2. לא נוגעים ב-`.github/workflows/`, ב-`CNAME`, בענף `gh-pages` — ולא מוחקים מ-`DEPLOY-LOG.md` (רק מוסיפים).
3. ב-PR: מה השתנה, ו-`git diff --name-status main` שמראה שאין נגיעה בקבצי-הפריסה.
4. מיזוג — רק באישור הבעלים, ורק כשזה בסדר שיעלה לאוויר מה שיש עכשיו ב-`maor-system@main`.
5. אחרי מיזוג: [אימות](docs/RUNBOOK.md#אימות) ב-`version.json`.

תמונות ≤ 500KB, לכל תמונה `alt`, ו-README בעברית ובאנגלית מתעדכנים יחד.

---


# Contributing (English)

This repo **serves the live site orbit-il.com**. Every merge to `main` — documentation included — rebuilds and redeploys from `maor-system@main`.

## What changes where

| You want to change… | Where |
|---|---|
| something on the site / in the app | in `maor-system`, not here |
| docs, illustrations, templates | here — branch + PR |
| the workflow, `CNAME`, Pages settings | only with the owner's explicit approval |

## Rules

1. Work on a branch and open a PR (draft preferred). **Never push straight to `main`.**
2. Don't touch `.github/workflows/`, `CNAME` or the `gh-pages` branch — and never remove from `DEPLOY-LOG.md` (append only).
3. In the PR: what changed, plus `git diff --name-status main` showing no deploy file was touched.
4. Merge — owner approval only, and only when it's fine for the current `maor-system@main` to go live.
5. After a merge: [verify](docs/RUNBOOK.md#verify) with `version.json`.

Images ≤ 500KB, every image has `alt`, and the Hebrew and English READMEs are updated together.
