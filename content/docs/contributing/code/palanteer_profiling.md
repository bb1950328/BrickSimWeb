---
title: "Profiling with Palanteer"
weight: 3
---

BrickSim uses [Palanteer](https://dfeneyrou.github.io/palanteer/) for instrumentation / profiling.
Like all dependencies it's included as a git submodule in `/src/lib/palanteer`.
To run BrickSim with Palanteer, you have to build it first.
Read the [Docs](https://dfeneyrou.github.io/palanteer/getting_started.md.html) of palanteer to see how to build it.
You also have to enable Palanteer in BrickSim. For that you have to enable the CMake option `USE_PALANTEER`.