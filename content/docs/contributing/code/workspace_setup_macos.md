---
title: "MacOS Workspace Setup"
weight: 3
---
Tested on a MacOS 10.13 VM

1. Install CLion like described in the [JetBrains Docs](https://www.jetbrains.com/help/clion/quick-tutorial-on-configuring-clion-on-macos.html#furthersteps).
   You can use another IDE, but you have to figure out by yourself how to install it. Please add a short description here if you know it for other IDEs.
1. Clone this repository with `git clone --recurse-submodules -j8 git://github.com/bb1950328/BrickSim.git` or using the feature in your IDE.
1. Execute the following command to unzip glew: `unzip src/lib/glew-2.1.0.zip && mv glew-2.1.0 src/lib/glew`
1. Copy the glad includes: `sudo unzip -o src/lib/glad.zip "include/*" -d "/Library/Developer/CommandLineTools/usr"`. The last path may be different if you have Xcode installed instead of command line tools.
1. If you don't have homebrew, install it: `/bin/bash -c "$(curl -fsSL https://raw.githubusercontent.com/Homebrew/install/master/install.sh"`
1. Install libraries: `brew install glm`
1. If you have CLion, you should do `Tools` > `CMake` > `Reload CMake project` now.