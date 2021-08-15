---
title: "Using Visual Studio 2019 on Windows"
weight: 4
---

1. Download Visual Studio 2019 from [here](https://visualstudio.microsoft.com/en/downloads/) if you haven't already
2. Install the C++ workload. The option "C++ CMake tools for Windows" is very important.
   ![VS 2019 install C++ workload](../../../../../img/vs_windows_install_cpp.png)
3. Clone the repository (`https://www.github.com/bb1950328/BrickSim.git`)
   ![VS 2019 clone BrickSim repository](../../../../../img/vs_windows_clone_repo.png)
4. Install vcpkg like described [here](https://docs.microsoft.com/en-us/cpp/build/install-vcpkg?view=msvc-160&tabs=windows)
5. Navigate to the folder where you cloned vcpkg to and execute the following command: `vcpkg.exe install freeglut:x64-windows libzip:x64-windows curl:x64-windows spdlog:x64-windows glm:x64-windows`
6. Execute the following command in the `BrickSim` repository root: `mklink /H LICENSE.txt LICENSE`
   PowerShell:
```PowerShell
   Expand-Archive 'src\lib\rapidjson.zip' 'src\lib'
   Expand-Archive 'src\lib\glad.zip' 'glad_tmp'
   Move-Item -Path 'glad_tmp\src\glad.c' -Destination 'src\lib\glad.c'
   Move-Item -Path 'glad_tmp\include' -Destination 'src\lib\include'
   Remove-Item -Recurse -Force 'glad_tmp'
```
6. Open the "CMake settings" in Visual Studio and paste the following path to "CMake toolchain file": `-DCMAKE_TOOLCHAIN_FILE=C:\Users\YOUR_USERNAME\source\repos\vcpkg\scripts\buildsystems\vcpkg.cmake`
   ![VS 2019 set CMake toolchain path](../../../../../img/vs_cmake_toolchain_path.png)
