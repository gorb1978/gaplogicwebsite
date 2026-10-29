# TODO (Claude-facing)

Working list of things to pick up next session on this repo. Check this file at the
start of a session and update it (mark done / add new items) whenever you touch
`apps.html`, `privacy.html`, or `index.html` — don't leave it stale.

## Open

- [ ] **GapApprentice's "no internet permission" lines depend on one open check.**
      D1(b) passed on Play's APK for versions 1 and 2 (0 INTERNET, only BILLING),
      but its docs still list the `dumpsys package` check on a real Play Store
      install as open, and say to pull the claim if it ever shows INTERNET. The
      lines on this site: `privacy.html` (the GapApprentice box in section 1 and
      the section 7 billing sentence) and the `apps.html` card's Core Philosophy.
      Re-check `GapApprentice/STATUS.md` for that result, and re-run the whole
      claim for any later version.
- [ ] `GapApprentice/PRIVACY_POLICY_DRAFT.md` §4 (a refund paragraph for section 6)
      was not applied; the refund rule is already described inside the GapApprentice
      box in section 1, so it would be a duplicate. §3 (the hour-target disclaimer)
      is now in section 4, but with the shorter end-card wording rather than the
      draft's longer paragraph (see Recently resolved). If Josh wants the longer
      text, it adds the 4,000 to 16,000+ hour range, the federal 8,000-hour preset
      baseline and a "GapLogic is not responsible for a submission based on a preset
      you did not confirm" sentence.
- [ ] Swap the `splash_logo.png` placeholder for GapNotes once that app actually
      exists (no folder for it anywhere in `StudioProjects` as of 2026-08-12 — it's
      a pure "coming soon" placeholder card right now).
- [ ] Update "Download on Google Play" `#` placeholder links to real Play Store URLs
      as each remaining app (GapVitals, GapBudget, GapWater, GapSeizure, GapReintro,
      GapLock, GapApprentice) actually goes live — and remove its "Coming Soon" `<p>`
      in the same edit. As of 2026-10-29, GapWater, GapSeizure, GapReintro,
      GapApprentice and GapLock are on closed/internal testing only (per Josh);
      GapVitals and GapBudget have not been checked since 2026-08-15 (404 then).
      Check each folder's `LAUNCH_CHECKLIST.md`/`STATUS.md`, then verify the Play URL
      returns HTTP 200 with the app's title before switching (curl with a browser
      User-Agent works; WebFetch can't read the page body). These seven are exactly
      the cards carrying the "Coming Soon" label on the live site (GapNotes is
      separate: it has a "Coming Soon" badge and no Download button). GapFluid,
      GapMed, GapCalc, GapRegister and GapJournal already have live links.
- [ ] Periodically re-sweep each app folder's most recent .md docs (README, HANDOFF,
      TODO, HUMAN_TASKS, SPRINT_HISTORY, STORE_LISTING) against `apps.html` /
      `privacy.html` — app docs update faster than the site, so treat the site as
      the thing that's usually behind unless proven otherwise (verified 2026-08-12,
      found several apps had stale copy: GapCalc, GapRegister, GapJournal all had
      shipped features missing from their site cards).

## Recently resolved

- [x] **2026-10-29 (approved by Josh in Cowork): hour-target disclaimer and root
      cleanup.** `56897fd`: `privacy.html` section 4 gained "**GapApprentice Hour
      Targets:** GapApprentice is a record-keeping tool. Confirm hour requirements
      with your program or licensing board." (the wording approved for its video end
      card, `GapApprentice/design/video/script.md`). The no-internet lines stay, as
      Josh said (D1(b) PASS on Play's APK for vc1 and vc2). Then the five unused
      root files were removed with `git rm` after re-checking that no site file
      referenced them (the only other hit anywhere in StudioProjects was a local
      Downloads path in a GapJournal QA note): `Gap Calc App Icon_old.png`,
      `Gap Med App Icon_old.png`, both `Gemini_Generated_Image_*.png`,
      `gemini-svg.svg`.
- [x] **2026-10-29 (approved by Josh in Cowork): GapApprentice on the site, new
      cards, videos, icons.** Commits `5caa043` (privacy, pushed first because it
      was urgent) and `3b12615` (everything else); both confirmed live on
      gaplogicsoftware.com the same day.
      - `privacy.html`: GapApprentice added to the intro list; a section 1 box
        (what it keeps, permissions = no internet permission and only Google Play
        billing, backups and exports, the refund rule); a backup-exception
        paragraph (allowBackup=false, every cloud-backup and device-transfer domain
        excluded, only the user's own backup file leaves the phone); the billing
        diagnostics sentence in section 7; "intended for people aged 18 and over" in
        children's privacy (the app's own draft said "unchanged", Josh's brief
        listed children's privacy, so this one sentence is the only addition there;
        it matches its Play target audience of 18+). Facts were checked against the
        app's manifest, backup rules, `STATUS.md` (D1(b) PASS 2026-10-23 on version
        1 and 2026-10-27 on version 2), `PLAY_CONSOLE_ANSWERS.md` and
        `lib/services/pro_ownership.dart`, not just the brief.
      - `apps.html` + `index.html`: new GapApprentice card (Pro $3.99, listing
        copy, includes the hour-targets-are-a-starting-point caution) and GapLock
        card (draft `ab47f6a` revalidated against GapLock's approved listing text:
        $2.99 Pro, no INTERNET, backup off; used its real icon instead of the
        placeholder; the local `gaplock-card` branch is now superseded). Both
        "Coming Soon", no Play link. Home-page cards added for both.
      - Videos (YouTube embeds, GapMed's markup): GapRegister replaced (the old id
        `Ie5pctdzmXk` went private, returns 403), plus GapFluid, GapWater,
        GapReintro, GapSeizure and GapApprentice added. All six ids returned 200 on
        YouTube oEmbed with the right titles, and the players were seen rendering
        on the live page.
      - Icons, resized to 256 px (web size, like GapFluid's): GapRegister and
        GapCalc (sparkle removed, from `design/store/*_no_sparkle.png`), GapWater
        (the newer clean store icon in `assets/images/app_icon_512.png`; it has no
        `design/store` icon), GapSeizure (replaces `splash_logo.png`; also fixed on
        its home card), GapApprentice and GapLock (new). GapReintro's home card
        also switched from `splash_logo.png` to its real icon. Left unchanged
        because they match or have no newer file: GapFluid (same image), GapReintro
        (identical), GapJournal (repo icon is byte-identical to the site copy),
        GapMed (no store icon file in its repo; its `assets/icon.png` is the old
        design, byte-identical to `Gap Med App Icon_old.png`, so the site's newer
        icon was kept).
      - Noticed then, since removed (see the entry above): five unreferenced
        files in the repo root. Still open: the GapMed (3.8 MB),
        GapBudget (4.6 MB), GapVitals (1.3 MB) and GapJournal (0.9 MB) card icons
        are still the old full-size originals; they could be web-sized like the rest.
- [x] 2026-10-17: GapLock added to `privacy.html` (intro list, permissions box in
      section 1, backup exception, section 5 app-locking limits line, section 7
      billing line, children's privacy). Approved by Josh in Cowork.
- [x] **GapCalc Download button is live — 2026-10-07 (app is on Play at 1.0.12).**
      Play URL verified HTTP 200 with the title "GapCalc - Apps on Google Play"
      before switching; "Coming Soon" removed, same markup as the other live
      buttons (commit `a30eadd`). Confirmed on the live `apps.html`: four Play links
      (GapMed, GapRegister, GapJournal, GapCalc), six cards still "Coming Soon".
      The GapCalc card's feature copy was not touched in this change.
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
