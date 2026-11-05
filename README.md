# SCHMOECRAFT MODPACK
**Minecraft 1.21.1 | NeoForge 21.1.265** | **PACKWIZ**  
*A lightweight modpack focused on quality-of-life and tech progression.*


## Tech Stages
The pack is designed to feature three distinct tech stages.

### Early Game:
The player is setting up a starter base and covering new-world essentials, setting up basic Create machines for resource gathering and processing, and dabbling in limited Aeronautics vessels. Limited mostly to Water Wheel and Windmill power. Storage is primarily handled with Storage Drawers, and some basic Create storage networking. Progress is gated by access to Blaze Rods from the Nether.

### Mid Game:
The player has settled into a dedicated base. Create automation is in full swing - proper linked storage vaults, renewable resource gathering, dedicated production lines for common craftables and materials, automated Steam Engines for power, long-distance travel and logistics via Trains and Aeronautics vessels. Player is transitioning to electrical transmission of power via Create Crafts & Additions. Player begins to convert logistics networks over to LaserIO, both for instant bulk item transfer and for lag prevention. Progress is gated by (???).

### Late Game:
This is the mega base stage. Modify or replace Create machines with Mekanism blocks, allowing for significant increases in resource generation and processing, while reducing server lag. Storage moves from Create storage networks over to Applied Energistics networks, allowing for massive, instant, and lag-free storage. Power generation is provided by high-output Mekanism Generators.

## Setup
### Server Setup
DOCKER: ensure the container has the variable `PACKWIZ_URL` set to the correct URL. Example: `https://raw.githubusercontent.com/Joey-Schmoe/SchmoeCraft/main/pack.toml`  

DEDICATED: Run `java -jar packwiz-installer-bootstrap.jar -g -s server https://raw.githubusercontent.com/Joey-Schmoe/SchmoeCraft/main/pack.toml`

### Client Setup
PRISM LAUNCHER:  
Create a new Instance, matching the Minecraft and NeoForge versions used by the pack.

 Under Edit -> Settings -> Custom Commands - > Pre-launch Command, enter `"$INST_JAVA" -jar packwiz-installer-bootstrap.jar https://raw.githubusercontent.com/Joey-Schmoe/SchmoeCraft/main/pack.toml`

### World Generation
1. Ensure Chunky is loaded, and Distant Horizons is disabled
2. Generate world with type "BetterX"
3. Access RCON - all following commands are entered here
4. `chunky world [overworld/nether/the_end]`
5. `chunky center [x] [z]`
6. `chunky radius [radius-in-blocks]
7. `chunky start`
8. Wait for pregen to complete - track progress in the docker logs
9. Swap Chunky for Distant Horizons
10. In RCON, enter `dh pregen start overworld [x] [z] [radius-in-chunks]
11. Repeat above for other dimensions, if needed

## Mods
### Tech
#### Create
[TO-DO] Description of Create Mod

Addons:

* Create Aeronautics
  * Vehicle building & physics contraptions
* Create: Connected
  * QoL blocks - clutch/gearbox variants, crank wheels
  * Vertical item vault & horizontal fluid tanks
  * Fan catalyst blocks
* Create: Copycats+
  * Greatly expands copycat block options
* Create Crafts & Additions
  * Adds electric motors, wires, energy storage, and FE conversion
* Create Deco
  * Adds catwalks and various other industrial-themed building blocks.
* Create: Dragons Plus
  * Bulk coloring/freezing/ending
  * Fluid hatch
  * Create Simulated integration - adds simulated contraption interaction for Air Current processing and fragile fluid tanks that break on impact
* Create: Enchantment Industry
  * New fluid: Liquid Experience
  * Deployer and Crushing Wheel kills drop experience nuggets
  * Blaze Enchanter/Forger for enchantment automation
  * Printer - print copies of books for exp cost
  * Spout liquid experience to repair Mending items
* Create: Integrated Farming
  * Vaccum harvester and fishing nets
  * Harvester compatability for Farmer's Delight crops
  * Mechanical Arm compatability for Farmer's Delight Baskets
* Create Jetpack
  * Adds a SU-powered jetpack
* Create: Power Loader
  * Adds Create-themed chunk loaders
  * Interacts correctly with contraptions and trains/stations

Integrations: 
* Applied Create  
  **[Applied Energistics 2]**
  * Conversion between SU/ME (network energy), and SU/AE (AE2 grid power)
  * SU storage in AE2 energy networks
* Create Slice & Dice  
  **[Farmer's Delight]**
  * "Slicer" machine, for processing FD's cutting recipes, as well as a Sprinkler block.
  * Sprinkler - pipe fluids to distribute water/lava/potion effects
  * Adds all FD Cooking Pot recipes as Create heated mixing recips
* Create: Central Kitchen  
  **[Farmer's Delight]**
  * Unpack ingredients into Cooking Pots with Packagers
  * Mechanical Arm support for FD's crafting blocks
  * Boiler Heaters work as heat sources
  * Convert cutting recipes into Sawing/Deploying recipes

Bugfixes:
* Aeronautics Hot Air Fix
  *  Fixes graphical error when viewing Aeronautics hot air envelopes while using Iris Shaders
* Copycats+ aeronautics weight
  * KPG (mass) for copycat+ blocks for Sable physics

#### Farmer's Delight
Vanilla+ style farming and cooking expansion

#### Applied Energistics 2
Convert items into energy stored on digital systems, complex auto crafting systems

#### Mekanism  
High-tech mod providing complex multi-tiered machinery for resource generation, processing, and refinement, as well as massive multi-block machines

* Mekanism Generators
  * Various Mekanism energy productions, up to Fusion/Fission Reactors

#### LaserIO
Logistics system centered on Laser Nodes - a Node placed against a storage block enables wireless item extraction/insertion, stocking, and stock counting

#### Storage Drawers
Interactive, high-density early-game storage system

### Quality-of-Life
* BetterF3
  * Configurable, cleaner F3 HUD
* Carry On
  * Pick up, carry, and place single block Tile Entities
* Controlling
  * Keybind menu search bar
  * Keybind conflict checking/notification
* Corpse
  * Creates a corpse object upon player death - contains all items and exp the player had, doesn't burn in lava or fall into the void
* EMI
  * Item and recipe viewer - includes recipe trees
  * EMI for Create
  * EMI Loot
  * EMI Ores
  * ~~EMI Trades~~
    * Not currently available for 1.21.1
* Enchantment Descriptions
  * Show tooltip on enchanted items with brief description of their effect
* Jade
  * Display information about the targeted block
* Jade Sable Compat
  * Corrects Jade block selection on Sable sublevels
* JourneyMap
  * Real-time mapping, viewable in-game or via browser.
  * Include minimap - currently deactived client-side
* Mouse Tweaks
  * Several mouse-control improvements for inventory screens
* Nature's Compass
  * Item that allows player to search for the location of specific biomes
* Pick Up Notifier
  * Shows on-screen notification for picked-up items
* Trade Cycling
  * Re-roll unlocked villager trades with a button on the trade screen 
* Traveler Tool Belt
  * Quick-swap tool inventory
* Traveler's Backpack
  * Upgradeable backpacks, with fluid tanks, special abilities, and sleeping bag
* Waystones
  * New blocks which allow for travel between discovered nodes

### World Gen
#### Terrain
* Terralith
  * 95+ new biomes
  * Custom caves
* Tectonic
  * Alters world generation parameters to produce large-scale features like continents, mountain ranges, canyons, plateaus, etc
* Continents
  * TO BE REMOVED

#### Structures
* Towns and Towers
  * New and improved Vanilla+ style villages, pillager outposts, and ships
* YUNG's Better Structure Suite
  * YUNG's Better Desert Temples
  * YUNG's Better Dungeons
  * YUNG's Better End Island  
    * *Verified compatability with Nullscape*
  * YUNG's Better Jungle Temples
  * YUNG's Better Mineshafts
  * YUNG's Better Nether Fortresses
    * *Implied compatability with BetterNether: New Dawn*
  * YUNG's Better Ocean Monuments
  * YUNG's Better Strongholds
  * YUNG's Better Witch Huts

#### Nether/End
* BetterNether: New Dawn
  * Many new biomes
  * Vertical biome layers
  * More Nether mobs
  * New structures
* Nullscape
  * Full End generation rework - overhauls old biomes, adds new biomes
  * Increases End's height to 384 blocks
  * New Crashed Ship structure

### Visuals
* Colorwheel
  * Provides shader compatiblity with Flywheel, Create's rendering engine
* Distant Horizons
  * LOD rendering and generation
* Iris Shaders
  * Shader pack loader

### Engine/Admin
* Chunky
  * Chunk pre-generation
* ModernFix
  * Load time optimization
  * Memory usage optimization
* Simple Backups
  * Configurable auto-backups
* Sodium
  * Engine optimization
* spark
  * Performance profiler

### Libraries/Dependencies
* AppleSkin
* Balm
* BCLib: New Dawn
* Bookshelf
* Cloth Config API
* Cristel Lib
* Curios API
* FerriteCore
* Fzzy Config
* GuideME
* Kotlin for Forge
* Lithostitched
* Prickle
* Puzzles Lib
* Sable
* Searchables
* WorldWeaver: New Dawn
* WunderLib: New Dawn
* YUNG's API

### Shaders
* Complementary Shaders - Reimagined  
  * Known compatible with Create and Distant Horizons

## Config Changes
### Create
maxChainConveyorLength = 32 -> 64  
*Double max length of chain conveyors*  

mechanicalPumpRange = 16 -> 32  
*Double range of mechanical pumps to reduce pump spam*

### Distant Horizons
logGarbageCollectorWarning = true -> false
showGarbageCollectorWarning = true -> false  
*Prevents incorrect error message on server join*

### Tectonic
"continents_scale": 0.3 -> 0.15  
*Increase size of continents/oceans. Lower numbers produce large features*  

"ocean_offset": -0.75
*Tweak ocean size down to prevent massive Mushroom Fields bug*

### Terralith
"skylands": true -> "skylands": false  
*Disable floating island generation*

### Traveler's Backpack
[TODO] Compare current state to default config for true values  
*Remove non-mob-related backpacks from mob spawns*  
*Remove non-Nether-mob-related backpacks from Nether mob spawns*  
*Decrease chance of mob spawning with backpack*

### Waystones
warpRequirements = ["[is_not_interdimensional] scaled_add_xp_cost(distance, 0.01)"  
-->  
warpRequirements = ["[is_not_interdimensional] scaled_add_xp_cost(distance, 0.10)"  
*Increase cost of teleportation, to promote travel via Train or Aeronautics*

## Modlist
    Aeronautics Hot Air Fix (aeronauticshotairfix-1.1.1.jar)
    AppleSkin (appleskin-neoforge-mc1.21-3.0.9.jar)
    Applied Create (appliedcreate-1.21.1-1.1.8.jar)
    Applied Energistics 2 (appliedenergistics2-19.2.18.jar)
    Balm (balm-neoforge-1.21.1-21.0.67.jar)
    BCLib: New Dawn (bclib-21.0.28.jar)
    BetterF3 (BetterF3-11.0.3-NeoForge-1.21.1.jar)
    BetterNether: New Dawn (BetterNether-21.0.30.jar)
    Bookshelf (bookshelf-neoforge-1.21.1-21.1.81.jar)
    Carry On (carryon-neoforge-1.21.1-2.2.6.13.jar)
    Chunky (Chunky-NeoForge-1.4.23.jar)
    Cloth Config API (cloth-config-15.0.140-neoforge.jar)
    Colorwheel (colorwheel-neoforge-1.3.1+mc1.21.1.jar)
    Complementary Shaders - Reimagined (ComplementaryReimagined_r5.9.3.zip)
    Continents (Continents_26.2_v1.1.14.jar)
    Controlling (Controlling-neoforge-1.21.1-19.0.5.jar)
    Copycats+ aeronautics weight (aerocopycats-1.1.1.jar)
    Corpse (corpse-neoforge-1.21.1-1.1.22.jar)
    Create (create-1.21.1-6.0.10.jar)
    Create Aeronautics (create-aeronautics-bundled-1.21.1-1.3.2.jar)
    Create Crafts & Additions (createaddition-1.7.2.jar)
    Create Deco (createdeco-2.1.3.jar)
    Create Jetpack (create_jetpack-forge-5.2.1.jar)
    Create Slice & Dice (sliceanddice-4.3.4-neoforge.jar)
    Create: Central Kitchen (create-central-kitchen-2.6.2b.jar)
    Create: Connected (create_connected-1.3.3-mc1.21.1.jar)
    Create: Copycats+ (copycats-3.0.9+mc.1.21.1-neoforge.jar)
    Create: Dragons Plus (CreateDragonsPlus-1.11.9.jar)
    Create: Enchantment Industry (create-enchantment-industry-2.5.4b.jar)
    Create: Integrated Farming (create-integrated-farming-1.4.3.jar)
    Create: Power Loader (create_power_loader-2.0.5-mc1.21.1.jar)
    Cristel Lib (cristellib-neoforge-1.21.1-3.1.7.jar)
    Curios API (curios-neoforge-9.5.1+1.21.1.jar)
    Distant Horizons (DistantHorizons-3.3.3-1.21.1-fabric-neoforge.jar)
    EMI (emi-1.1.24+1.21.1+neoforge.jar)
    EMI for Create (emicreatecompat-1.1.1.jar)
    EMI Loot (emi_loot-0.7.9+1.21+neoforge.jar)
    EMI Ores (emi_ores-1.3+1.21.1+neoforge.jar)
    Enchantment Descriptions (enchdesc-neoforge-1.21.1-21.1.11.jar)
    Farmer's Delight (FarmersDelight-1.21.1-1.3.4.jar)
    FerriteCore (ferritecore-7.0.3-neoforge.jar)
    Fzzy Config (fzzy_config-0.7.7+fix1+1.21+neoforge.jar)
    GuideME (guideme-21.1.22.jar)
    Iris Shaders (iris-neoforge-1.8.14-beta.1+mc1.21.1.jar)
    Jade Sable Compat (sablejade-1.3.0.jar)
    Jade 🔍 (Jade-1.21.1-NeoForge-15.10.6.jar)
    JourneyMap (journeymap-neoforge-1.21.1-6.0.9.jar)
    Kotlin for Forge (kotlinforforge-5.12.0-all.jar)
    LaserIO (laserio-1.9.11.jar)
    Lithostitched (lithostitched-1.8.1-neoforge-21.1.jar)
    Mekanism (Mekanism-1.21.1-10.7.19.85.jar)
    Mekanism Generators (MekanismGenerators-1.21.1-10.7.19.85.jar)
    ModernFix (modernfix-neoforge-5.27.27+mc1.21.1.jar)
    Mouse Tweaks (MouseTweaks-neoforge-mc1.21-2.26.1.jar)
    Nature's Compass (NaturesCompass-1.21.1-3.4.0-neoforge.jar)
    Nullscape (Nullscape_1.21.x_v1.2.14.jar)
    Pick Up Notifier (PickUpNotifier-v21.1.1-1.21.1-NeoForge.jar)
    Prickle (prickle-neoforge-1.21.1-21.1.11.jar)
    Puzzles Lib (puzzleslib-v21.1.66-mc1.21.1+neoforge.jar)
    Sable (sable-neoforge-1.21.1-2.0.6.jar)
    Searchables (Searchables-neoforge-1.21.1-1.0.2.jar)
    Simple Backups (SimpleBackups-1.21-4.0.30.jar)
    Sodium (sodium-neoforge-0.8.13+mc1.21.1.jar)
    spark (spark-1.10.124-neoforge.jar)
    Storage Drawers (StorageDrawers-neoforge-1.21.1-13.11.4.jar)
    Tectonic (tectonic-3.0.28-neoforge-21.1.jar)
    Terralith (Terralith_1.21.1_v2.6.2_Neoforge.jar)
    Towns and Towers (t_and_t-fabric-neoforge-1.13.11.jar)
    Trade Cycling (trade-cycling-neoforge-1.21.1-1.0.23.jar)
    Traveler Tool Belt (travelertoolbelt-neoforge-1.21.1-1.0.4.jar)
    Traveler's Backpack (travelersbackpack-neoforge-1.21.1-10.1.41.jar)
    Waystones (waystones-neoforge-1.21.1-21.1.46.jar)
    WorldWeaver: New Dawn (worldweaver-21.0.30.jar)
    WunderLib: New Dawn (wunderlib-21.0.11.jar)
    YUNG's API (YungsApi-1.21.1-NeoForge-5.1.9.jar)
    YUNG's Better Desert Temples (YungsBetterDesertTemples-1.21.1-NeoForge-4.1.5.jar)
    YUNG's Better Dungeons (YungsBetterDungeons-1.21.1-NeoForge-5.1.4.jar)
    YUNG's Better End Island (YungsBetterEndIsland-1.21.1-NeoForge-3.1.2.jar)
    YUNG's Better Jungle Temples (YungsBetterJungleTemples-1.21.1-NeoForge-3.1.2.jar)
    YUNG's Better Mineshafts (YungsBetterMineshafts-1.21.1-NeoForge-5.1.1.jar)
    YUNG's Better Nether Fortresses (YungsBetterNetherFortresses-1.21.1-NeoForge-3.1.5.jar)
    YUNG's Better Ocean Monuments (YungsBetterOceanMonuments-1.21.1-NeoForge-4.1.2.jar)
    YUNG's Better Strongholds (YungsBetterStrongholds-1.21.1-NeoForge-5.1.3.jar)
    YUNG's Better Witch Huts (YungsBetterWitchHuts-1.21.1-NeoForge-4.1.1.jar)

## Issues
## Unresolved Bugs

### Critical
**Tectonic**  
If ocean offset is set too low (testing showed values of -1 or less) massive Mushroom Field biomes spawn in the ocean, causing unintended structures to spawn underwater 

**Distant Horizons <---> Chunky**  
Server fails to start with both mods loaded - they must be alternated. Load Chunky only for pregenerating chunks. Once complete, swap for Distant Horizons.

### Conflicts/Overlap
**Create Slice & Dice <---> Create: Central Kitchen**  
Slice & Dice provides a Slicer machine for Farmer's Delight's cutting recipes   
**vs**  
Central Kitchen converts cutting recipes into Create Sawing/Deploying recipes  

**Tectonic <---> Continents**  
Tectonic provides configurable continent generation   
**vs**  
Continents tweaks world gen to produce discrete continents and oceans  
*Note: the current world was erroneously generated with Continents still active - monitor for issues, and remove mod before generating a new world*

### Warning
**Create: Power Loaders <---> Create Aeronautics**  
Chunk loaders have questionable compatability with Sable sub-levels. Avoid placing chunk loaders on Aeronautics contraptions until patched

## Useful Commands
### Container Console
---
**Access RCON CLI**  
`rcon-cli`

### Packwiz
---
**Add mod to pack with slug**  
`packwiz [mr/cf] (mr = modrinth, cf = curseforge) add [mod-slug]`

**Add mod to pack via search**  
`packwiz [mr/cf] (mr = modrinth, cf = curseforge) add "search-text"`

**After making *any* changes to the files**  
`packwiz refresh`

### Git
---
**Create and switch to new branch**  
`git switch -c [branch-name]`

**Merge branch into main**  
`git switch main`  
`git pull origin main` <-- brings local repo up-to-date with remote  
`git merge [branch-name]`  
`git push origin main`

## Notes
* BetterNether requires the world type to be set to "BetterX". This world type seems to be compatible with our world gen stack.

* Ensure git actions happen *only in the main folder*. Otherwise, line endings will break and throw off packwiz hash matching, crashing the server on startup