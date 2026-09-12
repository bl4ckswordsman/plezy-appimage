# Plezy AppImage

**🇬🇧 English** &nbsp;|
[简体中文](README.zh-CN.md) &nbsp;|
[Español](README.es.md) &nbsp;|
[हिन्दी](README.hi.md) &nbsp;|
[عربي](README.ar.md)

[![Build & Publish AppImage](https://github.com/bl4ckswordsman/plezy-appimage/actions/workflows/extract.yaml/badge.svg)](https://github.com/bl4ckswordsman/plezy-appimage/actions/workflows/extract.yaml)

Distro-agnostic AppImage packages for [Plezy](https://github.com/edde746/plezy) — a modern cross-platform Plex & Jellyfin client built with Flutter.

Releases are built automatically from upstream [edde746/plezy](https://github.com/edde746/plezy) releases and published here as self-contained AppImages. No root, no package manager, no distro-specific dependencies.

> [!NOTE]
> **Looking for Android?** Check out [plezy-apks](https://github.com/bl4ckswordsman/plezy-apks) for F-Droid and Obtainium releases.

---

## Download

Go to the [Releases page](https://github.com/bl4ckswordsman/plezy-appimage/releases/latest) and grab the file for your architecture:

| File | For |
| --- | --- |
| `Plezy-<version>-x86_64.AppImage` | Most desktop/laptop systems (Intel/AMD 64-bit) |
| `Plezy-<version>-aarch64.AppImage` | ARM systems (Raspberry Pi 5, Pinebook Pro, etc.) |
| `*.AppImage.zsync` | Delta updates via AppImageUpdate / Gear Lever |

---

## Install via Gear Lever

[Gear Lever](https://flathub.org/apps/it.mijorus.gearlever) is a GUI AppImage manager for GNOME that handles desktop integration and delta updates.

[![Install from Flathub](https://flathub.org/api/badge?locale=en)](https://flathub.org/apps/it.mijorus.gearlever)

<details>
<summary>Manual steps without Gear Lever</summary>

```bash
# 1. Download the AppImage (replace VERSION with the release tag, e.g. 2.19.1)
wget https://github.com/bl4ckswordsman/plezy-appimage/releases/download/VERSION/Plezy-VERSION-x86_64.AppImage

# 2. Make it executable
chmod +x Plezy-VERSION-x86_64.AppImage

# 3. Run it
./Plezy-VERSION-x86_64.AppImage
```

</details>

---

## FUSE requirement

AppImages use FUSE (Filesystem in Userspace) to mount their embedded filesystem at runtime.

| Distro | Install command |
| --- | --- |
| Ubuntu 22.04+ / Debian 12+ | `sudo apt install libfuse2` |
| Fedora | `sudo dnf install fuse` |
| Arch Linux | `sudo pacman -S fuse2` |

**No FUSE available?** Run the AppImage without mounting it:

```bash
./Plezy-VERSION-x86_64.AppImage --appimage-extract-and-run
```

---

## Upstream project

- **Canonical upstream:** [edde746/plezy](https://github.com/edde746/plezy)
- **Android packages:** [bl4ckswordsman/plezy-apks](https://github.com/bl4ckswordsman/plezy-apks)

---

## License

The packaging scripts in this repository are released under the [MIT License](LICENSE). Plezy itself is the work of its [upstream authors](https://github.com/edde746/plezy/blob/main/LICENSE).
