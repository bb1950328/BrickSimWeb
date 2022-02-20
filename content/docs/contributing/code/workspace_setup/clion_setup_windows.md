---
title: "Using CLion on Windows"
weight: 6
---

1. Download MSYS2 from [https://www.msys2.org/](https://www.msys2.org/) and follow the installation instructions there.
2. Execute the following command in a MSYS2 Shell to install git: `pacman -S git`
3. Add `C:\msys64\usr\bin\` to your windows `PATH` environment variable.
4. Download and install CLion if not already done.
5. 1. Clone the repository by `git clone --recurse-submodules -j8 https://github.com/bb1950328/BrickSim.git`
1. Run [`setup_workspace.sh`](https://github.com/bb1950328/BrickSim/blob/master/setup_workspace.sh)
6. Open CLion and open the directory where you cloned BrickSim into
7. If you haven't configured any toolchains yet, a popup named "Open Project Wizard" will open. Click on the blue text "MinGW".
8. Enter a path in the "Environment" field. Usually, this is `C:\msys64\mingw64`. You can leave the rest like it is and press "Next".
9. On the next screen, you have to change the "Build directory" to `cmake-build/debug64`. If you want, you can also add a "Release" configuration:
   ![CLion Debug Profile](../../../../../img/CLionDebugProfile.png)
10. After that, you can click "Finish". You may have to set the Git executable path in the settings. On my system, it was `C:\msys64\usr\bin\git.exe`.
11. You should now be able to run BrickSim by clicking the green play symbol.