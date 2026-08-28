# TODO (Claude-facing)

Working list of things to pick up next session on this repo. Check this file at the
start of a session and update it (mark done / add new items) whenever you touch
`apps.html`, `privacy.html`, or `index.html` — don't leave it stale.

## Open

- [ ] **Netlify is linked but push-triggered auto-deploy is currently BROKEN** — see
      `HUMAN_TASKS.md` for the "unrecognized Git contributor" fix Josh needs to do.
      Once he confirms it's fixed, re-run the same verification test (trivial
      whitespace push → confirm a new deploy appears and actually publishes → revert)
      to make sure it's really working before relying on it and dropping the
      "remind Josh to drag-and-drop" habit.
- [ ] Swap the `splash_logo.png` placeholder icons for GapSeizure and GapReintro once
      real app icons exist in their repos (`gapseizure/assets/images/`,
      `gapreintro/assets/images/` — both empty as of 2026-08-12).
- [ ] Swap the `splash_logo.png` placeholder for GapNotes once that app actually
      exists (no folder for it anywhere in `StudioProjects` as of 2026-08-12 — it's
      a pure "coming soon" placeholder card right now).
- [ ] **GapRegister's Play Store listing is still 404ing** as of 2026-08-15 (checked
      `https://play.google.com/store/apps/details?id=com.gaplogic.gapregister`
      directly — still not resolving, propagation after 2026-08-14 approval evidently
      takes longer than a day). `apps.html`'s Download button still points to `#`.
      **Re-check the URL next session** — once it resolves, swap the href in.
- [ ] Update "Download on Google Play" `#` placeholder links to real Play Store URLs
      as each remaining app (GapVitals, GapCalc, GapJournal, GapBudget, GapFluid,
      GapWater, GapSeizure, GapReintro) actually goes live — check each folder's
      `LAUNCH_CHECKLIST.md` for status before assuming "live." Spot-checked all 8
      Play Store URLs directly on 2026-08-15 (triggered by GapRegister's launch) —
      all still 404, none live yet. Worth re-checking periodically rather than only
      trusting `LAUNCH_CHECKLIST.md` state, since GapRegister's own checklist wasn't
      necessarily the trigger that caught its go-live either.
- [ ] Periodically re-sweep each app folder's most recent .md docs (README, HANDOFF,
      TODO, HUMAN_TASKS, SPRINT_HISTORY, STORE_LISTING) against `apps.html` /
      `privacy.html` — app docs update faster than the site, so treat the site as
      the thing that's usually behind unless proven otherwise (verified 2026-08-12,
      found several apps had stale copy: GapCalc, GapRegister, GapJournal all had
      shipped features missing from their site cards).

## Recently resolved

- [x] Netlify linked to GitHub (2026-08-15) — but see the new Open item above:
      linking succeeded, push-triggered auto-deploy did not. Verification test used
      a whitespace-only trailing-newline change to `index.html`
      (commit `dc0d43f`, reverted in `a088113`) — the push itself succeeded on
      GitHub, but Netlify's deploy of that commit failed with "Build blocked:
      Unrecognized Git contributor," confirming the pipeline isn't actually live
      yet. Site content was never affected since the blocked deploy never published.
- [x] Added a "Coming Soon" label above the Download button for every app that
      still points to the `#` placeholder (GapVitals, GapCalc, GapRegister,
      GapJournal, GapBudget, GapFluid, GapWater, GapSeizure, GapReintro) — 2026-08-15,
      Josh's request. GapMed was untouched since it already has a real Play Store
      link. When any app's placeholder link gets swapped for a real URL, remove its
      "Coming Soon" `<p>` at the same time — don't leave both.

- [x] GapRegister's `apps.html` header ("Offline Checkbook" → "Income & Expense
      Tracker") and Free Features list (added home-screen widget + font scale
      100%–200%) brought up to date, 2026-08-15 — matches live Play Store listing
      and the app's own README.md/STORE_LISTING.md. privacy.html and the YouTube
      embed were already correct and untouched.
- [x] Checked GapRegister's Play Store URL for the Download-button update,
      2026-08-15 — still 404, so the button was intentionally left as `#` (see Open
      list above for the re-check task).

## Notes / decisions to remember

- App naming on the site follows the "every app starts with Gap" convention — even
  when an app's own project docs use a different internal/working name (e.g.
  `clearbudget` folder's own README calls it "ClearBudget," but the site correctly
  calls it **GapBudget** per Josh's explicit correction on 2026-08-12; don't rename
  it back based on that folder's internal docs).
- IAP product IDs in several apps intentionally keep legacy/old-name prefixes
  (e.g. GapJournal's IAPs use `com.gaplogic.sleepdraft.*`) — that's deliberate,
  not a bug, don't "fix" it.
