# VEYLORIA ONLINE — Game Bible v1

## Identity
- Working title: **Veyloria Online**
- Tagline: **Legends Begin With You**
- Genre: 2D anime fantasy MMORPG, top-down / 3⁄4.
- Platforms: browser and PC; initial local single-player demo first, online infrastructure later.
- Camera and art: cute chibi sprite characters against layered colorful fantasy environments. Inspired by the charm of classic MMORPGs without reproducing existing protected designs.
- Resolution baseline 1280×720; tiles 32×32.

## Story and world
World: **Aetheria**; the kingdom of **Veyloria**. Seven fallen stars scattered **Astral Runes** that transformed civilization and opened the **Astral Fracture**, bringing monsters, ancient dragons and shadow armies.

Start in **Willowbrook Village** as a Novice, meet **Lyra Starborn** (guide/mage), **Garrick Ironhand** (blacksmith), **Seraphine Vale** (Adventurer Guild), investigate the ruinous Astral Fracture and the shadow leader **Noctis**.

Five major story acts: Rune Discovery → Royal Journey → Shadow Invasion → Ancient Dragons → The Fallen Star.

## Classes
- Starter: **Novice**, change to first job at Job Lv 10.
- **Knight** (tank/melee, sword/shield/spear) → Guardian or Berserker. Skills: Bash, Provoke, Shield Guard, Spiral Pierce.
- **Ranger** (ranged/trap/pet, bow) → Sniper or Beastlord. Skills: Double Shot, Arrow Rain, Falcon Strike, Wind Trap.
- **Mage** (magic AOE/control, staff) → Archmage or Sage. Skills: Fire Bolt, Frost Nova, Thunderstorm, Meteor.
- **Priest** (healer/support, staff/mace) → High Priest or Monk. Skills: Heal, Blessing, Sanctuary, Resurrection.
- **Assassin** (crit/stealth, dual daggers) → Shadowblade or Nightstalker. Skills: Stealth, Sonic Slash, Poison Edge, Shadow Step.
- **Merchant** (crafting/economy/combat, hammer/cart) → Artificer or Alchemist. Skills: Discount, Overcharge, Cart Strike, Item Appraisal.
- Base Level 1–120; each job progression uses Job Levels 1–50; proposal: advanced job at Base Lv 50 & Job Lv 40.
- Stats: STR, AGI, VIT, INT, DEX, LUK. Derive HP/MP, ATK/MATK, defenses, ASPD, accuracy/evasion, critical chance, cast speed.

## 30 maps / 8 regions
| Region | ID | Map | Suggested Level |
|---|---:|---|---|
| Willowbrook | 01 | Willowbrook Village | starting town |
| Willowbrook | 02 | Sunny Meadow | 1–12 |
| Willowbrook | 03 | Whispering Forest | 8–18 |
| Willowbrook | 04 | Abandoned Mine | 12–22 |
| Silvercrest | 05 | Silvercrest Capital | main town |
| Silvercrest | 06 | Royal Farmland | 18–28 |
| Silvercrest | 07 | Knight's Valley | 25–35 |
| Silvercrest | 08 | Old Castle Ruins | 30–45 |
| Emerald Wilds | 09 | Emerald Village | town |
| Emerald Wilds | 10 | Ancient Woodland | 30–42 |
| Emerald Wilds | 11 | Poisonous Swamp | 40–55 |
| Emerald Wilds | 12 | Venom Queen's Nest | 50–65 |
| Sundune Desert | 13 | Sandhaven Outpost | town |
| Sundune Desert | 14 | Golden Dunes | 45–60 |
| Sundune Desert | 15 | Forgotten Pyramid | 55–70 |
| Sundune Desert | 16 | Scorpion King's Tomb | 65–75 |
| Frostpeak | 17 | Frostholm Town | town |
| Frostpeak | 18 | Snowfall Pass | 60–75 |
| Frostpeak | 19 | Frozen Cavern | 70–85 |
| Frostpeak | 20 | Ice Dragon Sanctuary | 80–90 |
| Ashen Volcano | 21 | Ashen Camp | camp |
| Ashen Volcano | 22 | Burning Wasteland | 75–90 |
| Ashen Volcano | 23 | Infernal Forge | 85–100 |
| Ashen Volcano | 24 | Wyvern's Crater | 95–110 |
| Astral Isles | 25 | Skyport City | town |
| Astral Isles | 26 | Floating Gardens | 95–105 |
| Astral Isles | 27 | Celestial Ruins | 105–115 |
| Void Realm | 28 | Shadow Fortress | 110–120 |
| Void Realm | 29 | Void Crystal Temple | 115–120 |
| Void Realm | 30 | Astral Throne | 120 |

No default water everywhere: desert, volcano, temples, and indoor boss arenas should fit their environment. Each map needs walkable routes, collision, spawn zones, portals, sound/ambience and proper layered occlusion.

## Enemies
- **60 normal monster species** across forests, meadows, ruins, swamp, desert, snow, volcano, skies and void.
- Starter example: Leaf Slime, Mushling, Horn Rabbit, Forest Goblin, Venom Spore, Bone Soldier.
- **12 minibosses** and **6 major bosses**:
  1. Queen Vespera, poison empress, Lv 65. Poison mist, serpents, hazardous arena.
  2. Scarabax, scorpion king, Lv 75. Burrow, poison, sand summons.
  3. Frostmaw, glacier tyrant, Lv 90. Ice wall, freeze, ice attacks.
  4. Vaelthar, ancient crimson WYVERN, Lv 105. Two hind legs + two wing forelimbs; wing strike, fire breath, dive.
  5. Noctis, Astral Knight, Lv 115. Shadow clones, large sword, rift attacks.
  6. Astrael, fallen star, Lv 120. Astral dimensions, crystals, time/space hazards.
- Boss behavior: phased fights, readable telegraphs, aggro, reward contribution, drop tables.

## Systems
- **Combat**: real-time target based, WASD/click movement, cooldowns, cast windows, server-validated combat when online. Nine elements: neutral, fire, water, wind, earth, holy, shadow, poison, undead. Status effects: poison, burn, freeze, stun, silence, slow, blind, bleed, sleep, curse.
- **Equipment**: weapon, armor, headgear, shield, garment, boots, two accessories; five rarity levels; refinement +1 to +15; enchantments and crafting.
- **Monster cards**: rare collectible slotted bonuses; encyclopedia.
- **Rune Constellation**: 6 sockets; flame/frost/storm/earth/light/shadow/venom/astral; 3- and 6-piece effects (placeholder balance numbers).
- **Collection**: pets (capture/affection/level/evolution), mounts, costumes, crafting, recipes.
- **Progression**: XP, Job XP, stats, skill trees, respec.
- **Quests**: main, side, job, daily, world events; data-driven objective types kill/collect/talk/explore/boss/craft.
- **Party**: up to 6 players. **Guild**: 30 to 100 capacity through progression; guild wars and castle claims.
- **PvP**: 1v1, 3v3, 5v5 arenas, ranked seasons, guild war.
- **Economy**: currency **Luma**, stores, vending, trading, marketplace, fees and money sinks; no paid power.
- **World events**: monster invasion, treasure hunts, rare spawns, boss hunts, seasonal festivals, day/night and regional weather.

## Technical road map
Phase 1: 3 starter maps, 3 first classes, 8 normal monsters, 1 miniboss, 15 quests, 20 items, playable first chapter.
Phase 2: remaining jobs, progression and collection systems, up to 10 maps.
Phase 3: authoritative multiplayer, accounts, party, trading, guild, DB persistence.
Phase 4: 30 maps, bosses, raids, PvP, guild war and events.
Phase 5: polish art, audio, balancing, performance, security and operations.

For batch-by-batch asset creation refer to `docs/ART_PIPELINE.md`. Do not mislabel targets above as completed content.
