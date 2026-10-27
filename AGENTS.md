# AGENTS.md — Veyloria Online coding instructions

You are working on **VEYLORIA ONLINE**, an original 2D anime fantasy MMORPG inspired by the *feel* of classic Ragnarok Online. **Never copy Ragnarok sprites, maps, UI art, source code, audio, logos, or protected characters.**

## First reads
Read `README.md`, `docs/GAME_BIBLE.md`, `docs/ART_PIPELINE.md`, `docs/CODEX_START_TASK.md`, and `assets/manifest.json` before editing. Treat the art reference as a **concept board**, not a production texture.

## Priorities
1. Produce a small working browser game first: Novice, Willowbrook Village, Sunny Meadow, Leaf Slime, NPC, combat, loot, XP, save/load.
2. Use TypeScript + Phaser with clean modules: scene, world, player, animation, combat, quests, inventory, input, data, UI, assets.
3. Prefer data-driven JSON records for classes, monsters, items, maps, animations, VFX.
4. Add tests for game logic and automation for detecting missing assets and invalid sprite metadata.
5. Keep placeholder art clearly marked. Replace it safely when real PNGs arrive; never stretch an illustration into an animated sprite.
6. Stage real asset production in explicit batches; QA each batch before moving to next.
7. Prepare for an authoritative network backend but do not present simulated local multiplayer as real online service.
8. If a pre-existing game file is provided, inspect it, preserve working game logic/saves/maps, and migrate incrementally. Never replace it without a non-destructive audit.
9. Do not invent files/results, claim untested assets pass QA, or report completed game systems that have only placeholder buttons.
10. Document how to install, run, test, build and preview; list completed vs pending work clearly.

## Core asset contracts
- Base grid: 32×32 tiles.
- Novice/standard player sprite: nominal 48×64 **per frame**, alpha PNG (adjust sheet cell with metadata when a move needs more space).
- Direction rows: 0=down/front, 1=left, 2=right, 3=up/back.
- Anchor: feet at bottom center; no baked drop shadow if layered shadow used.
- Animation names: `idle`, `walk`, `run`, `attack`, `cast`, `hit`, `death`, `victory`, `sit`, `emote`.
- Required per-direction frame counts: idle 5, walk 8, run 8, attack 6, cast 6, hit 3, death 8, victory 6, sit 4, emote 4.
- Transparent sprites/VFX; no gridlines, text, or checkerboard pattern baked into images.
- Reusable maps: separate ground/objects/foreground/collision/spawn/portal layers, with walkable geometry.
- Event-driven VFX synced to animation and combat; damage validated by server in multiplayer.
- Boss Vaelthar is a **wyvern**: TWO hind legs and TWO wings that serve as forelimbs; NO extra forelegs.

## Definition of done
A feature is done only when it loads in the game, performs the intended gameplay interaction, survives the relevant save/load or reconnect scenario, and has reasonable tests or manual QA instructions. If not, mark it TODO.
