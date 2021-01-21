---
title: "Using VS Code on Windows"
weight: 2
---

1. add `C:\msys64\mingw64\bin` to PATH
1. Download and install VS Code from [here](https://code.visualstudio.com/download) if you haven't already
1. Install the extensions `ms-vscode.cpptools` and `ms-vscode.cmake-tools`
1. Open the BrickSim folder in VS Code. you should get the notifications like in the following screenshot (at least the first one):  
   ![screenshot of VS Code notifications after opening the project the first time](../../../../img/vscode_windows_screenshot1.png)  
   click "yes" on the first notification, we'll deal with the second one later.
1. Now it's time to adjust some settings:
   1. Press <kbd>Ctrl</kbd> + <kbd>Shift</kbd>+ <kbd>P</kbd> and type "preferences: Open Settings (JSON)"  
      ![After pressing Ctrl+Shift+P and typing "preferences: Open Settings (JSON)"](../../../../img/vscode_windows_screenshot2.png)  
      Hit <kbd>Enter</kbd> or click the first result.
   1. add the following text:
      ```json
      {
         "cmake.configureOnOpen": true,
         "cmake.cmakePath": "C:\\msys64\\mingw64\\bin\\cmake.exe",
         "cmake.generator": "MinGW Makefiles",
         "cmake.buildDirectory": "${workspaceFolder}/cmake-build",
         "cmake.mingwSearchDirs": [
            "C:\\msys64\\mingw64\\bin"
         ],
      
         "cmake.debugConfig": {
            "cwd": "${workspaceFolder}"
         },
      
         "terminal.integrated.shell.windows": "C:\\msys64\\usr\\bin\\bash.exe",
         "terminal.integrated.shellArgs.windows": ["-li"],
         "terminal.integrated.env.windows": {
            "MSYSTEM": "MINGW64",
            "CHERE_INVOKING": "1",
         },
      }
      ```
      Maybe you already have some settings here so make sure they don't contradict each other.
   1. Save the `settings.json` file.
   1. Now press <kbd>Ctrl</kbd>+<kbd>Shift</kbd>+<kbd>P</kbd> and type "CMake: Edit User-Local CMake Kits"  
      ![After pressing Ctrl+Shift+P and typing "CMake: Edit User-Local CMake Kits"](../../../../img/vscode_windows_screenshot3.png)
   1. Insert the following code: 
      ```json
      [
         {
            "name": "Mingw64 GCC",
            "compilers": {
               "C": "C:\\msys64\\mingw64\\bin\\gcc.exe",
               "CXX": "C:\\msys64\\mingw64\\bin\\g++.exe"
            },
            "preferredGenerator": {
               "name": "MinGW Makefiles",
               "platform": "x64"
            },
            "environmentVariables": {
               "PATH": "C:/msys64/mingw64/bin/"
            }
         }
      ]
      ```
   1. Save the `cmake-tools-kits.json` file.
1. Download git for windows from [here](https://git-scm.com/download/win) and install it if you want git integration in VS Code.
1. Restart VS Code
1. You should now be able to launch the application using the bottom status bar:  
   ![VS Code status bar with mouse hovering the run icon](../../../../img/vscode_windows_screenshot4.png)

