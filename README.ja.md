# Plezy AppImage

[🇬🇧 English](README.md) &nbsp;|
[简体中文](README.zh-CN.md) &nbsp;|
[Русский](README.ru.md) &nbsp;|
[Українська](README.uk.md) &nbsp;|
**日本語** &nbsp;|
[Español](README.es.md) &nbsp;|
[Português](README.pt-BR.md)

[![AppImageのビルドと公開](https://github.com/bl4ckswordsman/plezy-appimage/actions/workflows/extract.yaml/badge.svg)](https://github.com/bl4ckswordsman/plezy-appimage/actions/workflows/extract.yaml)

Flutterで構築された最新のクロスプラットフォームPlex & Jellyfinクライアント「[Plezy](https://github.com/edde746/plezy)」向けのディストリビューション非依存AppImageパッケージです。

本リポジトリでは、上流の [edde746/plezy](https://github.com/edde746/plezy) リリースから自動的にパッケージングし、スタンドアロンのAppImageとして公開しています。root権限やパッケージマネージャー、特定のディストリビューション依存関係は不要です。

> [!NOTE]
> **Android版をお探しですか？** F-DroidおよびObtainium向けのリリースは [plezy-apks](https://github.com/bl4ckswordsman/plezy-apks) をご確認ください。

## ダウンロード

[Releases ページ](https://github.com/bl4ckswordsman/plezy-appimage/releases/latest) からご使用のアーキテクチャに合わせたファイルをダウンロードしてください：

| ファイル | 対象環境 |
| --- | --- |
| `Plezy-<バージョン>-x86_64.AppImage` | 一般的なデスクトップ/ノートPC（Intel/AMD 64ビット） |
| `Plezy-<バージョン>-aarch64.AppImage` | ARMデバイス（Raspberry Pi 5、Pinebook Proなど） |
| `*.AppImage.zsync` | AppImageUpdate / Gear Leverによる差分更新用メタデータ |

## AppImageマネージャーとデスクトップ統合

メニュー追加や差分更新の自動化にはAppImageマネージャーの利用をおすすめします：[Gear Lever](https://flathub.org/apps/it.mijorus.gearlever) (GUI / Flathub)、[AppManager](https://github.com/kem-a/AppManager) (GUI)、[AppImageLauncher](https://github.com/TheAssassin/AppImageLauncher)、[Zap](https://github.com/srevinsaju/zap) (CLI)。

<details>
<summary>手動実行（マネージャーなし）</summary>

```bash
chmod +x Plezy-*-x86_64.AppImage
./Plezy-*-x86_64.AppImage
```

</details>

<details>
<summary>FUSEの要件とトラブルシューティング</summary>

AppImageは実行時に内包されたファイルシステムをマウントするためFUSE（Filesystem in Userspace）を使用します。

| ディストリビューション | インストールコマンド |
| --- | --- |
| Ubuntu 22.04+ / Debian 12+ | `sudo apt install libfuse2` |
| Fedora | `sudo dnf install fuse` |
| Arch Linux | `sudo pacman -S fuse2` |

**FUSEが利用できない場合:** マウントせずに直接実行できます：

```bash
./Plezy-VERSION-x86_64.AppImage --appimage-extract-and-run
```

</details>

## 上流プロジェクト

- **公式上流リポジトリ:** [edde746/plezy](https://github.com/edde746/plezy)

## ライセンス

本リポジトリ内のパッケージングスクリプトは [MIT License](LICENSE) の下で公開されています。Plezy本体の著作権は[上流の原作者](https://github.com/edde746/plezy/blob/main/LICENSE)に帰属します。
