# seeded

**seeded** is a fast, minimal command-line tool written in **C** for generating Debian metapackages from simple `.seed` files.

It is designed for Linux distribution builders, maintainers, and automated build systems that need a reliable way to define package sets and turn them into reproducible Debian source packages.

seeded is developed as part of the **ValhallaOS Ragnarök** tooling stack, but works on any Debian-based system.

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
