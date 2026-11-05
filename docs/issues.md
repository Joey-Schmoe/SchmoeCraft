# Known Issues, Bugs, and Warnings

## Watchlist

**Sable**  
*Note: Sable is a new, highly-intrusive mod with many possible issues and incompatabilities*

Vehicles larger then the current simulation distance may fail to load their chunks.

TEST: Watch for potential chunk loading issues with Aeronautics vehicles - reasonably-sized vehicles should work fine, but larger vehicles may have chunk-loading issues.

POTENTIAL FIX: Use chunk loaders from Create: Power Loaders to ensure sub-level chunks remain loaded - reported results vary, see below.

---

**Create: Power Loaders <---> Sable/Create Aeronautics**  
Chunk loaders have questionable compatability with Sable sub-levels. The changelog for Power Loaders lists Sable/Aeronautics compatability implemented in v2.0.3, dated 04/27/206, and a memory leak fixed in 2.05 a month after. However, a compat mod was released several months later, but has only 5k downloads, doesn't look to be in active development, and has no GitHub or other technical information provided.

TEST: Place Power Loaders chunk loaders on a physics contraption before assembly. They should remain funcitonal, providing chunk loading for the real-world entity **and** the sub-level chunks, and keeping very large vehicles loaded correctly. May require additional compatability mod.

## Testing
**Create Slice & Dice <---> Create: Central Kitchen**  
Slice & Dice provides a Slicer machine for Farmer's Delight's cutting recipes, while Central Kitchen converts those same recipes into Create's Sawing/Deploying recipes.   

TEST: Inspect the relevent recipes with EMI, test Slicer machine and processing cutting recipes via Saw and Deployer.

FIX: Remove Slice & Dice. Central Kitchen provides similar functionality for everything Slice & Dice does, except for S&D's Sprinkler block.

---

**Tectonic <---> Continents**  5
Both mods directly alter world generation.  
Continents lists compatibility with Terralith, but no mention of Tectonic. Web search shows that older (v2) versions of Tectonic overrode Continents completely - unclear if this has changed since the v3 release of Tectonic that added configurable continent generation.

TEST: Compare map generated with Tectonic *and* Continents active vs a map generated only with Tectonic; determine effect of Continents being installed, if any.

FIX: Remove Continents; Tectonic provides the same functionality, with many additional features. Generate an entirely new world.

## Fixed/Mitigated

**Tectonic**  
Massive Mushroom Field biomes generate in the ocean with no landmasses, causing unintended mod structure generation underwater. 

CAUSE:  
`ocean_offset` value set less then or equal to -1

FIX:  
Ensure `ocean_offset` value set at or above -0.8.

---

**Distant Horizons <---> Chunky**  
Known Distant Horizons 3.3.x issue: Fatal "Chunky is not loaded" error on startup, crashing the server.

CAUSE:  
Distant Horizons prematurely attempts to connect to Chunky while the spawn area is still loading

FIX:  
Ensure only one of the two mods is active on server startup

---

**Git**  
Causes a packwiz hash mismatch and fatal failure to download the pack at server/client load

CAUSE:  
Git actions, by default, alter the line endings of packwiz files

FIX:  
Added .gitattributes file with `* text=auto eol=lf` entry, preventing line ending changes

SECONDARY CAUSE:  
Running Git actions from sub-folders (minecraft-modpack/config, minecraft-modpack/docs etc) doesn't seem to apply the .gitattributes file, causing malformed line endings

SECONDARY FIX:  
Repair line endings via  
>`git add --renormalize`  
>`packwiz refresh`