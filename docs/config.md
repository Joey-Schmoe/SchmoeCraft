## Config File Changes

### Create

`/config/create-server.toml`  

- Double max length of chain conveyors 

  ```text
  maxChainConveyorLength = 32 -> 64
  ```
  
- Double range of mechanical pumps to reduce pump spam

  ```text
  mechanicalPumpRange = 16 -> 32
  ```

### Distant Horizons

`/config/DistantHorizons.toml`

- Prevent incorrect error message being logged

  ```text
  logGarbageCollectorWarning = true -> false
  ```

- Prevent incorrect error message being sent to client on join

  ```text
  showGarbageCollectorWarning = true -> false
  ``` 

### Falling Tree

`/config/fallingtree.json'

- Increase max cuttable tree size

  ```text
  "maxSize": 100 -> 200
  ```

### Tectonic

>In Tectonics' config, lowering numbers tends to *increase* effects, rather then reduce them.

`/config/tectonic.json`

- Increase size of continents/oceans

  ```text
  "continents_scale": 0.13 -> 0.15
  ````

- Slightly decrease size of oceans

  ```text
  "ocean_offset": -0.8 -> -0.75
  ```

### Terralith
`/config/terralith.json`

- Disable floating island generation

  ```text
  "skylands": true -> false
  ```

### Traveler's Backpack

>[TODO] Compare current state to default config for original values

`/config/travelersbackpack-server.toml`

- Limit Overworld mobs that can spawn with backpacks to zombies, skeletons

  ```text
  possibleOverworldEntityTypes = ["minecraft:zombie", "minecraft:skeleton"]
  ```

- Limit Nether mobs that can spawn with backpacks to only piglins
  ```text  
  possibleNetherEntityTypes = ["minecraft:piglin"]
  ```

- Remove non-mob-related backpacks from mob spawns

  ```text
  overworldBackpacks = ["travelersbackpack:standard", "travelersbackpack:skeleton", "travelersbackpack:spider", "travelersbackpack:creeper", "travelersbackpack:enderman"]
  ```  

- Remove non-Nether-mob-related backpacks from Nether mob spawns

  ```text
  netherBackpacks = ["travelersbackpack:standard", "travelersbackpack:nether", "travelersbackpack:blaze", "travelersbackpack:ghast", "travelersbackpack:magma_cube", "travelersbackpack:wither"]
  ```

- Decrease chance of mob spawning with backpack

  ```text
  chance = 0.005 -> 0.001
  ```

### Waystones
`/config/waystones-common.toml`

- Increase cost of teleportation, to promote travel via Train or Aeronautics
  
  ```text
  warpRequirements = ["[is_not_interdimensional] scaled_add_xp_cost(distance, 0.01)" <...>] ->  ["[is_not_interdimensional] scaled_add_xp_cost(distance, 0.10) <...>]
  ```

## Quark
`/config/quark-common.toml`

	"Enable 'q' Button" = [-true-]{+false+}
@@ -36 +36 @@
	automation = [-true-]{+false+}
@@ -41,2 +41,2 @@
	world = [-true-]{+false+}
	mobs = [-true-]{+false+}
@@ -97 +97 @@
	"Celebratory Lamps" = [-true-]{+false+}
@@ -107,4 +107,4 @@
	"Japanese Palette" = [-true-]{+false+}
	"Leaf Carpet" = [-true-]{+false+}
	Midori = [-true-]{+false+}
	"More Brick Types" = [-true-]{+false+}
@@ -114,3 +114,3 @@
	"Rainbow Lamps" = [-true-]{+false+}
	"Raw Metal Bricks" = [-true-]{+false+}
	Rope = [-true-]{+false+}
@@ -120,8 +120,8 @@
	Stools = [-true-]{+false+}
	"Sturdy Stone" = [-true-]{+false+}
	Thatch = [-true-]{+false+}
	"Variant Bookshelves" = [-true-]{+false+}
	"Variant Chests" = [-true-]{+false+}
	"Variant Furnaces" = [-true-]{+false+}
	"Variant Ladders" = [-true-]{+false+}
	"Vertical Planks" = [-true-]{+false+}
@@ -130 +130 @@
	"More Stone Variants" = [-true-]{+false+}
@@ -277 +277 @@
	"Hotbar Changer" = [-true-]{+false+}
@@ -330,4 +330,4 @@
	"Ambient Discs" = [-true-]{+false+}
	"Ancient Tomes" = [-true-]{+false+}
	"Beacon Redirection" = [-true-]{+false+}
	"Bottled Cloud" = [-true-]{+false+}
@@ -335,6 +335,6 @@
	"Endermosh Music Disc" = [-true-]{+false+}
	"Parrot Eggs" = [-true-]{+false+}
	"Pathfinder Maps" = [-true-]{+false+}
	Pickarang = [-true-]{+false+}
	"Seed Pouch" = [-true-]{+false+}
	"Skull Pikes" = [-true-]{+false+}
@@ -342 +342 @@
	"Torch Arrow" = [-true-]{+false+}
@@ -504 +504 @@
	"Campfires Boost Elytra" = [-true-]{+false+}
@@ -509,3 +509,3 @@
	"Dragon Scales" = [-true-]{+false+}
	"Dyeable Item Frames" = [-true-]{+false+}
	Emotes = [-true-]{+false+}
@@ -513 +513 @@
	"Glass Shard" = [-true-]{+false+}
@@ -515 +515 @@
	"Grab Chickens" = [-true-]{+false+}
@@ -520,2 +520,2 @@
	"Magma Keeps Concrete Powder" = [-true-]{+false+}
	"Map Washing" = [-true-]{+false+}
@@ -529 +529 @@
	"Poison Potato Usage" = [-true-]{+false+}
@@ -532 +532 @@
	"Replace Scaffolding" = [-true-]{+false+}
@@ -537,2 +537,2 @@
	"Slimes To Magma Cubes" = [-true-]{+false+}
	"Snow Golem Player Heads" = [-true-]{+false+}
@@ -742 +742 @@
		"Logs To Chests" = [-true-]{+false+}
@@ -750 +750 @@
		"Effective Dragon Breath" = [-true-]{+false+}
@@ -752 +752 @@
		"Torches Burn" = [-true-]{+false+}
@@ -754 +754 @@
		"Bone Meal Utility" = [-true-]{+false+}
@@ -758 +758 @@
		"Easy Hopper" = [-true-]{+false+}
@@ -760 +760 @@
		"Easy Sticks" = [-true-]{+false+}
@@ -762 +762 @@
		"Smelt Raw Ore Blocks" = [-true-]{+false+}
@@ -1543 +1543 @@
	"Back Button Keybind" = [-true-]{+false+}
@@ -1548 +1548 @@
	"Greener Grass" = [-true-]{+false+}
@@ -1551 +1551 @@
	"Microcrafting Helper" = [-true-]{+false+}
