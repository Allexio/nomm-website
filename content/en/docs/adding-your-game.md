---
title: Adding support for your game
description: A quick tutorial on how to create a yaml configuration for a game
weight: 4
---

One of the main ideas behind this project is that games are defined by easy to create config `.yaml` files.
This means that anyone can create a simple yaml for their game and submit it to the project with little to no coding knowledge and the tool will automate the rest.

This yaml file will need to be placed in `[nomm root folder]/default_game_configs`

For instance, if you would want to add support for Stadew Valley, you would create a `[nomm root folder]/default_game_configs/stardew_valley.yaml` file.

## Basic Information

<table class="compact-table">
  <thead>
    <tr>
      <th style="width: 15%">Field</th>
      <th style="width: 45%">Description</th>
      <th style="width: 35%">YAML Example</th>
      <th style="width: 5%">Req</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td><code>name</code></td>
      <td>The full name of the game, with any symbols, spaces, and formatting kept intact.</td>
      <td>{{< highlight yaml >}}name: "Metal Gear Solid Δ: Snake Eater"{{< /highlight >}}</td>
      <td><i class="fa fa-check"></i></td>
    </tr>
    <tr>
      <td><code>steam_id</code></td>
      <td>The Steam App ID. Can be found via <a href="https://steamdb.info/">SteamDB</a> or in the game's store page URL.</td>
      <td>{{< highlight yaml >}}steam_id: 2417610{{< /highlight >}}</td>
      <td></td>
    </tr>
    <tr>
      <td><code>steam_folder_name</code></td>
      <td>The exact folder name for the game inside your <code>steamapps</code> directory. Only required if it differs from the standard game name.</td>
      <td>{{< highlight yaml >}}steam_folder_name: "MGSDelta"{{< /highlight >}}</td>
      <td></td>
    </tr>
    <tr>
      <td><code>nexus_id</code></td>
      <td>The Nexus Mods game key used for downloads. Generally the game name with no symbols and all lowercase, but verify on the site first.</td>
      <td>{{< highlight yaml >}}nexus_id: "metalgearsoliddeltasnakeeater"{{< /highlight >}}</td>
      <td></td>
    </tr>
    <tr>
      <td><code>gog_id</code></td>
      <td>The GOG Store ID. This can be completely omitted if the game is not available on GOG.</td>
      <td>{{< highlight yaml >}}gog_id: 1207666893{{< /highlight >}}</td>
      <td></td>
    </tr>
    <tr>
      <td><code>load_order_path</code></td>
      <td>The path for games with a text-editable load order. Specifying this enables a shortcut button in the app to edit the file directly.</td>
      <td>{{< highlight yaml >}}load_order_path: mods/mod_load_order.txt{{< /highlight >}}</td>
      <td></td>
    </tr>
    <tr>
      <td><code>accent_colour</code></td>
      <td>The accent colour that will replace the primary colour when modding this game, if the <a href="/docs/nomm-guides/launcher-presentation/#options">per-game-accent-colours option</a> is enabled. Please provide a value in <a href="https://share.google/1ZhUzlpT78MaAFCxk">hex format</a>.</td>
      <td>{{< highlight yaml >}}accent_colour: "#ac1a24"{{< /highlight >}}</td>
      <td></td>
    </tr>
    <tr>
      <td><code>wiki_link</code></td>
      <td>The id of the wiki page on this repo</td>
      <td>{{< highlight yaml >}}wiki_link: "witcher-3"{{< /highlight >}}</td>
      <td></td>
    </tr>
  </tbody>
</table>




## Deployment Paths

It is also **required** to define a `mods_path` to which mods should be deployed to. This can be defined in two ways:

### Simple

This is the "legacy" configuration, a simple path where the mods need to be installed when they are enabled.

```yaml
mods_path: "mods/"
```

### Multiple

This is the more complex configuration, where you can add as many paths as you want. Each entry in the list is a dictionary that contains three fields:
- the `path` the mods will be deployed to
- the `name` that will be displayed to the user
- the `description` that will help the user choose which path to select

```yaml
mods_path:
- path: "{user_data_path}/drive_c/users/steamuser/AppData/Local/Larian Studios/Baldur's Gate 3/Mods"
  name: Default
  description: "Used for most mods, the in game mod manager included"
- path: "{game_path}/"
  name: Native
  description: "Used for native mods that require the Native mod loader, such as the 'Native Camera Tweaks' mod."
```

> [!NOTE]
> `mods_path` can contain as many paths as you want, but the goal here is not to add a path for a single mod. If there is only *one* mod using that path, chances are it is a library mod that should be installed with the utilities section below.

## Essential utilities

Nomm lets you define some "essential utilities" that will be used to mod a game. Think libraries or modding tools that have their own needs in terms of installation complexity that don't fit with other "standard" mods and generally require additional actions to get them set up.
```yaml
essential-utilities: # this lets you define things such as mod loaders or essential utilities
  darktide-mod-loader: # you can have multiple ones, each one needs its own unique key
    name: Darktide Mod Loader # the name of the tool
    creator: Talon-d # the creator of the tool
    creator-link: https://github.com/talon-d # a link to the creator's page, portal, social, whatever
    whitelist: d8input.dll # a list of files that should ONLY be included (optional)
    blacklist: d7input.dll # a list of files that should NOT be included (optional)
    source: "https://github.com/talon-d/darktideML-4linux/releases/download/1.5/darktideML-4linux1-5.zip" #the actual thing we'll need to download
    utility_path: "" # where the utility needs to be extracted to
    enable_command: "sh handle_darktide_mods.sh --enable" # any command that needs to be run (from the root of the game folder) to enable the mod loader
    steam_launch_options: "babla" # any launch option that needs to be added to the game on Steam
```

## Full example

Here is a functioning example for the game [Warhammer 40,000: Darktide](https://store.steampowered.com/app/1361210/Warhammer_40000_Darktide/):

```yaml
name: "Warhammer 40,000: Darktide"
steam_id: 1361210
mods_path: "mods/"

load_order_path: "mods/mod_load_order.txt"

nexus_id: "warhammer40kdarktide"

essential-utilities:
  darktide-mod-loader:
    name: "Darktide Mod Loader"
    version: 1.5
    creator: "Talon-d"
    creator-link: https://github.com/talon-d
    source: "https://github.com/talon-d/darktideML-4linux/releases/download/1.5/darktideML-4linux1-5.zip"
    utility_path: ""
    enable_command: "chmod +x tools/dtkit-patch; sh handle_darktide_mods.sh --enable"
```

You can find more examples directly in the repo [here](https://github.com/Allexio/nomm/tree/main/default_game_configs).