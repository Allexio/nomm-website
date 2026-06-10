---
title: "Warhammer 40,000: Darktide"
date: 2026-05-29
author: Allexio
rating: gold
---

<span style="font-size: 24px;">{{< rating >}}</span> <i class="fab fa-steam" style="font-size: 28px;"></i>

## Frameworks / utilities supported

| Name | Description |
| :--- | :--- |
| [Darktide Mod Loader](https://github.com/Darktide-Mod-Framework/Darktide-Mod-Loader) ([Linux version](https://github.com/talon-d/darktideML-4linux))| The Darktide Mod loader is installable via NOMM and fully working. |

## Manual actions required

### Summary 

The only manual action required is editing the load order added by DML.

A button is available to open it in the user's favourite text editor in the utilities tab.

### Details

To install mods on Warhammer 40K Darktide, you need to install a utility called "Darktide Mod Loader".
On NOMM, this can be done directly via the utilities tab, simply click the download and install buttons.

After this, you will be able to download all of your mods through a supported modding platform.

Once you are done downloading, installing, and enabling all the mods, you will have to edit the load order text file.

To do so, simply go on the utilities tab and click the "Edit Load Order" button.

The instructions should be displayed in the file itself, but basically you need to write the name of the mods on each line.

If you do not do this, your mods will not be enabled.

## Current configuration file

{{< remote-code "https://raw.githubusercontent.com/allexio/nomm/main/default_game_configs/darktide.yaml" >}}