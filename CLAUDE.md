# GapLogicWebSite

Plain static site (no build step) — `index.html`, `apps.html`, `privacy.html`, plus images.

This is a git repo (`github.com/gorb1978/gaplogicwebsite`, `main` branch) — **now a
public repo** (was private; made public 2026-08-15 to work around a Netlify
contributor-limit issue, see below). It IS linked to Netlify for continuous
deployment and **auto-deploy on push to `main` is confirmed working** as of
2026-08-15: pushing is enough, `https://gaplogicsoftware.com/` updates within
seconds, no manual drag-and-drop needed anymore. (History: linking initially hit a
"Netlify can't authorize — GitHub account flagged" block, then after that was
resolved, push-triggered deploys hit an "unrecognized Git contributor" error from
Netlify's free-plan private-repo limit; making the repo public fixed it. Both are
resolved — see `HUMAN_TASKS.md` for the full story if push-deploys ever break again.)

Since the repo is now public, don't commit anything sensitive to it (it never held
secrets, just site HTML/images, but worth remembering now that it's world-readable).

**Any edit to this site (adding a new app to `apps.html`, updating `privacy.html` for a
new app, etc.) should be committed and pushed to `main` as a normal part of finishing
that work** — that's now sufficient to go live; don't leave it as an uncommitted local
change.

**Check `TODO.md` and `HUMAN_TASKS.md` at the start of any session touching this
repo, and update them (check off resolved items, add new ones) whenever you make a
change** — don't just silently fix things, log what's still outstanding for next
time and what still needs Josh's action.
