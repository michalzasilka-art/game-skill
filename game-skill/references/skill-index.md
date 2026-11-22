# Skill index

The 155 game-development skills this skill was built from, grouped by what they do. They are **not** bundled here: install the ones you need from their authors (most come from public skill collections such as the official Claude plugin marketplace, the Unity plugin, the blender-agent-skills set, Higgsfield and sprite-gen). When a skill below is installed, load it at the moment the checklist points to it; when it isn't, the checklist in `SKILL.md` still works on its own.

## Which skills each answer pulls in

| Answer | Load |
|---|---|
| 2D, web | `phaser-core`, `phaser-arcade-physics` or `pixijs-rendering`, `create-game-assets`, `game-ui-ux`, `game-feel` |
| 2D, Godot | `godot-2d-movement`, `godot-tilemap`, `godot-ui-control`, `godot-animation`, `godot-export` |
| 3D, web | `threejs-scene-setup`, `threejs-materials-lighting`, `threejs-gltf-loading`, `camera-systems`, `game-feel` |
| 3D, Unity / Unreal / Godot | `new-unity-project` + `unity-*`; `unreal-*`; `godot-3d-essentials` + `godot-*` |
| Image creation: ChatGPT / Gemini | `create-game-assets` (style guide, QA, licence records) |
| Image creation: Higgsfield | `higgsfield-generate` (+ `create-game-assets`) |
| Image creation: sprites | `sprite-gen`, `create-game-assets` |
| Blender MCP | `blender-core` first, then `blender-lpm-skill`, `blender-asset-qa`, `blender-game-optimization`, `blender-export-pipelines`; characters: `blender-character-rigging`, `blender-animation` |
| Code modelling | `threejs-scene-setup`, `procedural-gen`, `blender-game-optimization` (budgets) |
| AI 3D generator | `blender-retopology-uv`, `blender-texture-baking`, `blender-character-rigging`, `blender-asset-qa` |
| Lighting | `threejs-materials-lighting`, `blender-lighting-lookdev`, `blender-time-of-day`, `blender-stylized-npr`, `shader-programming` |
| Max triangles | `blender-game-optimization`, `performance-optimization` |
| Quick prototype | `prototype-fast`, `game-jam` |
| Final version | `game-feel`, `audio-design`, `game-ui-ux`, `game-docs`, `performance-optimization`, the publishing skills |

## Start here (5)

| Skill | What it does |
|---|---|
| `find-skills` | Helps users discover and install agent skills when they ask questions like "how do I do X", "find a skill for X", "is there a skill that can...", or express … |
| `game-docs` | Writes and maintains a game's design docs: a one-page GDD with a feature index and short feature notes, kept true to the code by a link and status checker. |
| `game-jam` | Plans and ships a game jam entry against a fixed deadline: reads the jam rules, scopes to the clock, keeps a cut list and checks the build before submitting. |
| `prototype-fast` | Builds a throwaway playable prototype in about an hour to answer one question, usually "is this mechanic fun?": a one-question brief, a greybox, a debug HUD,… |
| `router` | Routes any game-development request to the right skills: detects the engine (Godot, Unity, Unreal, Ebitengine, Bevy, Phaser, PixiJS, three.js, Defold, LÖVE, … |

## 2D engines (7)

| Skill | What it does |
|---|---|
| `defold-core` | Builds and debugs Defold 1.14 games in Lua: collections, game objects, input focus, msg.post messaging, factories, collection proxies and Bob builds. |
| `ebitengine-game` | Creates, debugs and packages 2D games in Go with Ebitengine v2: a play-and-retry loop, input, pixel-art scaling, text, audio and desktop, WASM or mobile builds. |
| `love2d-core` | Builds and debugs LÖVE (Love2D) 11.x games in Lua: main.lua callbacks, conf.lua, fixed steps, crisp pixel-art scaling, love.filesystem saves and a scripted run. |
| `phaser-arcade-physics` | Phaser 4 Arcade Physics movement and collision: bodies, velocity, gravity, colliders vs overlaps, groups and bullet pools. |
| `phaser-core` | Sets up and debugs Phaser 4 games (and pinned Phaser 3.90): Game config, Scene lifecycle, the loader, scene transitions and Phaser 3 to 4 migration. |
| `pixijs-rendering` | Builds and debugs 2D browser game rendering with PixiJS v8: async init, Assets loading, the Container and Sprite scene graph, pointer dragging and v7-to-v8 m… |
| `pygame-core` | Builds and debugs 2D games in Python with pygame-ce (imported as pygame): the event-update-draw loop, delta time, Surfaces and Rects, Sprite groups and headl… |

## 3D on the web (three.js) (3)

| Skill | What it does |
|---|---|
| `threejs-gltf-loading` | Loads glTF/GLB models into three.js r187 and plays their animations: GLTFLoader, DRACO, Meshopt and KTX2 decoders, AnimationMixer cross-fades and SkeletonUti… |
| `threejs-materials-lighting` | Lights and shades three.js r187 scenes: standard, physical and unlit materials, lights, shadows, HDR environment lighting and tone mapping. |
| `threejs-scene-setup` | Sets up and debugs a plain three.js r187 game or 3D scene: import maps, Scene, PerspectiveCamera and WebGLRenderer, setAnimationLoop with Timer, resize, Orbi… |

## Godot (16)

| Skill | What it does |
|---|---|
| `godot-2d-movement` | Godot 4.7 CharacterBody2D movement in GDScript: platformer run and jump, top-down 8-direction motion, slopes and one-way platforms, with a headless landing t… |
| `godot-3d-essentials` | Godot 4.7 3D scene setup: Camera3D, lights, WorldEnvironment (sky, ambient, tonemap, fog), StandardMaterial3D, GridMap and local vs global transforms, with a… |
| `godot-animation` | Godot 4.7 animation APIs: AnimationPlayer, AnimationTree state machines, AnimatedSprite2D and create_tween() Tweens, with a headless state test. |
| `godot-audio` | Godot 4.7 audio APIs: AudioStreamPlayer 2D and 3D, the bus layout, AudioServer volume and mute, polyphony, looping imports and playback position for beat sync. |
| `godot-csharp` | C# and .NET in Godot 4.7: partial node classes, the PascalCase lifecycle, [Export] and [Signal], signals as C# events, the .csproj and calling GDScript. |
| `godot-export` | Exports Godot 4.7 projects: templates, export_presets.cfg for desktop, Web and Android, command-line exports and web COOP/COEP headers. |
| `godot-gdscript` | GDScript 2.0 for Godot 4.7: static typing, @export and @onready, await and coroutines, and porting 3.x code. |
| `godot-gdscript-headless-testing` | Runs Godot 4.7 GDScript tests with godot --headless and a SceneTree runner that exits non-zero on failure, so CI can gate merges. |
| `godot-multiplayer` | Godot 4.7 high-level multiplayer: ENet host and join, @rpc with rpc_id(), MultiplayerSpawner and MultiplayerSynchronizer, with a two-instance headless test. |
| `godot-nodes-scenes` | Godot 4.7 scene-tree structure: reusable .tscn scenes, instantiate(), autoloads and a checker for broken res:// paths and uids. |
| `godot-physics` | Godot 4.7 physics API in 2D and 3D: body and Area types, collision_layer and mask bits, Area signals for hurtboxes, RayCast and space queries, and Jolt (3D d… |
| `godot-resources` | Godot 4.7 data-driven design with custom Resources: class_name and @export fields, .tres files, shared references vs duplicate_deep(), uids and threaded load… |
| `godot-shaders` | Godot 4.7 Shading Language syntax and pipeline: canvas_item, spatial and particle shaders, built-ins, ShaderMaterial wiring, a headless compile check and 3.x… |
| `godot-signals-groups` | Godot 4.7 signals and node groups: typed signals, connect() with Callables, one-shot and deferred connections, event-bus autoloads and call_group broadcasts. |
| `godot-tilemap` | Godot 4.7 tile maps with TileMapLayer and TileSet: atlas sources, data layers, terrain autotiling and set_cell or local_to_map at runtime. |
| `godot-ui-control` | Godot 4.7 Control-node API for menus and HUDs: anchors, Containers, Theme and StyleBox, focus neighbours and stretch settings, with a headless layout check. |

## Unity (11)

| Skill | What it does |
|---|---|
| `new-unity-project` | Guides creating a new Unity project, from concept, platforms, and monetization to source control and packages. |
| `unity-animation` | Unity 6.3 LTS character animation with the Animator (Mecanim): states and transitions, blend trees, Avatar Mask layers, root motion and humanoid IK. |
| `unity-build-pipeline` | Builds and ships Unity 6.3 LTS players: Build Profiles, IL2CPP vs Mono, managed stripping with link.xml, scripted BuildPlayer, Addressables and CI or headles… |
| `unity-build-size` | Finds and shrinks what makes a Unity 6.3 LTS build too big: Build Report reading, uncompressed textures, glTFast models, PCM audio and per-platform levers. |
| `unity-cli` | Controls Unity Editors and projects from the command line, including a running Editor. |
| `unity-csharp-scripting` | Writes and fixes Unity 6.3 LTS C# gameplay scripts: MonoBehaviour lifecycle, serialization, .meta/GUID discipline and command-line tests. |
| `unity-input-system` | Wires Unity 6.3 LTS player input with the Input System package: .inputactions assets, action maps, PlayerInput and control schemes. |
| `unity-navmesh` | Unity 6.3 LTS pathfinding with the AI Navigation package: NavMeshSurface baking, NavMeshAgent, NavMeshLink jumps and runtime rebakes. |
| `unity-physics` | Unity 6.3 LTS physics in 3D and 2D: Rigidbody and Rigidbody2D, forces and linearVelocity, the layer collision matrix and raycasts. |
| `unity-scriptableobjects` | Unity 6.3 LTS data and decoupling with ScriptableObjects: CreateAssetMenu config assets, shared runtime variables, event channels and .asset files made from … |
| `unity-tilemap-2d` | Unity 6.3 LTS 2D tilemaps: the Tile Palette, Tilemap Collider 2D with a Composite Collider, Rule Tiles and runtime SetTile. |

## Unity (official plugin) (33)

| Skill | What it does |
|---|---|
| `2d-pixel-perfect` | Sets up, diagnoses, and fixes pixel perfect 2D rendering with PixelPerfectCamera in URP or Built-in. |
| `asset-transformer-toolkit` | In the Unity Editor, imports 3D models and point clouds with Asset Transformer Toolkit (formerly Pixyz), and creates, edits, and runs RuleSets, Actions, and … |
| `audio-setup-mixers` | Routes Audio Sources into existing Audio Mixer Groups, classifying each source by what it plays. |
| `build-gtk` | Builds node-based Editor tools with Unity Graph Toolkit (GTK) on Unity 6.6+: graphs, nodes, ports and validation, State Machine API tools on 6.7+, and runtim… |
| `build-live-game` | Builds and operates a live game's backend with Unity Gaming Services. |
| `craft-game-floors` | Makes a Unity game look and feel finished: art style, lighting, juice, sound, menus, saves and look scoring. |
| `create-2d-physics` | Creates and fixes Unity 2D physics in both systems, 2D Physics Core and the legacy Rigidbody 2D system. |
| `create-tile-palette-or-rule-tiles` | Create a 2D tile palette from sprites or textures, or make tiles change based on their neighbours. |
| `generate-editor-search-query` | Generates Unity Search queries and opens the Search window to find assets or scene objects. |
| `implement-in-app-purchases` | Implements, configures, and debugs Unity In-App Purchases, including subscriptions, receipt validation, and direct-to-customer payments via Stripe or Coda. |
| `initialize-ai-navigation` | Sets up and configures Unity AI Navigation, including NavMesh surfaces, agents, obstacles, and links. |
| `levelplay-unity-integration` | Integrates the LevelPlay ad mediation SDK via the Ads Mediation package. |
| `localization` | Sets up and configures Unity Localization, including locales, String and Asset Tables, and CJK fonts. |
| `manage-sprite-atlas` | Manages SpriteAtlas assets through a prebuild pipeline, covering master and variant atlases, packing settings, and platform overrides. |
| `migrate-birp-to-urp` | Plans, executes, and troubleshoots migration from the Built-in Render Pipeline to URP. |
| `new-unity-project` | Guides creating a new Unity project, gathering concept, platforms, and monetization before setting up the project, source control, and packages. |
| `optimize-audio` | Optimizes audio memory, CPU cost, and playback quality through import settings and mixer configuration. |
| `optimize-text-mesh-pro` | Optimizes TextMeshPro rendering, memory, and font setup, including font asset stacks, fallback atlases, SDF quality, and worldspace text. |
| `optimize-web` | Optimizes Unity WebGL and WebGPU builds for smaller downloads, faster loading, and smoother browser performance. |
| `physics-3d-collision` | Diagnoses 3D PhysX collision and trigger problems. |
| `setup-multiplayer-services` | Guides real-time online multiplayer with Unity Multiplayer Services. |
| `setup-vivox-voice-chat` | Adds and configures in-game voice and text chat with Unity Vivox. |
| `shader-graph-create-custom-node` | Generates custom Shader Graph nodes from HLSL code. |
| `sprite-editor` | Edits Unity sprite rectangles, borders, pivots, outlines, and slicing by generating C# scripts. |
| `sprite-segment-3x3grid` | Segments a Sprite texture into a 3x3 grid and outputs a pattern of cells matching the center cell's color. |
| `ui` | Routes Unity UI requests to the right framework skill (UI Toolkit, uGUI, or IMGUI) and answers UI comparison questions. |
| `ui-imgui` | Generates and modifies Unity IMGUI editor code such as EditorWindows, custom Inspectors, PropertyDrawers, and OnGUI scripts. |
| `ui-ugui` | Understands, edits, and generates Unity uGUI Canvas hierarchies, RectTransforms, Layout Groups, and prefab UI. |
| `ui-uitk` | Understands, edits, and generates Unity UI Toolkit UXML and USS with flex layouts. |
| `unity-cli` | Controls the Unity Editor and projects from the command line, driving a running Editor to edit scenes and assets or run C#. |
| `unity-package-management` | Adds, removes, upgrades, and discovers Unity (UPM) packages from outside the Editor, with the Pipeline package commands first and a C# script as the fallback. |
| `urp-postprocessing` | Sets up, configures, and debugs URP post-processing with the Volume framework. |
| `validate-urp-render-graph-renderer-feature` | Reviews a Unity 6 URP ScriptableRendererFeature that uses the Render Graph API, checking resource wiring, material binding, execution structure, and best pra… |

## Unreal (6)

| Skill | What it does |
|---|---|
| `unreal-behavior-trees` | Unreal Engine 5 (UE 5.8) NPC AI with Behavior Trees, Blackboards, EQS and StateTree: decorators with Observer Aborts, C++ BTTask nodes and running trees from… |
| `unreal-blueprints` | Unreal Engine 5 (UE 5.8) Blueprint visual scripting: Blueprint Classes vs the Level Blueprint, Event Graph, and Cast, Interfaces and Event Dispatchers. |
| `unreal-cpp-gameplay` | Unreal Engine 5 (UE 5.8) C++ gameplay code: UCLASS and UPROPERTY reflection, the Gameplay Framework, GC-safe pointers, Build.cs and command-line builds. |
| `unreal-enhanced-input` | Unreal Engine 5 (UE 5.8) player input with Enhanced Input: Input Actions (IA_), Mapping Contexts (IMC_), ETriggerEvent bindings and remappable keys. |
| `unreal-niagara` | Unreal Engine 5 (UE 5.8) Niagara VFX: systems, emitters, User parameters, spawning from C++ or Blueprints, bounds and GPU vs CPU sim. |
| `unreal-packaging` | Packages and ships Unreal Engine 5 (UE 5.8) projects: Shipping builds, cooking, pak/IoStore and RunUAT BuildCookRun with UAT and cook log reading. |

## Roblox (8)

| Skill | What it does |
|---|---|
| `roblox-characters` | Roblox player characters: CharacterAdded lifecycle, Humanoid and HumanoidRootPart, R6, R15 and custom rigs, respawn and Tools. |
| `roblox-datastores` | Roblox DataStoreService persistence: load on join, save on leave and BindToClose, UpdateAsync vs SetAsync, session locking and OrderedDataStore leaderboards. |
| `roblox-luau` | Roblox Luau scripting and code structure: services, Instances, Script vs LocalScript vs ModuleScript, the task library and typed Luau, with selene and luau-l… |
| `roblox-networking` | Roblox client-server networking and anti-exploit: RemoteEvent and RemoteFunction contracts, server authority, rate limits, hit validation and replication. |
| `roblox-physics` | Roblox physics and spatial queries: assemblies, constraints, collision groups, Raycast and Shapecast, and network ownership. |
| `roblox-simulator-economy` | Roblox simulator, tycoon and idle-game economies in Luau: upgrade cost curves, income per second, rebirth pacing, big-number formatting and paid-egg odds, wi… |
| `roblox-studio-workflow` | Safely edits an existing Roblox place or Rojo project: finds the source of truth and proves changes with the right test mode or Studio MCP (execute_luau). |
| `roblox-ui` | Roblox UI with ScreenGui and PlayerGui: ResetOnSpawn, UDim2 scale and offset, UIListLayout flex, safe areas, StyleSheet, gamepad selection and touch controls. |

## Bevy (Rust) (1)

| Skill | What it does |
|---|---|
| `bevy-ecs` | Builds and debugs Bevy 0.20 games in Rust: components, Query and Commands systems, schedules, States, observers and headless tests. |

## Blender (modelling, rigging, materials, export) (29)

| Skill | What it does |
|---|---|
| `blender-addon-development` | Write Blender 5.3 add-ons as extensions - blender_manifest.toml, operators/panels/menus/property groups/preferences, bpy.props rules after 5.0, undo/redo, mo… |
| `blender-animation` | Animation in Blender 5.3 - slotted/layered actions and the channelbag API, Python keyframing, F-curves, game loops with pop/hitch checks, NLA clips, pose lib… |
| `blender-asset-qa` | Mandatory review gate for any mesh or asset created or edited in Blender. |
| `blender-character-rigging` | Character rigging in Blender 5.3 - Rigify metarig fit/generate, bone naming/roll/collections, DEF/MCH/control layers, IK/FK, robust skinning (heat + proxy fa… |
| `blender-clothing` | Game clothing in Blender 5.3 - garments from body regions (ease offset, thickness), skin-weight transfer, hiding covered body faces, cloth-sim draping for fo… |
| `blender-core` | Foundation for any Blender 5.2+ task an agent drives - running bpy via MCP (live) or headless CLI, context overrides, locale-safe node lookup, enum discovery… |
| `blender-environment-kits` | Game environments in Blender 5.3 - terrain from noise or heightmaps (erosion, terraces, play areas, slope/height materials, 16-bit heightmaps + splat maps fo… |
| `blender-export-pipelines` | Export from Blender 5.3 with verified presets - Roblox (FBX/glTF, cages, R15, SurfaceAppearance), Unity (FBX, Humanoid), Unreal (FBX skeletal, Nanite, UCX), … |
| `blender-facial-shapekeys` | Facial rigs and shape keys in Blender 5.3 - ARKit 52 blendshapes, visemes for lip-sync, sculpting expressions, splitting symmetric shapes into Left/Right, mi… |
| `blender-game-optimization` | Optimize Blender assets for real-time engines - triangle/material/texture/bone budgets per platform (mobile, Roblox, web, VR, console, PC), LOD chains, decim… |
| `blender-geometry-nodes` | Geometry Nodes in Blender 5.3 - fields, domains, attributes, instancing, zones (simulation/repeat/for-each), closures/bundles, lists, SDF grids, node tools, … |
| `blender-hair-grooming` | Hair and fur in Blender 5.3 - hair curves on a surface, guides + interpolated children with the bundled hair node assets (clump, curl, noise, droop), density… |
| `blender-hardsurface-modeling` | Hard-surface and prop modeling in Blender 5.3 - blockout-to-detail flow, non-destructive modifier stacks (Mirror, Boolean Exact/Manifold, Bevel, Weighted Nor… |
| `blender-lighting-lookdev` | Lighting, cameras and look-dev in Blender 5.3 - studio 3-point and product lighting, HDRI environments, sun/sky exteriors, interiors, light linking, physical… |
| `blender-lpm-skill` | Blender Low Poly Modelling Skill — build stylized, flat-shaded, game-ready low-poly assets (weapons, shields, armor, props, modular architecture) from primit… |
| `blender-pbr-materials` | Physically based materials in Blender 5.3 - metal/roughness rules, Principled BSDF inputs, color spaces (sRGB vs Non-Color), measured albedo/F0 values, textu… |
| `blender-pipeline-automation` | Automate Blender 5.3 at scale - headless CLI flags, batch convert/inventory/run-any-skill-script over folders of .blend/.fbx/.glb/.obj/.usd, sharding, bpy pi… |
| `blender-rendering` | Render with Blender 5.3 Cycles/EEVEE/Workbench - quality presets, GPU setup, adaptive sampling, denoising, light paths, color management (AgX, Khronos PBR Ne… |
| `blender-retopology-uv` | Retopology and UVs in Blender 5.3 - auto retopo (Quadriflow, Decimate, planar), deformation edge flow, seams, unwrap (Angle Based, Minimum Stretch, Smart), p… |
| `blender-scene-setup` | Set up and audit Blender scenes the way studios do - units and real-world scale, collection layout, naming conventions (SM_/SK_/T_/M_), origins, linking vs a… |
| `blender-sculpting` | Sculpting in Blender 5.3 - base-to-detail workflow, voxel remesh, dyntopo, multires, 5.x brush types, masks/face sets, symmetry, plus headless-safe procedura… |
| `blender-simulation` | Physics in Blender 5.3 - rigid bodies (density mass, shapes, bake to keys), classic cloth presets and pinning, new node-based Cloth/Hair Dynamics (XPBD, Coll… |
| `blender-stylized-npr` | Stylized / NPR looks in Blender 5.3 - toon and cel shading (bands, shadow tint, rim, hard specular), anime faces with custom normals, inverted-hull outlines … |
| `blender-texture-baking` | Bake texture maps in Blender 5.3 Cycles - high-to-low normal maps with cage/extrusion, AO, curvature, ID, thickness, base color/roughness/metallic from proce… |
| `blender-texturing` | Texture authoring in Blender 5.3 - smart-material layers (edge wear, cavity grime, dust, rust, roughness breakup) from curvature/AO masks, z-fight-safe decal… |
| `blender-time-of-day` | Time of day and atmosphere in Blender 5.3 - measured sky + sun for dawn, morning, noon, golden hour, sunset, blue hour, overcast, night/moonlight with stars … |
| `blender-video-editing` | Video in Blender 5.3 - Video Sequencer edits from Python (clips, image sequences, crossfades, titles, music fades, proxies, color management, H.264/AAC outpu… |
| `blender-weather-fx` | Weather effects in Blender 5.3 - looping Geometry Nodes rain, snow, dust, ash and embers with ground hits and splashes, wet surfaces, puddles with animated r… |
| `blender-workflow-recipes` | End-to-end Blender 5.3 playbooks chaining the blender-* skills with QA gates - game props (mid-poly, high-to-low), game characters (sculpt/AI mesh to rigged,… |

## Art, images and video (11)

| Skill | What it does |
|---|---|
| `create-game-assets` | Plans, generates or sources, and validates consistent game art: style guides, sprites, pixel art, tilesets, icons and textures, with QA and licence records. |
| `higgsfield-brandkit` | Create and extend complete visual brand systems through the Higgsfield CLI and bundled deterministic local tooling: palettes, SVG logo marks, typography, moc… |
| `higgsfield-faceless-video` | Create a finished faceless explainer, documentary, illustrated story or children's music video, or edit a previously created faceless video. |
| `higgsfield-generate` | Generate images/videos/3D assets/audio via Higgsfield AI. |
| `higgsfield-marketplace-cards` | Generate marketplace product image cards through Higgsfield: compliant main image, secondary product images, and A+ style content modules. |
| `higgsfield-product-photoshoot` | Generate brand-quality product images through Higgsfield product-photoshoot prompt enhancement on GPT Image 2 / gpt_image_2. |
| `higgsfield-soul-id` | Train a Soul Character — a personalized model on a person's face that Higgsfield uses for identity-faithful image and video generation. |
| `higgsfield-video-explainer` | Compatibility entry for the former video explainer skill. |
| `higgsfield-websites` | Build, edit, and deploy full-stack websites, apps and games via the Higgsfield CLI (`higgsfield website …`). |
| `higgsfield-youtube-thumbnail` | Create high-click-through YouTube thumbnails and vertical video covers through the Higgsfield CLI. |
| `sprite-gen` | Generates images and game sprites through GPT or Grok with guided provider choices, separate saved defaults, automatic cleanup and optional curation. |

## Game feel, camera, input, UI, audio (8)

| Skill | What it does |
|---|---|
| `audio-design` | Engine-neutral game audio technique: bus layout, volume sliders in decibels, loudness, ducking music under dialogue, adaptive music and SFX variation, with G… |
| `camera-systems` | Builds and tunes game cameras, engine-neutral with Godot and Cinemachine 3 mappings: 2D follow with deadzone and look-ahead, third-person orbit, first-person… |
| `game-feel` | Adds engine-neutral juice to a working mechanic: trauma-based screen shake, hit-stop, eased tweens, squash and stretch, and knockback. |
| `game-ui-ux` | Engine-neutral design rules for game HUDs and menus: anchors and containers, scaling, safe areas, gamepad focus, HUDs driven by events instead of polling, an… |
| `input-systems` | Engine-neutral input architecture with Godot InputMap code: named actions, stick deadzones, buffered presses and rebinding with conflict checks. |
| `performance-optimization` | Finds and fixes game frame-rate problems by measurement in Godot, Unity, Unreal or Roblox: CPU- vs GPU-bound, then the biggest fix (draw calls, pooling, GC s… |
| `physics-tuning` | Engine-neutral physics tuning with Godot checks: fixed timestep and interpolation, CCD against tunnelling, damping, solver iterations and collision layer mat… |
| `shader-programming` | Engine-neutral shader technique in GLSL with HLSL equivalents: how dissolve, outline, fresnel rim and post effects work, and porting GLSL to HLSL. |

## AI, levels, systems (6)

| Skill | What it does |
|---|---|
| `ai-behavior-trees-utility-ai` | Engine-neutral behavior tree and utility AI code for NPCs in any language: Blackboard, reactive composites, decorators and response-curve scoring. |
| `dialogue-systems` | Builds engine-neutral branching dialogue with Ink, Yarn Spinner or a small JSON graph runner: lines, choices, conditions, variables and localization IDs. |
| `game-ai` | Designs engine-neutral enemy and NPC AI: picks FSM, behavior tree, utility or GOAP, and builds perception, steering and A* pathfinding. |
| `level-design` | Engine-neutral level design with Godot checks: player metrics from the real controller, key and ability gating with a soft-lock check, and pacing. |
| `procedural-gen` | Engine-neutral procedural generation in Python with Godot and Unity mappings: seeded RNG, dungeon layouts, wave function collapse, noise terrain and loot tab… |
| `save-systems` | Engine-neutral save and load with Godot and Python code: what to serialize, slots and autosave, atomic writes and versioned migration. |

## Genres (9)

| Skill | What it does |
|---|---|
| `card-game` | Designs card games and deckbuilders in any engine: cards as data with one effect interpreter, deck zones, a trigger stack and seeded shuffles. |
| `fps-shooter` | Designs first-person shooter combat in any engine: hitscan vs projectiles, time-to-kill, damage falloff, recoil patterns, ADS sensitivity and lag-compensated… |
| `platformer` | Designs 2D platformers in any engine: jump feel (coyote time, jump buffering, variable height, fall gravity, corner correction), wall jumps, hazards, checkpo… |
| `puzzle` | Designs grid and logic puzzle games in any engine: match-3 cascades, Sokoban pushing, unique-solution grids (nonogram, Sudoku), exact undo and solver-checked… |
| `roguelike` | Designs run-based roguelikes and roguelites in any engine: run structure, permadeath, meta-progression, seeded and daily runs, turn order and symmetric field… |
| `rpg` | Designs RPG progression and combat numbers in any engine: stats with a modifier stack, XP curves, damage formulas, items and equipment (slots, rarity, affixe… |
| `survival-crafting` | Designs survival-crafting loops in any engine: gathering, recipes and tech trees, carry weight, spoilage, hunger and temperature, and base building. |
| `tower-defense` | Designs tower defense games in any engine: lane and maze pathing, wave pacing, targeting priorities, armoured and flying counters, and the gold economy, with… |
| `visual-novel` | Builds visual novels and choice-driven stories in Ren'Py or any engine: routes and endings, save-anywhere, backlog, skip-read-only and typewriter text. |

## Publishing (2)

| Skill | What it does |
|---|---|
| `itch-publish` | Publishes and updates games on itch.io with the butler CLI: butler push to user/game:channel, channel platform tags, HTML5 builds, --userversion and CI uploads. |
| `steam-publish` | Publishes or updates a game on Steam with Steamworks and SteamPipe: depots, app_build .vdf scripts, steamcmd uploads, beta branches, SetLive, store review an… |

