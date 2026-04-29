---
title: Firmware architecture
slug: mcu-firmware/architecture
docTags: 
createdAt: Sun Apr 26 2026 18:22:16 GMT+0000 (Coordinated Universal Time)
updatedAt: Tue Apr 28 2026 13:07:05 GMT+0000 (Coordinated Universal Time)
---

Flipper One uses a dual-processor architecture with **High-Performance Linux CPU (Rockchip RK3576)** and **Low-Power MCU (Raspberry Pi RP2350)**. While the CPU runs Linux and manages all high-level peripherals (USB, HDMI, M.2, Wi-Fi, Ethernet, and audio), the MCU is responsible for the following tasks:

- Rendering image on the LCD display anc controlling backlight brightness.
- Processing events from the buttons and touchpad, and controlling haptic feedback.
- Handling 3.5 mm audio jack connect/disconnect and headset button press events.
- Managing the battery and power subsystems.
- Managing system power states and implementing Power Bank mode.
- Managing the main CPU power-on sequence and boot process.
- Handling communication over the CC pins of the USB-C ports.
- Exposing 2 PIO (Programmable I/O) pins to the GPIO expansion connector.
- Controlling all device LEDs.

![MCU connection diagram](/files/pics/mcu-connection-diagram.jpg "MCU connection diagram")

## Firmware architecture

The MCU firmware is built on the [FreeRTOS](https://www.freertos.org/) kernel and a set of libraries and drivers organized in a layered firmware architecture.

![MCU firmware architecture](/files/pics/mcu-firmware-architecture.jpg "MCU firmware architecture")

