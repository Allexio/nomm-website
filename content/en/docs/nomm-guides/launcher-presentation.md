---
title: Launcher Presentation
description: A quick presentation of the launcher's features
weight: 2
---

# Initial scan & access check

Your first step when you launch the app is the "launcher". It is where all the library-based logic happens.

## Access check

First, the launcher checks if it has access to all your libraries.

If it doesn't it will display a special screen to ask you to provide access or to ignore and continue anyway.

> [!NOTE] Access to special directories
> If NOMM is lacking access to either the downloads or the staging directories **it will not let you ignore the warning and launch the application**. This is intentional and was designed to stop the user from potentially launching NOMM in a broken state.

## Game detection

The launcher will then check all of your config files and try and match them with games in your libraries.

Once that process is done (generally takes <1 second), it will display all your games in a neat library-style format.

# Main screen

Congratulations, you've reached NOMM's main library window!

<img src="https://i.imgur.com/5NkZTC6.png" alt="A screenshot showcasing NOMM's main launcher window">

> [!NOTE] Duplicate game detection
> NOMM is not capable of detecting two copies of the same game (e.g. one on Steam and one on GOG). It will pick one of the two. If you have two copies of the same game, please make sure you only install it once, or that you **fully** uninstall the second copy before scanning for games.

Each detected game will be represented by a tile. Each tile has:
- the logo of the platform it was detected on bottom right
- the number of downloaded mods displayed bottom left
- the detected path of that game when you mouse over


From here you can do one of three things:

You can:
- Select a game and move on to the [dashboard](/docs/nomm-guides/dashboard-presentation)
- Modify the options 
- Force a full rescan of libraries & config files

## Options

NOMM comes with some options to customise your modding experience.

<img src="https://i.imgur.com/rA7wjCj.png" alt="A screenshot showcasing NOMM's settings menu">

First you have the options to modify the downloads and staging paths. Doing this will cause NOMM to check that it has access to these new folders right away.

You also have the option to modify the Nexus API key (with a little button that checks if the API key is valid)

### "General" settings

#### Per-game accent colour

In the configuration yamls for each game, it is possible to define a colour that corresponds to that game.
If that value is set and this option is turned on, when the user launches a game from the launcher, the primary colour will be replaced by that configured colour.

#### Skip Launcher

If this option is turned on, the app will entirely skip the launcher and instantly launch the dashboard for the last selected game.

#### Disable download window

By default, NOMM spawns download windows when downloading files from [supported platforms](/docs/about/mod-platforms). It is possible to hide those windows entirely and only show the notifications that signal a download started and was finished (or an error occurred).

#### Fullscreen NOMM

This will launch the **dashboard** windows in full screen (this will not impact the launcher windows).

## Forcing a rescan

You can always force NOMM to rescan libraries.
This will:

- Force NOMM to scan for all libraries
- Force NOMM to un-ignore previously ignored libraries
- Force NOMM to syncronise the configuration files with the versions included in the release

> [!NOTE] Custom YAML modifications
> If you have done any modifications to your yaml configuration files on files that were already included in the release, these changes **will** get overwritten when forcing a rescan.

