---
title: Operation modes
slug: user-interface/operation-modes
docTags: 
createdAt: Sun Apr 26 2026 18:22:16 GMT+0000 (Coordinated Universal Time)
updatedAt: Tue Apr 28 2026 13:21:50 GMT+0000 (Coordinated Universal Time)
---

This page describes the device's operating modes. Hardware state and what type of software is loaded. Visual indicators: LED and screen identify the current mode.

---

### Power OFF

Device is completely powered down. The main CPU and MCU are fully off, and the display is not active. This mode is used for long-term storage, shipping, and maximum power saving.

![Power OFF](/files/pics/ui/ui-power-off.png "Flipper One in Power OFF Mode")

---

### MCU Mode

Only the low-power Microcontroller Unit (MCU) is active. Device work as power bank and display basic info on screen. Two GPIO pins (M40, M41) available in this mode.

![MCU Mode](/files/pics/ui/ui-mcu-mode.png "Flipper One in MCU Mode")

---

### Boot Menu

Device running U-Boot menu with available Flipper OS boot profiles. Main CPU is powered on, but the operating system is not running yet. 

![Boot Menu](/files/pics/ui/ui-boot-menu.png "Flipper One in Boot Menu Mode")

---

### Linux Mode

Primary mode - full Linux system is running. All hardware components are active. Ready for networking router, applications, desktop/TV profiles.

![Linux Mode](/files/pics/ui/ui-linux-mode.png "Flipper One in Linux Mode")

---

### How to switch operation mode

- Long press :inlineImage[]{src="/files/pics/ui/ui_power_button.png" alt caption} for 1 second to switch from `Power OFF` to `MCU Mode`

- Pressing :inlineImage[]{src="/files/pics/ui/ui_power_button.png" alt caption} in `MCU Mode` or `Linux mode` opens the Power menu. Modal window with the available power options:

| MCU Mode | Linux Mode |
| --- | --- |
| ![Power menu MCU Mode](/files/pics/ui/ui_power_menu_mcu_mode.png) | ![Power menu Linux Mode](/files/pics/ui/ui_power_menu_linux_mode.png)|

:::hint{type="warning"}
⚠️ **Work in progress:** Button names are not final and may change.
:::

- Pressing :inlineImage[]{src="/files/pics/ui/ui_power_button.png" alt caption}  in `Boot Menu` switching device to `MCU Mode`


