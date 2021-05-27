---
title: GitHub Actions Build
weight: 4
---

## Jobs
All jobs are defined in one workflow file, [.github/workflows/cmake_build.yml](https://github.com/bb1950328/BrickSim/blob/master/.github/workflows/cmake_build.yml). Splitting them into multiple smaller files is unfortunately not possible, because sharing data between different workflows is difficult.  
There are three jobs which do the actual compilation `buildLinux`, `buildWindows` and `buildMac`. The output of these jobs are saved in Artifacts named `BrickSimRawBinary_{platform}` and `BrickSimTests_{platform}`.  
The jobs `testLinux` and `testWindows` then download the `BrickSimTests_{platform}` artifacts and run them. They then upload the output as an artifact named `UnitTestReport_{platform}`  

### Build
These jobs are essentially the same for all platforms:
1. Clone the repository
1. Run [`setup_workspace.sh`](https://github.com/bb1950328/BrickSim/blob/master/setup_workspace.sh)
1. Install other tools like `ccache`
1. Setup cache
1. Configure CMake
1. Build
1. Upload artifacts

### Installer Build
These jobs depend on the build jobs because they obviously need the raw binary to pack it into the installer. The steps are also mostly the same on all platforms:
1. Clone the repository
1. Install VMware InstallBuilder
1. Download the raw binary artifact and copy it where it was
1. Build the installer
1. Upload it as an artifact

### Test
These jobs execute the `BrickSimTests` executable built by the build jobs. Currently they run the tests on `Linux64`, `Windows32` and `Windows64`.
After running, they upload the test report as an artifact.

### Publish test results
After all tests have run, this job downloads all report artifacts and publishes a comment with the formatted results on the commit or pull request.

## Platforms
Name | Architecture | Description |
---- | ------------ | ----------- |
`Linux64` | `x86_64` | Linux 64bit |
`Linux32` | `i386` | Linux 32bit |
`Windows64` | `x86_64` | Windows 64bit |
`Windows32` | `i686` | Windows 32bit |
`Mac64` | `x86_64` | MacOS 64bit (for Intel processors) |
`MacARM` | `arm64` | MacOS ARM64 (for Apple Silicon processors) |
