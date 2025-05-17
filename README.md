# Creating a Bootable Chrome OS USB Installer

## Method 1: Chromebook Recovery Utility (Easiest)

Follow the steps in the main [README.md](../README.md#chrome-os-priority-guide).

---

## Method 2: Manually Creating a Chrome OS USB on Windows, Linux, or macOS

### Step 1: Download a Recovery Image

- Go to [Chrome OS Recovery Images](https://cros.tech/)
- Find your device or use a generic image.

### Step 2: Prepare Your USB Drive

- Use a USB at least 8GB.
- Back up any data (it will be erased).

#### On Windows

- Use [Rufus](https://rufus.ie/) or [balenaEtcher](https://www.balena.io/etcher/)
- Select the downloaded `.bin` image and your USB.

#### On Linux/macOS

- Insert USB and find its device path (e.g., `/dev/sdX`).
- Use `dd` (replace `X` with your USB's letter):

    ```bash
    sudo dd if=chromeos_image.bin of=/dev/sdX bs=4M status=progress
    sync
    ```

- Or use [balenaEtcher](https://www.balena.io/etcher/).

### Step 3: Boot from USB

- Insert USB into target device.
- Enter boot menu (often Esc, F12, or F2 during power-on).
- Select USB as boot device.

---

## Troubleshooting

- Try a different USB port or drive if you have issues.
- Ensure recovery image matches your Chromebook model.
- See [Common Issues](../README.md#common-issues--troubleshooting).
