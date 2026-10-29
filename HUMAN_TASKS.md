# Human Tasks (Josh-facing)

Things only Josh can do — clicking through OAuth flows, external accounts, judgment
calls. Claude should check this file in and update it whenever a task here gets
resolved or a new one comes up.

## Open

- [ ] **Decide whether to delete the unused image files in the site's repo root:**
      `Gap Calc App Icon_old.png`, `Gap Med App Icon_old.png`, the two
      `Gemini_Generated_Image_*.png` files and `gemini-svg.svg`. Nothing on the site
      uses them, but they're publicly reachable and about 15 MB together. Say "delete
      them" and Claude will (they stay in git history).
- [ ] **Decide whether to add GapApprentice's hour-target disclaimer** (its
      `PRIVACY_POLICY_DRAFT.md` §3) to `privacy.html`'s "4. User Responsibility &
      Accuracy". It wasn't in the 2026-10-29 brief, so it was left out.
- [ ] **When each app reaches production, tell Claude** so its card's "Coming Soon"
      label and `#` link can be switched to the Play link: GapWater, GapSeizure,
      GapReintro, GapApprentice, GapLock (all closed/internal testing now), plus
      GapVitals and GapBudget.
- [ ] Decide what **GapNotes** actually is — there's a placeholder "Coming Soon"
      card/section for it on the site now, but no project folder or spec exists for
      it anywhere in `StudioProjects`.

## Resolved

- [x] Real icons for **GapSeizure** and **GapReintro** now exist in their repos and
      are on the site (replacing the splash-logo placeholder) — 2026-10-29. GapLock
      and GapApprentice cards use their real icons too.
- [x] GapRegister's and GapJournal's Play Store listings are live and their
      `apps.html` Download buttons point to them — 2026-10-07 (supersedes the old
      "GapRegister is still 404ing" item).
- [x] GapBudget vs ClearBudget naming — confirmed 2026-08-12: site should say
      **GapBudget** (portfolio convention: every app name starts with "Gap"),
      regardless of what the `clearbudget` folder's own internal docs say.
- [x] GapRegister's `apps.html` naming/feature-list fixed for its 2026-08-14 launch —
      2026-08-15.
- [x] GitHub account flag lifted and Netlify successfully linked to
      `github.com/gorb1978/gaplogicwebsite` (branch `main`, no build command,
      publish directory `.`) — 2026-08-15.
- [x] **Push-triggered auto-deploy confirmed fully working — 2026-08-15.** First
      test (`main@dc0d43f`) failed with "unrecognized Git contributor" (Netlify's
      free-plan private-repo contributor limit). Josh made the repo public to fix
      it. Re-tested with two more real pushes (`main@24f0565`, then its revert
      `main@5057b91`) — both auto-deployed and published successfully within
      seconds. Continuous deployment is genuinely live now: pushing to `main` is
      enough, manual Netlify drag-and-drop is no longer needed.
