---
title: "Using XCode on macOS"
weight: 5
---

1. Download XCode from the AppStore if you haven't already
2. Clone the repository. The cloning feature of XCode did't work correctly on my machine, so I cloned it from the command line:
   `git clone https://www.github.com/bb1950328/BrickSim`
3. In the terminal, navigate to the cloned folder and execute `./setup_workspace.sh`
4. Because XCode doesn't have a bundled CMake, you have to install it with `brew install cmake`
5. Then you can generate the XCode project files with cmake: `mkdir cmake-build && cd cmake-build && cmake -G Xcode ..` (you have to be inside the `BrickSim` directory)
6. Open the BrickSim folder in XCode