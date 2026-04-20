# Supported boards 

This page provides a list of boards that support installing Flipper OS using images built by the official build system. It also includes the target name, board-specific notes, hardware-defined boot priority, and instructions for switching each board to MaskROM mode for flashing via USB. Learn more about MaskROM mode in the [Rockchip MaskROM mode](./How-to-install-an-image.md#rockchip-maskrom-mode) section.

## Flipper One (HW ver. F0B0C1)

**Prototype. Not for sale!**

::Image[]{src="files/pics/flipper_one_prototype.jpg" size="50" position="center" caption=""}

✅ DisplayPort on USB-C1.

✅ USB-A to USB-A cable not required for flashing via MaskROM mode.

**Target name:** `flipper-one`.

**Boot priority:** UFS flash → SD card → USB (MaskROM).

**Switching to MaskROM mode:** from the boot menu on the screen.

**MaskROM USB port:**
![usb-c icon](files/pics/icon_usb_c.png) USB-C1.

---

## Armsom Sige5 (aka Banana Pi BPI-M5 Pro)

**Recommended board!**

::Image[]{src="files/pics/banana-pi-m5-pro.png" size="38" position="center" caption=""}

✅ DisplayPort on USB-C.

✅ USB-A to USB-A cable not required for flashing via MaskROM mode.

**Target name:** `sige5`.

**Boot priority:** eMMC flash → SD card → USB (MaskROM).

**Switching to MaskROM mode:** Hold the MASKROM button while powering on the board.

**MaskROM USB port:** ![usb-c icon](files/pics/icon_usb_c.png) OTG USB-C.

**Product documentation:**

Banana Pi BPI-M5 Pro: 
https://docs.banana-pi.org/en/BPI-M5/BananaPi_BPI-M5_Pro

Armsom Sige5:
https://docs.armsom.org/armsom-sige5

---

## FireFly ROC-RK3576-PC

::Image[]{src="files/pics/roc-rk3576.jpg" size="42" position="center" caption=""}

✅ DisplayPort on USB-C.

✅ USB-A to USB-A cable not required for flashing via MaskROM mode.

**Target name:** `rock-pc`.

**Boot priority:** eMMC flash → SD card → USB (MaskROM).

**Switching to MaskROM mode:** Hold the MASKROM button while powering on the board.

**MaskROM USB port:** ![usb-c icon](files/pics/icon_usb_c.png) USB-C port. 

**Product documentation:** https://wiki.t-firefly.com/en/ROC-RK3576-PC/

---

## Luckfox Omni3576

::Image[]{src="files/pics/luckfox-omni3576.png" size="48" position="center" caption=""}

✅ DisplayPort on USB-C.

✅ USB-A to USB-A cable not required for flashing via MaskROM mode.

**Target name:** `omni3576`.

**Boot priority:** eMMC flash → SD card → USB (MaskROM).

**Switching to MaskROM mode:** Connect the ADC0 pin to the GND pin while powering on the board.

**MaskROM USB port:** ![usb-c icon](files/pics/icon_usb_c.png) USB-C port next to the HDMI port.

**Product documentation:** https://wiki.luckfox.com/Luckfox-Omni3576/Luckfox-Omni3576-quick-start

---

## Radxa ROCK 4D

::Image[]{src="files/pics/radxa-rock-4d.png" size="38" position="center" caption=""}

❌ No DisplayPort on USB-C. 

❌ USB-A to USB-A cable required for flashing via MaskROM mode.

**Target name:** `rock-4d`.

**Boot priority:** FSPI0 flash → UFS flash → USB (MaskROM).

**Switching to MaskROM mode:** Hold the Maskrom button while powering on the board.

**MaskROM USB port:** ![usb-a icon](files/pics/icon_top_usb3.png) Top USB-A 3.0 port.

**Product documentation:** https://docs.radxa.com/en/rock4/rock4d

---

## NanoPi M5

::Image[]{src="files/pics/nanopi-m5.png" size="38" position="center" caption=""}

❌ No DisplayPort on USB-C.

❌ USB-A to USB-A cable required for flashing via MaskROM mode.

**Target name:** `nanopi-m5`.

**Boot priority:** 

* Boot mode switch in the FSPI position: FSPI1_M1 flash → eMMC flash → USB (MaskROM).

* Boot mode switch in the UFS/SD position: UFS flash → SD card → USB (MaskROM).

**Switching to MaskROM mode:** Hold the MASK button while powering on the board.

**MaskROM USB port:** ![usb-a icon](files/pics/icon_top_usb3.png) Top USB-A 3.0 port.

**Product documentation:** https://wiki.friendlyelec.com/wiki/index.php/NanoPi_M5

---

## Rockchip RK3576 EVB1

**Evaluation board. Not for sale!**

::Image[]{src="files/pics/evb1.png" size="38" position="center" caption=""}

**Target name:** `evb1`.

Official Rockchip RK3576 Evaluation board EVB1. This board is supported by Flipper OS; however, we cannot disclose detailed information about it due to NDA restrictions.



