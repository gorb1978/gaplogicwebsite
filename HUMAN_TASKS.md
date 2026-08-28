# Human Tasks (Josh-facing)

Things only Josh can do — clicking through OAuth flows, external accounts, judgment
calls. Claude should check this file in and update it whenever a task here gets
resolved or a new one comes up.

## Open

- [ ] **Netlify's auto-deploy-on-push is blocked by an "unrecognized Git
      contributor" error**, discovered 2026-08-15 during the CD verification test.
      Netlify's free plan only allows one verified contributor on private repos;
      the git commit identity (`gorb1978` / `josh.gorby@gaplogicsoftware.com`) isn't
      recognized as matching your linked GitHub account. Fix by either:
      (a) Netlify dashboard → Deploys → "manage Git contributors" → link/verify your
      Git identity, or
      (b) upgrade to a plan with unlimited private-repo contributors, or
      (c) make the `gaplogicwebsite` repo public (removes the contributor limit).
      Until this is fixed, **pushes to `main` will NOT auto-deploy** — see the test
      evidence in `TODO.md`.
- [ ] Until the above is fixed, **manual deploy still required**: drag-and-drop the
      `GapLogicWebSite` folder into Netlify after any local edit gets committed —
      the repo IS now linked to Netlify, but deploys from pushes are being blocked,
      so this is still the working fallback.
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
      publish directory `.`) — 2026-08-15. Initial deploy from the setup wizard
      published successfully (`main@f8171a9`). NOTE: this does NOT mean push-based
      auto-deploy actually works yet — see the new Open item above, found
      immediately after by testing it.
