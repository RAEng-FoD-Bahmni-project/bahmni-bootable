<div align="center">
  <b>English</b> |
  <a href="./README.ar.md">العربية</a>
</div>

---

# Bahmni (Arabic) — Bootable USB Appliance

---

## 📖 Full Installation Guides

- **English Guide:** [Download PDF](https://drive.google.com/file/d/18Z1ruQNfTZCaWEv9QzFcNzpFqYoLeTbf/view?usp=sharing)
- **الدليل بالعربية:** [تحميل PDF](https://drive.google.com/file/d/1tAcgKpV1vUTgCDnOqqdAOi6G0FyURZZW/view?usp=sharing)

---

## 💻😊 User Facility Setup Guide

To learn more about the steps of system configuration and deployment at a facility. Follow the guide below. 

[English User Guide](https://drive.google.com/file/d/17c9cz87okPUyGKveduW79jrCzieu1ctv/view?usp=sharing)

---


### Overview

A pre-configured, bootable system image containing the full Bahmni Arabic stack. Flash it to a USB drive, boot any server from it, and have a complete hospital EMR running in minutes.

### Download

| File | Size | Link |
|------|------|------|
| Bootable USB Image | ~80 GB | [Download from Google Drive](https://drive.google.com/file/d/1APqyFU8IddtPc2QY-BiDCINN49G8q9OH/view?usp=drivesdk) |

### What's Included

The appliance image contains:

- **Ubuntu OS** — Pre-installed and configured
- **Bahmni Arabic Stack** — All services running in Docker containers:
  - OpenMRS — Core medical records
  - Bahmni Apps — Clinical UI, fully Arabic
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
3. After Ubuntu is installed, the Bahmni Arabic system deploys automatically via Docker

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

## Related Repositories

- 🌐 [Landing Page](https://raeng-fod-bahmni-project.github.io)
- 🔬 [Lab Integrations](https://github.com/RAEng-FoD-Bahmni-project/lab-integrations-RTL)
- 📦 [All Repositories](https://github.com/RAEng-FoD-Bahmni-project)

## License

Components are licensed under their respective open-source licenses. See the [Licensing section](https://raeng-fod-bahmni-project.github.io#licensing) for details.
