# Mythic Flow Studio — landing site

Studio showcase for Mythic Flow Studio (https://mythicflowstudio.com). Purpose: promote ALL the studio's games through **gameplay highlights**.

## Structure
- `index.html` — the whole site (HTML/CSS/JS inline). No build step, no framework.
- `assets/media/` — highlight clips (`*.mp4`, H.264, no audio, faststart) + `*-poster.jpg`.
- `assets/img/` — app icons, favicon, `og-image.jpg` (1200x630 share image).
- `CNAME` points GitHub Pages at the custom domain. **Never remove or rename it.**

## Content rules
- Real in-game footage only. No drawn/SVG gameplay stand-ins, no "clip coming" placeholders.
- Short highlight clips (~5–13 s loops), not long footage. Keep each web clip ≲1.2 MB.
- Exception: the Apex Dragon trailer (`assets/media/apexdragon-trailer.mp4`, 720p, 61 s, ~16 MB) plays only on demand, in the `#apex-trailer` dialog opened by the game's "Watch the trailer" button (`preload="none"`).
- Mobile first: the owner presents the site from a phone at conventions. Each game's footage has a full-screen button for that.
- Studio-level copy is genre-neutral; each game's pitch lives in its own section.
- Games:
  - **BEAMLOCK** — Android laser-routing puzzle, 200 levels, status "In closed testing".
  - **Apex Dragon** (final name; on Google Play as "Apex Dragon: Evolution .io") — Android top-down .io-style dragon arena. Stages Hatchling → Whelp (dash) → Juvenile (fire breath) → Young Dragon → Adult → Elder → Apex. Online multiplayer, free-for-all (owner confirmed 2026-09-26 that it runs online). Status "On Google Play" (production release sent for review 2026-11-07); its main button is "Get it on Google Play" (https://play.google.com/store/apps/details?id=com.daniel.apexdragon).
- Adding a game: copy one game section (see the HTML comment "HOW TO ADD A GAME").

## Design rules ("river" design)
- The look comes from the studio logo: white tribal strokes on near-black, and a river. Colour appears only in the game footage, in the soft glow behind it, and in each game's `--accent`.
- The logo emblem is one inline SVG symbol (`#emblem`, traced from the logo); reuse it with `<use href="#emblem">`, never redraw it.
- **One river** runs down the whole page. It starts as the river drawn in the logo, visits every island and ends by circling the pool in the studio section. The script at the bottom works it out and draws it (see "THE RIVER" there; settings in `RIVER`).
  - `[data-river-source]`: the hero emblem. The river continues the logo's own river: `RIVER.mouth` holds where that river leaves the emblem, in the emblem's drawing units. If the emblem art ever changes, those numbers must be measured again.
  - `[data-river-island]`: a footage frame. The river finds it by itself, flares onto it and wraps it. Lab prototypes (`#lab .lab-media`) are islands too, round ones.
  - `[data-river-via]`: a gap between two blocks of text that the river must run straight down (wide screens only).
  - `[data-river-pool]`: where the river ends.
- Nothing that holds an island or a glow may get a `transform`, `opacity`, `z-index` or scroll-reveal class (`.rv`): the river is drawn where the island is measured to be, in a layer under the content.
- Wide screens: text sits on the two banks of the river. Phones (under 900px): the river runs down the left edge and the islands lie on it.
- Each game is one `section.game`: `game--wide` for landscape footage, `game--tall` for phone-shaped footage. See the "HOW TO ADD A GAME" comment in `index.html`.
- Colors: `--void`, `--ink`, `--mist`, `--rule` for the studio; `--beam`, `--amber` for the games. `--bg-deep`, `--bg-panel`, `--line`, `--dim` stay defined because the Forge lab block uses them.
- Font: `Montserrat` only (600 for the wordmark, as in the logo; 700/800 for headings; 400 for text). Small labels are Montserrat 600, uppercase, widely spaced.
- The prototype lab block between the `forge:lab` markers is written by Mythic Forge. Style it from the page's own CSS under `#lab`; don't edit the block. Keep the `forge:lab` and `forge:lab-nav` marker pairs, `</main>` and the exact `STUDIO` comment line: Forge looks for them when it publishes.

## Preview
`python -m http.server` in this folder, then http://localhost:8000 (file:// won't play some videos reliably).

## Deploy
Commit and push to `main`. GitHub Pages rebuilds in ~1 minute.

## Out of scope
DNS / Namecheap settings live outside the repo and already work — don't touch.
