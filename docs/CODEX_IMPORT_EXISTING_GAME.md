# Codex prompt — IMPORT AND PRESERVE THE EXISTING VEYLORIA ONLINE GAME

**Do not start a new empty game.** The user has supplied an existing static build archive, `Veyloria Online (1).zip`.

First read `AGENTS.md`, `docs/GAME_BIBLE.md`, `docs/ART_PIPELINE.md`, `docs/EXISTING_BUILD_AUDIT.md`.

## Stage A: import and verify
1. Receive user uploaded ZIP or extracted `legacy-build/` directory. If not actually present in the Codex workspace, **stop and request the upload**; do not hallucinate access to the user's ChatGPT files.
2. Preserve exact original 4 files under `legacy-build/`: `index.html`, `assets/index-M4WZzahQ.js`, `assets/index-Cq4vhBbx.css`, `assets/asset-manifest.json`.
3. Verify ZIP integrity, static paths, manifest and JS parse. Serve `legacy-build` locally. Test browser UI and core gameplay; capture concrete failures without changing original.
4. Build a functional inventory: maps, jobs, NPCs, monsters, quests, combat, user data, save format, render path, animation registry. Distinguish implemented vs placeholders.
5. Add Playwright smoke tests (or report missing browser runtime if can't install).
6. Note lack of original editable source and ask for it if available; meanwhile create a conservative migration plan.

## Stage B: integrate production assets without changing original game logic
1. Create an override asset registry keyed by the original manifest IDs (`chr_novice`, `map_willowbrook_ground`, etc.).
2. Prepare folders for transparent sprites, tilesets, environment props and VFX, using exact sheet and metadata formats.
3. Generate Batch 001 artwork when PixelLab/image tools are actually available; otherwise create **specific generation prompts**, metadata templates and **clearly labeled placeholders**.
4. Test that adding a sheet does not break the existing gameplay; preserve original procedural graphics as fallbacks.
5. Plan conversion of old animations (idle2, walk4, attack3, cast3, hit1, death3) to future target anim sets (idle5, walk8, attack6, etc.) explicitly, adapting loading and timing rather than assuming sheets are compatible.

## Stage C: maintainable source (only after audit)
1. Prefer recovery of the user's original `src/` and `package.json` if possible.
2. If original source cannot be supplied, reimplement/port in small testable increments from observed behavior and in-bundle data. Leave legacy build intact throughout.
3. Prove save/load compatibility or build migration/export path; never discard user progress.

## Done criteria
- Original game archive is preserved.
- Browser build runs/has an exact diagnosed blocker.
- Core gameplay tests are reported honestly.
- Correct paths for future production assets documented.
- Art production pipeline is staged with reliable fallback.
- No original code has been overwritten or deleted.

**Begin with verification, not redesign.**
