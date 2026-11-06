# Setup
## Server
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

## Client
Using Prism launcher

1. Create a New Instance
    - Minecraft version 1.21.1
    - NeoForge 21.1.265

2. Download [packwiz-installer-bootstrap.jar](https://github.com/packwiz/packwiz-installer-bootstrap) and copy it into the instance's .minecraft folder

3. Under Edit -> Settings -> Custom Commands - > Pre-launch Command enter:

    ```text
    "$INST_JAVA" -jar packwiz-installer-bootstrap.jar <pack-url>
    ```

## World Generation
>**World Type is set in the container env variables, or the server.properties file on a dedicated server. BetterNether requires the BetterX world type.**

>**Chunky and Distant Horizons must never be active at the same time - server will crash on start-up**

All Chunky and Distant Horizons commands are entered via RCON

```bash
rcon-cli
```

### Chunky Pregen
1. Set dimension

    ```text
    chunky world [overworld/nether/the_end]
    ```
2. Set center
  
    ```text
    chunky center [x] [z]
    ```
3. Set radius

    ```text
    chunky radius [radius-in-blocks]
    ```
4. Start pregen

    ```text
    chunky start
    ```
5. In a second terminal, follow progress via the server log

   ```bash
   docker logs -f <container-name>
   ```

### Distant Horizons Pregen
>**Distant Horizons uses chunk measurements - divide Chunky radius by 16 to convert**
1. Swap the mods: disable Chunky, then enable Distant Horizons.

2. [Publish the pack](operations.md#publishing)

2. In the RCON console, start DH generation:

   ```text
   dh pregen start <overworld|nether|the_end> <x> <z> <radius-in-chunks>
   ```

3. Follow the log as in Chunky Pregen.

