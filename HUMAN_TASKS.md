# Human Tasks (Josh-facing)

Things only Josh can do — clicking through OAuth flows, external accounts, judgment
calls. Claude should check this file in and update it whenever a task here gets
resolved or a new one comes up.

## Open

- [ ] Provide real app icons for **GapSeizure** and **GapReintro** — neither has one
      generated yet anywhere in their project folders. Site currently shows the
      GapLogic splash logo as a placeholder for both.
- [ ] Decide what **GapNotes** actually is — there's a placeholder "Coming Soon"
      card/section for it on the site now, but no project folder or spec exists for
      it anywhere in `StudioProjects`.
- [ ] **GapRegister's Play Store listing is still 404ing** as of 2026-08-15 (checked
      directly, not just assumed) — propagation after the 2026-08-14 approval is
      taking longer than a day. Once `https://play.google.com/store/apps/details?id=com.gaplogic.gapregister`
      actually resolves, let Claude know so the `apps.html` Download button can be
      switched from the `#` placeholder to the real link.

## Resolved

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
