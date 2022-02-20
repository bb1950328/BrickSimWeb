---
title: "Using XCode on macOS"
weight: 5
---

1. Download XCode from the AppStore if you haven't already
2. 1. Execute the following command to install the XCode command line tools if you haven't already: `sudo xcode-select --install`
3. Clone the repository. The cloning feature of XCode did't work correctly on my machine, so I cloned it from the command line:
   `git clone --recurse-submodules -j8 https://www.github.com/bb1950328/BrickSim.git`
4. In the terminal, navigate to the cloned folder and execute `./setup_workspace.sh`
5. Install CMake. You can install the CMake GUI from [here](https://cmake.org/download/) or just the command line version with `brew install cmake`
6. Then you can generate the XCode project files.
   * If you have the CMake GUI, you can configure the project like this:
     1. Set the path of the directory you just cloned BrickSim into:
        ![configure CMake Project for Xcode using CMake GUI](../../../../../img/xcode_cmake_gui_step1.png)
     2. Click on "Configure" (Click on "Yes" if the question "Build directory does not exist, should I create it?" pops up:
        ![configure CMake Project for Xcode using CMake GUI](../../../../../img/xcode_cmake_gui_step2.png)
     3. Click on "Done" after setting the generator to "Xcode". After waiting a minute, the window should look like this:
        ![configure CMake Project for Xcode using CMake GUI](../../../../../img/xcode_cmake_gui_step3.png)
     4. Check the log in the lower part of the window. Warnings are OK, errors are not. When there are no errors, click the "Generate" Button.
     5. The "Open Project" Button isn't greyed out anymore, and you can click it too.
     
   * If you have the command line cmake, execute the following commands:
     ```bash
     mkdir -p cmake-build
     cd cmake-build
     cmake -G Xcode ..
     ```
     (you have to be inside the `BrickSim` directory initially)
     Then you can open the project in Xcode.
7. When Xcode has loaded the project, you have to switch the target to BrickSim:
   ![Xcode target selection](../../../../../img/xcode_cmake_gui_step4.png)
8. After that, you should be able to build and run BrickSim. Happy coding!