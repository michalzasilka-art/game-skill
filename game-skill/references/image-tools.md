# Image creation tools

Read before making any picture. The answer to "What should I use for image creation?" picks the tool; the rules at the bottom apply to all of them.

## Which tool for what

| Tool | Best at | Weak at | Typical use in a game |
|---|---|---|---|
| **ChatGPT / GPT Image** | following long instructions, keeping a character consistent from a reference picture, readable text (logos, UI labels), clean edits ("same picture, but…") | exact pixel sizes, true transparency (check it), very wide panoramas | style frames, character sheets, 3D reference pictures (front A-pose), UI icons, posters, library tiles, painted skies |
| **Higgsfield** (`higgsfield-generate`) | many models in one CLI: GPT Image, Nano Banana (cartoon characters), Seedance (video), image-to-3D (GLB), sound effects and music | costs credits per generation; pick the model on purpose | animated loops and cutscenes from approved stills, cartoon character variations, quick 3D props, SFX |
| **Gemini (Nano Banana)** | fast drafts and edits, many variations quickly | less exact with long style rules | first idea boards, quick variations before the final picture in another tool |
| **sprite-gen skill** (GPT / Grok) | sprite rows, cleanup, chroma removal, animation atlases, video loops | needs its CLI installed | 2D animated characters, sprite sheets |
| **Tripo / Meshy / Higgsfield 3D** | image → 3D model, smart low-poly mesh, auto rig | topology and texture quality vary | characters and props from an approved reference |
| **Code-drawn** (SVG, canvas, procedural) | crisp at any size, free, tiny files, exact control | painterly / detailed art | prototypes, UI shapes, particles, geometric styles, placeholder art |

## Prompt templates

**Style frame (the master reference)**
> A mock screenshot of a [2D / 3D low-poly] mobile game in portrait 9:16. [Scene]. Art style: [flat pastel low-poly with big clean facets / painted cartoon / pixel art 16-bit]. Palette: [list 8–12 hex colours]. Soft warm light from the low left, coloured violet shadows. Large readable shapes, uncluttered, room at the bottom for 2–4 big answer buttons. No text, no UI.

**Character sheet / 3D reference**
> [Character] full body, front view, A-pose (arms 45° down), standing straight, neutral expression, plain pure white background, even flat lighting, no shadows, flat [low-poly] colours, the whole body in frame with space around it. Style matching the attached style frame.
Then the same prompt for side and back views, attaching the front view.

**Sprite / asset**
> [Object] for a [style] game, matching the attached style frame and palette, centred, on a flat pure magenta (#FF00FF) background for keying, no shadow on the ground, no text.

**Painted sky (3D)**
> A wide equirectangular panorama sky for a game, [time of day], soft painterly clouds, palette [hex list], horizon colour [hex] at the middle, no ground, no objects, seamless left-right.

**Poster / library tile**
> Game poster for "[Title]": [hero] in [action pose] in [scene], the title "[Title]" in bold friendly lettering at the top, [palette], square 1:1 (or 3:4).

## Rules for every tool

1. **Style first.** Make and approve one style frame (and a character sheet for characters) before any other asset. Every later prompt attaches it.
2. **Approval before 3D.** A character never goes to Blender or an AI 3D tool before the user approves its reference picture.
3. **Check transparency yourself** (open the alpha channel). Generate on flat magenta/green when you need cut-outs.
4. **Name and file it the same day:** `<game>/art/<what>-<version>.png`; keep originals outside the build, optimised copies (WebP) inside it.
5. **Keep a manifest** of tool, model, prompt, date and licence for each asset.
6. **Budget credits:** draft cheaply (Gemini / low settings), finish with the best model only once the direction is approved.
7. **No real people, logos or other games' characters** in prompts unless the user owns them.
