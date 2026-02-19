# Bahmni RTL — Bootable USB Appliance

A pre-configured, bootable system image containing the full Bahmni Arabic RTL stack. Flash it to a USB drive, boot any server from it, and have a complete hospital EMR running in minutes.

## Download

| File | Size | Link |
|------|------|------|
| Bootable USB Image | ~80 GB | [Download from Google Drive](#) <!-- TODO: Replace with Google Drive link --> |

## What's Included

The appliance image contains:

- **Ubuntu OS** — Pre-installed and configured
- **Bahmni RTL Stack** — All services running in Docker containers:
  - OpenMRS (core medical records)
  - Bahmni Apps (clinical UI, fully RTL/Arabic)
  - OpenELIS (laboratory information system)
  - Odoo (billing & inventory)
  - Dcm4chee (medical imaging — DICOM/PACS)
- **Pre-loaded configurations** — Arabic locale, RTL interface, default clinical forms

## Requirements

- A server or PC with a USB port
- A USB drive (minimum 128 GB recommended)
- Network connectivity (for post-install configuration)

## Installation

### 1. Prepare the USB Drive

Flash the downloaded image to a USB drive using a tool like [balenaEtcher](https://etcher.balena.io/) or `dd`:

```bash
# Linux/macOS (replace /dev/sdX with your USB device)
sudo dd if=bahmni-appliance.img of=/dev/sdX bs=4M status=progress
sync
```

### 2. Configure BIOS

1. Insert the USB drive into the target server
2. Enter BIOS settings at startup (typically by pressing F2, F12, Del, or Enter)
3. Set the boot priority to boot from USB first

### 3. Boot and Install

1. Boot the server from the USB drive
2. The installer will launch automatically and install Ubuntu onto one of the server's hard disk drives
3. After Ubuntu is installed, the Bahmni RTL system deploys automatically via Docker containers

### 4. Start the System

Once installation is complete, the system can be started and stopped with simple boot/shutdown scripts:

```bash
# Start all services
./start-bahmni.sh

# Stop all services
./stop-bahmni.sh
```

### 5. Access the System

Open a browser and navigate to the server's IP address. All modules are pre-configured and ready to use:

- **Patient Registration**
- **Clinical Encounters**
- **Laboratory (OpenELIS)**
- **Pharmacy**
- **Medical Imaging**
- **Billing (Odoo)**

## Full Installation Guides

For detailed step-by-step instructions with screenshots:

- **English Guide:** [Download PDF](https://drive.google.com/file/d/18Z1ruQNfTZCaWEv9QzFcNzpFqYoLeTbf/view?usp=sharing)
- **الدليل بالعربية:** [تحميل PDF](https://drive.google.com/file/d/1tAcgKpV1vUTgCDnOqqdAOi6G0FyURZZW/view?usp=sharing)

## Related Repositories

- 🌐 [Landing Page](https://raeng-fod-bahmni-project.github.io)
- 🔬 [Lab Integrations](https://github.com/RAEng-FoD-Bahmni-project/lab-integrations-RTL)
- 📦 [All Repositories](https://github.com/RAEng-FoD-Bahmni-project)

## License

Components are licensed under their respective open-source licenses. See the [Licensing section](https://raeng-fod-bahmni-project.github.io#licensing) on the landing page for details.
