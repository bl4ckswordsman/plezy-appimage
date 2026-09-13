# Plezy AppImage

[🇬🇧 English](README.md) &nbsp;|
**简体中文** &nbsp;|
[Русский](README.ru.md) &nbsp;|
[Українська](README.uk.md) &nbsp;|
[日本語](README.ja.md) &nbsp;|
[Español](README.es.md) &nbsp;|
[Português](README.pt-BR.md)

[![构建与发布 AppImage](https://github.com/bl4ckswordsman/plezy-appimage/actions/workflows/extract.yaml/badge.svg)](https://github.com/bl4ckswordsman/plezy-appimage/actions/workflows/extract.yaml)

适用于 [Plezy](https://github.com/edde746/plezy) 的发行版无关 AppImage 软件包 —— 一款基于 Flutter 构建的现代跨平台 Plex & Jellyfin 客户端。

每次 [edde746/plezy](https://github.com/edde746/plezy) 上游发布新版本后，本仓库会自动将其打包为独立的 AppImage 并发布于此。无需 root 权限，无需包管理器，无发行版依赖。

> [!NOTE]
> **寻找 Android 版本？** 请查看 [plezy-apks](https://github.com/bl4ckswordsman/plezy-apks)，提供 F-Droid 和 Obtainium 安装包。

## 下载

前往 [Releases 页面](https://github.com/bl4ckswordsman/plezy-appimage/releases/latest) 并下载适合你架构的文件：

| 文件 | 适用场景 |
| --- | --- |
| `Plezy-<版本>-x86_64.AppImage` | 大多数桌面/笔记本电脑（Intel/AMD 64位） |
| `Plezy-<版本>-aarch64.AppImage` | ARM 设备（树莓派5、Pinebook Pro 等） |
| `*.AppImage.zsync` | 通过 AppImageUpdate / Gear Lever 进行增量更新 |

## AppImage 管理器与桌面集成

推荐使用 AppImage 管理器实现桌面菜单集成与自动更新：[Gear Lever](https://flathub.org/apps/it.mijorus.gearlever)（GUI / Flathub）、[AppManager](https://github.com/kem-a/AppManager)（GUI）、[AppImageLauncher](https://github.com/TheAssassin/AppImageLauncher) 或 [Zap](https://github.com/srevinsaju/zap)（CLI 命令行工具）。

<details>
<summary>手动运行（不使用管理器）</summary>

```bash
chmod +x Plezy-*-x86_64.AppImage
./Plezy-*-x86_64.AppImage
```

</details>

<details>
<summary>FUSE 依赖与故障排除</summary>

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

</details>

## 上游项目

- **官方上游：** [edde746/plezy](https://github.com/edde746/plezy)

## 许可证

本仓库中的打包脚本基于 [MIT 许可证](LICENSE) 发布。Plezy 本身由其[上游作者](https://github.com/edde746/plezy/blob/main/LICENSE)持有版权。
