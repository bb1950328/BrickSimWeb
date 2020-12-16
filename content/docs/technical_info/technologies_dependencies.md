---
title: "Technologies and dependencies"
weight: 1
---

| Logo | Description |
|:---- | ----------- |
| {{< logo5rem alt="C++ Logo" src="https://raw.githubusercontent.com/isocpp/logos/master/cpp_logo.png" class="logo" >}} | BrickSim uses C++. The main reason for this choice was execution speed.  |
| {{< logo5rem alt="CMake Logo" src="https://cmake.org/wp-content/uploads/2019/05/Cmake-logo-header.png" class="logo" >}} | BrickSim is built using the platform-independent build system CMake.  |
| {{< logo5rem alt="Dear ImGui Logo" src="../../../img/dear_imgui_logo.png" class="logo" >}} | The User Interface is made with [Dear ImGui](https://github.com/ocornut/imgui).  |
| {{< logo5rem alt="OpenGL Logo" src="../../../img/openGL_logo.svg" class="logo" >}} | OpenGL is used for rendering on all platforms.  |
| {{< logo5rem alt="SQLite Logo" src="../../../img/sqlite_logo.gif" class="logo" >}} | SQLite3 is used to save settings and cache to the disk. The library [SQLiteCpp](https://github.com/SRombauts/SQLiteCpp.git) is used. |

* [mingw-std-threads](https://github.com/meganz/mingw-std-threads) is needed to use `std::thread` on MinGW.
* [GLFW](https://github.com/glfw/glfw.git) is used to create a window and handle inputs.
* [glad](https://glad.dav1d.de/) is used to load the OpenGL library
* [glew](http://glew.sourceforge.net/) is used to load OpenGL extensions.
* [Miniball](https://people.inf.ethz.ch/gaertner/subdir/software/miniball.html) is used to determine the smallest enclosing ball of points, for example to center the part thumbnails.
* [stb_image.h](https://github.com/nothings/stb/blob/master/stb_image.h) and [stb_image_write.h](https://github.com/nothings/stb/blob/master/stb_image_write.h) and is used for image reading and writing.
* [tinyfiladialogs](https://sourceforge.net/projects/tinyfiledialogs/) is used to open native file dialogs on all platforms.