# THE ROW

*A living campus in a single file.*

A procedurally generated, watchable simulation of Greek life at **Colonnade College** — a small
white-columned school in Lexford, Virginia that is culturally, permanently, somewhere between
1999 and 2006. Open it and a campus is alive: quiet Tuesday class streams, Friday night igniting
down the Row, rush and initiation and Fancy Dress and graduation rolling past year after year,
while a Chronicle writes the house lore in the voice it will be retold in at Homecoming.

Zoom from the whole valley down to a keg on a porch. Watch for five minutes or five hours.
Meddle if you want.

## Run it

`the_row.html` is the entire thing — vanilla JS + Three.js from CDN, no build, no server.

- **Locally:** double-click `the_row.html`.
- **Hosted:** drop the file on any static host (Netlify, GitHub Pages). Nothing to configure.
- **Share a campus:** the seed lives in the URL hash (`#s=xxxxxx`). Same link, same campus,
  same history. *Copy link* button does this for you.

## Watching

- **AUTO (default):** a documentary auto-director finds the story — parties, strikes, prank
  wars, cows at large — flies the camera to it, and captions it. Time itself breathes: dead
  weekday afternoons fast-forward, Friday at 11 PM lingers.
- **Manual speeds:** ⏸ / ▶ porch / ▶▶ weekend / ▶▶▶ semester / ▶▶▶▶ saga (a year in minutes).
  Keys `1–4`, `5`/`A` for AUTO, space to pause.
- **Camera:** drag to orbit, right-drag to pan, scroll to zoom. Any input politely suspends the
  director for 45 seconds. `C` hides the UI (watch mode), `D` toggles the director.
- **Click things:** houses, rentals, sorority houses. House cards show the ledger — prestige,
  brotherhood, GPA, treasury, strikes — the roster by class year, and the **composite**
  (procedurally drawn oval portraits, blazers and all, per house per year).
- **The Chronicle** (right panel): the permanent record, written retrospectively, clickable —
  each entry flies the camera to where it happened. *Save* exports the whole saga as a `.txt`.

## Meddling

The **Meddle** drawer (bottom right): issue or forgive strikes, send the Dean down the Row on a
Friday night, wire alumni money, book a big act at the pavilion, pull a landlord's lease, play
Cupid, spark a prank war, rain out a weekend, start mono season, let the livestock loose, march
the cadets through campus, flood the river, re-charter a dark house. Every act has a cooldown;
the campus needs time to recover, and so does the Dean.

## The rules of the world

- **Three strikes.** The Dean's office issues strikes — for what gets *caught*, which is not the
  same as what *happens*. One strike: the house goes dry and the parties move to the pole houses
  on the river. Three: the letters come off the facade and the house goes dark, sometimes for
  years, until a colony class brings it back.
- **Everything is a ledger.** Prestige, brotherhood, GPA, treasury, landlord patience, sorority
  favor — all of it earned, spent, and lied about. Top house draws the most scrutiny.
- **People persist.** ~450 named students age freshman → senior → alumni. They pledge, mix,
  fall in love, break up, road-trip to the women's colleges, get chanted at on porches, and
  graduate on the Colonnade lawn. The nicknames are permanent. That's the point of nicknames.
- **Grave things are written gravely.** Honor hearings and real disgraces get no punchlines.

## Dev notes

Deterministic per seed: four segregated RNG streams (worldgen / history / names / ambient), so
camera work and frame rate can never change what happens. Console harness: `SIM.fastSim(years)`
runs headless (a decade in ~1s), `SIM.audit()` snapshots the ledgers, `SIM.hash()` fingerprints
the chronicle for golden-seed regression. Rendering: merged vertex-colored geometry + instancing,
~60–90 draw calls, hemisphere + sun + a hard cap of 4 party point lights.

The design document this grew from is in [`The Row - Game Design Document.md`](./The%20Row%20-%20Game%20Design%20Document.md).
