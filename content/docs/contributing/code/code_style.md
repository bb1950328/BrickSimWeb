---
title: "Code style"
weight: 2
---

A consistent code style is important for everyone. Pull requests are only accepted if they follow our code style. But don't worry, it's not that difficult. The main points are:
1. Reformat your code with `clang-format`. There is a [`.clang-format`](https://github.com/bb1950328/BrickSim/blob/master/.clang-format) file in the repository root.
1. Function and method names are in `camelCase`
1. Class and struct names are in `PascalCase`
1. Namespaces, files and directories are named in `snake_case`
1. Headers have the extension `.h` and C++ source files are named `.cpp`
1. Macros and constants are in `SCREAMING_SNAKE_CASE` and macros are prefixed with `BRICKSIM_`
1. Typedefs are `snake_case_t` (with `_t` postfix)
1. No `using namespace` in headers and no `using namespace std` in `.cpp` files
1. When there is no explicit rule for something, ask or adapt to the existing code