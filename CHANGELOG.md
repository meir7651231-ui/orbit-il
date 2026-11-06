# Changelog

כל השינויים הבולטים בריפו `orbit-il` מתועדים כאן. הפורמט מבוסס על [Keep a Changelog](https://keepachangelog.com/en/1.1.0/). לריפו אין גרסאות — כל פרק הוא **יום**, לפי `git log`, והשינוי ב-`### Changed` הוא מה שעלה לאוויר ב-orbit-il.com. פירוט מלא לכל פריסה: [`DEPLOY-LOG.md`](DEPLOY-LOG.md).

*All notable changes to `orbit-il` are documented here, based on [Keep a Changelog](https://keepachangelog.com/en/1.1.0/). The repo has no versions — each section is a **day** from `git log`; `### Changed` lists what went live on orbit-il.com. Full per-deploy detail: [`DEPLOY-LOG.md`](DEPLOY-LOG.md).*

## [Unreleased]

### Added

- README בעברית ובאנגלית: «נסו עכשיו», hero (כהה/בהיר עם `<picture>`), תגיות חיות (סטטוס Build Orbit, `version.json`, `gh-pages`), ניווט-עוגנים · Hebrew + English README with a "try it now" line, light/dark hero, live badges and anchor nav.
- צילום אמיתי של orbit-il.com (מחשב + נייד) — `assets/live-site.jpg` · A real desktop + mobile screenshot of orbit-il.com.
- תרשים זרימת-פריסה וציר-זמן של ריצה, כהה ובהיר — `assets/deploy-flow*.svg`, `assets/deploy-timeline*.svg` · Deploy-flow and run-timeline diagrams, dark and light.
- «אימות פריסה תוך 30 שניות», «מה הוא לא עושה», «שאלות נפוצות» · "Verify in 30 seconds", "What it does not do", FAQ.
- `docs/RUNBOOK.md` — הרצה ידנית, אבחון כשל לפי שלב, חזרה לאחור · manual run, per-step failure diagnosis, rollback.
- `CONTRIBUTING.md`, `SECURITY.md`, `.github/ISSUE_TEMPLATE/` (בעיית פריסה, תיעוד), `.github/pull_request_template.md`.

### Changed

- שורות-הטריגר הישנות מה-README עברו, מילה במילה, לסעיף מקופל בתחתית שני ה-README · The old README trigger lines are kept verbatim in a collapsed section of both READMEs.

## [2026-10-22] - 2026-10-22

### Changed

- maor-system 7f85d45 — קופות צדקה: כפתורים חסרים + תזכורות לקופה (`f5ada8b`)
- maor-system c796379 — מסך הרשמה: חנות, מסכים מתגלגלים, וואטסאפ, נגישות, סמל חדש (`bee20c2`)
- maor-system bcb2ed3 — לשונית אורביט + סמל חדש בחנות (`9732410`)
- maor-system 7bc753b — חיפוש החנות מוצא הכול (`8adc080`)
- maor-system 3a4d043 — דמו נעול + «פתחו אתר משלכם» מגיב (`fff83c4`)

## [2026-10-13] - 2026-10-13

### Changed

- build from maor-system main dfe8a30 (ביצועי טאב-התורמים שלב א׳) (`1905d1e`)
- build from maor-system main fa0df3e (רשימת-בעלים 13.10, PR #510) (`d182111`)

## [2026-10-06] - 2026-10-06

### Changed

- build from maor-system main (PR #505 — 40 יום: הדגל שולט בכפתור) (`42ac0de`)
- build from maor-system main (PR #506 — 40 יום/יומי/שבועי/חודשי בלוח מעקב-הטיפול + הגיע הזמן) (`b1abe23`)
- build from maor-system main (PR #508 — קשר-הבא בלוח: על מה לדבר + שמירה + טופל) (`dd3a0f5`)
- build from maor-system main (PR #507 — כתיבת-קונפיג נקודתית + config last write) (`5e4ce32`)

## [2026-10-05] - 2026-10-05

### Changed

- בנייה ידנית מ-maor-system@main (סידור כרטיס-התורם) — יומן-פריסה (`1b485b5`)
- בנייה ידנית מ-maor-system@main (קשר הבא אחרי הושלם) — יומן-פריסה (`c7aa96b`)
- build from maor-system main 37831c2 (קשר הבא מהלוח + הגיע הזמן) (`16ea253`)
- build from maor-system main 7bf8e7c (PR #504 — 40 יום: הדלקת-דגל מגיעה לענן) (`feb802d`)

## [2026-09-23] - 2026-09-23

### Changed

- build from maor #501 (segula default-on) (`de15f4a`)

## [2026-09-17] - 2026-09-17

### Changed

- build from maor #498 (care-back) (`d4f750b`)

## [2026-09-16] - 2026-09-16

### Changed

- build from maor main (#494) (`c37ae94`)
- build from maor main (#496) (`ea8fd4f`)

## [2026-09-14] - 2026-09-14

### Changed

- build from maor main (#492) (`ec7acb0`)

## [2026-09-10] - 2026-09-10

### Changed

- build from maor main (#489) (`8462dab`)
- build from maor main (#490) (`ea82dc4`)

## [2026-09-09] - 2026-09-09

### Changed

- build from maor main (#486 #487) (`275265a`)

## [2026-09-06] - 2026-09-06

### Changed

- רענון-פריסה — שמות לתפילה + זיכרון-גלילה #480 (`38933c6`)
- רענון-פריסה — שם-תצוגה לעובד/ת #481 (`2c09317`)
- רענון-פריסה — סינון ישראל/חו״ל במעקב-הטיפול #482 (`de6a95b`)
- build from maor main (#483 segula panel) (`9ca3cca`)
- build from maor main (#484 last-donation filter) (`94969dc`)

## [2026-09-05] - 2026-09-05

### Changed

- רענון-פריסה — סגולת 40 יום + הושלם יורד מהלוח #478 (`49d915c`)
- רענון-פריסה — גרסה גלויה + בדיקת-עדכון #479 (`baa24d2`)

## [2026-09-03] - 2026-09-03

### Changed

- רענון-פריסה — ביקורת-עומק #473 (main של מאור) (`e68095c`)
- רענון-פריסה — שאריות ביקורת-עומק #474 (`0865c4f`)
- רענון-פריסה — נחיל ב׳ #475 (`b68d2ba`)
- רענון-פריסה — לוח מעקב הטיפול #476 (`5f3a289`)
- רענון-פריסה — יישור לוח-המעקב #477 (`98861c1`)

## [2026-08-23] - 2026-08-23

### Changed

- פריסה מיידית — עליית /plans.html (דף המחירון) לאוויר (`714ea73`)
- רענון-פריסה — הסרת דף-המחירון (`68864a8`)

## [2026-08-18] - 2026-08-18

### Added

- Initial commit (`dc30022`)
- ה-workflow ‏`Build Orbit from maor-system` (push · cron 03:00 UTC · ידני) · the deploy workflow (`e82d25d`)

[Unreleased]: https://github.com/meir7651231-ui/orbit-il/compare/fff83c4...HEAD
[2026-10-22]: https://github.com/meir7651231-ui/orbit-il/commit/fff83c4
[2026-10-13]: https://github.com/meir7651231-ui/orbit-il/commit/d182111
[2026-10-06]: https://github.com/meir7651231-ui/orbit-il/commit/5e4ce32
[2026-10-05]: https://github.com/meir7651231-ui/orbit-il/commit/feb802d
[2026-09-23]: https://github.com/meir7651231-ui/orbit-il/commit/de15f4a
[2026-09-17]: https://github.com/meir7651231-ui/orbit-il/commit/d4f750b
[2026-09-16]: https://github.com/meir7651231-ui/orbit-il/commit/ea8fd4f
[2026-09-14]: https://github.com/meir7651231-ui/orbit-il/commit/ec7acb0
[2026-09-10]: https://github.com/meir7651231-ui/orbit-il/commit/ea82dc4
[2026-09-09]: https://github.com/meir7651231-ui/orbit-il/commit/275265a
[2026-09-06]: https://github.com/meir7651231-ui/orbit-il/commit/94969dc
[2026-09-05]: https://github.com/meir7651231-ui/orbit-il/commit/baa24d2
[2026-09-03]: https://github.com/meir7651231-ui/orbit-il/commit/98861c1
[2026-08-23]: https://github.com/meir7651231-ui/orbit-il/commit/68864a8
[2026-08-18]: https://github.com/meir7651231-ui/orbit-il/commit/e82d25d
