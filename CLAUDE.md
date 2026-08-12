# GapLogicWebSite

Plain static site (no build step) — `index.html`, `apps.html`, `privacy.html`, plus images.

This is a git repo (`github.com/gorb1978/gaplogicwebsite`, `main` branch). It is
**intended** to be connected to Netlify for continuous deployment, but as of
2026-08-12 that link is NOT active — Josh's GitHub account is flagged and can't
authorize the Netlify OAuth app yet (see `HUMAN_TASKS.md`). Until that's resolved,
Josh deploys manually by drag-and-dropping this folder into Netlify.

**Any edit to this site (adding a new app to `apps.html`, updating `privacy.html` for a
new app, etc.) should be committed and pushed to `main` as a normal part of finishing
that work** — don't leave it as an uncommitted local change. Also remind Josh he'll
need to manually redeploy (drag-and-drop) until continuous deployment is actually
linked.

**Check `TODO.md` and `HUMAN_TASKS.md` at the start of any session touching this
repo, and update them (check off resolved items, add new ones) whenever you make a
change** — don't just silently fix things, log what's still outstanding for next
time and what still needs Josh's action.
