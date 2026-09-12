# Plezy AppImage

[🇬🇧 English](README.md) &nbsp;|
**简体中文** &nbsp;|
[Español](README.es.md) &nbsp;|
[हिन्दी](README.hi.md) &nbsp;|
[عربي](README.ar.md)

[![构建与发布 AppImage](https://github.com/bl4ckswordsman/plezy-appimage/actions/workflows/extract.yaml/badge.svg)](https://github.com/bl4ckswordsman/plezy-appimage/actions/workflows/extract.yaml)

适用于 [Plezy](https://github.com/edde746/plezy) 的发行版无关 AppImage 软件包 —— 一款基于 Flutter 构建的现代跨平台 Plex & Jellyfin 客户端。

每次 [edde746/plezy](https://github.com/edde746/plezy) 上游发布新版本后，本仓库会自动将其打包为独立的 AppImage 并发布于此。无需 root 权限，无需包管理器，无发行版依赖。

> [!NOTE]
> **寻找 Android 版本？** 请查看 [plezy-apks](https://github.com/bl4ckswordsman/plezy-apks)，提供 F-Droid 和 Obtainium 安装包。

---

## 下载

前往 [Releases 页面](https://github.com/bl4ckswordsman/plezy-appimage/releases/latest) 并下载适合你架构的文件：

| 文件 | 适用场景 |
| --- | --- |
| `Plezy-<版本>-x86_64.AppImage` | 大多数桌面/笔记本电脑（Intel/AMD 64位） |
| `Plezy-<版本>-aarch64.AppImage` | ARM 设备（树莓派5、Pinebook Pro 等） |
| `*.AppImage.zsync` | 通过 AppImageUpdate / Gear Lever 进行增量更新 |

---

## 通过 Gear Lever 安装

[Gear Lever](https://flathub.org/apps/it.mijorus.gearlever) 是适用于 GNOME 的图形化 AppImage 管理器，可处理桌面集成（桌面条目、图标、系统菜单）和增量更新。

[![从 Flathub 安装](https://flathub.org/api/badge?locale=zh-CN)](https://flathub.org/apps/it.mijorus.gearlever)

<details>
<summary>不使用 Gear Lever 的手动步骤</summary>

```bash
# 1. 下载 AppImage（将 VERSION 替换为版本号，如 2.19.1）
wget https://github.com/bl4ckswordsman/plezy-appimage/releases/download/VERSION/Plezy-VERSION-x86_64.AppImage

# 2. 赋予执行权限
chmod +x Plezy-VERSION-x86_64.AppImage

# 3. 运行
./Plezy-VERSION-x86_64.AppImage
```

</details>

---

## FUSE 依赖

AppImage 使用 FUSE（用户空间文件系统）在运行时挂载其内置文件系统。

| 发行版 | 安装命令 |
| --- | --- |
| Ubuntu 22.04+ / Debian 12+ | `sudo apt install libfuse2` |
| Fedora | `sudo dnf install fuse` |
| Arch Linux | `sudo pacman -S fuse2` |

**无 FUSE 环境？** 可以不挂载直接运行：

```bash
./Plezy-VERSION-x86_64.AppImage --appimage-extract-and-run
```

---

## 上游项目

- **官方上游：** [edde746/plezy](https://github.com/edde746/plezy)
- **Android 安装包：** [bl4ckswordsman/plezy-apks](https://github.com/bl4ckswordsman/plezy-apks)

---

## 许可证

本仓库中的打包脚本基于 [MIT 许可证](LICENSE) 发布。Plezy 本身由其[上游作者](https://github.com/edde746/plezy/blob/main/LICENSE)持有版权。
