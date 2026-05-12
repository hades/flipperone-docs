---
title: Power meter
slug: hardware/power-meter
docTags: 
createdAt: Sun Apr 26 2026 18:22:16 GMT+0000 (Coordinated Universal Time)
updatedAt: Tue Apr 28 2026 11:00:55 GMT+0000 (Coordinated Universal Time)
---

On the front right side of Flipper One, there is a power meter that enables real-time monitoring of the device’s power subsystem. It helps understand what is happening under the hood: whether the system is idle or active, charging or discharging, and how much power the connected USB power source is supplying.

The power meter consists of four separate sections:

* **Power consumption gauge.** Displays real-time overall device power consumption. This gauge shows in real time how much power the entire system uses, including the CPU and peripherals.

* **Power & charging status light.** The battery icon shows the device is powered on, and the lightning-in-battery icon shows it is charging.

* **Input power gauge.** This gauge shows the USB-C1 port input power. You can see if power is not enough to charge the battery or the device is using both power sources to operate without charging.

* **USB-C power in status light.** Lights up when a power source connects to USB-C1.

![Power meter sections](/files/pics/flipper-one-power-meter.jpg "Power meter sections")

## Power meter state examples

The following describes common use cases and how the power meter shows the device’s power state in each of them, depending on the power received via the USB-C1 port, the device’s power consumption, and the battery charging state.

### Case 1: Battery-only operation

The device is powered only by the battery and is discharging. The battery indicator is on, and the power consumption gauge blinks to show current draw from the battery.

![](/files/pics/flipper-one-power-meter-battery-only.jpg)

### Case 2: Battery charged, device powered via USB-C

A power source is connected to USB-C 1, but the battery is not charging because it is fully charged. The lightning icon inside the battery is off, indicating that charging is not in progress. Both gauges show the power drawn by the device from the USB-C1 port.

![](/files/pics/flipper-one-power-meter-usb-only.jpg)

### Case 3: Battery charging, device powered via USB-C

A power source is connected to USB-C 1, and its output is sufficient to both power the device and charge the battery. Both the battery and lightning icons are lit, indicating power is connected and the battery is charging. The power consumption gauge shows the device’s current power usage, while the input power gauge shows power drawn from the USB-C1 port.

![](/files/pics/flipper-one-power-meter-battery-charging.jpg)

### Case 4: Device powered by both USB-C and battery

A power source is connected to USB-C1, but its output is insufficient to charge the battery while the device is operating, so the lightning icon inside the battery is off and the battery icon is red. The power consumption gauge shows higher power than the input power gauge.

![](/files/pics/flipper-one-power-meter-battery-not-charging.jpg)
