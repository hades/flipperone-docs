---
title: Operation modes
slug: user-interface/operation-modes
docTags: 
createdAt: Sun Apr 26 2026 18:22:16 GMT+0000 (Coordinated Universal Time)
updatedAt: Tue Apr 28 2026 13:21:50 GMT+0000 (Coordinated Universal Time)
---

Flipper One operates in several modes depending on its hardware state and the type of software loaded. The display and LED indicate the current mode.

---

### Power OFF

The device is completely powered down. The main CPU and MCU are fully off, and the display is not active. This mode is used for long-term storage, shipping, and maximum power saving.

![Power OFF](/files/pics/ui/ui-power-off.png "Flipper One in Power OFF Mode")

---

### MCU Mode

Only the low-power Microcontroller Unit (MCU) is active. The device works as a power bank and displays basic info on the screen. Two GPIO pins (M40, M41) are available in this mode.

![MCU Mode](/files/pics/ui/ui-mcu-mode.png "Flipper One in MCU Mode")

---

### Boot Menu

The device is running the U-Boot menu with available Flipper OS boot profiles. The main CPU is powered on, but the operating system has not yet started.

![Boot Menu](/files/pics/ui/ui-boot-menu.png "Flipper One in Boot Menu Mode")

---

### Linux Mode

Primary mode: the full Linux system is running. All hardware components are active. Ready for networking router, applications, and desktop/TV profiles.

![Linux Mode](/files/pics/ui/ui-linux-mode.png "Flipper One in Linux Mode")

---

### How to switch modes

Modes can be switched through the Power button :inlineImage[]{src="/files/pics/ui/ui_power_button.png" alt caption} and the Power menu. 

**Power menu** - a modal window with the available power options.

- To turn on the device from `Power OFF` to `MCU Mode`, long press :inlineImage[]{src="/files/pics/ui/ui_power_button.png" alt caption} for 1 second. 

- Press :inlineImage[]{src="/files/pics/ui/ui_power_button.png" alt caption} in `MCU Mode` or `Linux Mode` to open the Power menu.

| MCU Mode | Linux Mode |
| --- | --- |
| ![Power menu MCU Mode](/files/pics/ui/ui_power_menu_mcu_mode.png) | ![Power menu Linux Mode](/files/pics/ui/ui_power_menu_linux_mode.png)|

:::hint{type="warning"}
⚠️ **Work in progress:** Button names are not final and may change.
:::

- Press :inlineImage[]{src="/files/pics/ui/ui_power_button.png" alt caption} in `Boot Menu` to switch the device to `MCU Mode`.


