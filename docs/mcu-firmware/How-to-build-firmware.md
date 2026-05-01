---
title: How to build firmware
slug: mcu-firmware/how-to-build-firmware
docTags: 
createdAt: Sun Apr 26 2026 18:22:16 GMT+0000 (Coordinated Universal Time)
updatedAt: Tue Apr 28 2026 13:14:38 GMT+0000 (Coordinated Universal Time)
---

This page explains how to build the MCU firmware file (`.UF2`) from source code. The resulting file can be uploaded to the MCU of Flipper One via USB.

To build the MCU firmware locally:

:::::WorkflowBlock
:::WorkflowBlockItem
Install [Visual Studio Code](https://code.visualstudio.com/), [Python](https://www.python.org/downloads/), and [git](https://git-scm.com/).
:::

:::WorkflowBlockItem
Open a terminal in the folder where you want to store the firmware source code.
:::

:::WorkflowBlockItem
Clone the MCU firmware repository to your computer:

`git clone --recursive https://github.com/flipperdevices/flipperone-mcu-firmware`
:::

:::WorkflowBlockItem
Open Visual Studio Code and go to **File → Open Folder...** and select the **flipperone-mcu-firmware** folder you just cloned.
:::

:::WorkflowBlockItem
Visual Studio Code will prompt you to install the recommended extensions. Click **Install** to accept, and wait until the process is complete.

![](/files/pics/mcu-firmware-vscode-install-extensions.png)
:::

:::WorkflowBlockItem
Click **Raspberry Pi Pico Project** in the left sidebar.
:::

:::WorkflowBlockItem
Click **Configure CMake**.
:::

:::WorkflowBlockItem
Click **Compile Project**. 

:::hint{type="info"}
If you get an error during the first build, click **Compile Project** again.
:::

:::

:::::

![](/files/pics/mcu-firmware-vscode-compilation.png)

After a successful build, the firmware .UF2 file will be located in the **flipperone-mcu-firmware/build** folder. To flash it to the MCU, follow the instructions on the [Firmware Update](Firmware-update.md) page.
