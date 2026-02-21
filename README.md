# seeded

**seeded** is a fast, minimal command-line tool written in **C** for generating Debian metapackages from simple `.seed` files.

It is designed for Linux distribution builders, maintainers, and automated build systems that need a reliable way to define package sets and turn them into reproducible Debian source packages.

seeded is developed as part of the **Valhalla Linux Ragnarök** tooling stack, but works on any Debian-based system.

---

## Overview

Creating metapackages manually is repetitive and error-prone. seeded solves this by converting a human-readable `.seed` definition into a fully structured Debian source package.

A `.seed` file describes:

- Package name
- Dependencies
- Optional relationships
- Description metadata

seeded then generates a ready-to-build Debian package skeleton.

---

## Features

- Generate Debian metapackage sources from `.seed` files
- Debian policy-friendly output
- Lightweight native C implementation
- Works with `dpkg-buildpackage`, `sbuild`, and custom build farms
- Designed for distro maintainers
- Deterministic output for reproducible builds

---

## Repository Structure
├── src/ # seeded source code
├── include/ # headers
├── debian/ # Debian packaging
├── examples/ # example .seed files
└── Makefile

---

## Installation

### Build from Source

```bash
git clone https://github.com/jafetegill33/seeded.git
cd seeded
make
sudo install -m755 seeded /usr/local/bin/

## Usage

### Commands
seeded verify <file.seed>
seeded print-deps <file.seed>
seeded render <file.seed> -o <outdir> [--version X] [--maintainer "Name <email>"] [--distro yourdistro]
seeded build  <file.seed> -o <outdir> [--version X] [--maintainer "Name <email>"] [--distro yourdistro]
seeded verify yourdistro-desktop-xfce4.seed
seeded print-deps yourdistro-desktop-xfce4.seed
seeded render valhalla-desktop-xfce4.seed -o out \
  --version 1.0 \
  --maintainer "your name <yourname@example.com>"

## Seed File Example

### usage
Package: yourdistro-desktop-xfce4
Section: metapackages
Priority: optional

Description: yourdistro XFCE Desktop
 XFCE desktop environment for yourdistro.

Depends:
 xfce4
 xfce4-goodies
 lightdm
 network-manager

## Supported Fields

### Currently Supported

Package

Section

Priority

Description

Depends

Recommends

Suggests

Provides

Conflicts

Breaks

## Generated Packaging

### How It Looks

<package>/
 ├── debian/
 │   ├── control
 │   ├── rules
 │   ├── changelog
 │   ├── copyright
 │   └── source/format
 └── README.seeded

## Status

### Current Status
Status

Current version: v1

Stable:

.seed parsing

metapackage generation

Debian-native layout

Planned:

seed inheritance

architecture filters

autopkgtest scaffolding

profile layering

## Contributing
Issues and pull requests are welcome.
Before submitting

### usage
make clean
make

## License
MIT License

See the LICENSE file for details.
