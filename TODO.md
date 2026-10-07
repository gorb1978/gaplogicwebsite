# TODO (Claude-facing)

Working list of things to pick up next session on this repo. Check this file at the
start of a session and update it (mark done / add new items) whenever you touch
`apps.html`, `privacy.html`, or `index.html` — don't leave it stale.

## Open

- [ ] Swap the `splash_logo.png` placeholder icons for GapSeizure and GapReintro once
      real app icons exist in their repos (`gapseizure/assets/images/`,
      `gapreintro/assets/images/` — both empty as of 2026-08-12).
- [ ] Swap the `splash_logo.png` placeholder for GapNotes once that app actually
      exists (no folder for it anywhere in `StudioProjects` as of 2026-08-12 — it's
      a pure "coming soon" placeholder card right now).
- [ ] Update "Download on Google Play" `#` placeholder links to real Play Store URLs
      as each remaining app (GapVitals, GapCalc, GapBudget, GapFluid, GapWater,
      GapSeizure, GapReintro) actually goes live — and remove its "Coming Soon" `<p>`
      in the same edit. Check each folder's `LAUNCH_CHECKLIST.md` for status, then
      verify the Play URL returns HTTP 200 with the app's title before switching
      (curl with a browser User-Agent works; WebFetch can't read the page body).
      Last checked all of these on 2026-08-15, all still 404 — **re-check them**,
      since GapRegister and GapJournal have both gone live since then.
- [ ] Periodically re-sweep each app folder's most recent .md docs (README, HANDOFF,
      TODO, HUMAN_TASKS, SPRINT_HISTORY, STORE_LISTING) against `apps.html` /
      `privacy.html` — app docs update faster than the site, so treat the site as
      the thing that's usually behind unless proven otherwise (verified 2026-08-12,
      found several apps had stale copy: GapCalc, GapRegister, GapJournal all had
      shipped features missing from their site cards).

## Recently resolved

- [x] **GapRegister and GapJournal Download buttons are live — 2026-10-07 (Josh
      approved the push).** Both Play URLs verified HTTP 200 with the right titles
      ("GapRegister – Income & Expense", "Gap Journal: Sleep Diary") before
      switching; "Coming Soon" removed from both cards, buttons use the same
      `target="_blank" rel="noopener noreferrer"` markup as GapMed. GapJournal's
      card also moved CSV export to Free and renamed the Pro item to "AI-Ready
      Summary Export" (commit `60b285e`); GapRegister is `9f3c159`. Confirmed on the
      live `gaplogicsoftware.com/apps.html`: three Play links (GapMed, GapRegister,
      GapJournal), seven cards still "Coming Soon". This supersedes the old
      "GapRegister is still 404ing" item from 2026-08-15, which was removed.
- [x] **GapFluid privacy wording (2026-10-06, approved by Josh).** `privacy.html`:
      "Last Updated" now October 2026; the Android-backup section says GapFluid is
      the exception (Auto Backup and device transfer off, only the user's own
      backup file leaves the phone); section 7 explains the Play Billing library's
      Google diagnostics component, which has no network access in GapFluid. Only
      GapFluid is named, since it's the only app whose merged manifest was checked.
      The GapFluid card's Free list gained "Free backup & restore" the same day
      (approved by Josh after seeing the diff).

- [x] **Fixed the 2 remaining unfixed instances + the heading, from the 2026-08-28
      sweep — same day.** `apps.html` GapJournal and GapWater Core Philosophy text
      now carry the same Android-backup caveat as GapVitals/GapRegister/GapBudget.
      `privacy.html`'s Section 1 heading reworded from "100% Local Architecture" to
      "Local-First Architecture" so it doesn't contradict the corrected body text
      right below it. Josh explicitly said to leave the borderline items alone —
      the "100% Offline"/"no internet permission" badges and GapCalc's "it cannot
      send your data anywhere" are a different, still-accurate claim (genuine lack
      of network access) and should NOT be qualified with the backup caveat; don't
      "fix" those in a future sweep.
- [x] **Fixed overstated "never uploaded / exclusively on-device" privacy claims —
      2026-08-28.** `privacy.html`'s GapRegister callout rewritten using the exact
      wording from `pocketledger/LAUNCH_CHECKLIST.md` (Josh's instruction — don't
      improvise). Same claim class also found and fixed in `apps.html`'s GapVitals,
      GapRegister, and GapBudget Core Philosophy text (all now note that Android's
      own system backup may include app data in the user's own Google Drive backup,
      and that this is Android's doing, not the app's). Confirmed live on
      `gaplogicsoftware.com` via direct fetch after the Netlify auto-deploy
      published (commit `9ea18b3`).
- [x] Deleted `Testapps.html` — an unlinked, stale draft of `apps.html` (6 apps,
      last touched only in the initial commit) that was still technically live at
      `gaplogicsoftware.com/Testapps.html` since the publish directory is repo
      root. It repeated the old internal "PocketLedger" codename and the same
      overstated privacy claims. Josh confirmed: delete entirely, don't just fix
      the wording.
- [x] **Netlify continuous deployment is fully working — 2026-08-15.** Linked
      successfully, but the first push-triggered deploy attempt (`dc0d43f`) failed
      with "Build blocked: Unrecognized Git contributor" (Netlify's free-plan
      private-repo contributor limit — site content was never affected since that
      deploy never published). Josh made the `gaplogicwebsite` repo public to fix
      it. Re-verified with two more real pushes (`24f0565`, reverted by `5057b91`)
      — both auto-deployed and published within seconds. Pushing to `main` is now
      sufficient; manual Netlify drag-and-drop is no longer needed going forward.
      If future pushes stop deploying, check `HUMAN_TASKS.md`'s resolved note for
      what the failure mode looks like and how it was fixed last time.
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
