---
title: Installation
description: How to install codots
sidebar:
  order: 2
---

## Fresh Install

1. Fetch codots:
   ```bash
   git clone https://github.com/constructor2828-web/codots ~/.codots
   cd ~/.codots
   ```

2. Edit `flake.nix` to set your `username` and `hostname`.

3. Choose a host. Look into `hosts/` to see available hosts (e.g., `default`).

4. Run `make switch` to apply the configuration.

## On Existing Install

On a system that already has NixOS installed:

```bash
cd ~/.codots
make update
make switch
```

Or directly:

```bash
sudo nixos-rebuild switch --flake .#<hostname>
```