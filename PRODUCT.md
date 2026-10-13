# Product

<!-- impeccable:product-schema 1 -->

## Platform

web

## Users

A single competitive Beyblade player (the developer's friend). Uses the app solo — no multi-user support, no public access. Primary context is at tournaments on a phone; occasional desktop use at home.

## Product Purpose

A purpose-built stat tracker for competitive Beyblade. Replaces notes apps and spreadsheets with a tool that understands the game's own scoring system — tracking match results per bey per event, automatically calculating Win Rate, Score Over Opponent Rate (SOOR), and Stat Points, so the player always knows which build is objectively performing best right now.

## Positioning

The only Beyblade tracker built around this specific scoring system (Burst Finish = 4pts, Xtreme = 3pts, Pocket = 2pts, Spin = 1pt, with self-finish tracking and SOOR). No generic sports tracker or spreadsheet understands these rules natively.

## Operating Context

- Used at competitive Beyblade tournaments, primarily on a phone
- Player logs results during or immediately after an event
- Leaderboard consulted when deciding which bey to bring to the next tournament
- Events page browsed to review performance trends over time
- Private tool — hosted URL is not public, single user only

## Capabilities and Constraints

- Three core entities: Beys (builds), Events (tournament sessions), Entries (match results per bey per event)
- Match results stored as compact round-code strings (e.g. `2.431505`)
- Stats calculated client-side from round codes: WR, SOOR, Stat Points
- Beys have a build string, optional nickname, optional photo
- Events have a name, date, and a list of bey entries
- Leaderboard filters by minimum/maximum matches; sorts by Stat Points, WR, or SOOR
- Events page filters by one or more beys (AND logic — must have used all selected beys)
- Filter and leaderboard preferences persisted in localStorage
- Backend: Supabase (Postgres + Storage)
- Frontend: React + TypeScript + Vite, MUI components, React Router

## Brand Commitments

- Name: **BEYTRACK** (all caps in the wordmark)
- Color scheme: dark purple backgrounds with yellow highlights — dark mode only, energetic competitive feel
- This palette is locked: do not replace or neutralize it

## Evidence on Hand

- Full README at `/README.md` with scoring system table, feature descriptions, and stat formula explanations
- Working implementation across Events, Leaderboard, Beys, and Add/Edit flows
- Screenshots confirm: deep purple `#1a1025`-range background, yellow `#f5c518`-range accent on top stat points and the wordmark, card surfaces in dark purple-grey, bottom nav bar

## Product Principles

1. **The number doesn't lie.** Stat Points is the single ranking metric — design always makes it the most prominent piece of data.
2. **Phone-first, tournament-ready.** Every interaction must work one-handed on a small screen under pressure.
3. **Speed over ceremony.** Logging a result should take seconds. No unnecessary confirmation screens or modal stacks.
4. **Private by default.** This is a personal tool. No social features, no sharing flows, no public-facing content.
5. **Trust the scoring system.** The app reflects the game's actual rules exactly — no approximations, no rounding that changes rank.

## Accessibility & Inclusion

No specific requirement stated beyond standard usability. Touch targets must be comfortable for phone use.
