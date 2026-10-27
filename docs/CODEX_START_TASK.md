# CODEX FIRST TASK — VEYLORIA ONLINE

## Use this prompt inside Codex

You are the software engineer for **Veyloria Online**, an original 2D anime fantasy browser MMORPG inspired by the charm of classic Ragnarok Online.

READ FIRST: `AGENTS.md`, `README.md`, `docs/GAME_BIBLE.md`, `docs/ART_PIPELINE.md` and `assets/manifest.json`.

The repository currently contains **specifications only**. Do not pretend there are already PNG sprites, maps or a working server. Build the first playable vertical slice.

### Task: scaffold the Phase 1 browser game
1. Create a runnable TypeScript + Vite + Phaser project with `npm install`, `npm run dev`, `npm run build`, `npm test`.
2. Implement boot/loading scene, main menu, new Novice, movement with keyboard (WASD/arrows), camera follow, collision and depth sorting.
3. Implement **Willowbrook Village** and **Sunny Meadow** as small navigable map samples, with separate terrain, blocked objects and portal zones. Prefer Tiled JSON; if no actual artwork exists, make unmistakably temporary procedural/color-block pixel placeholders.
4. Add an Adventurer Guild NPC, readable dialogue, first quest ('defeat three Leaf Slimes'), progress tracking and rewards.
5. Create data-driven Leaf Slime with idle/chase/attack/hit/death states, targeting, melee combat, HP, drops, EXP, respawn; choose clear starter balance from config.
6. Add playable HUD (HP, MP, XP, skill hotbar, quest tracker, minimap), inventory (drops), and local save/load for offline prototype, labeled as offline.
7. Build asset registry/loader for future sprite sheets, with default placeholders and missing-asset fallback. Use `assets/manifest.json` to track production.
8. Add automated tests for XP/level, damage, inventory item stacking, collision logic and asset manifest validation.
9. Document local run/build/test, what was actually implemented, and next art integration actions.

### Constraints
- Do not copy RO artwork or other game content.
- Use original characters; 32×32 tiles, nominal 48×64 character sprite cells, 4 directions in order down-left-right-up.
- Organize code for replacing placeholders with the future PixelLab/Aseprite/Tiled assets without rewriting combat.
- Do not create fake MMO behavior or pretend a server/database exists. Add a future networking architecture note.
- Keep work within Phase 1, but preserve data extension hooks for 6 jobs, 30 maps, and all bosses.
- If any original Runevale single-file HTML is added later, do not overwrite it blindly; audit and migrate useful systems incrementally.
- Don't just plan. Implement actual runnable code, run available checks, and report exact files plus limitations.

### Definition of done
From the browser, I can start as Novice, walk in a navigable town/field, talk to NPC, fight three Leaf Slimes, receive EXP and an item, see quest complete, and reload the offline save. Document unimplemented online/MMORPG systems accurately.

### Next task after vertical slice
Integrate **Batch 001** high-quality **original** sprite sheets and modular town tilesets. Use PixelLab/Aseprite when available to create true sprites; if those tools aren't available, produce exact prompts/specifications, maintain honest placeholder status and DO NOT claim the PNGs were generated.
