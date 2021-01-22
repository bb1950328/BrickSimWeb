---
title: "Linux"
weight: 2
---
1. Go to [CMake Linux Build](https://github.com/bb1950328/BrickSim/actions?query=branch%3Astable+workflow%3A%22CMake+Linux+Build%22), select the topmost run and download the "BrickSimLinux" artifact.
1. Unzip it somewhere
1. Open the terminal and go to the folder you unzipped the files
1. Install the package using `sudo apt install ./BrickSim.deb`  
   Maybe you will get a message like `E: Unmet dependencies. Try 'apt --fix-broken install' with no packages (or specify a solution).`  
   As the message already says, you have to execute `apt --fix-broken install`
1. Run the program with `BrickSim`

If you want to uninstall it, execute `sudo apt remove bricksim`