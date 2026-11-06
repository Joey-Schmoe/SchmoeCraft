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