# Arch-Custom-PKGs

A collection of my personal **PKGBUILD** scripts for building packages on Arch-based systems (Arch Linux, CachyOS, EndeavourOS, etc.).

## ⚠️ Disclaimer ⚠️
**Use these PKGBUILDs at your own risk.**

Before building or installing any package, always review the contents of the PKGBUILD and any included files (.install, .patch, etc.) to ensure they are safe and do what you expect.

## Structure
Each directory corresponds to a single package and contains a `PKGBUILD` file along with any additional files (e.g. `install`, `patch`, `service`).

```
pkgname/
├── PKGBUILD
└── ...
```

## Building a package
To build and install a package:
```
makepkg -si
```
Or to build only (without installing):
```
makepkg -sf
```

## Usage
You can clone the repository and build any package locally:
```
git clone https://github.com/odziom91/arch-custom-pkgs.git
cd arch-custom-pkgs/<package-name>
makepkg -si
```