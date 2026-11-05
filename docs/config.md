## Config File Changes

### Create
>`/config/create-server.toml`  

*Double max length of chain conveyors*  
`maxChainConveyorLength = 32 -> 64`
  
*Double range of mechanical pumps to reduce pump spam*  
`mechanicalPumpRange = 16 -> 32`

---

### Distant Horizons
>`/config/DistantHorizons.toml`

*Prevent incorrect error message on server join*  
`logGarbageCollectorWarning = true -> false`  
`showGarbageCollectorWarning = true -> false`  

---

### Tectonic
>`/config/tectonic.json`

**Note: In Tectonics' config, lowering numbers tends to *increase* effects, rather then reduce them.**

*Increase size of continents/oceans. Lower numbers produce large features*  
`"continents_scale": 0.3 -> 0.15`
  
*Tweak ocean size down to prevent bug causing massive Mushroom Fields biomes to spawn in oceans*  
`"ocean_offset": -0.8 -> -0.75`

---

### Terralith
>`/config/terralith.json`

*Disable floating island generation*  
`"skylands": true -> false`

---

### Traveler's Backpack
>`/config/travelersbackpack-server.toml`

**[TODO] Compare current state to default config for original values**

*Limit mobs that can spawn with backpacks to zombies, skeletons, and piglins*  
`possibleOverworldEntityTypes = ["minecraft:zombie", "minecraft:skeleton"]`  
`possibleNetherEntityTypes = ["minecraft:piglin"]`

*Remove non-mob-related backpacks from mob spawns*  
`overworldBackpacks = ["travelersbackpack:standard", "travelersbackpack:skeleton", "travelersbackpack:spider", "travelersbackpack:creeper", "travelersbackpack:enderman"]`  

*Remove non-Nether-mob-related backpacks from Nether mob spawns*  
`netherBackpacks = ["travelersbackpack:standard", "travelersbackpack:nether", "travelersbackpack:blaze", "travelersbackpack:ghast", "travelersbackpack:magma_cube", "travelersbackpack:wither"]`

*Decrease chance of mob spawning with backpack*  
`chance = 0.005 -> 0.001`

---

### Waystones
>`/config/waystones-common.toml`

*Increase cost of teleportation, to promote travel via Train or Aeronautics*  
`warpRequirements = ["[is_not_interdimensional] scaled_add_xp_cost(distance, 0.10)" ->  0.01`