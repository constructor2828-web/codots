---
title: "Post-Installation"
desc: "Things to do after installing codots"
sidebar:
    order: 3
---

- **Change the password** -> Change the initial password using `sudo passwd <username>`.
- **Set your timezone** -> Edit `hosts/default/configuration.nix` and set `time.timeZone`.
- **Updating codots** -> Run `make update` or `nix flake update`.
- **Configuring stuff** -> Most configs are in `modules/`. Edit the relevant `.nix` files to enable/disable features.
- **Check hosts** -> Go through `hosts/default/configuration.nix` and make changes as needed.