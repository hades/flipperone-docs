---
title: Power subsystem
slug: hardware/power-subsystem
docTags: 
createdAt: Sun Apr 26 2026 18:22:16 GMT+0000 (Coordinated Universal Time)
updatedAt: Tue Apr 28 2026 11:00:55 GMT+0000 (Coordinated Universal Time)
---

Flipper One is a portable device powered by an internal 2-cell Li-ion battery, which can be charged from a USB PD charger via the USB-C1 port. For flexible power management, the device employs controllable DC/DC converters and power switches managed by the RP2350 MCU.

## Specifications

:::hint{type="info"}

**Specifications are preliminary**

Some specifications listed here have not yet been fully validated and are subject to change. The device may also dynamically reduce performance and power capabilities under thermal limiting conditions.

:::

* **Battery capacity:** 22.9 Wh
* **USB-C1 charging input:** USB PD up to 60 W
* **USB-C2 output power:** up to 15 W
* **USB-A output power:** up to 15 W
* **GPIO port output power:** up to 25 W
* **M.2 slot power delivery:** up to 13 W

Below is a simplified block diagram of the power subsystem showing power distribution to the device’s internal loads.

![Power subsystem block diagram](/files/pics/flipper-one-power-subsystem-diagram.png "Power subsystem block diagram")

## How we measure power consumption

In the Flipper One prototypes, power monitoring is significantly more advanced than in the production version to support debugging and optimization of low-power modes.

The power monitoring uses five INA4230 chips, each providing four measurement channels. Every channel measures both voltage and current in its corresponding power path. In addition, a single-channel INA219 power monitor is connected to the main power rail to track the device’s total power consumption, while the battery protection board includes a fuel gauge for measuring charge and discharge currents.

![Power monitor in Linux](/files/pics/flipper-one-power-monitor-linux.png "Power monitor in Linux")

In production devices, only the fuel gauge and the power monitor on the main power rail will remain, with real-time power consumption displayed on the [power meter](Power-meter.md).
