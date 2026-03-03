# MeshCore Repeater Setup — NEO

---

## What You Need
- Any MeshCore-compatible device (RAK4631, T-Beam, Heltec, E22-based, etc.)
- Antenna connected before powering on
- USB cable for your device
- Browser (required for web flasher)

---

## Step 1 — Flash MeshCore via Web Flasher

**1.** Open your browser and go to:
>  https://flasher.meshcore.co.uk

**2.** Select your **device model** from the dropdown and click on it.

**3.** Select device role: **Repeater**

**4.** Plug in your device via USB

**5.** Put your device into bootloader/flash mode
> This varies by device — check your specific hardware docs. Common methods:
> - **RAK4631:** Double-tap RESET button or click Enter DFU mode
> - **T-Beam / Heltec:** Hold BOOT button while plugging in USB
> - **Others:** Check your device's documentation

**6.** Click **Flash** and wait for it to complete 
> Do not unplug during flashing

---

## Step 2 — Configure NEO Radio Settings

After flashing, click **Configure via USB**, click connect and select your device from the list.

Set the following settings:

| Setting | Value |
|---|---|
| **Name** | Your Repeater name |
| **Latitude  Longitude** | Your Repeater coordinates |
| **Preset** | USA/Canada (Recommended) |
| **TX Power** | Max for your device |
| **New Admin Password** | your_password_here (for remote admin access via mesh) |

## Step 3 — Verify public key availability

Utilizing the first 2 values from the public key check via Discord that that key is available using /prefix-list.


## Step 4 — Save & Reboot

Click **Save settings** in the web setup
> The device will reboot and come online within a few seconds



## Useful Links

- Web Flasher: https://flasher.meshcore.co.uk
- MeshCore GitHub: https://github.com/meshcore-dev/MeshCore

