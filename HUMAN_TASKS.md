# Human Tasks (Josh-facing)

Things only Josh can do — clicking through OAuth flows, external accounts, judgment
calls. Claude should check this file in and update it whenever a task here gets
resolved or a new one comes up.

## Open

- [ ] **When each app reaches production, tell Claude** so its card's "Coming Soon"
      label and `#` link can be switched to the Play link: GapWater, GapSeizure,
      GapReintro, GapLock (closed/internal testing as of 2026-10-29), plus
      GapVitals and GapBudget. (GapApprentice went live 2026-11-04 and is done.)
- [ ] **Play Store and listing-file wording that now disagrees with the site** (you
      said you'd handle the Play listings yourself; this is just the list, found in the
      2026-11-04 review). The site was changed to follow your rules, the listings
      were not:
      - **GapMed** (live): says "premium medical scheduling utility", "peace of mind"
        and "perfect offline companion for managing chronic illness, post-surgery
        recovery, ADHD medication schedules". It has no current `STORE_LISTING.md`
        (retired as `STALE_STORE_LISTING.md`), so the live listing is the only copy.
      - **GapJournal** (live): says the diary uses "the standard sleep-diary questions
        used in CBT-I", calls the breathing tool "a guided breathing exercise to help
        you relax before sleep", and names an export "PDF Health Record".
      - **"Stays on your phone" wording**: GapSeizure ("Your diary stays on your
        phone."), GapReintro ("so your diary stays on your phone unless you export or
        back it up yourself") and GapApprentice (live: "kept in a database on your
        phone; a copy only goes somewhere else when you export or back up a file")
        still use it. GapVitals' and GapBudget's June `STORE_LISTING.md` files say
        "No data ever leaves your phone" / "it never leaves your phone". GapLock's
        listing says "Your PIN and your rules never leave your phone."
      - **Prices**: the GapWater and GapReintro listings show no Pro price, so their
        site cards now say "one-time unlock" instead of $3.99. If you want the price
        on the cards, add it to the listings first.
      - **"No internet permission" on the site**: removed for GapMed, GapRegister,
        GapBudget and GapLock until each has a D1(b) PASS on its live build in
        STATUS.md (run `tool/d1b_check.sh`-style check on Play's APK, then tell Claude).
      - **Stale listing files**: GapVitals' (BodyLog, June) and GapBudget's
        (ClearBudget, June) `STORE_LISTING.md` predate the Gap names and the current
        apps; GapRegister's is from August (its live text is in
        `tools/play-publish/full_description.txt`). Worth a refresh before those apps
        ship, since the site only has these to compare against.
- [ ] Decide what **GapNotes** actually is — there's a placeholder "Coming Soon"
      card/section for it on the site now, but no project folder or spec exists for
      it anywhere in `StudioProjects`.

## Resolved

- [x] 2026-10-29 (Josh in Cowork): GapApprentice's hour-target disclaimer added to
      `privacy.html` section 4 (`56897fd`), and the five unused root files deleted
      (below). The disclaimer uses the end-card wording ("GapApprentice is a
      record-keeping tool. Confirm hour requirements with your program or licensing
      board."), not the longer paragraph in the app's draft; say so if you want the
      longer one instead.
- [x] 2026-10-29: deleted the five unused files from the site's repo root (about
      15 MB, publicly reachable): `Gap Calc App Icon_old.png`,
      `Gap Med App Icon_old.png`, both `Gemini_Generated_Image_*.png` and
      `gemini-svg.svg`. They stay in git history if one is ever needed.
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
