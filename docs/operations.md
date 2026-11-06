# Development & Maintanence
## Process
Every change follows this cycle:
1. Open new git branch

    ```bash
    git switch -c <new-branch-name>
    ```

2. [Make changes to the pack](#editing)

3. Update documentation

3. [Publish changes to Github](#publishing)

4. Restart the server to fetch updated pack

    >**Current workflow hard-links the server and client to the `main` branch, which serves for both testing *and* full deployment. Alternative workflow would set up a second server targeting a `test` branch with a duplicated world folder from `main`**

## Editing modlist

>**packwiz-refresh must be run after <u>ANY</u> changes to the modpack files, excepting files in the /docs folder**

### Adding a mod

```bash
packwiz mr add <mod-slug>
```

- "mr" searches Modrinth. Use "cf" instead for CurseForge
- Instead of a slug you can use search text in quotes: `packwiz mr add "mod name"`.

### Removing a mod

```bash
packwiz remove <mod-name>
```

### Updating mods

Singe mod:

```bash
packwiz update <mod-name>
```

All mods:

>**Updating terrain generation mods is likely to cause seams and other issues - use with care**

```bash
packwiz update -all
```

## Editing config files

>**Any files in the /config folder will be pushed to the server and client on load, overwriting existing files in the process. All configuration should be done in the modpacks /config files.**

>**packwiz doesn't generate config files on it's own - they must first be copied over from the server's minecraft/config folder**

1. Document proposed change in /docs/config.md, including default value and reason for change

2. Apply change to the file

## Publishing

1. Commit changes to packwiz and update modlist.md using custom command
  
    ```bash
    packwiz-refresh
    ```

2. Add changes to git

    ```bash
    git add .
    git commit -m "<what was changed>"
    git push origin <branch-name>
    ```

3. Merge changes onto the server's active branch

    ```bash
    git switch main
    git pull origin main
    git merge <branch-name>
    git push origin main
    ```

    >**This step is an artifcat of the current, flawed dev process. The server and client both point at the `main` branch. In a future setup, we will merge to a `test` branch in this step, then merge *that* into `main` after testing**

## Troubleshooting

| Symptom | Cause | Fix |
|---|---|---|
| Server crashes on startup with "Chunky is not loaded" | Chunky and Distant Horizons both active | Disable one. See [World Generation](setup.md#world-generation). |
| Pack fails to download; hash mismatch | Git changed the line endings of pack files | Run `git add --renormalize` then commit and push. |
| Watchdog server shutdown during Chunky pregen | Chunky extended a tick past `max-tick-time` |  Run pregen in stages (5,000 -> 7,500 -> 10,000 radius) or temporarily disable watchdog during pregen with `MAX_TICK_TIME=-1` in the container. 

## Reference

### RCON Access

Access RCON from docker container terminal

```bash
rcon-cli
```

### Packwiz

Custom PowerShell script which runs `packwiz refresh` and then logs `packwiz modlist -v` to `/docs/modlist.md`

```bash
packwiz-refresh
```

### Git

Repair line endings

```bash
git add --renormalize .
```