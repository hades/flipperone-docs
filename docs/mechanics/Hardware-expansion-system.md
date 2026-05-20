---
title: Hardware expansion system
slug: mechanics/hardware-expansion-system
docTags: 
createdAt: Sun Apr 26 2026 18:22:16 GMT+0000 (Coordinated Universal Time)
updatedAt: Tue Apr 28 2026 13:04:15 GMT+0000 (Coordinated Universal Time)
---

Flipper One features a hardware expansion system with two types of expansion modules:

* **M.2 module.** A standardized internal expansion module that connects to the device’s M.2 B-key port, providing access to high-speed interfaces, SIM/eSIM connectivity, and several GPIO pins. The module can also expose an external antenna connector through dedicated openings in the device’s chassis.

* **GPIO module.** A custom external expansion module that connects to the GPIO port on the back of the device, which provides access to a range of low-speed interfaces including USB 2.0, UART, SPI, ADC inputs, and more.

We have open-sourced the [3D models of the enclosure parts](https://cad.onshape.com/documents/32ee3b79861e4ff5fe28ee3b/w/8eca0dcb9e92b0271d434028/e/adb36e3c67cc1a734691cf20) involved in the hardware expansion system, enabling the community and module manufacturers to design custom enclosure parts.

***

## M.2 modules

The M.2 expansion module (SSDs, cellular or satellite modems, SDR radios, and more) can be installed inside the device via the internal M.2 port. To access the port, the back plate must be removed by unscrewing its mounting screws. The module is then secured to one of the two threaded standoffs on the device’s main board, depending on the module’s length.

![](/files/pics/m2-expansion-port.png)

Flipper One supports M.2 modules with top-side component placement (S3 type, with component height up to 1.5 mm above the PCB). The following module form factors are supported:

* **2242:** 22 mm wide, 42 mm long
* **3042:** 30 mm wide, 42 mm long
* **3052:** 30 mm wide, 52 mm long

:::hint{type="info"}
M.2 port pinout and a list of supported interfaces are available on the [M.2 port](../hardware/M2-port.md) page.

Examples of M.2 modules can be found on the [M.2 modules](../hardware/M2-Modules.md) page.
:::

***

## Antenna rail

At the top of the rear side of Flipper One, above the back plate, there is an antenna rail — a separate part designed to hold up to four SMA antennas connected to an M.2 module. It is intentionally separated from the back plate, allowing antennas to be installed into the antenna rail and cables to be routed before attaching the rail to the device. This design helps prevent antenna cable damage during assembly.

![](/files/pics/flipper-one-antenna-rail.png)

***

## GPIO modules

The GPIO module connects to the GPIO port on the back of the device. 

:::hint{type="info"}
GPIO port pinout and a list of supported interfaces are available on the [GPIO port](../hardware/GPIO-port.md) page.

Examples of GPIO modules can be found on the [GPIO modules](../hardware/GPIO-Modules.md) page.
:::

***

### GPIO module screw mounting

The back plate and antenna rail include six threaded nuts for mounting GPIO modules. The threads are M2, with a maximum screw insertion depth of 3 mm. All threaded nuts are arranged on a 2.54 mm grid, aligned with the GPIO connector pin layout. This makes it possible to build a simple GPIO module from perfboard by cutting it to size and drilling out the existing holes to 2 mm in diameter for mounting to the Flipper One enclosure.

![](/files/pics/flipper-one-gpio-module-screw-mount.png)

***

### Snap-fit mounting for module cover

On the Flipper One enclosure, there are two snap-fit notches located on the top and bottom, designed to secure a GPIO module cover to the device body.

![](/files/pics/flipper-one-gpio-module-cover-mount.png)
