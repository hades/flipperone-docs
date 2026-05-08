---
title: Firmware update
slug: mcu-firmware/firmware-update
docTags: 
createdAt: Sun Apr 26 2026 18:22:16 GMT+0000 (Coordinated Universal Time)
updatedAt: Tue Apr 28 2026 13:14:38 GMT+0000 (Coordinated Universal Time)
---

This page explains how to flash the MCU firmware file (`.UF2`) to the Flipper One MCU via USB.

To flash firmware to the Flipper One MCU:

:::::WorkflowBlock
:::WorkflowBlockItem
**Get the `.UF2` firmware file.**
- [Download the file from Update Server](https://update.flipperzero.one/builds/flipper-one-mcu/dev/)
    or
- [Build the file from source code](How-to-build-firmware.md) — if you modified the firmware.
:::

:::WorkflowBlockItem
**Connect Flipper One to your PC** via the **USB-C 1** port.

![](/files/pics/mcu-firmware-usbc1-connection.png)
:::
 
:::WorkflowBlockItem
**Switch the MCU to BOOTSEL mode.**

**Step 1:** Press and hold the **PTT** button.
![BOOTSEL step 1: hold PTT button](/files/pics/mcu-bootsel-rev-f0-b0-c1-step-1.png)

**Step 2:** Press and hold **Left** and **Back** buttons for **3 seconds**, then release.
![BOOTSEL step 2: hold Left and Back buttons](/files/pics/mcu-bootsel-rev-f0-b0-c1-step-2.png)

**Step 3:** Release the **PTT** button.
![BOOTSEL step 3: release PTT button](/files/pics/mcu-bootsel-rev-f0-b0-c1-step-3.png)

After switching the MCU to BOOTSEL mode, Flipper One's screen goes black and the device appears on your PC as a Mass Storage Device named RP2350.

If Flipper One does not appear, try a different USB cable and repeat the BOOTSEL procedure.
:::
 
:::WorkflowBlockItem
**Upload the `.UF2` firmware file** to the Mass Storage Device.
:::
:::::

:::Iframe{code="<video&#xA;    autoplay muted loop playsinline style=&#x22;width: 100%; margin: 0 !important;&#x22;&#xA;    src=&#x22;https://cdn.flipperzero.one/Upload_uf2_file.mp4&#x22;&#xA;></video>" iframeHeight="500"}
:::

:::hint{type="success"}
Once the `.UF2` file upload is complete, the Flipper One will automatically reboot and the Mass Storage Device will disconnect from your PC — the MCU firmware has been successfully updated.
:::
