# GIRA_ECHO1_FIRMWARE
Repository for the latest firmware versions of the GIRA Echo 1 MIDI controller

# GIRA Controller — Firmware Releases

Welcome to the official firmware repository for the GIRA Controller (ECHO-1).
This repository contains:

the firmware binaries ready to be flashed onto the device,

the latest.json file used by the GIRA Configurator application to check for updates.

## This repository does not contain the source code.
Firmware development is carried out in a private repository.

### Download the latest version

The file containing information about the latest available version is: 

```latest.json```

**It is always accessible via:**

https://raw.githubusercontent.com/FJeanmaire/GIRA_ECHO1_FIRMWARE/main/latest.json

**This file is used by the GUI (GIRA Configurator) to:**

- determine the most recent firmware version,

- retrieve the download URL for the .bin file,

- verify the integrity of the file via its SHA-256 signature.

Example of latest.json:

```json
{
  "version": "1.0.0",
  "url": "https://github.com/FJeanmaire/GIRA_ECHO1_FIRMWARE/releases/download/v1.0.0/gira-controller-1.0.0.bin",
  "sha256": "d2b2c9c0f83e..."
}
```

# Manual downloads

If you want to download firmware manually, go to the tab:

**Releases**
( https://github.com/FJeanmaire/GIRA_ECHO1_FIRMWARE/releases )

Each version contains a ```.bin``` file:

```gira-controller-X.Y.Z.bin```

# Device update

**Via the GIRA Configurator app (recommended)**

1. Connect your device via USB.

2. Open the GIRA Configurator app.

3. The app:

    - automatically downloads latest.json,
    
    - compares the device version with the server version,
    
    - offers the update if necessary.

# Manual update (advanced)

Download the ```.bin``` file for the desired version from the Releases tab.

Use a tool such as:

```esptool.py```

or a compatible ESP32 flasher.

Flash the binary to the address defined by the device's partition table.

# 🔐 File integrity

Each firmware release is accompanied by a SHA-256 hash in ```latest.json```.

You can verify the integrity with:

**Linux / macOS**
```bash
shasum -a 256 gira-controller-X.Y.Z.bin
```

**Windows PowerShell**
```powershell
Get-FileHash gira-controller-X.Y.Z.bin -Algorithm SHA256
```
Compare the value obtained with the one mentioned in ```latest.json```.

# ℹ️ Information

The firmware is based on ```ESP32-S3```.

The update protocol uses **MIDI SysEx messages** for HMI ↔ device communication.

The binary is provided as a ```.bin``` file ready to flash.

# 📝 Changelog

Release notes and fixes can be found on the GitHub Releases pages.

# 🛠 Developers

The firmware source code is not public.
This repository is only used to distribute release artifacts:

firmware binaries ```.bin```

```latest.json``` file

# 📬 Contact

For any questions regarding the GIRA controller or its updates:

**📧 contact:** [DISCUSSIONS](https://github.com/FJeanmaire/GIRA_ECHO1_FIRMWARE/discussions)

**🌐 website:** No website for the moment
