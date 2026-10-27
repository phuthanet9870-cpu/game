# VEYLORIA ONLINE — Art Pipeline and Technical Asset Contracts

## Goal
Turn the shared Veyloria concept board into **original modular game assets**, not a flattened picture of a town. Use **PixelLab AI** for pixel art generation where connected, **Aseprite** for frame cleanup/atlas metadata, **Krita** for painted concept art and layers, **Tiled** for map building, and **Phaser + TypeScript** for rendering and gameplay. AI-generated sprite sheets require human/tool QA.

## Art bible
- Cute, bright classic anime fantasy MMORPG feel, approximately 2.5–3-head chibi sprite proportions, 3⁄4 top-down view.
- Distinct original character designs; **do not trace Ragnarok Online assets**.
- Consistent projected perspective, lighting from upper left, readable outlines, color palette and pixel scale.
- Tile cell: **32×32**.
- Human gameplay animation cell: nominal **48×64** (allow larger cells for wide weapons/moves; never crop).
- Direction order ROWS: **down/front**, **left**, **right**, **up/back**.
- Anchors: foot position centered at bottom. Separate shadow/effects.
- Export transparent `RGBA PNG` plus machine-readable `JSON`; prefer lossless source and nearest-neighbor render.
- Concept illustration is art direction only; NEVER use as gameplay sprite without properly separated production layers.

## Recommended art sequence
1. Make character 4-direction turnaround from one master reference.
2. Generate/hand-edit independent animation frames (not repeated stills).
3. QA frame proportions, color consistency, hands/feet and weapon position, transparent edges.
4. Export each animation separately and create JSON describing row order, frames and offsets.
5. Use checker scripts to verify dimensions, transparency and missing image files.
6. Load into Phaser and visually test motion, depth sorting, camera scaling and effect sync.
7. Move to the next batch only when current art is tested in the game.

## Character animation standard
| State | Frames each direction | Nominal sheet at 48×64 |
|---|---:|---:|
| idle | 5 | 240×256 |
| walk | 8 | 384×256 |
| run | 8 | 384×256 |
| attack | 6 | 288×256 |
| cast | 6 | 288×256 |
| hit | 3 | 144×256 |
| death | 8 | 384×256 |
| victory | 6 | 288×256 |
| sit | 4 | 192×256 |
| emote | 4 | 192×256 |

**233?** No. Correct total frames per character = (5+8+8+6+6+3+8+6+4+4) × 4 = **232 frames**. 10 sheets per design. Changes to cell size must be reflected in every consumer.

Sample `assets/characters/novice/walk.json`:
```json
{
  "key": "novice_walk",
  "image": "assets/characters/novice/walk.png",
  "frameWidth": 48,
  "frameHeight": 64,
  "rows": 4,
  "columns": 8,
  "directions": ["down", "left", "right", "up"],
  "frameDurationMs": 90,
  "repeat": -1,
  "origin": {"x": 0.5, "y": 1},
  "status": "not_generated"
}
```
Remove `status: not_generated` only after the image is actually created and verified.

## Map pipeline
- Region targets are listed in `docs/GAME_BIBLE.md`.
- Each map: Tiled JSON/TMX + modular 32×32 tilesets + objects with correct pixel scale.
- Mandatory layers: **ground**, **ground_detail**, **walls/buildings**, **interactive_objects**, **foreground/above_player**, **collision**, **spawns**, **portals**.
- Props (trees, signs, buildings, furniture) are separate RGBA images; collision shapes do not come from decorative pixels alone.
- Animated environment textures (water, lava, torches, magic crystals, portal, leaves, snow, fog) use timing metadata.
- No water for regions without environmental reasons.
- Suggested first map: Willowbrook Village (80×80 tile design proposal, adjustable to existing game data).
- Strong readability and generous walkable routes matter more than decorative density.

## VFX
- Recommended sizes: 64×64 small, 128×128 medium, 256×256 large, up to 512×512 boss; per-effect metadata overrides these.
- Each attack effect comprises independent caster glow, projectile and impact when appropriate.
- Animations: flame, ice, lightning, holy/heal, shadow, poison, physical slashes, teleports, rune activation, item drops, boss specials.
- Effects are cosmetic consequences of game events. Damage/currency/drops remain combat or server responsibilities.
- Metadata should track `castEvent`, `impactFrame`, `frameDurationMs`, `loop`, `origin`, `blendMode`, `attachment`.

## Asset paths
```text
assets/
  characters/{novice,knight,ranger,mage,priest,assassin,merchant,advanced}/
  npcs/
  monsters/{species_id}/
  bosses/{boss_id}/
  maps/{region}/{map_id}/
  tilesets/
  environment/{region}/
  weapons/ equipment/ items/ cards/ runes/
  pets/ mounts/
  vfx/{fire,ice,lightning,holy,shadow,poison,physical,special}/
  ui/ portraits/ manifests/
```

## 23 production batches (all PLANNED)
001 Novice & starter animations.
002 Knight/Guardian/Berserker.
003 Ranger/Sniper/Beastlord.
004 Mage/Archmage/Sage.
005 Priest/High Priest/Monk.
006 Assassin/Shadowblade/Nightstalker.
007 Merchant/Artificer/Alchemist.
008 25 named NPC designs/sprites.
009 Monsters #1–20.
010 Monsters #21–40.
011 Monsters #41–60.
012 12 mini-bosses.
013 Six major bosses.
014 Ground & terrain tilesets/autotiles.
015 Buildings and environment props.
016 Thirty map projects.
017 Weapons and equipment.
018 Skill icons & monster cards.
019 Elemental skill VFX.
020 Physical/boss/special VFX.
021 Pets and mounts.
022 User interface/HUD.
023 Engine integration, validation and polish.

## BATCH 001: Actual starter deliverables
- Original Novice character concept and four-direction turnaround.
- Transparent Novice `idle`, `walk`, `run`, `attack`, `cast`, `hit`, `death`, `victory`, `sit`, `emote` sheets + JSON.
- Original modular Willowbrook grass/dirt/cobblestone tiles, transitions and props.
- Buildings: blacksmith, general shop, Adventurer Guild, inn, house.
- Monsters: Leaf Slime, Mushling, Horn Rabbit, each with idle/walk/attack/hit/death.
- VFX: sword slash, impact, heal, level-up.
- QA contact sheet, animation preview and proof of Phaser/Tiled loading.

## QA acceptance (verify, don't assume)
- Image exists, opens, correct RGBA channels.
- Sheet width = `frameWidth*columns`, height = `frameHeight*rows`.
- Animation rows and counts match metadata.
- No backgrounds, labels or grids baked into transparent game sheets.
- Alpha edges clean; no clipped body, sword or wings.
- Same model identity in all directions; feet stable and movement visibly animated.
- Terrain transitions tile seamlessly; collisions match actual objects.
- VFX does not cause damage on its own.
- Every asset in manifest has an honest status: `planned`, `generated`, `qa_passed`, `integrated`. Never declare `qa_passed` based on a prompt.
