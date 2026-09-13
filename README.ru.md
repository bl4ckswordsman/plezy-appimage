# Plezy AppImage

[🇬🇧 English](README.md) &nbsp;|
[简体中文](README.zh-CN.md) &nbsp;|
**Русский** &nbsp;|
[Українська](README.uk.md) &nbsp;|
[日本語](README.ja.md) &nbsp;|
[Español](README.es.md) &nbsp;|
[Português](README.pt-BR.md)

[![Сборка и публикация AppImage](https://github.com/bl4ckswordsman/plezy-appimage/actions/workflows/extract.yaml/badge.svg)](https://github.com/bl4ckswordsman/plezy-appimage/actions/workflows/extract.yaml)

Дистрибутиво-независимые пакеты AppImage для [Plezy](https://github.com/edde746/plezy) — современного кроссплатформенного клиента Plex и Jellyfin на базе Flutter.

Релизы собираются автоматически из апстрим-релизов [edde746/plezy](https://github.com/edde746/plezy) и публикуются здесь в виде самодостаточных AppImage. Без root-прав, без пакетных менеджеров и без специфичных для дистрибутивов зависимостей.

> [!NOTE]
> **Ищете версию для Android?** Ознакомьтесь с [plezy-apks](https://github.com/bl4ckswordsman/plezy-apks) с релизами для F-Droid и Obtainium.

## Скачать

Перейдите на [страницу релизов](https://github.com/bl4ckswordsman/plezy-appimage/releases/latest) и выберите файл для вашей архитектуры:

| Файл | Для |
| --- | --- |
| `Plezy-<версия>-x86_64.AppImage` | Большинство ПК и ноутбуков (Intel/AMD 64-бит) |
| `Plezy-<версия>-aarch64.AppImage` | ARM-устройства (Raspberry Pi 5, Pinebook Pro и т. д.) |
| `*.AppImage.zsync` | Дельта-обновления через AppImageUpdate / Gear Lever |

## Менеджеры AppImage и интеграция

Для интеграции в меню приложений и дельта-обновлений рекомендуется использовать менеджер AppImage: [Gear Lever](https://flathub.org/apps/it.mijorus.gearlever) (GUI / Flathub), [AppManager](https://github.com/kem-a/AppManager) (GUI), [AppImageLauncher](https://github.com/TheAssassin/AppImageLauncher) или [Zap](https://github.com/srevinsaju/zap) (CLI).

<details>
<summary>Ручной запуск (без менеджера)</summary>

```bash
chmod +x Plezy-*-x86_64.AppImage
./Plezy-*-x86_64.AppImage
```

</details>

<details>
<summary>Требования FUSE и устранение неполадок</summary>

AppImage использует FUSE (файловую систему в пользовательском пространстве) для монтирования образа во время работы.

| Дистрибутив | Команда установки |
| --- | --- |
| Ubuntu 22.04+ / Debian 12+ | `sudo apt install libfuse2` |
| Fedora | `sudo dnf install fuse` |
| Arch Linux | `sudo pacman -S fuse2` |

**Нет FUSE?** Запустите AppImage без монтирования:

```bash
./Plezy-VERSION-x86_64.AppImage --appimage-extract-and-run
```

</details>

## Апстрим-проект

- **Официальный апстрим:** [edde746/plezy](https://github.com/edde746/plezy)

## Лицензия

Скрипты упаковки в этом репозитории распространяются под [лицензией MIT](LICENSE). Сам Plezy защищён лицензией своих [исходных авторов](https://github.com/edde746/plezy/blob/main/LICENSE).
