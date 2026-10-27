# VEYLORIA ONLINE

**Legends Begin With You** — an original, Ragnarok Online-*inspired* 2D anime fantasy MMORPG. This repository is the **Codex project starter and design specification**, not a completed game or finished art pack.

## Goal
Build a browser-playable, top-down / 3⁄4 perspective fantasy RPG that can evolve into an authoritative-server MMORPG. Preserve an original character/world identity; do not copy Ragnarok Online art, code, names or maps.

## Visual target
- Cute readable chibi anime pixel-art characters, approximately 2.5–3 heads tall
- 32×32 terrain grid, nominal player animation cells 48×64 pixels
- Bright, richly detailed medieval fantasy towns and modular environment layers
- Four directional animation rows: down, left, right, up
- Separate VFX, transparent sprites, environment props, collision/occlusion layers
- Game resolution baseline: 1280×720, pixel-perfect scaling where appropriate

## Scope
- 6 first jobs; 12 advanced jobs; Novice starter
- 30 maps in 8 regions
- 60 regular monsters, 12 mini-bosses, 6 major bosses
- Skills, equipment, refinement, cards, rune constellations, pet/mounts, quests, party, guild, economy, dungeons, PvP/Guild War, world events
- Target technology: **Phaser + TypeScript** client; **Tiled** tilemaps; **PixelLab AI + Aseprite** art workflow; later **Node.js/Colyseus + PostgreSQL + Redis** backend

## Start here in Codex
1. Open the Codex web/desktop client and select GitHub repository `phuthanet9870-cpu/game`.
2. Read `AGENTS.md` and `docs/CODEX_START_TASK.md`; paste the start-task request into Codex.
3. Build in small, independently runnable increments. Phase 1 must be a playable vertical slice, not a mockup.
4. **Do not claim visuals have been generated** until transparent PNGs and animation metadata exist and were tested.
5. If importing existing Runevale/Veyloria game files later, audit them and preserve functional saves, maps, combat and assets; never overwrite blindly.

## Documentation
- [Game design and content catalog](docs/GAME_BIBLE.md)
- [Art pipeline, sprite/tileset/VFX requirements](docs/ART_PIPELINE.md)
- [First Codex implementation task](docs/CODEX_START_TASK.md)
- [Asset inventory](assets/manifest.json)

**Current state:** Specifications only. No playable client, server, actual sprite sheets or map images are present yet.

## Existing Veyloria game build supplied by user (2026-10-27)
The user has supplied a compiled playable-looking web build ZIP in ChatGPT. **The binary archive is not yet in this GitHub repo.** Before scaffolding a replacement, read [existing build audit](docs/EXISTING_BUILD_AUDIT.md) and [Codex import procedure](docs/CODEX_IMPORT_EXISTING_GAME.md), and import the ZIP into `legacy-build/`. Preserve its four original files and inspect the current game first. The original editable `src/` and `package.json` were not provided.
