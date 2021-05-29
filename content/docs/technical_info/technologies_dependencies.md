---
title: "Technologies and dependencies"
weight: 1
---

| Logo | Description | License |
|:---: | ----------- | ------- |
| {{< logo5rem alt="C++ Logo" src="../../../img/cpp_logo.png" class="logo" >}} | BrickSim uses [C++](https://www.cplusplus.com/). The main reason for this choice was execution speed.  | - |
| {{< logo5rem alt="CMake Logo" src="../../../img/cmake_logo.png" class="logo" >}} | BrickSim is built using the platform-independent build system [CMake](https://cmake.org/).  | [BSD 3-clause](https://cmake.org/licensing/)
| {{< logo5rem alt="Dear ImGui Logo" src="../../../img/dear_imgui_logo.png" class="logo" >}} | The User Interface is made with [Dear ImGui](https://github.com/ocornut/imgui).  | [MIT](https://github.com/ocornut/imgui/blob/master/LICENSE.txt) |
| {{< logo5rem alt="OpenGL Logo" src="../../../img/openGL_logo.svg" class="logo" >}} | [OpenGL](https://www.opengl.org/) is used for rendering on all platforms.  | - |
| {{< logo5rem alt="SQLite Logo" src="../../../img/sqlite_logo.gif" class="logo" >}} | [SQLite3](https://www.sqlite.org/index.html) is used to save settings and cache to the disk. The library [SQLiteCpp](https://github.com/SRombauts/SQLiteCpp.git) is used. | [Public Domain](https://www.sqlite.org/copyright.html), [MIT](https://github.com/SRombauts/SQLiteCpp/blob/master/LICENSE.txt) |
| {{< logo5rem alt="Hugo Logo" src="../../../img/hugo_logo.svg" class="logo" >}} | [Hugo](https://gohugo.io/) is a static site generator using go. It is used in [BrickSimWeb](https://github.com/bb1950328/BrickSimWeb). | [Apache 2.0](https://gohugo.io/about/license/) |
| [mingw-std-threads](https://github.com/meganz/mingw-std-threads) | to use `std::thread` on MinGW. | [BSD 2-clause license](https://github.com/meganz/mingw-std-threads/blob/master/LICENSE) |
| [GLFW](https://github.com/glfw/glfw.git) |  to create a window and handle inputs. | [zlib/libpng](https://www.glfw.org/license) |
| [glad](https://glad.dav1d.de/)  | to load the OpenGL library | [MIT](https://github.com/Dav1dde/glad/blob/master/LICENSE) |
| [Miniball](https://people.inf.ethz.ch/gaertner/subdir/software/miniball.html) | to determine the smallest enclosing ball of points, for example to center the part thumbnails. | [GPLv3](https://people.inf.ethz.ch/gaertner/subdir/software/miniball.html) |
| [stb_image.h](https://github.com/nothings/stb/blob/master/stb_image.h)  and [stb_image_write.h](https://github.com/nothings/stb/blob/master/stb_image_write.h) | for image reading and writing. | [Public domain](https://github.com/nothings/stb#whats-the-license) |
| [tinyfiledialogs](https://sourceforge.net/projects/tinyfiledialogs/) | to open native file dialogs on all platforms. | [zlib/libpng](https://sourceforge.net/projects/tinyfiledialogs/) |
| [rapidjson](https://github.com/Tencent/rapidjson) | to read and write data in the JSON format. | [MIT](https://github.com/Tencent/rapidjson/blob/master/license.txt) |
| {{< logo5rem alt="Catch2 Logo" src="../../../img/catch2_logo.png" class="logo" >}} | used for unit testing. | [Boost Software License 1.0 ](https://github.com/catchorg/Catch2/blob/devel/LICENSE.txt) |
| [pytorch/cpuinfo](https://github.com/pytorch/cpuinfo) | used to get information about the processor | [BSD-2-Clause](https://github.com/pytorch/cpuinfo/blob/master/LICENSE) |
| [magic_enum](https://github.com/Neargye/magic_enum) | used for easier enum handling | [MIT](https://github.com/Neargye/magic_enum/blob/master/LICENSE) |