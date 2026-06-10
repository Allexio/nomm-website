---
title: Dashboard Presentation
description: A quick presentation of the dashboard's features
weight: 3
resources:
- src: "nomm-preview-pane.png"
  params:
    byline: "*Photo*: Bjørn Erik Pedersen / CC-BY-SA"
---

The NOMM dashboard is split into three tabs.

## The Mods tab

<image src=https://i.imgur.com/O0Wtlja.png alt="A screenshot showcasing the mods tab">

### Action Buttons

Let's start by explaining the handful of buttons top right.

| Icon | Description |
| :--: | :---------- |
| <i class="fa fa-folder"></i> | Opens the **staging** folder in your file explorer |
| <i class="fa fa-refresh"></i> | Refreshes metadata with latest information from the [mod platform](/docs/about/mod-platforms). This will replace all current metadata, including the mod's name with newer versions if available. This will also [check for updates]() to said mods. |
| <i class="fa fa-play"></i> | Launches the game via the [game's platform](/docs/about/game-platforms) |

The mods tab lists all the mods currently available in the staging folder.

### Refreshing the metadata (Checking for updates)

As previously mentioned, checking for updates is done via the metadata refresh button (<i class="fa fa-refresh"></i>).

Once the button is clicked, all mods **that have mod IDs** will get their data refreshed from the connected modding platform.

> [!NOTE] Adding a mod ID to a mod
> It is possible to retroactively add a mod ID to a mod so that its metadata can be refreshed. Please see the section on the preview panel for more information.

If a mod is detected, a new button will appear on the mod's row in the list.

Clicking this button will take you to 

> [!NOTE] False positives
> Unfortunately, many mod authors do not properly update the latest version ID on mod hosting websites. This means that NOMM will often detect false positives. If you notice that the mod version you currently have is the latest one there is, but NOMM is still indicating that there is a mismatch in version numbers, please feel free to contact the mod's author to ask them to update the mod version information on the mod hosting website. There is nothing the NOMM team can do about this. (Though we _are_ looking into ways to let the user manually ignore updates)

### The mod list

The main part of this screen is the list of currently installed mods.

Here is where we need to differentiate between manually downloaded mods and mods downloaded through NOMM.
- For manually downloaded mods, all NOMM knows is
  - the file's name
  - the file's download date
  - the file's contents
- For mods downloaded through NOMM, we have also access to:
  - The mod's real name (often quite different from the file name)
  - The author(s)
  - The uploader
  - The version
  - The description
  - The link to upvote/endorse a mod
  - The thumbnail

#### Row contents

<image src=https://i.imgur.com/BBdrlrN.png alt="A screenshot showcasing a row in the mods list">

Each row contains (if the mod was downloaded from a [supported platform](/docs/about/mod-platforms))

On the left side:
- A toggle to enable/disable the mod
- The mod's name as a title of the row (or the file's name if the mod was manually downloaded)
- The mod's author(s) as a subtitle

On the right side:
- The update available indicator (<i class="fa fa-circle-arrow-up"></i>) (only appears if an update is available)
- The mod installation (<i class="fa fa-box"></i>) date & time (_you can mouse over this to get a full date format_)
- The mod enabled (<i class="fa fa-check"></i>) date & time (_you can mouse over this to get a full date format_)
- A bin (<i class="fa fa-trash"></i>) button to remove a mod from the staging folder. This **does not** remove the downloaded files, only the installed files. It will still be possible to reinstall the mod from the [downloads tab](/docs/nomm-guides/dashboard-presentation#the-downloads-tab) later.


### The mod preview pane

With **NOMM 0.10.0** we have introduced a mod preview pane, accessed by **clicking directly on any row in the mod list**.

<image src=/assets/nomm-screenshots/preview-pane.png alt="A screenshot showcasing the preview pane on the mods tab">

| Line      | Button title    | Action | Description of actions |
| :-------- | :-------------- | ------ | :--------------------- |
| More Info | Mod Description | Click  | Opens up the **full** description of the mod in NOMM |
|           | Nexus           | Click  | Opens web browser on Nexus page of that mod |
| Mod Contents | X File(s)    | Click  | Opens file explorer where mod is stored in staging folder.<br>**Mouse over** lists contents. |
|           |                 | Mouseover | List contents of mod |
| Versioning | Version badge  | Click | Opens up mod platform page on files tab.
|           |                 | Mouseover | _If a changelog was provided ( <i class="fa fa-circle-info"></i> will be displayed)_<br>Displays the changelog |
| Deploy to path | Path       | Click | Opens file explorer where mod is deployed in game files |
|           |                 | Mouseover | Displays the **full** deployment path |
|           | Edit (<i class="fa fa-pencil"></i>) | Click | _If mod is disabled_<br>Allows the user to change the deployment path<br> |
| Uploader | Uploader badge | Click | Opens up mod platform on uploader's profile |
| Endorsements | Endorsement count | Click | Endorse/Unendorse the mod |
| Mod ID | Mod ID | Click | Modify a mod's ID |

#### Changing the deployment path

The preview pane allows the user to change the deployment path of a specific mod.

This is useful for mods that don't fit the mold and need to be deployed somewhere different than most other mods for a game.

For obvious reasons, **this can only be done when the mod is not deployed**.

This change is permanent **until the mod is removed or reinstalled**. In those cases, you will need to re-do the change.

#### Changing a mod ID

The preview pane also allows the user to change a mod's ID.

This is generally used when you manually downloaded a mod and you want to link that mod to an entry on a [supported modding platform](/docs/about/mod-platforms).

After having modified the mod IDs of the mods you want to link, you have to [refresh the metadata of the mods](/docs/nomm-guides/dashboard-presentation#refreshing-the-metadata-checking-for-updates).

## The downloads tab

The downloads tab is designed to handle the downloaded mods (i.e. the archives).
