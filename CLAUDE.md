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
- Mobile first: the owner presents the site from a phone at conventions. The highlight reel has a full-screen button for that.
- Studio-level copy is genre-neutral; each game's pitch lives in its own card.
- Games:
  - **BEAMLOCK** — Android laser-routing puzzle, 200 levels, status "In closed testing".
  - **Apex Dragon** (working title; Unity productName "Territorial Dragon") — Android top-down .io-style dragon arena. Stages Hatchling → Whelp (dash) → Juvenile (fire breath) → Young Dragon → Adult → Elder → Apex. Online multiplayer, free-for-all (owner confirmed 2026-09-26 that it runs online). Status "In development".
- Adding a game: copy one game card block (see the HTML comment "how to add a game") and one reel slide.

## Design rules
- Colors come from the `:root` CSS variables (`--bg-deep`, `--bg-panel`, `--bg-raised`, `--line`, `--beam`, `--beam-deep`, `--hot`, `--dim`, `--amber`). Reuse them; don't invent new colors.
- Fonts: `Baloo 2` (headings), `Manrope` (body), `JetBrains Mono` (`.mono`).

## Preview
`python -m http.server` in this folder, then http://localhost:8000 (file:// won't play some videos reliably).

## Deploy
Commit and push to `main`. GitHub Pages rebuilds in ~1 minute.

## Out of scope
DNS / Namecheap settings live outside the repo and already work — don't touch.
