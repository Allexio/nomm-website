---
title: Flatpak Security
description: An explanation of what makes NOMM secure and privacy-first
weight: 10
---

## A short explainer on Flatpaks

From the official [Flatpak website](https://docs.flatpak.org/en/latest/introduction.html):
> _Flatpak is a framework for distributing desktop applications across various Linux distributions. It was created by developers with a long history of working on the Linux desktop and is run as an independent open source project._

We also have a specific paragraph on the following:
> _...one of Flatpak’s main goals is to increase the security of desktop systems. This is achieved by isolating applications from one another and limiting their access to the host environment._

Basically Flatpaks are designed to be isolated. The **user** is the one who controls what the flatpak has access to, in detail.
You can control whether the Flatpak can connect to the internet, whether it can see different types of hardware connected to your computer, and which files specifically on your computer it can read or write to.

## How NOMM handles isolation

NOMM was thought to request the absolute minimum rights it needs to function.

You can see the current access it requires in the latest [manifest file](https://github.com/Allexio/nomm/blob/main/build/flatpak/com.nomm.Nomm.yaml) in the repo.

But it boils down to the following:
- Internet access
- A few very specific paths to get the locations of your libraries (basically paths to Steam / Heroic configuration files)

...And that's it!

Once it has found your libraries, NOMM will simply and transparently ask you to execute a command that will give it access to them!

You, the user, will decide whether or not you want NOMM to have access to them.

We understand if you don't want to share all your libraries with NOMM, so we give you the opportunity to ignore this request at startup.