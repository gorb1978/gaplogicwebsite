# Human Tasks (Josh-facing)

Things only Josh can do — clicking through OAuth flows, external accounts, judgment
calls. Claude should check this file in and update it whenever a task here gets
resolved or a new one comes up.

## Open

- [ ] **Resolve the GitHub account flag.** `gorb1978` is currently flagged and can't
      authorize third-party OAuth apps, which blocks linking Netlify to
      `github.com/gorb1978/gaplogicwebsite` for continuous deployment. Contact
      GitHub Support (support.github.com) to get the flag reviewed/lifted.
- [ ] **Link Netlify to GitHub** once the flag is resolved: Site configuration →
      Build & deploy → Link repository → GitHub → `gorb1978/gaplogicwebsite` →
      branch `main`. Build command blank, publish directory `.`.
- [ ] Until CD is linked, **manual deploy still required**: drag-and-drop the
      `GapLogicWebSite` folder into Netlify after any local edit gets committed —
      currently editing the git repo does NOT make the live site update by itself.
- [ ] Provide real app icons for **GapSeizure** and **GapReintro** — neither has one
      generated yet anywhere in their project folders. Site currently shows the
      GapLogic splash logo as a placeholder for both.
- [ ] Decide what **GapNotes** actually is — there's a placeholder "Coming Soon"
      card/section for it on the site now, but no project folder or spec exists for
      it anywhere in `StudioProjects`.

## Resolved

- [x] GapBudget vs ClearBudget naming — confirmed 2026-08-12: site should say
      **GapBudget** (portfolio convention: every app name starts with "Gap"),
      regardless of what the `clearbudget` folder's own internal docs say.
