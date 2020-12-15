---
title: "Linux"
weight: 2
---
1. Go to [CMake Linux Build](https://github.com/bb1950328/BrickSim/actions?query=branch%3Astable+workflow%3A%22CMake+Linux+Build%22), select the topmost run and download the "BrickSimLinux" artifact.
1. Unzip it somewhere
1. Open the terminal and go to the folder you unzipped the files
1. Mark the program as executable with the following command: `chmod a+x BrickSim`
1. Install some dependencies: `sudo apt install libgl1-mesa-dev libglew-dev`
1. Run the program with `./BrickSim`