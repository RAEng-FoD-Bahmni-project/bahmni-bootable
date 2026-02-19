# Bahmni RTL — Bootable USB Appliance | نظام باهمني — صورة USB قابلة للتمهيد

A pre-configured, bootable system image containing the full Bahmni Arabic RTL stack. Flash it to a USB drive, boot any server from it, and have a complete hospital EMR running in minutes.

صورة نظام مُعدّة مسبقاً وقابلة للتمهيد تحتوي على نظام باهمني العربي الكامل. انسخها على ذاكرة USB، شغّل أي خادم منها، واحصل على نظام سجلات طبية متكامل للمستشفى في دقائق.

---

## 📖 Full Installation Guides | أدلة التثبيت الكاملة

- **English Guide:** [Download PDF](https://drive.google.com/file/d/18Z1ruQNfTZCaWEv9QzFcNzpFqYoLeTbf/view?usp=sharing)
- **الدليل بالعربية:** [تحميل PDF](https://drive.google.com/file/d/1tAcgKpV1vUTgCDnOqqdAOi6G0FyURZZW/view?usp=sharing)

---

## Download | التحميل

| File / الملف | Size / الحجم | Link / الرابط |
|------|------|------|
| Bootable USB Image / صورة USB القابلة للتمهيد | ~80 GB | [Download from Google Drive / تحميل من Google Drive](#) <!-- TODO: Replace with Google Drive link --> |

---

## What's Included | المحتويات

The appliance image contains: / تحتوي صورة النظام على:

- **Ubuntu OS / نظام أوبنتو** — Pre-installed and configured / مُثبّت ومُعدّ مسبقاً
- **Bahmni RTL Stack / حزمة باهمني** — All services running in Docker containers / جميع الخدمات تعمل في حاويات Docker:
  - OpenMRS — Core medical records / السجلات الطبية الأساسية
  - Bahmni Apps — Clinical UI, fully RTL/Arabic / واجهة سريرية عربية بالكامل
  - OpenELIS — Laboratory information system / نظام معلومات المختبر
  - Odoo — Billing & inventory / الفوترة والمخزون
  - Dcm4chee — Medical imaging, DICOM/PACS / التصوير الطبي
- **Pre-loaded configurations / إعدادات جاهزة** — Arabic locale, RTL interface, default clinical forms / واجهة عربية، نماذج سريرية افتراضية

---

## Requirements | المتطلبات

- A server or PC with a USB port / خادم أو حاسوب مزود بمنفذ USB
- A USB drive (minimum 128 GB recommended) / ذاكرة USB (يُنصح بـ 128 جيجابايت كحد أدنى)
- Network connectivity for post-install configuration / اتصال بالشبكة للإعداد بعد التثبيت

---

## Installation | التثبيت

### 1. Prepare the USB Drive | تحضير ذاكرة USB

Flash the downloaded image to a USB drive using [balenaEtcher](https://etcher.balena.io/) or `dd`:

انسخ الصورة المحمّلة على ذاكرة USB باستخدام [balenaEtcher](https://etcher.balena.io/) أو أمر `dd`:

```bash
# Linux/macOS (replace /dev/sdX with your USB device)
# استبدل /dev/sdX بجهاز USB الخاص بك
sudo dd if=bahmni-appliance.img of=/dev/sdX bs=4M status=progress
sync
```

### 2. Configure BIOS | تهيئة إعدادات BIOS

1. Insert the USB drive into the target server / أدخل ذاكرة USB في الخادم المستهدف
2. Enter BIOS settings at startup (typically F2, F12, Del, or Enter) / ادخل إعدادات BIOS عند بدء التشغيل
3. Set the boot priority to boot from USB first / اضبط أولوية الإقلاع من USB أولاً

### 3. Boot and Install | الإقلاع والتثبيت

1. Boot the server from the USB drive / شغّل الخادم من ذاكرة USB
2. The installer launches automatically and installs Ubuntu onto the server's hard drive / يبدأ برنامج التثبيت تلقائياً وينصّب أوبنتو على القرص الصلب
3. After Ubuntu is installed, the Bahmni RTL system deploys automatically via Docker / بعد تثبيت أوبنتو، يتم نشر نظام باهمني تلقائياً عبر Docker

### 4. Start the System | تشغيل النظام

```bash
# Start all services / تشغيل جميع الخدمات
./start-bahmni.sh

# Stop all services / إيقاف جميع الخدمات
./stop-bahmni.sh
```

### 5. Access the System | الوصول إلى النظام

Open a browser and navigate to the server's IP address. All modules are pre-configured:

افتح المتصفح وانتقل إلى عنوان IP الخادم. جميع الوحدات مُعدّة مسبقاً:

- **Patient Registration / تسجيل المرضى**
- **Clinical Encounters / اللقاءات السريرية**
- **Laboratory / المختبر (OpenELIS)**
- **Pharmacy / الصيدلية**
- **Medical Imaging / التصوير الطبي**
- **Billing / الفوترة (Odoo)**

---

## Related Repositories | المستودعات ذات الصلة

- 🌐 [Landing Page / الصفحة الرئيسية](https://raeng-fod-bahmni-project.github.io)
- 🔬 [Lab Integrations / تكامل المختبر](https://github.com/RAEng-FoD-Bahmni-project/lab-integrations-RTL)
- 📦 [All Repositories / جميع المستودعات](https://github.com/RAEng-FoD-Bahmni-project)

## License | الترخيص

Components are licensed under their respective open-source licenses. See the [Licensing section](https://raeng-fod-bahmni-project.github.io#licensing) on the landing page for details.

المكونات مرخّصة بموجب تراخيص المصدر المفتوح الخاصة بها. راجع [قسم التراخيص](https://raeng-fod-bahmni-project.github.io#licensing) على الصفحة الرئيسية للتفاصيل.
