# Testing and publishing

Run this **once, after every step of the prompt is done** (see `SKILL.md` section 0). Then publish once.

## 1. Full test

**Automated playthrough (Playwright, headless Chromium)**
- Viewports: **390×844** (phone, `isMobile: true, hasTouch: true`), **360×640** (small phone) for text-heavy screens, **1280×720** (wide).
- Play one complete round / match / level with scripted input (right and wrong choices, pausing, restarting).
- Screenshot every ~0.3 s and assemble contact sheets (e.g. 6×4 thumbnails per sheet). Look at every sheet: cut-off text, overlaps, flicker, camera inside walls, blank frames.
- Collect `page.on('pageerror')` and `console.error`; any error fails the test. Check failed network requests (404 assets).
- Slow phones: CDP `Emulation.setCPUThrottlingRate` ×4 and ×8 — the game must stay playable and never race ahead (game-time waits).
- Measure: average and worst frame time; 3D triangles in the busiest view (`renderer.info.render.triangles`); 2D first-load size (sum of transferred bytes until the menu is interactive).

**Worst cases**
- The longest text the game can show, the shortest, numbers, apostrophes, accented letters.
- The most objects at once (all enemies, full crowd, all particles).
- Rotate the phone; resize the window mid-game; background the tab and come back.
- Fresh load with an empty cache.

**Every step of the prompt**
- Make a list: step → how the playthrough proved it. A step with no proof isn't tested.

**Verify it yourself.** Don't ask the user to check what a screenshot or a script can check.

## 2. Publish once

1. Bump cache-busting versions on every changed file (`game.js?v=42`) or use hashed file names from the build.
2. Deploy (one of):
   - **Vercel:** `vercel deploy --prod --yes` (retry up to 3 times on a network error).
   - **Netlify / GitHub Pages / Cloudflare Pages:** their CLI or a push to the deploy branch.
   - **itch.io:** `butler push <dir> user/game:html5 --userversion X` (`itch-publish`).
   - **Steam:** SteamPipe build scripts (`steam-publish`).
   - **Engines:** `godot-export`, `unity-build-pipeline`, `unreal-packaging`.
3. Check live: the key URLs return 200; the live file hashes match the local build (fetch with a `?nocache=<time>` query); one quick live playthrough with no errors.
4. Git: commit, tag the version (`v1.4.0`), push. The changelog entry lists every step of the prompt, what changed and how it was tested.
5. New game: a cover / poster / store tile, a short description, and a link in the README.

## 3. Report to the user

- One line per step: what was done.
- The numbers: triangles or load size, fps, viewports tested.
- The live link(s) and the tag.
- Anything not done or not verified, said plainly.
