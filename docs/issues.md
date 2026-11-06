# Known Issues, Bugs, and Warnings

## Watchlist

### Sable

*Note: Sable is a new, highly-intrusive mod with many possible issues and incompatabilities*

ISSUE: Vehicles larger then the current simulation distance may fail to load their chunks.

WATCH: Watch for potential chunk loading issues with Aeronautics vehicles - reasonably-sized vehicles should work fine, but larger vehicles may have chunk-loading issues.

FIX: Add chunk loaders - see [chunk loader compatability concerns below](#create-power-loaders-----sablecreate-aeronautics).

---

### Create: Power Loaders <---> Sable/Create Aeronautics

ISSUE: Chunk loaders have questionable compatability with Sable sub-levels.
  - [Create: Power Loaders changelog lists Sable/Aeronautics compatability](https://github.com/hlysine/create_power_loader/blob/main/CHANGELOG.md#fixed-1)
  - [Create: Power Loaders changelog lists a later Sable/Aeronautics memory leak fix](https://github.com/hlysine/create_power_loader/blob/main/CHANGELOG.md#205---2026-05-22)
  - As of May 22 2026, [users still report some incompatability on the newest version](https://github.com/hlysine/create_power_loader/issues/80#issue-4546250188)

WATCH: Create: Power Loaders' chunk loaders placed on Aeronautics vehicles of any size should remain functional, providing chunk loading for the real-world entity **and** the sub-level chunks.

FIX: Apply the available [compatability mod](https://www.curseforge.com/minecraft/mc-mods/sable-power-loader-compat) 

## Testing

### Create Slice & Dice <---> Create: Central Kitchen

ISSUE: Slice & Dice provides a Slicer machine for Farmer's Delight's cutting recipes, while Central Kitchen converts those same recipes into Create's Sawing/Deploying recipes.

RESULT: ???

TEST: Inspect the relevent recipes with EMI, test Slicer machine and processing cutting recipes via Saw and Deployer.

FIX: Remove Slice & Dice. Central Kitchen provides similar functionality for everything Slice & Dice does, except for S&D's Sprinkler block.

## Fixed/Mitigated

### Tectonic

ISSUE: Massive Mushroom Field biomes generate in the ocean with no landmasses, causing unintended mod structure generation underwater. 

CAUSE: `ocean_offset` value set less then or equal to -1.

TEST: Generated worlds with `ocean_offset` value set to -1.2, -1, and -0.8 (default value).

RESULT: Worlds with -1.2 and -1 values exhibit the bug, -0.8 does not.

FIX: Set `ocean_offset` to -0.8 or higher.

---

### Tectonic <---> Continents

ISSUE: Both mods directly alter world generation.  
  - Continents lists compatibility with Terralith, but no mention of Tectonic.
  - Web search shows that older (v2) versions of Tectonic overrode Continents completely - unclear if this has changed since the v3 release of Tectonic that added configurable continent generation.

TEST: Generated a world with both mods active, and one with only Tectonic.

RESULT: The two worlds were significantly different - Continents **does** alter world generation, even with Tectonic v3+ active. Tectonic-only world had better generation, to my personal preference.

FIX: Removed Continents mod.

---

### Distant Horizons <---> Chunky  

ISSUE: Known Distant Horizons 3.3.x issue: Fatal "Chunky is not loaded" error on startup, crashing the server.

CAUSE: Distant Horizons prematurely attempts to connect to Chunky while the spawn area is still loading

FIX: Ensure only one of the two mods is active on server startup