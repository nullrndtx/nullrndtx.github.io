---
layout: post
title: "How To Use SP FlashTools in Arch Linux"
summary:
---

**Unfortunately this seems to work only on Linux 64-bit**

```
DISCLAIMER: It is always risky to flash your mobile device. I do not and will
not take any responsibility for bootloops and bricks.
Please check carefully that the ROM or recovery.img you want to flash is
suitable for your specific device and for the sp_flash_tool. The firmware
directory should neither contain meta-inf nor system folder, but
something_with_a_scatter.txt and a system.img
Backup your phone before flashing!
Your phone's battery should be at least half charged (50 percent) before you
start this.
```

### Step 1

If you haven't done so before, install the Linux generic usb-driver package:

#### Ubuntu/Debian Family

> sudo apt-get install libusb-dev libmtp libmtp-runtime

#### Arch Linux

> sudo pacman -S gvfs-mtp libmtp

### Step 2

Download SP Flashtools and locate to __/opt__

```sh
cd /opt
wget
http://spflashtool.com/download/SP_Flash_Tool_exe_Linux_64Bit_v5.1520.00.100.zip
unzip SP_Flash_Tool_exe_Linux_64Bit_v5.1520.00.100.zip
mv SP_Flash_Tool_exe_Linux_v5.1520.00.100 SPflashtools
rm SP_Flash_Tool_exe_Linux_64Bit_v5.1520.00.100.zip
```

### Step 3

Fixing BROM Error

```sh
touch /etc/udev/rules.d/80-persistent-usb.rules
echo "SUBSYSTEM=="usb", ACTION=="add", ATTR{idVendor}=="0e8d",
ATTR{idProduct}=="*"" > /etc/udev/rules.d/80-persistent-usb.rules
touch /etc/udev/rules.d/20-mm-blacklist-mtk.rules
echo "ATTRS{idVendor}=="0e8d", ENV{ID_MM_DEVICE_IGNORE}="1"" > /etc/udev/rules.d/20-mm-blacklist-mtk.rules
echo "ATTRS{idVendor}=="6000", ENV{ID_MM_DEVICE_IGNORE}="1"" >> /etc/udev/rules.d/20-mm-blacklist-mtk.rules
```

### Step 4

If you're done, now restart udev by using the following command

#### Ubuntu/Debian Family

> service udev restart

#### Arch Linux

> udevadm control --reload

===

__Update__ 

For debian/ubuntu user you can use my installer script

[SPFlashtools
Installer](https://gist.githubusercontent.com/nullrndtx/a331cb7611dd4b022bc5aebddbca3428/raw/4b92faa1aa4a5f6e4682cd61039e816b035f59ed/FlashTools-Installer.sh)
