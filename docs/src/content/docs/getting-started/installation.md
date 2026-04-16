---
title: Installation
description: How to install codots
sidebar:
  order: 2
---

## Fresh Install

1. Fetch codots:
   ```bash
   nix-shell -p git --run "git clone https://github.com/constructor2828-web/codots ~/.codots"
   cd ~/.codots
   ```

2. Edit `flake.nix` to set your `username` and `hostname`.

3. Choose a host. Look into `hosts/` to see available hosts (e.g., `default`).

4. Run `make switch` to apply the configuration.

## On Existing Install

On a system that already has NixOS installed:

```bash
nix-shell -p git --run "git clone https://github.com/constructor2828-web/codots ~/.codots"
cd ~/.codots
make update
make switch
```

Or directly:

```bash
sudo nixos-rebuild switch --flake .#<hostname>
```

### Troubleshooting: Home Manager packages not installing

If `home-manager-<username>.service` is missing, usually one of these is true:

1. You still have placeholder values in `flake.nix` (`username = "user"` and/or `hostname = "nixos"`).
2. You changed `flake.nix` but did not run a new rebuild.
3. You are checking `systemctl` as a different user than the one configured in `flake.nix`.

After editing `flake.nix`, rebuild again:

```bash
sudo nixos-rebuild switch --flake .#<hostname>
```

Then verify with your configured user:

```bash
systemctl status home-manager-<username>.service
```
