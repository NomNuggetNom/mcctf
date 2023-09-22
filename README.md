<p align="center">
  <img src="https://github.com/NomNuggetNom/mcctf/assets/1479568/fd9956a9-dfe4-4743-8518-1ab4da97a997" />
</p>

<p align="center"><b>MCCTF - The classic MPVP gamemode reborn</b></p>

# Getting Started

## Basics

The JAR file can be found on the [releases page]([url](https://github.com/NomNuggetNom/mcctf/releases)). This plugin can be run on a vanilla server (with some additional plugins required). Months of work have been put into this - it was not a simple copy and paste - and practically everything has been rewritten from scratch. Here are some more details:

- Runs on Minecraft 1.8
- Supports around 700 CTF maps
- Includes all classes up to Scout (no Angel or Wraith)
- Highly customizable and user friendly
- No modes (ZC, DM, etc) besides plain CTF

## Downloads

1. Download the [CTF map archive]([url](https://discord.com/channels/@me/123296961511030784/1153080239711330314)). This is a large file and might take some time, so get it started now.
2. PaperMC 1.8.8 (build 445) is recommended. Head to their [build explorer](https://papermc.io/downloads/all) and click 1.8.8 on the left. This [direct link](https://api.papermc.io/v2/projects/paper/versions/1.8.8/builds/445/downloads/paper-1.8.8-445.jar) might work too.
3. Download a compatible Java version. I use [Temurin 17](https://adoptium.net/temurin/releases/). You need to be able to run `java` from your command prompt to start the server - you can follow the [installation instructions here](https://adoptium.net/installation/).
    - For advanced users, consider using [sdkman](https://sdkman.io/install) to install `17.0.3-tem`.
4. You'll also need a few more plugins:
    - [LuckPerms](https://luckperms.net/download) for managing permissions. Download the Bukkit version. Tested with v5.4.98
    - [ProtocolLib](https://www.spigotmc.org/resources/protocollib.1997/). Tested with v4.7.0.
    - [ViaVersion](https://www.spigotmc.org/resources/viaversion.19254/) for allowing newer clients - this is optional.

## Running

Before you install the plugins, you should run the server on its own. Move the downloaded PaperMC JAR to its own folder, as it will create a lot of folders and files. Then open a command prompt, `cd` to that directory, and run the following console command:

```bash
java -jar paper-1.8.8-455.jar
```

To stop the server, type `stop` into the console. Within the folder that you made, you should now have a folder called `plugins`:

- Open that folder and place the mcctf JAR as well as all the other plugin JARs into that folder.
- Create a new folder called `ctf`, then a folder called `maps` in that directory.
- Unzip the map archive into that maps folder. See below for an example.
- Edit the `server.properties` to ensure `spawn-protection=0` and `allow-flight=true`.
- Start the server and hope everything works. View [known issues]([url](https://github.com/NomNuggetNom/mcctf/issues)) here.

### Example File Layout

```
documents/
├─ ctf_server/
│  ├─ plugins/
│  │  ├─ mcctf.jar
│  │  ├─ LuckPerms-Bukkit.jar
│  │  ├─ ProtocolLib.jar
│  │  ├─ ctf/
│  │  │  ├─ maps/
│  │  │  │  ├─ 60 - Lighthouse V1/
│  │  │  │  ├─ 65 - Kill Creek V2/
│  │  │  │  ├─ ...etc
│  ├─ paper-1.8.8-445.jar
```

# Configuration

The plugin will automatically create a config file for you, and it lives at `plugins/ctf/config.json`. This file provides many options for tweaking the plugin.

## Permissions

Permissions are managed using LuckPerms. The CTF plugin will create a few groups by default:

1. `default` - All players receive this role
2. `mod` - Given to players who need to manage game flow and options
3. `admin` - For players who should have all commands

I suggest using the LuckPerms GUI via `/lp editor users`.

## Commands

Commands can be executed if the person executing matches ANY of the following criteria:

1. The user is OP
2. The user has the group that the command requires
3. The user has the specific command permission

Each command has a specific permission. For example, `/timer lock` is executable by any user in the `mod` group; however, any user who has the `mcctf.command.timer` permission can also execute it.

# Q&A

## Can I use this plugin to make money?

No. This plugin is intentionally designed not to scale. If you expect to be able to use it to run a profitable server, you'll probably find yourself struggling - don't bother.

## Was this code just copied and pasted from Brawl?

No. The Brawl codebase is enormous and not worth porting. This code was reconstructed from legacy MCCTF gameplay, with almost all supporting features recreated from scratch.

# Credits

- ryguy1 and redslime for their help in modernizing
- wintergreen3, without whose testing and help this project would have never been completed

# Future Plans

- Source code release
- Instructions for adding individual maps
- New classes, if desired
