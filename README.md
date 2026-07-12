# Installing Kitsune Magisk on LDPlayer 14 (Android 14)

This guide walks you through installing **Kitsune Magisk** on **LDPlayer 14** running **Android 14**.

## Prerequisites

Before you begin, make sure you have the Kitsune Magisk APK downloaded and ready to install.

## Steps

### 1. Enable Required Settings

In LDPlayer settings, enable the following options:

- **Root**
- **Writable System**

![Placeholder: LDPlayer settings with Root and Writable System enabled](./screenshots/01-enable-settings.png)

### 2. Install the Kitsune Magisk APK

Install the Kitsune Magisk APK file inside the emulator, just like you would install any other APK.

![Placeholder: Installing the Kitsune Magisk APK](./screenshots/02-install-apk.png)

### 3. Open a Root Shell

Open a terminal (via ADB or a terminal emulator app inside LDPlayer) and enter root mode:

```bash
su
```

![Placeholder: Terminal showing su command granting root access](./screenshots/03-root-shell.png)

### 4. Remount the Filesystem as Writable (if needed)

If the root filesystem is mounted as read-only, remount it as read-write:

```bash
mount -o remount,rw /
```

![Placeholder: Terminal output after remounting filesystem as rw](./screenshots/04-remount-rw.png)

### 5. Run the Bootstrap Script

Create the `/sbin` directory, set the correct permissions, and run the Magisk bootstrap setup:

```bash
mkdir /sbin
chmod 755 /sbin

/system/etc/init/magisk/magisk64 \
    --setup-sbin \
    /system/etc/init/magisk \
    /sbin
```

![Placeholder: Terminal output of the bootstrap script running successfully](./screenshots/05-bootstrap-script.png)

### 6. Reboot the Emulator

Restart LDPlayer to complete the installation.

![Placeholder: LDPlayer reboot confirmation](./screenshots/06-reboot.png)

## Done

After the reboot, Kitsune Magisk should be fully installed and active on your LDPlayer 14 (Android 14) instance.
