# Plezy AppImage

[🇬🇧 English](README.md) &nbsp;|
[简体中文](README.zh-CN.md) &nbsp;|
**Español** &nbsp;|
[हिन्दी](README.hi.md) &nbsp;|
[عربي](README.ar.md)

[![Compilar y publicar AppImage](https://github.com/bl4ckswordsman/plezy-appimage/actions/workflows/extract.yaml/badge.svg)](https://github.com/bl4ckswordsman/plezy-appimage/actions/workflows/extract.yaml)

Paquetes AppImage independientes de la distribución para [Plezy](https://github.com/edde746/plezy) — un cliente moderno multiplataforma de Plex y Jellyfin construido con Flutter.

Los lanzamientos se generan automáticamente a partir de los tarballs de [edde746/plezy](https://github.com/edde746/plezy) y se publican aquí como AppImages autocontenidas. Sin root, sin gestor de paquetes, sin dependencias específicas de distribución.

> [!NOTE]
> **¿Buscas Android?** Consulta [plezy-apks](https://github.com/bl4ckswordsman/plezy-apks) para versiones compatibles con F-Droid y Obtainium.

---

## Descarga

Ve a la [página de Releases](https://github.com/bl4ckswordsman/plezy-appimage/releases/latest) y descarga el archivo para tu arquitectura:

| Archivo | Para |
| --- | --- |
| `Plezy-<versión>-x86_64.AppImage` | La mayoría de equipos de escritorio/portátiles (Intel/AMD 64 bits) |
| `Plezy-<versión>-aarch64.AppImage` | Sistemas ARM (Raspberry Pi 5, Pinebook Pro, etc.) |
| `*.AppImage.zsync` | Actualizaciones delta mediante AppImageUpdate / Gear Lever |

---

## Instalar con Gear Lever

[Gear Lever](https://flathub.org/apps/it.mijorus.gearlever) es un gestor gráfico de AppImage para GNOME que gestiona la integración en el escritorio y las actualizaciones delta.

[![Instalar desde Flathub](https://flathub.org/api/badge?locale=es)](https://flathub.org/apps/it.mijorus.gearlever)

<details>
<summary>Pasos manuales sin Gear Lever</summary>

```bash
# 1. Descargar el AppImage (sustituye VERSION por la etiqueta, p. ej. 2.19.1)
wget https://github.com/bl4ckswordsman/plezy-appimage/releases/download/VERSION/Plezy-VERSION-x86_64.AppImage

# 2. Hacerlo ejecutable
chmod +x Plezy-VERSION-x86_64.AppImage

# 3. Ejecutarlo
./Plezy-VERSION-x86_64.AppImage
```

</details>

---

## Requisito de FUSE

Las AppImages utilizan FUSE (Filesystem in Userspace) para montar su sistema de archivos embebido en tiempo de ejecución.

| Distribución | Comando de instalación |
| --- | --- |
| Ubuntu 22.04+ / Debian 12+ | `sudo apt install libfuse2` |
| Fedora | `sudo dnf install fuse` |
| Arch Linux | `sudo pacman -S fuse2` |

**¿Sin FUSE disponible?** Ejecuta la AppImage sin montarla:

```bash
./Plezy-VERSION-x86_64.AppImage --appimage-extract-and-run
```

---

## Proyecto original

- **Upstream oficial:** [edde746/plezy](https://github.com/edde746/plezy)
- **Paquetes Android:** [bl4ckswordsman/plezy-apks](https://github.com/bl4ckswordsman/plezy-apks)

---

## Licencia

Los scripts de empaquetado de este repositorio se publican bajo la [Licencia MIT](LICENSE). Plezy en sí es obra de sus [autores originales](https://github.com/edde746/plezy/blob/main/LICENSE).
