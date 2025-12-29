![Plugin Icon](assets/icon.png)

# OpenDeck Ajazz AKP05 / Mirabox N4 / VSDInside N4 Pro / Soomfon CN003 Plugin

An unofficial plugin for Mirabox N4-family devices

## OpenDeck version

Requires OpenDeck 2.5.0 or newer

## Supported devices

- Mirabox N4 (6603:1007)
- Ajazz AKP05E (0300:3004)
- VSDInside N4 Pro (5548:1023)
- Soomfon CN003 (1500:3002)

## Installation

1. Download an archive from [releases](https://github.com/4ndv/opendeck-akp03/releases)
2. In OpenDeck: Plugins -> Install from file
3. Download [udev rules](./40-opendeck-akp03.rules) and install them by copying into `/etc/udev/rules.d/` and running `sudo udevadm control --reload-rules`
4. Unplug and plug again the device, restart OpenDeck

## Building

### Prerequisites

You'll need:

- A Linux OS of some sort
- Rust 1.87 and up with `x86_64-unknown-linux-gnu` and `x86_64-pc-windows-gnu` targets installed
- gcc with Windows support
- Docker
- [just](https://just.systems)

On Arch Linux:

```sh
sudo pacman -S just mingw-w64-gcc mingw-w64-binutils
```

Adding rust targets:

```sh
rustup target add x86_64-pc-windows-gnu
rustup target add x86_64-unknown-linux-gnu
```

### Preparing environment

```sh
$ just prepare
```

This will build docker image for macOS crosscompilation

### Building a release package

```sh
$ just package
```

## Acknowledgments

This plugin is a fork of [ambiso's opendeck-akp05](https://github.com/ambiso/opendeck-akp05) plugin, modified to support Soomfon CN003 and changed dial/touch behaviour.

The icon was yoinked from https://github.com/naerschhersch/opendeck-akp05/