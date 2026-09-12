# Plezy AppImage

[🇬🇧 English](README.md) &nbsp;|
[简体中文](README.zh-CN.md) &nbsp;|
[Español](README.es.md) &nbsp;|
[हिन्दी](README.hi.md) &nbsp;|
**عربي**

[![بناء ونشر AppImage](https://github.com/bl4ckswordsman/plezy-appimage/actions/workflows/extract.yaml/badge.svg)](https://github.com/bl4ckswordsman/plezy-appimage/actions/workflows/extract.yaml)

<div dir="rtl">

حزم AppImage المستقلة عن التوزيعة لـ [Plezy](https://github.com/edde746/plezy) — عميل Plex و Jellyfin متعدد المنصات مبني بـ Flutter.

يتم إنشاء الإصدارات تلقائيًا من الأرشيفات الأصلية لـ [edde746/plezy](https://github.com/edde746/plezy) ونشرها هنا كـ AppImages مكتفية بذاتها. لا حاجة لصلاحيات root، ولا مدير حزم، ولا تبعيات خاصة بالتوزيعة.

> [!NOTE]
> **تبحث عن Android؟** تحقق من [plezy-apks](https://github.com/bl4ckswordsman/plezy-apks) للحصول على إصدارات F-Droid و Obtainium.

---

## التنزيل

انتقل إلى [صفحة الإصدارات](https://github.com/bl4ckswordsman/plezy-appimage/releases/latest) وقم بتنزيل الملف المناسب لمعمارية جهازك:

| الملف | لـ |
| --- | --- |
| `Plezy-<الإصدار>-x86_64.AppImage` | معظم أجهزة سطح المكتب والحواسيب المحمولة (Intel/AMD 64 بت) |
| `Plezy-<الإصدار>-aarch64.AppImage` | أنظمة ARM (Raspberry Pi 5، Pinebook Pro، إلخ) |
| `*.AppImage.zsync` | تحديثات دلتا عبر AppImageUpdate / Gear Lever |

---

## التثبيت عبر Gear Lever

[Gear Lever](https://flathub.org/apps/it.mijorus.gearlever) هو مدير AppImage رسومي لـ GNOME.

[![التثبيت من Flathub](https://flathub.org/api/badge?locale=ar)](https://flathub.org/apps/it.mijorus.gearlever)

<details>
<summary>الخطوات اليدوية بدون Gear Lever</summary>

```bash
# 1. تنزيل الـ AppImage (استبدل VERSION برقم الإصدار، مثل 2.19.1)
wget https://github.com/bl4ckswordsman/plezy-appimage/releases/download/VERSION/Plezy-VERSION-x86_64.AppImage

# 2. منح صلاحية التنفيذ
chmod +x Plezy-VERSION-x86_64.AppImage

# 3. تشغيله
./Plezy-VERSION-x86_64.AppImage
```

</details>

---

## متطلب FUSE

| التوزيعة | أمر التثبيت |
| --- | --- |
| Ubuntu 22.04+ / Debian 12+ | `sudo apt install libfuse2` |
| Fedora | `sudo dnf install fuse` |
| Arch Linux | `sudo pacman -S fuse2` |

**FUSE غير متوفر؟**

```bash
./Plezy-VERSION-x86_64.AppImage --appimage-extract-and-run
```

---

## المشروع الأصلي

- **المصدر الرسمي:** [edde746/plezy](https://github.com/edde746/plezy)
- **حزم Android:** [bl4ckswordsman/plezy-apks](https://github.com/bl4ckswordsman/plezy-apks)

---

## الترخيص

سكريبتات التغليف في هذا المستودع مرخصة بموجب [رخصة MIT](LICENSE).

</div>
