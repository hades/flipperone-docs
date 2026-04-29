---
title: MCU Firmware Architecture
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

## CPU and MCU interconnection

The MCU and CPU are interconnected via several interfaces and GPIO pins, including:

- **UART (Universal Asynchronous Receiver-Transmitter)** connects Linux console serial port to the RP2350.
- **SPI (Serial Peripheral Interface)** for transferring frame buffer from the Linux side to the RP2350 side for output to the display.
- **I²C (Inter-Integrated Circuit)** for transferring commands from Linux side (I²C master) and input events from MCU side (I²C slave).
- **INT** pin is used by the MCU to notify the CPU of new events.
- **BOOT0 & BOOT1** pins are used to control the main CPU’s boot process. The BOOT0 pin can force the CPU into MaskROM mode, enabling UFS flash programming via USB. The BOOT1 pin selects the OS boot source; the MCU generates a PWM signal that is converted into a voltage level, which the CPU reads via its ADC during the early boot stage.

![CPU and MCU interconnection](/files/pics/cpu-and-mcu-interconnection.jpg "CPU and MCU interconnection")

## Firmware architecture

The MCU firmware is built on the [FreeRTOS](https://www.freertos.org/) kernel and a set of libraries and drivers organized in a layered firmware architecture.

![MCU firmware architecture](/files/pics/mcu-firmware-architecture.jpg "MCU firmware architecture")

