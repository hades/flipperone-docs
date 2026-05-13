---
title: Power subsystem
slug: hardware/power-subsystem
docTags: 
createdAt: Sun Apr 26 2026 18:22:16 GMT+0000 (Coordinated Universal Time)
updatedAt: Tue Apr 28 2026 11:00:55 GMT+0000 (Coordinated Universal Time)
---

## Specifications (preliminary)

* 2-cell 22.9 Wh Li-ion battery
* Fast USB PD charging (up to 60 W)
* 8.4V internal power rail
* Controllable DC/DC converters and switches for flexible power management
* Up to 15 W per USB host port
* Up to 25W on GPIO expansion port
* Up to 13W on M.2 slot

Below is a simplified block diagram of the power subsystem showing power distribution to the device’s internal loads.

![Power subsystem block diagram](/files/pics/flipper-one-power-subsystem-diagram.jpg "Power subsystem block diagram")

## How we measure power consumption

In the Flipper One prototypes, power monitoring is significantly more advanced than in the production version to support debugging and optimization of low-power modes.

The power monitoring uses five INA4230 chips, each providing four measurement channels. Every channel measures both voltage and current in its corresponding power path. In addition, a single-channel INA219 power monitor is connected to the main power rail to track the device’s total power consumption, while the battery protection board includes a fuel gauge for measuring charge and discharge currents.

![Power monitor in Linux](/files/pics/flipper-one-power-monitor-linux.png "Power monitor in Linux")

In production devices, only the fuel gauge and the power monitor on the main power rail will remain, with real-time power consumption displayed on the [power meter](Power-meter.md).
