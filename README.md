# Bahmni RTL — Bootable USB Appliance

---

## 📖 Full Installation Guides

- **English Guide:** [Download PDF](https://drive.google.com/file/d/18Z1ruQNfTZCaWEv9QzFcNzpFqYoLeTbf/view?usp=sharing)
- **الدليل بالعربية:** [تحميل PDF](https://drive.google.com/file/d/1tAcgKpV1vUTgCDnOqqdAOi6G0FyURZZW/view?usp=sharing)

---

## English

### Overview

A pre-configured, bootable system image containing the full Bahmni Arabic RTL stack. Flash it to a USB drive, boot any server from it, and have a complete hospital EMR running in minutes.

### Download

| File | Size | Link |
|------|------|------|
| Bootable USB Image | ~80 GB | [Download from Google Drive](#) <!-- TODO: Replace with Google Drive link --> |

### What's Included

The appliance image contains:

- **Ubuntu OS** — Pre-installed and configured
- **Bahmni RTL Stack** — All services running in Docker containers:
  - OpenMRS — Core medical records
  - Bahmni Apps — Clinical UI, fully RTL/Arabic
  - OpenELIS — Laboratory information system
  - Odoo — Billing & inventory
  - Dcm4chee — Medical imaging (DICOM/PACS)
- **Pre-loaded configurations** — Arabic locale, RTL interface, default clinical forms

### Requirements

- A server or PC with a USB port
- A USB drive (minimum 128 GB recommended)
- Network connectivity for post-install configuration

### Installation

#### 1. Prepare the USB Drive

Flash the downloaded image to a USB drive using [balenaEtcher](https://etcher.balena.io/) or `dd`:

```bash
# Linux/macOS (replace /dev/sdX with your USB device)
sudo dd if=bahmni-appliance.img of=/dev/sdX bs=4M status=progress
sync
```

#### 2. Configure BIOS

1. Insert the USB drive into the target server
2. Enter BIOS settings at startup (typically F2, F12, Del, or Enter)
3. Set the boot priority to boot from USB first

#### 3. Boot and Install

1. Boot the server from the USB drive
2. The installer launches automatically and installs Ubuntu onto the server's hard drive
3. After Ubuntu is installed, the Bahmni RTL system deploys automatically via Docker

#### 4. Start the System

```bash
# Start all services
./start-bahmni.sh

# Stop all services
./stop-bahmni.sh
```

#### 5. Access the System

Open a browser and navigate to the server's IP address. All modules are pre-configured:

- Patient Registration
- Clinical Encounters
- Laboratory (OpenELIS)
- Pharmacy
- Medical Imaging
- Billing (Odoo)

---

## العربية

### نظرة عامة

صورة نظام مُعدّة مسبقاً وقابلة للتمهيد تحتوي على نظام باهمني العربي الكامل. انسخها على ذاكرة USB، شغّل أي خادم منها، واحصل على نظام سجلات طبية متكامل للمستشفى في دقائق.

### التحميل

| الملف | الحجم | الرابط |
|------|------|------|
| صورة USB القابلة للتمهيد | ~80 جيجابايت | [تحميل من Google Drive](#) <!-- TODO: Replace with Google Drive link --> |

### المحتويات

تحتوي صورة النظام على:

- **نظام أوبنتو** — مُثبّت ومُعدّ مسبقاً
- **حزمة باهمني** — جميع الخدمات تعمل في حاويات Docker:
  - OpenMRS — السجلات الطبية الأساسية
  - Bahmni Apps — واجهة سريرية عربية بالكامل
  - OpenELIS — نظام معلومات المختبر
  - Odoo — الفوترة والمخزون
  - Dcm4chee — التصوير الطبي (DICOM/PACS)
- **إعدادات جاهزة** — واجهة عربية، نماذج سريرية افتراضية

### المتطلبات

- خادم أو حاسوب مزود بمنفذ USB
- ذاكرة USB (يُنصح بـ 128 جيجابايت كحد أدنى)
- اتصال بالشبكة للإعداد بعد التثبيت

### التثبيت

#### 1. تحضير ذاكرة USB

انسخ الصورة المحمّلة على ذاكرة USB باستخدام [balenaEtcher](https://etcher.balena.io/) أو أمر `dd`:

```bash
# Linux/macOS — استبدل /dev/sdX بجهاز USB الخاص بك
sudo dd if=bahmni-appliance.img of=/dev/sdX bs=4M status=progress
sync
```

#### 2. تهيئة إعدادات BIOS

1. أدخل ذاكرة USB في الخادم المستهدف
2. ادخل إعدادات BIOS عند بدء التشغيل (عادةً بالضغط على F2 أو F12 أو Del أو Enter)
3. اضبط أولوية الإقلاع من USB أولاً

#### 3. الإقلاع والتثبيت

1. شغّل الخادم من ذاكرة USB
2. يبدأ برنامج التثبيت تلقائياً وينصّب نظام أوبنتو على القرص الصلب للخادم
3. بعد تثبيت أوبنتو، يتم نشر نظام باهمني تلقائياً عبر حاويات Docker

#### 4. تشغيل النظام

```bash
# تشغيل جميع الخدمات
./start-bahmni.sh

# إيقاف جميع الخدمات
./stop-bahmni.sh
```

#### 5. الوصول إلى النظام

افتح المتصفح وانتقل إلى عنوان IP الخادم. جميع الوحدات مُعدّة مسبقاً وجاهزة للاستخدام:

- تسجيل المرضى
- اللقاءات السريرية
- المختبر (OpenELIS)
- الصيدلية
- التصوير الطبي
- الفوترة (Odoo)

---

## Related Repositories | المستودعات ذات الصلة

- 🌐 [Landing Page](https://raeng-fod-bahmni-project.github.io)
- 🔬 [Lab Integrations](https://github.com/RAEng-FoD-Bahmni-project/lab-integrations-RTL)
- 📦 [All Repositories](https://github.com/RAEng-FoD-Bahmni-project)

## License | الترخيص

Components are licensed under their respective open-source licenses. See the [Licensing section](https://raeng-fod-bahmni-project.github.io#licensing) for details.

المكونات مرخّصة بموجب تراخيص المصدر المفتوح الخاصة بها. راجع [قسم التراخيص](https://raeng-fod-bahmni-project.github.io#licensing) للتفاصيل.
