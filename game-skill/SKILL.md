---
name: game-skill
description: Makes a new game with Claude Code from idea to published build. First asks the right questions (2D or 3D; final version or quick prototype; which tool makes the images; for 3D also the max triangles, Blender MCP or code modelling, and the lighting), then follows the budgets, art pipeline, game-feel, testing and publishing rules learned from 20+ shipped web games. Handles prompts with several steps by doing each step on its own and testing + publishing everything once at the end. Use whenever the user asks to make, start, prototype, remake or "create a game", a level, a mode or a mini-game, in any engine.
---

# Game Skill

A working checklist for making a game with Claude Code. It was distilled from ~155 game-development skills (engines, Blender, art, audio, AI, publishing) and from 20+ browser games built and published with Claude Code (three.js, Phaser, canvas, Unity WebGL).

Follow it in order: **0 → 1 → 2 (2D) or 3 (3D) → 4 → 5 → 6 → 7.**

Deeper notes live in `references/`:

| File | Read it when |
|---|---|
| `references/2d.md` | the game is 2D (engines, resolution, sprites, animation, budgets) |
| `references/3d.md` | the game is 3D (triangle budgets, Blender MCP, code modelling, AI 3D, lighting code) |
| `references/image-tools.md` | you are about to make any picture (style frames, sprites, skies, UI, posters, 3D references) |
| `references/testing-publishing.md` | before you test or publish |
| `references/skill-index.md` | you need a specialised skill (engine API, Blender task, genre, store publishing) |

---

## 0. One prompt, many steps — do each step alone, test and publish once

Users often put several things into one prompt ("add a shop, fix the jump, new level, make the menu nicer"). Treat it like this:

1. **Split** the prompt into numbered steps and put every step into the task list before you start. Keep the user's order unless a step depends on a later one.
2. **Do each step as if it were its own prompt.**
   - Re-read only that step's words; read only the files it needs.
   - Finish it completely (code, art, data) before you touch the next step. Never half-do two steps at once and never mix their changes.
   - Give it a quick local check of its own (it loads, no console errors, the feature does what the step asked). This is a smoke check, not the full test.
   - Mark it done in the task list, then move on.
3. **Do not publish between steps.** No deploy, no push, no store upload, no "it's live" message while steps are still open.
4. **After the last step, test everything at once** (section 6): one full playthrough that covers every step, on a phone size and a wide screen, with screenshots and the numbers.
5. **Publish once** (section 7): one deploy, one commit/tag, one changelog entry that lists every step.
6. If the full test breaks something, fix it, run the **whole** test again, then publish. Report per step what was done and how it was checked.

The same applies to a long brief: each numbered item in the brief is one step.

---

## 1. Ask first (unless the request already answers it)

Use the `AskUserQuestion` tool. Put the recommended option first and mark it "(Recommended)". Skip any question the request or memory already answers. Never ask more than these; when the user says "no questions", pick the Recommended options and write the choices into the plan.

### Round 1 — both kinds of game (one call, 2 questions)

1. **2D or 3D?**
   - **3D** — sports, racing, adventure, exploring, anything with a camera that moves through space.
   - **2D** — puzzles, card/board games, quizzes, platformers, arcade, visual novels.
   - Recommend the one that fits the idea; if both fit, recommend 2D (faster, cheaper, fewer ways to fail on phones).
2. **Should I take the time to make it the final version?**
   - **Quick prototype (~1 hour)** — the rules working first: greybox / code shapes, placeholder art, one mode, playable. Recommended when the idea or the mechanic is new and nobody knows yet if it is fun.
   - **In between (a few hours)** — real hero art and the look, a simple level/set, one polish pass, a phone test.
   - **Final version (take the time, long session)** — everything: the art pipeline, models, sounds, juice, menus, camera, full testing, published. Recommended when the user describes a complete game or says it is for real players. After this answer, ask no further questions: choose the Recommended defaults yourself and write them down.

### Round 2 — 2D (one call, up to 3 questions)

1. **What should I use for image creation?** (details and prompts: `references/image-tools.md`)
   - **ChatGPT / GPT Image (Recommended)** — follows instructions best, consistent characters from a reference, readable text in logos and UI, clean edits.
   - **Higgsfield** — many models in one place (GPT Image, Nano Banana for cartoon characters, Seedance video for animated loops and cutscenes, sound effects). Costs credits.
   - **Gemini (Nano Banana)** — fast idea drafts and edits; good for first style explorations.
   - **Code-drawn, no AI** — SVG / canvas shapes and procedural art. Free, crisp, tiny files; best for a prototype or a geometric style.
2. **Art style?** (ask only if the request doesn't say) — flat cartoon / painted / pixel art / clean vector UI-style.
3. **Engine?** (ask only if there is no project yet and the platform isn't obvious) — plain Canvas or Phaser for the web (Recommended for phones and sharing a link), PixiJS for heavy sprite counts, Godot for desktop/mobile apps.

### Round 2 — 3D (one call, 4 questions)

1. **How many triangles MAX?** (counted per frame, in the busiest view, shadow pass included)
   - **100k — phones and the web (Recommended)** — runs on a mid-range phone in a browser; hero character 5–9k.
   - **30–50k — extreme low poly / old phones** — ISLANDERS-style big facets, characters 1–3k.
   - **300–500k — desktop browser / low-end PC** — more detail, still one download.
   - **1M+ — PC / console build** — LODs and culling become mandatory.
2. **Blender MCP or code modelling?**
   - **Mix (Recommended)** — code builds the world (ground, track, buildings, props, effects); Blender MCP or an AI 3D generator makes the characters and hero props.
   - **Blender MCP** — real meshes, UVs, rigs and animation in the user's live Blender, exported as GLB/FBX. Best quality; needs Blender + the MCP add-on running.
   - **Code modelling** — models built from primitives in the game's code (three.js geometry, vertex colours, flat shading). Instant, tiny files, perfect for greybox and stylised low-poly.
   - **AI 3D generator** — Tripo / Higgsfield 3D / Meshy from an approved reference picture, then cleaned and packed.
3. **Lighting?** (code for each: `references/3d.md`)
   - **Warm low sun (Recommended)** — golden-hour sun with long soft shadows, warm sky + coloured ground fill, a cool rim light, fog in the sky's horizon colour. The classic stylised low-poly look.
   - **Bright day / cartoon** — high sun, short shadows, strong ambient; or unlit / toon bands. Cheapest on phones.
   - **Night / neon** — dark blue ambient, moonlight, emissive lamps and signs with glow (bloom only on real lights).
   - **Indoor / studio** — 3-point light for rooms, menus and character showcases.
4. **What should I use for image creation?** (style frames, character references for 3D, painted skies, textures, UI, posters) — same options as 2D: ChatGPT / GPT Image (Recommended), Higgsfield, Gemini, code-drawn.

### Second-set questions — only when the answer isn't obvious

Default them silently otherwise:
- **Platform and screen:** phone portrait 9:16 first; it must also work at 16:9. Browser unless the user names a store.
- **Players:** solo (vs a simple AI) by default; local friend / online only if asked.
- **Audience:** kids or casual players → no reflex or memory pressure in core decisions (see section 5).
- **Session length:** 3–5 minute rounds for casual/mobile.

After the answers: write a short plan into the task list (the steps from section 0), then start.

---

## 2. 2D — what the answers mean

Full notes: `references/2d.md`.

- **Design resolution:** 1080×1920 portrait (or 1920×1080 landscape) with a safe area; scale to fit, never stretch. Test at 390×844 and 1280×720.
- **Style first, assets second:** one palette of 12–20 hex colours, one style frame approved by the user, one character sheet. Every later picture is made *from* those references so everything matches.
- **Sprites:** real alpha (check the alpha channel — AI images often fake transparency with a drawn checkerboard or a white box). Make them at 2× their on-screen size, export WebP, pack into atlases ≤ 2048 px for phones.
- **Animation:** 6–12 fps frame animation for characters, tweens (squash, stretch, bounce) for everything else; short video loops (MP4/WebM, muted, `playsinline`) for cutscenes and living backgrounds.
- **Budget:** first load ≤ ~10 MB on a phone, 60 fps on a mid-range phone, every image lazy-loaded after the menu.
- **Prototype:** coloured rectangles and circles, real rules, placeholder sounds. **Final:** full art set, menu scene, juice, sounds, cutscenes if the story needs them.

## 3. 3D — what the answers mean

Full notes and code: `references/3d.md`.

### 3a. Triangle budget (example for the 100k choice; scale the rows for the other choices)

| Slot (one frame) | Budget | Notes |
|---|---|---|
| Hero character | 5–9k (20k is a ceiling, not a target) | detail where the camera looks: face, hands, hero prop |
| Second character / rival | 3–9k | |
| Crowd / NPCs | 300–1,000 each, ≤ 10–20k together | instanced, no shadows |
| Animals | 1–3k each | |
| Near set + ground | 25–35k | |
| Far background | 5–10k | painted sky dome, instanced far hills |
| Props | 15–20k together | ball 200–500, rock 20–80, bush 80–320, tree 200–800 |
| Effects | 1–3k | instanced quads / sprites |
| Shadow pass | 10–20k | only near things cast shadows |
| Spare | 10 % | for the busiest moment |

Rules that apply to every choice:
- **Spend triangles wisely, never overshoot.** A model gets only what its job needs — a low-poly hero once came back at 229k triangles; 5k looked the same.
- One material per model if possible (vertex colours or a small palette texture); one ≤ 1024 px texture per character.
- Fewer than ~150 draw calls on phones; repeated things in instanced meshes; static scenery merged per area.
- **Max 20 animation clips per character**, in place (no root motion), on one standard skeleton (Mixamo names), with the event frames written down (e.g. "frame 14: ball leaves hand").
- **Measure, don't guess:** in three.js read `renderer.info.render.triangles` right after the scene render (before post-processing). Say the number when you report.

### 3b. Blender MCP vs code modelling vs AI 3D

- **Blender MCP:** check `get_addon_status` + `get_scene_info` first, build with `execute_blender_code`, look at every result with `look`, run the asset QA (normals, floating parts, scale, tris) before export, export GLB, then pack it (`gltfpack -cc -kn -km`).
- **Code modelling:** primitives with few segments (cylinders 6–12 sides), flat shading for scenery and smooth for characters, each face ±10 % shade, merged per material, instanced when repeated. Export to GLB once it's final if other tools need it.
- **AI 3D:** reference picture (front, A-pose, white background, flat colours) → **user approval** → generator with a polygon target ~20 % below the budget → retopo/re-bake instead of a blind Decimate → rig → pack → check tris, scale, facing (+Z) and clip names.
- **Mix:** do the code world first with a grey test character, so movement and camera are right before the real character arrives with the same clip names.

### 3c. Lighting and camera

- Lighting presets with numbers: `references/3d.md`. Whatever the preset: one key light that casts shadows, a coloured fill (hemisphere), fog that matches the sky's horizon colour, tone mapping on (ACES/AgX), pixel ratio ≤ 2.
- **Camera:** FOV 58–62° in portrait, 46–48° in landscape, picked from the aspect ratio; close third person (behind the shoulder, 1.2–3 m high), looking slightly ahead of the player; keep it inside rooms and out of characters (ray checks); short cinematic cut-ins for big moments.

---

## 4. Look and menus (both 2D and 3D)

- **Style guide before models:** palette of 12–20 colours per place, soft and coherent; no pure black, pure white or neon except as accents; coloured shadows (violet or warm brown) instead of grey.
- **Silhouette first:** players must read every object from its shape at phone size.
- **The menu is the front door:** a real scene with the hero in it, the logo, the game's palette and light — never a flat form. Symmetrical (logo, hero and PLAY on one vertical axis; pairs mirrored), one big PLAY button plus at most 2–3 secondary actions, labels of 1–3 words, everything else behind an icon.
- Check the menu at 390×844 and 1280×720: left and right halves mirror each other; nothing unimportant on screen.

## 5. Game feel

Load the `game-feel` and `camera-systems` skills if installed. The essentials:
- **Juice on every important action:** a popup word (PERFECT / GREAT / GOOD), a combo counter, particles, a short hit-stop and screen shake, a flash, a phone vibration, a sound. A soft, clear "oops" on mistakes — never harsh.
- **The decision moment stays still:** when the player has to choose, freeze the camera and show the choices big and readable; react the moment they choose.
- **No reflex or memory pressure in the core decision** for kids and casual games: no "tap NOW", no words that vanish, no countdown bars on answers. The challenge comes from the content, not the clock.
- **Game time, not wall time:** every wait counts frames/delta time (`wait(seconds)` inside the loop), never `setTimeout`, so slow phones never race.
- **Physics serves the outcome:** real bounces and collisions, but a scripted result is guaranteed (a "miss" can't drop in; a "hit" aims true).
- **Animation never flickers:** pick clips with hysteresis and a ~0.3 s minimum hold; cross-fade 0.2 s; turn characters with a damped yaw.

## 6. Test everything (once, after the last step)

Full checklist: `references/testing-publishing.md`.
- Headless browser (Playwright) at **390×844** (phone) and **1280×720**: play a full round with scripted input, screenshot every ~0.3 s, look at the contact sheets yourself.
- No page errors or failed requests; 60 fps target, still playable at CPU ×4–8 throttle.
- 3D: report the triangle count of the busiest view. 2D: report the first-load size.
- Worst-case content: the longest text, the smallest screen, many objects at once.
- **Verify it yourself.** Never ask the user to check something you can check.

## 7. Publish (once)

- Web: Vercel / Netlify / GitHub Pages / itch.io (`itch-publish`). Stores: Steam (`steam-publish`), Unity/Godot/Unreal export skills.
- Bump cache-busting versions (`script.js?v=N`) on every changed file; check the live URLs return 200 and the live files match.
- Commit, tag the version, push; write a changelog entry listing every step from section 0 and how it was tested.
- Make a cover image / poster for the game page if it is new.

## 8. Before saying "done"

- [ ] Every step of the prompt was done on its own and is listed in the report.
- [ ] One full test covered all steps; phone + wide screenshots looked at; no errors.
- [ ] 3D: busiest view ≤ the chosen triangle max (say the number); ≤ 20 clips per character. 2D: first load size said.
- [ ] The menu is symmetrical and shows only the important things.
- [ ] Published once; live URLs checked; tag + changelog written.
