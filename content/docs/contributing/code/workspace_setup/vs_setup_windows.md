---
title: "Using Visual Studio 2022 on Windows"
weight: 4
---

1. Download Visual Studio 2022 from [here](https://visualstudio.microsoft.com/en/downloads/) if you haven't already
2. Install the C++ workload.
   ![VS 2022 install C++ workload](../../../../../img/vs_windows_install_cpp_workload.png)
3. When the installer has finished, launch Visual Studio
4. Clone the repository (`https://www.github.com/bb1950328/BrickSim.git`)
   ![VS 2022 clone BrickSim repository](../../../../../img/vs_windows_clone_repo.png)
5. In "Solution Explorer", select the "Folder View":
   ![VS 2022 select folder view in solution explorer](../../../../../img/vs_windows_solution_explorer_select_folder_view.png)
6. Install vcpkg like described [here](https://vcpkg.io/en/getting-started.html). If your vcpkg root is not next to the BrickSim root, you will have to edit the toolchain path in `BrickSim/CMakeSettings.json`.
7. Add the vcpkg root folder to your `Path` environment variable and create a new one called `VCPKG_DEFAULT_TRIPLET` with the value `x64-windows`
8. Restart your computer
9. Open a PowerShell, navigate to the BrickSim root folder and execute `.\setup_workspace.ps1` to install some dependencies and unzip `glad.zip`
10. Right-click on `CMakeLists.txt` in the "Solution Explorer" and choose "Configure Cache"
11. Click on the small arrow next to "Select Startup Item" and choose "BrickSim.exe". Then click on the green play button.
    ![VS 2022 Select startup item](../../../../../img/vs_windows_select_startup_item.png)
