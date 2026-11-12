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
- Exception: the Apex Dragon trailer (`assets/media/apexdragon-trailer.mp4`, 720p, 61 s, ~16 MB) plays only on demand, in the `#apex-trailer` dialog opened by the card's "Watch the trailer" button (`preload="none"`).
- Mobile first: the owner presents the site from a phone at conventions. Each game's footage has a full-screen button for that.
- Studio-level copy is genre-neutral; each game's pitch lives in its own card.
- Games:
  - **BEAMLOCK** — Android laser-routing puzzle, 200 levels, status "In closed testing".
  - **Apex Dragon** (final name; on Google Play as "Apex Dragon: Evolution .io") — Android top-down .io-style dragon arena. Stages Hatchling → Whelp (dash) → Juvenile (fire breath) → Young Dragon → Adult → Elder → Apex. Online multiplayer, free-for-all (owner confirmed 2026-09-26 that it runs online). Status "On Google Play" (production release sent for review 2026-11-07); the card's main button is "Get it on Google Play" (https://play.google.com/store/apps/details?id=com.daniel.apexdragon).
- Adding a game: copy one scene block and the bend before it (see the HTML comment "HOW TO ADD A GAME").

## Design rules ("river" design)
- The look comes from the studio logo: white tribal strokes on near-black, and a river. The logo emblem is one inline SVG symbol (`#emblem`, traced from the logo); reuse it with `<use href="#emblem">`, never redraw it.
- One river runs down the whole page, from the dragon in the hero to the pool in the studio section. The script at the bottom draws it (`RIVER` settings at the top of that part). On wide screens it runs down the middle, with text on the two banks; on phones it runs down the left edge.
- Each game is a full-screen scene (`section.scene`), with a `div.bend` of open water before it. A scene sets `--accent` (a color token) and `--world` (its deep background color). See the "HOW TO ADD A GAME" comment in `index.html`.
- Studio colors: `--void`, `--ink`, `--mist`, `--rule`. Game colors: `--beam`, `--beam-deep`, `--amber`. `--bg-deep`, `--bg-panel`, `--line`, `--dim`, `--hot` stay defined because the Forge lab block uses them.
- Fonts: `Manrope` (800 uppercase for headings, like the logo's wordmark; 400/700 for text), `JetBrains Mono` (`.mono`, `.kicker`).
- The prototype lab block between the `forge:lab` markers is written by Mythic Forge. Style it from the page's own CSS under `#lab`; don't edit the block.

## Preview
`python -m http.server` in this folder, then http://localhost:8000 (file:// won't play some videos reliably).

## Deploy
Commit and push to `main`. GitHub Pages rebuilds in ~1 minute.

## Out of scope
DNS / Namecheap settings live outside the repo and already work — don't touch.
