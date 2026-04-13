---
title: Intro
description: Introduction to codots
sidebar:
    order: 1
---

codots is a NixOS + Home Manager configuration using flakes and a dendritic module structure.

## Prerequisites

- **Nix**: Install from [nixos.org](https://nixos.org/download.html).
- **Flakes**: Ensure flakes are enabled.
- **Home Manager**: Included as a flake input.

## Quick Start

```bash
git clone https://github.com/constructor2828-web/codots ~/.codots
cd ~/.codots
```

Edit `flake.nix` to set your `username` and `hostname`.

```bash
nix flake check
sudo nixos-rebuild switch --flake .
```

Or use the Makefile:

```bash
make switch
```