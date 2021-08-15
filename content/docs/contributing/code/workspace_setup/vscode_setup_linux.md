---
title: "Using VS Code on Linux"
weight: 3
---

This tutorial was tested on Ubuntu 20.10, but it should work too on other versions or distributions. You'll have to install packages manually if you don't have `apt`.

1. Install VS Code via [a way described in the offical VS Code docs](https://code.visualstudio.com/docs/setup/linux)
1. Open VS Code and install the `ms-vscode.cpptools` and `ms-vscode.cmake-tools` extensions
1. Press <kbd>Ctrl</kbd> + <kbd>Shift</kbd>+ <kbd>P</kbd> and type "preferences: Open Settings (JSON)"  
   ![After pressing Ctrl+Shift+P and typing "preferences: Open Settings (JSON)"](../../../../../img/vscode_windows_screenshot2.png)  
   Hit <kbd>Enter</kbd> or click the first result and add the following text:
   ```json
   {
      "cmake.buildDirectory": "${workspaceFolder}/cmake-build",
      "cmake.debugConfig": {
         "cwd": "${workspaceFolder}"
      },
   }
   ```
1. Open the BrickSim folder in VS Code. You should get a notification like this one:  
   ![screenshot of VS Code notifications after opening the project the first time](../../../../../img/vscode_linux_screenshot1.png)
   Click "Yes" on that notification
1. You will get a prompt looking like this:
   ![select cmake kit prompt in VS Code on linux](../../../../../img/vscode_linux_screenshot2.png)
   Select the one with `/bin/gcc`, the second last element on this screenshot
1. The "Play" button in the bottom status bar doesn't choose the correct working directory
   as described in [microsoft/vscode-cmake-tools#1395](https://github.com/microsoft/vscode-cmake-tools/issues/1395)  
   You have to run it from the menu on the left side:
   ![run configuration in VS Code on linux](../../../../../img/vscode_linux_screenshot3.png)