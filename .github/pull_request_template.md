## מה השתנה · What changed

<!-- תיאור קצר · short description -->

## בדיקות · Checks

- [ ] `git diff --name-status main` — אין שינוי ב-`.github/workflows/`, `CNAME`, `DEPLOY-LOG.md` (מחיקה) · no change to deploy files
- [ ] README עברית ואנגלית מעודכנים יחד · Hebrew and English READMEs updated together
- [ ] קישורים תקינים, תמונות ≤ 500KB עם `alt` · links OK, images ≤ 500KB with `alt`

## ⚠️ מיזוג = פריסה · Merge = deploy

- [ ] ידוע לי שמיזוג ל-`main` בונה ומעלה את `maor-system@main` הנוכחי ל-orbit-il.com · I know merging to `main` ships the current `maor-system@main` to orbit-il.com
- [ ] אחרי מיזוג: `curl -s "https://orbit-il.com/version.json?t=$(date +%s)"` · after merge: verify `version.json`
