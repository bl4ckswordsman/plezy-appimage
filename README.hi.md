# Plezy AppImage

[🇬🇧 English](README.md) &nbsp;|
[简体中文](README.zh-CN.md) &nbsp;|
[Español](README.es.md) &nbsp;|
**हिन्दी** &nbsp;|
[عربي](README.ar.md)

[![AppImage बिल्ड और प्रकाशन](https://github.com/bl4ckswordsman/plezy-appimage/actions/workflows/extract.yaml/badge.svg)](https://github.com/bl4ckswordsman/plezy-appimage/actions/workflows/extract.yaml)

[Plezy](https://github.com/edde746/plezy) के लिए वितरण-स्वतंत्र AppImage पैकेज — Flutter से बना एक आधुनिक क्रॉस-प्लेटफ़ॉर्म Plex और Jellyfin क्लाइंट।

रिलीज़ स्वचालित रूप से [edde746/plezy](https://github.com/edde746/plezy) के अपस्ट्रीम टारबॉल से बनाए जाते हैं और यहाँ सेल्फ-कंटेंड AppImage के रूप में प्रकाशित किए जाते हैं। कोई root की ज़रूरत नहीं, कोई पैकेज मैनेजर नहीं, कोई वितरण-विशिष्ट निर्भरता नहीं।

> [!NOTE]
> **Android ढूंढ रहे हैं?** F-Droid और Obtainium रिलीज़ के लिए [plezy-apks](https://github.com/bl4ckswordsman/plezy-apks) देखें।

---

## डाउनलोड

[Releases पेज](https://github.com/bl4ckswordsman/plezy-appimage/releases/latest) पर जाएं और अपनी आर्किटेक्चर के लिए फ़ाइल डाउनलोड करें:

| फ़ाइल | किसके लिए |
| --- | --- |
| `Plezy-<संस्करण>-x86_64.AppImage` | अधिकांश डेस्कटॉप/लैपटॉप (Intel/AMD 64-bit) |
| `Plezy-<संस्करण>-aarch64.AppImage` | ARM सिस्टम (Raspberry Pi 5, Pinebook Pro, आदि) |
| `*.AppImage.zsync` | AppImageUpdate / Gear Lever के ज़रिए डेल्टा अपडेट |

---

## Gear Lever से इंस्टॉल करें

[Gear Lever](https://flathub.org/apps/it.mijorus.gearlever) GNOME के लिए एक GUI AppImage मैनेजर है।

[![Flathub से इंस्टॉल करें](https://flathub.org/api/badge?locale=hi)](https://flathub.org/apps/it.mijorus.gearlever)

<details>
<summary>Gear Lever के बिना मैन्युअल स्टेप्स</summary>

```bash
# 1. AppImage डाउनलोड करें (VERSION को रिलीज़ टैग से बदलें, जैसे 2.19.1)
wget https://github.com/bl4ckswordsman/plezy-appimage/releases/download/VERSION/Plezy-VERSION-x86_64.AppImage

# 2. एक्सीक्यूटेबल बनाएं
chmod +x Plezy-VERSION-x86_64.AppImage

# 3. चलाएं
./Plezy-VERSION-x86_64.AppImage
```

</details>

---

## FUSE की ज़रूरत

| डिस्ट्रो | इंस्टॉल कमांड |
| --- | --- |
| Ubuntu 22.04+ / Debian 12+ | `sudo apt install libfuse2` |
| Fedora | `sudo dnf install fuse` |
| Arch Linux | `sudo pacman -S fuse2` |

**FUSE उपलब्ध नहीं?**

```bash
./Plezy-VERSION-x86_64.AppImage --appimage-extract-and-run
```

---

## अपस्ट्रीम प्रोजेक्ट

- **मूल अपस्ट्रीम:** [edde746/plezy](https://github.com/edde746/plezy)
- **Android पैकेज:** [bl4ckswordsman/plezy-apks](https://github.com/bl4ckswordsman/plezy-apks)

---

## लाइसेंस

इस रिपॉजिटरी के पैकेजिंग स्क्रिप्ट [MIT लाइसेंस](LICENSE) के तहत जारी किए गए हैं।
