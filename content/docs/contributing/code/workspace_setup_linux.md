---
title: "Linux Workspace Setup"
weight: 1
---

1. Update your package index: `sudo apt update`
1. Install some tools for C++ development (if you haven't already): `sudo apt install build-essential`
1. Clone out this repository with `git clone --recurse-submodules -j8 git://github.com/bb1950328/BrickSim.git`
1. Execute the following commant to unzip glew: `unzip src/lib/glew-2.1.0.zip && mv glew-2.1.0 src/lib/glew`
1. Copy the glad includes: `sudo unzip -o src/lib/glad.zip "include/*" -d "/usr"`
1. Install some libraries: `sudo apt-get install mesa-utils freeglut3-dev libxinerama-dev libxrandr-dev libxcursor-dev libxi-dev libglew-dev libcurl4-openssl-dev libglm-dev libzip-dev`
1. Open your project with your favourite IDE (I recommend CLion). It should support CMake.