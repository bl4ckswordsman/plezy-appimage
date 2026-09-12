# Plezy AppImage

**🇬🇧 English** &nbsp;|
[&#x7b80;&#x4f53;&#x4e2d;&#x6587;](README.zh-CN.md) &nbsp;|
[Español](README.es.md) &nbsp;|
[हिन्दी](README.hi.md) &nbsp;|
[&#x639;&#x631;&#x628;&#x64a;](README.ar.md)

[![Build & Publish AppImage](https://github.com/bl4ckswordsman/plezy-appimage/actions/workflows/extract.yaml/badge.svg)](https://github.com/bl4ckswordsman/plezy-appimage/actions/workflows/extract.yaml)

Distro-agnostic AppImage packages for [Plezy](https://github.com/edde746/plezy) — a modern
cross-platform Plex & Jellyfin client built with Flutter.

Releases are built automatically from upstream
[edde746/plezy](https://github.com/edde746/plezy) tarballs and published here
as self-contained AppImages. No root, no package manager, no distro-specific dependencies.

> [!NOTE]
> **Looking for Android?** Check out [plezy-apks](https://github.com/bl4ckswordsman/plezy-apks)
> for F-Droid and Obtainium releases.

---

## Download

Go to the [Releases page](https://github.com/bl4ckswordsman/plezy-appimage/releases/latest)
and grab the file for your architecture:

| File | For |
| --- | --- |
| `Plezy-<version>-x86_64.AppImage` | Most desktop/laptop systems (Intel/AMD 64-bit) |
| `Plezy-<version>-aarch64.AppImage` | ARM systems (Raspberry Pi 5, Pinebook Pro, etc.) |
| `*.AppImage.zsync` | Delta updates via AppImageUpdate / Gear Lever |

---

## Install via Gear Lever

[Gear Lever](https://flathub.org/apps/it.mijorus.gearlever) is a GUI AppImage manager for
GNOME. It handles integration (desktop entry, icon, system menu) and delta updates.

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

To integrate it into your system launcher, move it to a stable location and create a
`.desktop` entry, or use a tool such as
[AppImageLauncher](https://github.com/TheAssassin/AppImageLauncher).

</details>

---

## Install via Zap, AppImageUpdate, or direct download

**[Zap](https://github.com/nicholasgasior/zap)** (CLI AppImage manager):

```bash
# Install or update Plezy AppImage in one command
zap install --from \
  https://github.com/bl4ckswordsman/plezy-appimage/releases/latest/download/Plezy-VERSION-x86_64.AppImage
```

**[AppImageUpdate](https://github.com/AppImageCommunity/AppImageUpdate)** — delta upgrades
using the embedded zsync update information:

```bash
AppImageUpdate Plezy-VERSION-x86_64.AppImage
```

**Direct download** — latest release download links:

```
https://github.com/bl4ckswordsman/plezy-appimage/releases/latest/download/Plezy-VERSION-x86_64.AppImage
https://github.com/bl4ckswordsman/plezy-appimage/releases/latest/download/Plezy-VERSION-aarch64.AppImage
```

---

## FUSE requirement

AppImages use FUSE (Filesystem in Userspace) to mount their embedded filesystem at runtime.

| Distro | Install command |
| --- | --- |
| Ubuntu 22.04 + / Debian 12+ | `sudo apt install libfuse2` |
| Fedora | `sudo dnf install fuse` |
| Arch Linux | `sudo pacman -S fuse2` |

**No FUSE available?** Run the AppImage without mounting it:

```bash
./Plezy-VERSION-x86_64.AppImage --appimage-extract-and-run
```

Or extract it permanently:

```bash
./Plezy-VERSION-x86_64.AppImage --appimage-extract
# The app is now in ./squashfs-root/
./squashfs-root/AppRun
```

---

## Architecture table

| AppImage file | Architecture | Target systems |
| --- | --- | --- |
| `Plezy-*-x86_64.AppImage` | x86\_64 | Standard Intel/AMD 64-bit desktops & laptops |
| `Plezy-*-aarch64.AppImage` | aarch64 | 64-bit ARM boards, Raspberry Pi 5, ARM laptops |

> **Note:** If the upstream release does not include an ARM tarball for a given version,
> the corresponding AppImage will be absent from that release. The x86\_64 build is always
> expected to be present.

---

<details>
<summary>🔩 Under the Hood — why this repo exists and how it works</summary>

### Why this repo exists

The upstream [eddre746/plezy](https://github.com/edde746/plezy) project ships pre-built
Linux binaries as `.tar.gz` tarballs as well as `.deb`, `.rpm`, and `.pkg.tar.zst` packages.
Those formats are distribution-specific — a `.deb` won't install on Fedora, and an `.rpm`
won't install on Ubuntu without workarounds.

AppImages are fully self-contained: every library the app needs (except the OS kernel and
basic glibc/libstdc++) is bundled inside. You download one file, make it executable, and run
it — on any distro, without root.

This companion repo automates the process of wrapping the upstream Flutter binary into a
proper AppImage every time a new upstream release appears.

### How it works

1. A GitHub Actions workflow (`extract.yaml`) runs **every hour** on a schedule and can also
   be triggered manually via `workflow_dispatch`.
2. It calls the GitHub API to find the **latest upstream release tag** from
   `edde746/plezy`.
3. It checks whether this repo already has a release with that tag. If it does, the
   workflow exits early — making runs **idempotent**.
4. Otherwise it downloads `plezy-linux-x64.tar.gz` (and `plezy-linux-arm64.tar.gz` if
   available), assembles a valid **AppDir** for each architecture:
   - An `AppRun` launcher script that sets `APPDIR` and `LD_LIBRARY_PATH`.
   - A `plezy.desktop` file (validated with `desktop-file-validate`).
   - The Plezy icon fetched from the upstream source tree.
5. It invokes `appimagetool` (itself downloaded at runtime via the GitHub API — never
   hardcoded) with a `-u` **zsync update URL** so AppImageUpdate can do delta upgrades.
6. It generates `.zsync` sidecar files alongside each AppImage.
7. Finally it creates a **GitHub Release** tagged with the same version as upstream, attaches
   all AppImages and zsync files, and writes a formatted body that includes the verbatim
   upstream changelog.

No binaries are committed to this repository. Everything happens in CI and goes straight to
a release.

### Supply-chain security

All GitHub Actions are pinned to **exact commit SHAs** (with a human-readable version
comment) rather than floating tags. Dependabot is configured to propose updates weekly.

</details>

---

## Upstream project

- **Canonical upstream:** [edde746/plezy](https://github.com/edde746/plezy)  
- **Android packages:** [bl4ckswordsman/plezy-apks](https://github.com/bl4ckswordsman/plezy-apks)

---

## License

The packaging scripts in this repository are released under the [MIT License](LICENSE).

Plezy itself is the work of its [upstream authors](https://github.com/edde746/plezy/blob/main/LICENSE)
and is not covered by this repo's license.
