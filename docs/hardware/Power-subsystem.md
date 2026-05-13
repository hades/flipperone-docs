---
title: Power subsystem
slug: hardware/power-subsystem
docTags: 
createdAt: Sun Apr 26 2026 18:22:16 GMT+0000 (Coordinated Universal Time)
updatedAt: Tue Apr 28 2026 11:00:55 GMT+0000 (Coordinated Universal Time)
---

Specifications:
* 2-cell 23Wh Li-ion battery.
* Fast PD charging (up to x W).
* 8.4V internal power rail.
* Controllable DC/DCs and switches for flexible power management.
* Up to 15W on each USB host port.
* Up to 25W on GPIO expansion port.
* Up to 13W on M.2 slot.

![Power subsystem block diagram](/files/pics/flipper-one-power-subsystem-diagram.jpg "Power subsystem block diagram")

## How we measure power consumption

In the Flipper One prototypes, power monitoring is significantly more advanced than in the production version to support debugging and optimization of low-power modes.

The power monitoring uses five INA4230 chips, each providing four measurement channels. Every channel measures both voltage and current in its corresponding power path. In addition, a single-channel INA219 power monitor is connected to the main power rail to track the device’s total power consumption, while the battery protection board includes a fuel gauge for measuring charge and discharge currents.

![Power monitor in Linux](/files/pics/flipper-one-power-monitor-linux.png "Power monitor in Linux")

In production devices, only the fuel gauge and the power monitor on the main power rail will remain, with real-time power consumption displayed on the [power meter]().

## Low power mode

* Which components are powered and which are fully powered down.

* How all unnecessary subsystems — including the RK3576 — are completely powered off.

***Simplified diagram***

Estimated power consumption. Estimated battery life in this mode.

## Deep sleep mode

* Which components are powered and which are fully powered down.

* How the RTC is powered in this mode.

***Simplified diagram***

Estimated power consumption. Estimated battery life in this mode.

