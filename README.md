# Plezy AppImage

**🇬🇧 English** &nbsp;|
[简体中文](README.zh-CN.md) &nbsp;|
[Русский](README.ru.md) &nbsp;|
[Українська](README.uk.md) &nbsp;|
[日本語](README.ja.md) &nbsp;|
[Español](README.es.md) &nbsp;|
[Português](README.pt-BR.md)

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

## AppImage Managers & Integration

For automatic desktop integration (app menu, icon) and delta updates, an AppImage manager is recommended:

- **[Gear Lever](https://flathub.org/apps/it.mijorus.gearlever)** (GUI / Flathub)
- **[AppManager](https://github.com/kem-a/AppManager)** (GUI)
- **[AppImageLauncher](https://github.com/TheAssassin/AppImageLauncher)** (Desktop integration)
- **[Zap](https://github.com/srevinsaju/zap)** (CLI)

<details>
<summary>Manual execution (no manager)</summary>

```bash
chmod +x Plezy-*-x86_64.AppImage
./Plezy-*-x86_64.AppImage
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
