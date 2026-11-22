<p align="center"><img src="images/cover.jpg" alt="Games made with Claude Code using this skill: Streetball, Gummy the Fisherman, FoxKarts, Clue Quest, Penalty Star, Foxino Adventures" width="100%"></p>

# Game Skill for Claude Code

**A skill that makes Claude Code build a game the way a small studio would:** it asks the few questions that change everything (2D or 3D, how polished, which image tool, how many triangles, Blender or code, what light), then follows budgets, an art pipeline, game-feel rules, testing and publishing that were learned by shipping 20+ browser games with Claude Code.

It was distilled from **155 game-development skills** (engines, Blender, art, audio, AI, genres, publishing) and from the games in the gallery below.

## ⬇️ Download

| | |
|---|---|
| **[game-skill.zip](https://github.com/michalzasilka-art/game-skill/releases/latest/download/game-skill.zip)** | the skill, ready to unzip into your skills folder |
| [download/game-skill.zip](download/game-skill.zip) | the same file inside this repo |

### Install

```bash
unzip game-skill.zip -d ~/.claude/skills/
```

Or from a clone:

```bash
git clone https://github.com/michalzasilka-art/game-skill.git && cp -r game-skill/game-skill ~/.claude/skills/
```

Then ask Claude Code something like *"make me a game where a fox races go-karts"*. The skill starts by itself when you ask to make, prototype or remake a game, a level or a mode.

## How it works

<p align="center"><img src="images/how-it-works.svg" alt="How the skill works: round 1 questions, round 2 for 2D or 3D, each step done alone, test everything once, publish once" width="100%"></p>

## The questions it asks

Asked with Claude Code's question cards, the recommended option first. Anything your prompt already says is skipped. Say *"no questions"* and it picks the recommended options.

### Round 1 — every game

| Question | Options |
|---|---|
| **2D or 3D?** | 3D (sports, racing, adventure) · 2D (puzzle, cards, quiz, platformer, arcade) |
| **Should I take the time to make it the final version?** | Quick prototype (~1 h, rules first, greybox) · In between (a few hours, real hero art) · Final version (long session, everything, no more questions) |

### 2D

| Question | Options |
|---|---|
| **What should I use for image creation?** | ChatGPT / GPT Image *(recommended)* · Higgsfield · Gemini (Nano Banana) · Code-drawn, no AI |
| **Should I take the time to make it the final version?** | asked in round 1 |
| Art style *(only if unclear)* | flat cartoon · painted · pixel art · clean vector |
| Engine *(only for a new project)* | Canvas / Phaser *(web, recommended)* · PixiJS · Godot |

### 3D

| Question | Options |
|---|---|
| **How many triangles MAX?** (per frame, busiest view, shadows included) | 100k phones & web *(recommended)* · 30–50k extreme low poly · 300–500k desktop web · 1M+ PC / console |
| **Blender MCP or code modelling?** | Mix: code world + Blender/AI characters *(recommended)* · Blender MCP · Code modelling · AI 3D generator (Tripo / Higgsfield / Meshy) |
| **Lighting?** | Warm low sun *(recommended)* · Bright day / cartoon · Night / neon · Indoor / studio |
| **What should I use for image creation?** | ChatGPT / GPT Image *(recommended)* · Higgsfield · Gemini · Code-drawn |
| **Should I take the time to make it the final version?** | asked in round 1 |

## One prompt, many steps

If your prompt has several steps (*"add a shop, fix the jump, new level, nicer menu"*), Claude:

1. splits it into numbered steps in the task list,
2. does **each step on its own, as if it were a separate prompt** — finishes it and smoke-checks it before starting the next,
3. **does not publish in between**,
4. **tests everything at once** after the last step (one full playthrough on a phone size and a wide screen),
5. **publishes once** — one deploy, one tag, one changelog entry listing every step.

## Budgets it enforces (3D, 100k choice)

| Slot (one phone frame) | Budget |
|---|---|
| Hero character | 5–9k triangles (20k is a ceiling, not a target) |
| Rival / second character | 3–9k |
| Crowd / NPCs | 300–1,000 each, ≤ 10–20k together, instanced, no shadows |
| Near set + ground | 25–35k |
| Far background | 5–10k (painted sky dome) |
| Props | 15–20k together |
| Shadow pass | 10–20k |
| Spare | 10 % |
| Animation clips | ≤ 20 per character, in place, one skeleton |
| Draw calls | < 150 |

Other choices (30k, 300k, 1M+) have their own column in [`references/3d.md`](game-skill/references/3d.md).

## Example images — games made with Claude Code

All of these were built with Claude Code following the rules in this skill (browser games for [fugio.co](https://www.fugio.co)).

### 2D games

| | |
|---|---|
| <img src="images/2d/gummy-the-fisherman.jpg" width="100%"><br>**Gummy the Fisherman** — whiteboard party game, DOM + canvas, ChatGPT backgrounds, Higgsfield character loops | <img src="images/2d/clue-quest-teacher-board.jpg" width="100%"><br>**Clue Quest** — pixel-art host screen; students answer on their phones |
| <img src="images/2d/clue-dive-board-and-phones.jpg" width="100%"><br>**Clue Dive** — the class board next to two phone screens | <img src="images/2d/timber-town.jpg" width="100%"><br>**Timber Town** — pixel-art canvas game |
| <img src="images/2d/tug-of-words-screens.jpg" width="100%"><br>**Tug of Words** — painted 2D, two players at one board | <img src="images/2d/tile-dash.jpg" width="100%"><br>**Tile Dash** — Vite + TypeScript board race, 2–8 teams |

### 3D games

| | |
|---|---|
| <img src="images/3d/streetball.jpg" width="100%"><br>**Streetball** — three.js, Blender models, 20 clips per player, ~25k-triangle court | <img src="images/3d/penalty-star.jpg" width="100%"><br>**Penalty Star** — answer bubbles in the goal, instanced crowd |
| <img src="images/3d/foxkarts-alps-tracks.jpg" width="100%"><br>**FoxKarts** — kart racer, tracks and karts modelled in code | <img src="images/3d/foxkarts-garage.jpg" width="100%"><br>**FoxKarts garage** — 3D scene + game UI |
| <img src="images/3d/sky-dive.jpg" width="100%"><br>**Sky Dive** — fall through the ring with the right word | <img src="images/3d/foxino-adventures-phone.jpg" width="100%"><br>**Foxino Adventures** — the first phone preview (9:16) |

### Model renders (Blender MCP, Blender on a PC, code)

| | |
|---|---|
| <img src="images/models/test-man-20-clips.jpg" width="100%"><br>**Test Man** — 458-triangle grey prototype character with 20 in-place clips | <img src="images/models/pit-garages-blender.jpg" width="100%"><br>**Pit garages** — five themed garages made in Blender |
| <img src="images/models/rear-wings.jpg" width="100%"><br>**Rear wings** — nine variants on one kart | <img src="images/models/led-tyres.jpg" width="100%"><br>**LED tyres** — six tyre and rim designs |
| <img src="images/models/hover-kart-blender.jpg" width="100%"><br>**Hover kart** — Blender model on a track | <img src="images/models/foxspy-paris-kit.jpg" width="100%"><br>**FoxSpy Paris kit** — low-poly museum room kit |

<p><img src="images/models/alps-mountains.jpg" width="100%"><br><b>Alps mountains</b> — low-poly far-background pieces (5–10k triangle slot)</p>

### Art, style frames and UI (ChatGPT / Higgsfield)

| | |
|---|---|
| <img src="images/art/temple-style-frame.jpg" width="100%"><br>**Style frame** — the approved look for a 3D level, made before any model | <img src="images/art/foxkarts-lobby-mockup.jpg" width="100%"><br>**Lobby mock-up** — symmetrical menu with one big PLAY |
| <img src="images/art/clue-dive-poster.jpg" width="60%"><br>**Poster** — library art for a new game | <img src="images/art/nitro-ui-icons.jpg" width="100%"><br>**UI icons** — nitro canister, button ring, burst |

<p><img src="images/art/library-posters.jpg" width="100%"><br><b>Library posters</b> — one consistent poster style for every game</p>

## What's inside

```
game-skill/
├── SKILL.md                       the checklist Claude follows (questions → build → test → publish)
└── references/
    ├── 2d.md                      engines, screen layout, sprite pipeline, animation, budgets
    ├── 3d.md                      triangle budgets per choice, Blender MCP, code modelling (three.js), AI 3D, lighting code, camera
    ├── image-tools.md             ChatGPT vs Higgsfield vs Gemini vs Tripo vs code-drawn, prompt templates
    ├── testing-publishing.md      Playwright playthrough, worst cases, deploy, live checks
    └── skill-index.md             the 155 skills it was built from, and which ones each answer pulls in
```

The skill works on its own. If you also have the specialised skills from `skill-index.md` installed (three.js, Blender, Godot, Unity, Phaser, sprite-gen, Higgsfield…), it tells Claude which ones to load and when.

## Related

- **[foxino-game-skill](https://github.com/michalzasilka-art/foxino-game-skill)** — the same skill made specific for [fugio.co](https://www.fugio.co) and Foxino: English-learning games for students, teachers, and teacher + students together.

## License

MIT — see [LICENSE](LICENSE). Game screenshots and art in `images/` show the author's own games and stay © their owner; they are here as examples only.
