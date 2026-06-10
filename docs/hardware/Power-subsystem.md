---
title: Power subsystem
slug: hardware/power-subsystem
docTags: 
createdAt: Sun Apr 26 2026 18:22:16 GMT+0000 (Coordinated Universal Time)
updatedAt: Tue Apr 28 2026 11:00:55 GMT+0000 (Coordinated Universal Time)
---

Flipper One is a portable device powered by an internal 2-cell Li-ion battery, which can be charged from a USB PD charger via the USB-C1 port. For flexible power management, the device employs controllable DC/DC converters and power switches managed by the Raspberry Pi RP2350 MCU.

## Specifications

:::hint{type="info"}

**Specifications are preliminary**

Some specifications listed here have not yet been fully validated and are subject to change. The device may also dynamically reduce performance and power capabilities under thermal limiting conditions.

:::

* **Battery capacity:** 22.9 Wh
* **USB-C1 input power:** USB PD up to 60 W
* **USB-C1 output power:** USB PD up to 36 W
* **USB-C2 output power:** up to 15 W
* **USB-A output power:** up to 15 W
* **GPIO port output power:** up to 25 W
* **M.2 port output power:** up to 13 W

Below is a simplified block diagram of the power subsystem showing power distribution to the device’s internal loads.

![Power subsystem block diagram](/files/pics/flipper-one-power-subsystem-diagram-v2.png "Power subsystem block diagram")

## How we measure power consumption

Flipper One includes a single-channel INA219 power monitor for measuring total system power consumption, as well as a BQ28Z620 battery fuel gauge for monitoring battery parameters. These measurements are displayed in real time on the [power meter](Power-meter.md). 

In **Flipper One prototype units**, the power monitoring system includes five additional INA4230 power monitors, providing 20-channel monitoring of voltage and current across Rockchip RK3576 power domains. This allows us to precisely measure power consumption across different parts of the RK3576.

All measured parameters are available as graphs in the Linux System Monitor, along with CPU load and temperature metrics.

![System monitor in Linux](/files/pics/flipper-one-power-monitor-linux.png "System monitor in Linux")

