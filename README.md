# Circuit League product guide

Static product-review guide for Circuit League. `index.html` and `styles.css` are the published files. Phone illustrations explain product decisions; they are not screenshots or evidence that a native feature has shipped.

## October 21, 2026 refresh

Published baseline: guide commit `18659edd51b5bc3d5da9afeda1f66fe0f095b482` (October 9).

Application baseline: local `Pickleball-Tournaments` main at `78f080e07cbd8a7ebcd01891a6395b7fb29a2025` (October 21). This includes the integrated 48-hour confirmation, reminder, player-record and rating-detail changes. The local product repository contains other unfinished work; the guide update does not edit or incorporate those unrelated changes.

Additional approved policy: `apps/docs/docs/decisions/scoring-game-count-by-mode.md`, October 21. This decision document is an uncommitted local draft at review time. Its owner-approved flexible-play and optional-game injury rules are explicitly marked **implementation pending** in the guide. The committed October 19 game-plan/complete-block guards are not presented as already remediated.

The application brief records local implementation rather than a production release. This refresh does not independently verify deployment, open an area, apply database changes or send messages.

## Source map

Paths below are relative to the application repository, `Pickleball-Tournaments`, rather than this static-guide repository. Later dated owner amendments take precedence over older prose in the same brief.

| Guide content | Owning source |
| --- | --- |
| Current direction and dated owner amendments | `apps/docs/docs/decisions/circuit-league.md` |
| League versus organizer ladders | `apps/docs/docs/decisions/circuit-league-positioning.md` |
| Operating switches, clocks, notifications, Scan and support | `apps/docs/docs/operations/circuit-league-reference.md` |
| Screens, entry and next-action hierarchy | `apps/docs/docs/operations/circuit-league-ux-design.md` and the October 17/18 mobile UX plans |
| Membership before venues; suggestions and private review status | October 18 amendments in the brief; `apps/docs/docs/operations/circuit-league-ux-followup-plan-2026-10-18.md` |
| Boards earned through as-played venues | October 18 “Boards from where you play” amendment |
| Standard opening plans and repeated game drafts | October 19 standard-format amendment; `packages/shared/src/league/rotations.ts`, `scoring.ts` |
| Voluntary finishing and optional-game injury | October 21 scoring decision above; `apps/docs/docs/operations/scoring-correctness-remediation-plan-2026-10-21.md` (pending implementation) |
| Favorite venue order, separate backups | October 19 ranked-favorites amendment; `packages/shared/src/league/venue-choices.ts` |
| No partnership cap; player names replace team names | October 19/20 amendments; `packages/shared/src/league/player-labels.ts` and `teams.ts` |
| Search, genuine DUPR and reliability details | October 20 amendments; `apps/docs/docs/operations/circuit-league-leaderboard-search-plan-2026-10-20.md` |
| Recent PD, season totals and game-specific lineups | October 20 amendments; `packages/shared/src/league/point-differential.ts` and `recap-result-groups.ts` |
| 48-hour confirmation and reminder channels | October 20 score-confirmation amendment; application integration commit `78f080e07` |
| Weekly/season stories and immutable facts | October 20 story amendment; `apps/docs/docs/operations/league-recap-stories-plan-2026-10-20.md`, `packages/shared/src/recaps/league-story.ts` |
| Recap identity erasure | October 20 recap-erasure amendment; application commit `8cb5f13da` |
| Record badges and their explanations | October 20 record-badge amendment; `packages/shared/src/league/badges.ts` |
| Rating worked examples | Product brief section 6; `packages/shared/src/league/rating/__tests__/worked-example-fixtures.json` |
| Private fake-result review | `packages/shared/src/league/weekly-review.ts` |
| Pause offers until Monday Central | `packages/shared/src/league/snooze.ts` |

## Updating and previewing

Keep the existing noindex/nofollow directive. Reconcile decisions and current implementation separately, particularly when a later amendment replaces older brief text. Do not turn old simulations, venue prices, legal research or local verification into current operational claims.

Serve this directory with a static HTTP server and open `index.html`. Check 360×800, 390×844 and 1280×900 layouts, section-menu links, tables, illustrations, light/dark theme and browser console errors. Check internal fragment/file links and run `git diff --check`.

GitHub Pages currently publishes the repository root from `master`. Publishing requires a separately authorized commit/push to that branch and a fresh Pages check. Local preview or an edited file alone does not update the live URL.

### Verification of this refresh

- HTML nesting, 20 unique IDs and all 35 local fragment/file references pass.
- All 16 section destinations work at 360×800, 390×844 and 1280×900 (48 navigation checks); the mobile menu closes after a choice.
- Rendered width checks find no page overflow at those three sizes. Matched before/after screenshots cover the introduction, score review, board illustration and notification table. Additional sampled checks cover dark theme and the opened mobile menu.
- Browser error/warning logs are empty; `git diff --check` passes.
- This verifies the static guide. It does not verify native app appearance, production behavior, provider delivery or deployment.
