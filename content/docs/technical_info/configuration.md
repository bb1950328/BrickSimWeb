---
title: "Configuration"
weight: 5
---

The user configuration is saved in a file named `config.json` located in the working directory of the BrickSim executable.
The JSON is mapped to the struct `bricksim::config::Config`. Most places should use `bricksim::config::get()` to access the config (readonly). If you want to modify the config, use `bricksim::config::getMutable()` and `bricksim::config::save()`.
