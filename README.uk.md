# Plezy AppImage

[🇬🇧 English](README.md) &nbsp;|
[简体中文](README.zh-CN.md) &nbsp;|
[Русский](README.ru.md) &nbsp;|
**Українська** &nbsp;|
[日本語](README.ja.md) &nbsp;|
[Español](README.es.md) &nbsp;|
[Português](README.pt-BR.md)

[![Збірка та публікація AppImage](https://github.com/bl4ckswordsman/plezy-appimage/actions/workflows/extract.yaml/badge.svg)](https://github.com/bl4ckswordsman/plezy-appimage/actions/workflows/extract.yaml)

Дистрибутиво-незалежні пакети AppImage для [Plezy](https://github.com/edde746/plezy) — сучасного кросплатформового клієнта Plex і Jellyfin на базі Flutter.

Релізи збираються автоматично з апстрім-релізів [edde746/plezy](https://github.com/edde746/plezy) та публікуються тут як самодостатні файли AppImage. Без root-прав, без пакетних менеджерів і без прив'язки до конкретного дистрибутива.

> [!NOTE]
> **Шукаєте версію для Android?** Перегляньте [plezy-apks](https://github.com/bl4ckswordsman/plezy-apks) з релізами для F-Droid та Obtainium.

---

## Завантаження

Перейдіть на [сторінку релізів](https://github.com/bl4ckswordsman/plezy-appimage/releases/latest) та завантажте файл для вашої архітектури:

| Файл | Для кого |
| --- | --- |
| `Plezy-<версія>-x86_64.AppImage` | Більшість ПК та ноутбуків (Intel/AMD 64-біт) |
| `Plezy-<версія>-aarch64.AppImage` | ARM-пристрої (Raspberry Pi 5, Pinebook Pro тощо) |
| `*.AppImage.zsync` | Дельта-оновлення через AppImageUpdate / Gear Lever |

---

## Менеджери AppImage та інтеграція

Для інтеграції в системне меню та дельта-оновлень рекомендується використовувати менеджер AppImage:

- **[Gear Lever](https://flathub.org/apps/it.mijorus.gearlever)** (GUI / Flathub)
- **[AppManager](https://github.com/kem-a/AppManager)** (GUI)
- **[AppImageLauncher](https://github.com/TheAssassin/AppImageLauncher)** (системна інтеграція)
- **[Zap](https://github.com/srevinsaju/zap)** (CLI)

<details>
<summary>Ручний запуск (без менеджера)</summary>

```bash
chmod +x Plezy-*-x86_64.AppImage
./Plezy-*-x86_64.AppImage
```

</details>

---

## Вимоги FUSE

AppImage використовує FUSE (файлову систему в просторі користувача) для монтування образу під час запуску.

| Дистрибутив | Команда встановлення |
| --- | --- |
| Ubuntu 22.04+ / Debian 12+ | `sudo apt install libfuse2` |
| Fedora | `sudo dnf install fuse` |
| Arch Linux | `sudo pacman -S fuse2` |

**Немає FUSE?** Запустіть AppImage без монтування:

```bash
./Plezy-VERSION-x86_64.AppImage --appimage-extract-and-run
```

---

## Апстрім-проєкт

- **Офіційний апстрім:** [edde746/plezy](https://github.com/edde746/plezy)
- **Пакети для Android:** [bl4ckswordsman/plezy-apks](https://github.com/bl4ckswordsman/plezy-apks)

---

## Ліцензія

Скрипти пакування в цьому репозиторії поширюються за [ліцензією MIT](LICENSE). Сам Plezy захищено ліцензією його [первинних авторів](https://github.com/edde746/plezy/blob/main/LICENSE).
