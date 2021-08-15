---
title: "Using CLion on Windows"
weight: 6
---

1. Add `C:\msys64\usr\bin\` to your windows `PATH` environment variable.
2. Download and install CLion if not already done.
3. Open CLion and open the directory where you cloned BrickSim into
4. If you haven't configured any toolchains yet, a popup named "Open Project Wizard" will open. Click on the blue text "MinGW".
5. Enter a path in the "Environment" field. Usually, this is `C:\msys64\mingw64`. You can leave the rest like it is and press "Next".
6. On the next screen, you have to change the "Build directory" to `cmake-build/debug64`. If you want, you can also add a "Release" configuration:
   ![CLion Debug Profile](../../../../../img/CLionDebugProfile.png)
7. After that, you can click "Finish". You may have to set the Git executable path in the settings. On my system, it was `C:\msys64\usr\bin\git.exe`.
8. You should now be able to run BrickSim by clicking the green play symbol.