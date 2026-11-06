# Setup and Operation
## Server Setup
### Docker

Using the itzg/minecraft-server image

1. Create and/or set PACKWIZ_URL environment variable on the container:

    ```text
    PACKWIZ_URL=<pack-url>
    ```

2. Set world_type environment variable on the container:

   ```text
   LEVEL_TYPE=wover:betterx
   ```

3. Start container. Modpack is updated/downloaded automatcally on start-up

### Dedicated Server  

```bash
java -jar packwiz-installer-bootstrap.jar -g -s server <pack-url>
```

- `-g` runs without a graphical window.
- `-s server` installs only the mods marked for the server side.

### Client Setup
---
PRISM LAUNCHER:  
Create a New Instance, matching the Minecraft and NeoForge versions used by the pack.
Download `packwiz-installer-bootstrap.jar` from the packwiz-installer GitHub repo and place it in the instance's `.minecraft` folder.  

 Under Edit -> Settings -> Custom Commands - > Pre-launch Command, enter `"$INST_JAVA" -jar packwiz-installer-bootstrap.jar https://raw.githubusercontent.com/Joey-Schmoe/SchmoeCraft/main/pack.toml`

### Chunk/LOD Generation
**!!! Chunky and Distant Horizons must never be active at the same time !!!**
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

## Mod Management
### Adding a mod
```bash
packwiz <mr/cf> add <mod-slug>` *or* "<text-search>"
packwiz refresh  
git add .  
git commit -m "<commit message>"  
git push origin <branch-name>
```

### Removing a mod
**Option A:** Remove with packwiz command  
```bash
packwiz remove <mod-name>
packwiz refresh
git add .
git commit -m "[commit message]
git push origin [branch-name]
```  

**OR**

**Option B:** Remove manually  
>Manually remove file from /mods folder  
`packwiz refresh`  
`git add .`  
`git commit -m "[commit message]"`  
`git push origin [branch-name]`

### Git Deployment

### Updating mods
---
**Single Mod:**  
>`packwiz update [mod-name]`  
`packwiz refresh`  

**All Mods:**  
>`packwiz update --all`  
`packwiz refresh`

## Useful Commands

### Container Console
---
**Access RCON CLI**  
>`rcon-cli`

### Packwiz
---
**Add mod to pack with slug**  
>`packwiz [mr/cf] (mr = modrinth, cf = curseforge) add [mod-slug]`

**Add mod to pack via search**  
>`packwiz [mr/cf] (mr = modrinth, cf = curseforge) add "search-text"`

**After making *any* changes to the files**  
>`packwiz refresh`

**Print modlist to terminal**  
>`packwiz list`

**Print modlist with full filename and version**  
>`packwiz list -v`

### Git
---
**Create and switch to new branch**  
>`git switch -c [branch-name]`

**Merge branch into main**  
>`git switch main`  
`git pull origin main` <-- brings local repo up-to-date with remote  
`git merge [branch-name]`  
`git push origin main`