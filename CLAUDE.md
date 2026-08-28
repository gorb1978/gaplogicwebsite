# GapLogicWebSite

Plain static site (no build step) — `index.html`, `apps.html`, `privacy.html`, plus images.

This is a git repo (`github.com/gorb1978/gaplogicwebsite`, `main` branch), and as of
2026-08-15 it IS linked to Netlify for continuous deployment (Site config → Build &
deploy → Repository shows "Deploys from GitHub"). **However, push-triggered
auto-deploy is currently broken** — Netlify blocks deploys from pushed commits with
an "unrecognized Git contributor" error (free-plan private-repo contributor limit).
See `HUMAN_TASKS.md` for the fix Josh needs to make. Until he confirms it's fixed,
**treat this exactly like the old unlinked state**: commits pushed to `main` do NOT
reliably go live, so manual drag-and-drop into Netlify is still required after
pushing. Don't assume CD works again without re-verifying (see `TODO.md`).

**Any edit to this site (adding a new app to `apps.html`, updating `privacy.html` for a
new app, etc.) should be committed and pushed to `main` as a normal part of finishing
that work** — don't leave it as an uncommitted local change. Also remind Josh he
still needs to manually redeploy (drag-and-drop) until the contributor issue is fixed
and auto-deploy is re-verified.

**Check `TODO.md` and `HUMAN_TASKS.md` at the start of any session touching this
repo, and update them (check off resolved items, add new ones) whenever you make a
change** — don't just silently fix things, log what's still outstanding for next
time and what still needs Josh's action.
