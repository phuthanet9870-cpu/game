# User-supplied Veyloria Online ZIP — existing build audit

## Origin
User provided **Veyloria Online (1).zip** in ChatGPT on 2026-10-27. It is the user's current game artifact. **Its files have not yet been committed into this repository**. Upload/extract via the Codex import ZIP accompanying the ChatGPT response, or upload the original ZIP directly into Codex.

## Observed archive contents (4 files)
```
index.html (880 bytes)
assets/index-M4WZzahQ.js (1,475,620 bytes)
assets/index-Cq4vhBbx.css (15,781 bytes)
assets/asset-manifest.json (45,349 bytes)
```
Archive uncompressed total ~1.54 MB.

## Evidence of implementation
- A browser entry point titled **Veyloria Online**; a game `div`, UI `div`, CSS and bundled JavaScript.
- Bundled JavaScript contains Phaser references and game data, plus local save/storage code; sources are compiled/minified.
- Three early maps appear in art manifest: `willowbrook`, `sunny_meadow`, `whispering_forest`, each with proposed `ground`, `walls`, `above` layers.
- Four base/class sprite placeholders: Novice, Knight, Ranger, Mage.
- Nine monster sprite placeholders: Leaf Slime, Horn Rabbit, Mushling, Buzz Wasp, Forest Goblin, Venom Spore, Thorn Wolf, Bone Soldier, Grukk Thornking.
- Several NPC definitions and dozens of item/skill icons appear in the manifest.
- `assets/asset-manifest.json` contains **127 entries**, of which **127 are marked `source: procedural` and `placeholder: true`**. Thus the ZIP does **not** contain production-ready PNG texture/sprite sheets; game visuals may be drawn procedurally at runtime.
- Existing manifest declares player cells 48×64, rows `down,left,right,up`; animation counts **idle 2, walk 4, attack 3, cast 3, hit 1, death 3**. These differ from *future target* values in `ART_PIPELINE.md` and **must be reconciled rather than assumed compatible**.
- There is no unminified `src/`, `package.json`, Tiled project, or original Aseprite source in this ZIP.

## Validation performed on the received ZIP
- ZIP CRC/integrity: PASS.
- JavaScript syntax check (`node --check`): PASS.
- JSON parse of Asset Manifest: PASS.
- HTML-referenced JS and CSS files: PRESENT.
- **Not** confirmed: live UI/playthrough, browser integration tests, save migration, server/networking, animation quality.

## Important migration rules
1. **Do not discard this build** or overwrite it with the previously proposed new starter.
2. Preserve the original 4 files *byte-for-byte* in `legacy-build/` once uploaded.
3. First run the legacy build with a simple static server: `python3 -m http.server 8000 --directory legacy-build` and open `http://localhost:8000`.
4. Inspect browser console and exercise creation, movement, combat, quests, inventory and save/load before refactor.
5. Compiled JS is not full editable source. Ask the user for original `src/`, `package.json`, `vite.config.*`, `public/` and related files if available; **if absent**, treat any de-minification as reconstruction and test incrementally.
6. If rebuilding to maintainable TypeScript+Phaser source, match existing behavior and data tables, maintain saves or provide explicit export/import migration; do not claim exact source restoration.
7. Route future artwork through `ART_PIPELINE.md`, but respect legacy manifest keys and frame counts until integration is modified to accommodate new animation sheets.
8. Don't invent multiplayer functionality; verify real server usage first.

## Current repo status
Design docs and this audit are committed. **The attached compiled game ZIP itself is not committed here.** Codex cannot see a ChatGPT sandbox link unless the file is separately attached/imported in its task or repository.
