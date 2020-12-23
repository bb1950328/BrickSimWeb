---
title: "Windows Workspace Setup"
weight: 2
---

1. Download MSYS2 from [https://www.msys2.org/](https://www.msys2.org/) and follow the installation instructions there
1. Execute the following command in a MSYS2 Shell: `pacman -S git mingw-w64-x86_64-toolchain mingw-w64-i686-toolchain base-devel mingw-w64-x86_64-cmake mingw-w64-i686-cmake libcurl-devel $(pacman -Ssq freeglut) mingw-w64-x86_64-glm mingw-w64-i686-glm mingw-w64-x86_64-libzip mingw-w64-i686-libzip`
1. Clone out this repository with `git clone --recurse-submodules -j8 git://github.com/bb1950328/BrickSim.git`
1. Unzip `src/lib/glew-2.1.0.zip` and rename the resulting folder from `glew-2.1.0` to `glew`
1. Unzip the include folder of `src/lib/glad.zip` and copy the `glad` and `KHR` folders to `C:\msys64\mingw32\include` and to `C:\msys64\mingw64\include`
1. Open your project with your favourite IDE (I recommend CLion). It should support CMake.