---
title: "Workspace Setup"
weight: 1
---

This page describes how to set up your workspace, so you can develop on BrickSim too.

## Preparation on Windows
1. Download MSYS2 from [https://www.msys2.org/](https://www.msys2.org/) and follow the installation instructions there.
1. Execute the following command in a MSYS2 Shell to install git: `pacman -S git`

## Preparation on MacOS
1. Execute the following command to install the XCode command line tools if you haven't already: `sudo xcode-select --install`

## Preparation on Linux
1. Execute the following command to install git `sudo apt install git`

## Setup the workspace
1. Do the platform-specific preparation
1. Clone the repository by `git clone --recurse-submodules -j8 https://github.com/bb1950328/BrickSim.git`
1. You can execute the [`setup_workspace.sh`](https://github.com/bb1950328/BrickSim/blob/master/setup_workspace.sh)

## Open the IDE
The project is CMake-based, so your IDE should support CMake.
I recommend you to use [CLion](https://www.jetbrains.com/clion/).  
You can follow [this tutorial](../vscode_setup_windows) if you want to use VS Code on Windows.
A tutorial for VS Code ({{< issue 15 >}}), Visual Studio 2019 ({{< issue 16 >}}) and XCode ({{< issue 16 >}}) is in planning.