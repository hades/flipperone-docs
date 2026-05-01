---
title: Firmware update
slug: mcu-firmware/firmware-update
docTags: 
createdAt: Sun Apr 26 2026 18:22:16 GMT+0000 (Coordinated Universal Time)
updatedAt: Tue Apr 28 2026 13:14:38 GMT+0000 (Coordinated Universal Time)
---

This page explains how to flash the MCU firmware file (`.UF2`) to the Flipper One MCU via USB. You can download the firmware file from the [Firmware Update Server](https://update.flipperzero.one/builds/flipper-one-mcu/dev/) or [build it from source code](How-to-build-firmware.md).

To flash Flipper One MCU:

:::::WorkflowBlock
:::WorkflowBlockItem
Connect Flipper One **USB-C 1** port to your computer.
:::

:::WorkflowBlockItem
Put the MCU into BOOTSEL mode. The method depends on Flipper One hardware revision. If you are unsure which revision you have, try the available methods below.

**For Flipper One rev F0.B0.C1:** 

**Step 1:** Press and hold **PTT** button.

**Step 2:** Press and hold **Left** and **Back** buttons for **3 sec**, then release.

**Step 3:** Release **PTT** button.

![](/files/pics/mcu-switching-to-bootsel-mode-rev-F0.B0.C1.png)

**For Flipper One rev 2.F0.B1.C2:** 

**Step 1:** Press and hold **✔ and ✖** buttons.

**Step 2:** Press and hold **Left** and **Back** buttons for **3 sec**, then release.

**Step 3:** Release **✔ and ✖** buttons.

![](/files/pics/mcu-switching-to-bootsel-mode-rev-2.F0.B1.C2.png)

If the MCU has successfully swithced to BOOTSEL mode, your operating system will detect it as a Mass Storage Device. If it does not appear, try using a different USB cable and repeat the BOOTSEL procedure.
:::

:::WorkflowBlockItem
Copy the `.UF2` firmware file onto the Mass Storage Device. Once the file copy is complete, the MCU will automatically reboot and the Mass Storage Device will disconnect from the computer.
:::
:::::

:::Iframe{code="<video&#xA;    autoplay muted loop playsinline style=&#x22;width: 100%; margin: 0 !important;&#x22;&#xA;    src=&#x22;https://cdn.flipperzero.one/Monosnap_screencast_2024-01-24_21-27-24.mp4&#x22;&#xA;></video>" iframeHeight="500"}

:::

:::hint{type="success"}
The MCU firmware has been successfully updated.
:::
