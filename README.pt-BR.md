# Plezy AppImage

[🇬🇧 English](README.md) &nbsp;|
[简体中文](README.zh-CN.md) &nbsp;|
[Русский](README.ru.md) &nbsp;|
[Українська](README.uk.md) &nbsp;|
[日本語](README.ja.md) &nbsp;|
[Español](README.es.md) &nbsp;|
**Português**

[![Compilar e publicar AppImage](https://github.com/bl4ckswordsman/plezy-appimage/actions/workflows/extract.yaml/badge.svg)](https://github.com/bl4ckswordsman/plezy-appimage/actions/workflows/extract.yaml)

Pacotes AppImage independentes de distribuição para o [Plezy](https://github.com/edde746/plezy) — um cliente moderno e multiplataforma de Plex e Jellyfin desenvolvido com Flutter.

As versões são geradas automaticamente a partir dos lançamentos originais do [edde746/plezy](https://github.com/edde746/plezy) e publicadas aqui como AppImages independentes. Sem root, sem gerenciador de pacotes e sem dependências específicas de distribuição.

> [!NOTE]
> **Procurando a versão para Android?** Veja o [plezy-apks](https://github.com/bl4ckswordsman/plezy-apks) para versões no F-Droid e Obtainium.

## Baixar

Acesse a [página de Releases](https://github.com/bl4ckswordsman/plezy-appimage/releases/latest) e baixe o arquivo correspondente à sua arquitetura:

| Arquivo | Para |
| --- | --- |
| `Plezy-<versão>-x86_64.AppImage` | A maioria dos computadores e laptops (Intel/AMD 64-bit) |
| `Plezy-<versão>-aarch64.AppImage` | Dispositivos ARM (Raspberry Pi 5, Pinebook Pro, etc.) |
| `*.AppImage.zsync` | Atualizações delta via AppImageUpdate / Gear Lever |

## Gerenciadores de AppImage e Integração

Para integração com o menu do sistema e atualizações delta, recomenda-se um gerenciador de AppImages: [Gear Lever](https://flathub.org/apps/it.mijorus.gearlever) (GUI / Flathub), [AppManager](https://github.com/kem-a/AppManager) (GUI), [AppImageLauncher](https://github.com/TheAssassin/AppImageLauncher) ou [Zap](https://github.com/srevinsaju/zap) (CLI).

<details>
<summary>Execução manual (sem gerenciador)</summary>

```bash
chmod +x Plezy-*-x86_64.AppImage
./Plezy-*-x86_64.AppImage
```

</details>

<details>
<summary>Requisito do FUSE e solução de problemas</summary>

Os AppImages utilizam o FUSE (Filesystem in Userspace) para montar seu sistema de arquivos em tempo de execução.

| Distribuição | Comando de instalação |
| --- | --- |
| Ubuntu 22.04+ / Debian 12+ | `sudo apt install libfuse2` |
| Fedora | `sudo dnf install fuse` |
| Arch Linux | `sudo pacman -S fuse2` |

**Não tem o FUSE?** Execute o AppImage sem montagem:

```bash
./Plezy-VERSION-x86_64.AppImage --appimage-extract-and-run
```

</details>

## Projeto original

- **Upstream oficial:** [edde746/plezy](https://github.com/edde746/plezy)

## Licença

Os scripts de empacotamento deste repositório são distribuídos sob a [Licença MIT](LICENSE). O Plezy em si é obra de seus [autores originais](https://github.com/edde746/plezy/blob/main/LICENSE).
