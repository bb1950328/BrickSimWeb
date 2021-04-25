---
title: "Code structure"
weight: 2
---

| Folder | Purpose |
| ------ | ------- |
| [`/.github`](https://github.com/bb1950328/BrickSim/blob/master/.github) | GitHub-specific things like Actions Workflows |
| [`/.idea`](https://github.com/bb1950328/BrickSim/blob/master/.github) | CLion configuration |
| [`/.vscode`](https://github.com/bb1950328/BrickSim/blob/master/.github) | VS Code configuration |
| [`/cmake-build`](https://github.com/bb1950328/BrickSim/blob/master/.github) | This folder is ignored in `.gitignore`. <br>You should set the CMake build directory to `/cmake-build/debug64` <br>in the Debug 64bit configuration for example. |
| [`/docs`](https://github.com/bb1950328/BrickSim/blob/master/.github) | This is the root of the [BrickSim.org](https://www.bricksim.org) Website. <br>Do not edit the content of this directory, it is automatically <br>updated when someone pushes to `master` in the [BrickSimWeb](https://www.github.com/bb1950328/BrickSimWeb) repository. |
| [`/resources`](https://github.com/bb1950328/BrickSim/blob/master/.github) | Non-code files like images or fonts |
| [`/scripts`](https://github.com/bb1950328/BrickSim/blob/master/.github) | Shell scripts |
| [`/src`](https://github.com/bb1950328/BrickSim/blob/master/.github) | All source code of the application itself |
| [`/src/constant_data`](https://github.com/bb1950328/BrickSim/blob/master/.github) | Constants and generated sources |
| [`/src/gui`](https://github.com/bb1950328/BrickSim/blob/master/.github) | All source files that belong to the graphical user interface |
| [`/src/helpers`](https://github.com/bb1950328/BrickSim/blob/master/.github) | Code that "helps" other code components. |
| [`/src/info_providers`](https://github.com/bb1950328/BrickSim/blob/master/.github) | Providers that load information about bricks. |
| [`/src/ldr_files`](https://github.com/bb1950328/BrickSim/blob/master/.github) | LDraw file parser |
| [`/src/lib`](https://github.com/bb1950328/BrickSim/blob/master/.github) | Third-party code |
| [`/src/shaders`](https://github.com/bb1950328/BrickSim/blob/master/.github) | OpenGL shader source files (`.fsh`=fragment, `.gsh`=geometry, `.vsh`=vertex) |
| [`/src/test`](https://github.com/bb1950328/BrickSim/blob/master/.github) | Catch2 unit tests |
| [`/src/tools`](https://github.com/bb1950328/BrickSim/blob/master/.github) | Code for tools like gear ratio calculator |
| [`/test_files`](https://github.com/bb1950328/BrickSim/blob/master/.github) | Files to test the LDraw parser |

