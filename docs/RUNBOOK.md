<p align="left"><a href="#runbook--orbit-ilcom-english">English</a> · <b>עברית</b></p>

# ספר-הפעלה · orbit-il.com

כל מה שכאן נגזר מקובץ ה-workflow ‏[`deploy.yml`](../.github/workflows/deploy.yml) ונבדק מול האתר החי ב-6.11.2026. שלבי ה-workflow ‏`Build Orbit from maor-system`, לפי הסדר:

```
checkout maor-system@main → Node 22 → npm ci → npm run build → CNAME + .nojekyll → git push -f gh-pages
```

**ניווט:** [הרצה ידנית](#הרצה-ידנית) · [אימות](#אימות) · [אבחון כשל](#אבחון-כשל) · [האתר לא התעדכן](#הריצה-ירוקה-והאתר-ישן) · [חזרה לאחור](#חזרה-לאחור)

## הרצה ידנית

1. נכנסים ל-[Actions ← Build Orbit from maor-system](https://github.com/meir7651231-ui/orbit-il/actions/workflows/deploy.yml), לוחצים **Run workflow**, בוחרים ענף `main` ולוחצים שוב **Run workflow**.
2. הריצה בונה תמיד את `maor-system@main` — אי אפשר לבחור ענף או commit אחר.
3. אחריה רצה אוטומטית ריצת `pages build and deployment` (כדקה).

דרך חלופית: רשומה חדשה ב-[`DEPLOY-LOG.md`](../DEPLOY-LOG.md) ודחיפה ל-`main` כאן — מפעיל את אותו workflow.

## אימות

```console
$ curl -s "https://orbit-il.com/version.json?t=$(date +%s)"
{"id":"2026-11-06T10:02:48.801Z"}
```

השדה `id` הוא זמן הבנייה ב-UTC. אם הוא מאוחר מתחילת הריצה — הפריסה חיה.

## אבחון כשל

פותחים את הריצה האדומה ב-Actions ומסתכלים איזה שלב נכשל:

| שלב שנכשל | סיבה סבירה | מה עושים |
|---|---|---|
| `Checkout maor-system` | אין גישה ל-`meir7651231-ui/maor-system` (ה-workflow מושך אותו עם הטוקן המובנה; למשל אם הריפו הפך לפרטי) | לבדוק נראות והרשאות של `maor-system`. שינוי ב-workflow — רק באישור הבעלים |
| `actions/setup-node` | תקלה זמנית ב-GitHub | Re-run |
| `npm ci` | `package-lock.json` לא תואם ל-`package.json` ב-`maor-system` | לתקן ב-`maor-system`, ואז הרצה ידנית |
| `npm run build` | שגיאת בנייה ב-`maor-system@main` | לתקן ב-`maor-system` (שם יש בדיקות), ואז הרצה ידנית |
| `CNAME + deploy` | הדחיפה ל-`gh-pages` נדחתה (הרשאת `contents: write`, הגנת-ענף על `gh-pages`) | לבדוק הגדרות הריפו — רק באישור הבעלים |
| `pages build and deployment` | תקלה בצד GitHub Pages | Re-run לריצה הזאת |

> כשל בכל שלב **לא פוגע באתר החי**: `gh-pages` מתעדכן רק בשלב האחרון, אחרי בנייה מוצלחת.

## הריצה ירוקה והאתר ישן

1. ייתכן שריצת `pages build and deployment` עוד רצה — מחכים כדקה.
2. מטמון: השרת מחזיר `cache-control: max-age=600` — עד 10 דקות. בודקים עם `?t=` כמו למעלה.
3. האפליקציה היא PWA עם `sw.js` — הדפדפן יכול להחזיק עותק שמור. רענון קשיח או סגירה ופתיחה של האפליקציה.

## חזרה לאחור

- **הענף `gh-pages` לא שומר היסטוריה.** כל ריצה עושה `git init` חדש ו-`push -f`, כך שבענף יש תמיד commit אחד (`deploy orbit`). אין למה לחזור בו.
- **הדרך היחידה בלי לשנות את ה-workflow:** `git revert` לשינוי הבעייתי ב-`maor-system@main`, ואז [הרצה ידנית](#הרצה-ידנית). האתר חוזר תוך 2–3 דקות.
- בנייה ישירה מ-commit ישן דורשת שינוי ב-workflow (קלט `ref`) — לא קיים היום, ורק באישור הבעלים.

---


# Runbook · orbit-il.com (English)

Everything here is derived from [`.github/workflows/deploy.yml`](../.github/workflows/deploy.yml) and checked against the live site on 2026-11-06. The workflow, `Build Orbit from maor-system`: checkout `maor-system@main` → Node 22 → `npm ci` → `npm run build` → `CNAME` + `.nojekyll` → `git push -f` to `gh-pages`.

**Jump to:** [Manual run](#manual-run) · [Verify](#verify) · [Diagnose a failure](#diagnose-a-failure) · [Green run, old site](#green-run-old-site) · [Rollback](#rollback)

## Manual run

1. [Actions → Build Orbit from maor-system](https://github.com/meir7651231-ui/orbit-il/actions/workflows/deploy.yml) → **Run workflow** → branch `main` → **Run workflow**.
2. The run always builds `maor-system@main` — there is no branch or commit choice.
3. `pages build and deployment` follows automatically (about a minute).

Alternative: add an entry to [`DEPLOY-LOG.md`](../DEPLOY-LOG.md) and push to `main` here — it starts the same workflow.

## Verify

```console
$ curl -s "https://orbit-il.com/version.json?t=$(date +%s)"
{"id":"2026-11-06T10:02:48.801Z"}
```

`id` is the build time in UTC. Later than the run's start means the deploy is live.

## Diagnose a failure

Open the red run in Actions and find the failed step:

| Failed step | Likely cause | What to do |
|---|---|---|
| `Checkout maor-system` | no access to `meir7651231-ui/maor-system` (the workflow pulls it with the built-in token; e.g. the repo became private) | check `maor-system`'s visibility and permissions. Workflow changes — owner approval only |
| `actions/setup-node` | transient GitHub issue | Re-run |
| `npm ci` | `package-lock.json` out of sync with `package.json` in `maor-system` | fix in `maor-system`, then a manual run |
| `npm run build` | build error on `maor-system@main` | fix in `maor-system` (its tests live there), then a manual run |
| `CNAME + deploy` | the push to `gh-pages` was refused (`contents: write`, branch protection on `gh-pages`) | check repo settings — owner approval only |
| `pages build and deployment` | GitHub Pages side issue | Re-run that run |

> A failure at any step **does not affect the live site**: `gh-pages` is only updated in the last step, after a successful build.

## Green run, old site

1. `pages build and deployment` is still running — wait about a minute.
2. Cache: the server sends `cache-control: max-age=600` — up to 10 minutes. Check with `?t=` as above.
3. The app is a PWA with `sw.js` — the browser may hold a cached copy. Hard-refresh, or close and reopen the app.

## Rollback

- **`gh-pages` keeps no history.** Every run does a fresh `git init` and `push -f`, so the branch always holds one commit (`deploy orbit`). There is nothing to roll back to there.
- **The only path without changing the workflow:** `git revert` the bad change on `maor-system@main`, then a [manual run](#manual-run). The site is back in 2–3 minutes.
- Building an older commit directly needs a workflow change (a `ref` input) — it does not exist today, and is owner-approval only.
