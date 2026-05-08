---
title: Wi-Fi & Bluetooth
slug: hardware/wifi-bluetooth
docTags: 
createdAt: Sun Apr 26 2026 18:22:16 GMT+0000 (Coordinated Universal Time)
updatedAt: Tue Apr 28 2026 12:56:47 GMT+0000 (Coordinated Universal Time)
---

The Flipper One includes a built-in **Wi-Fi 6** (802.11ax, 2.4/5/6 GHz) and **Bluetooth 5.4** module — the Hui Zhou Gaoshengda WXT2AM2101, based on the MediaTek MT7921AUN chipset. This chip has a well-supported and stable Linux driver and provides the following capabilities:

* Monitor mode
* Packet capture
* Wireless traffic sniffing
* WPA/WPA2 handshake capture
* Client device enumeration
* Signal strength analysis
* Channel hopping
* Raw 802.11 frame monitoring
* Passive network reconnaissance
* Packet injection (limited)

In addition, users can expand connectivity by attaching an external Wi-Fi module via USB or installing one through the M.2 slot using an M.2 E-key to M.2 B-key adapter.

## Wi-Fi/BT module and antennas placement

The WXT2AM2101 module is soldered on the Main board. It is located beneath the M.2 module and covered by an aluminum heatsink.

![WXT2AM2101 module on the Main board](/files/pics/flipper-one-wifi-module-on-main-pcb.jpg "WXT2AM2101 module on the Main board")

The antennas for the built-in Wi-Fi/BT module are located inside the Flipper Zero enclosure and connected to the module via coaxial cables.

The **Wi-Fi antenna** is located in the middle of the lower part of the device housing. It is a MIMO (Multiple Input Multiple Output) antenna system, consisting of two separate antenna elements mounted on a single PCB.

![Wi-Fi antenna placement](/files/pics/flipper-one-wifi-antenna.jpg "Wi-Fi antenna placement")

The **Bluetooth antenna** is located behind the top edge of the device housing, between the lanyard loop and the USB-A port.

![Bluetooth antenna placement](/files/pics/flipper-one-bluetooth-antenna.jpg "Bluetooth antenna placement")

## Wi-Fi/BT module schematics

The Wi-Fi/BT module is connected to the Rockchip RK3576 via USB 3.0 through a USB hub. 

![Wi-Fi/BT module schematics](/files/pics/flipper-one-wifi-module-schematics.png "Wi-Fi/BT module schematics")

### A trick for USB port sharing 

The number of internal USB interfaces in Flipper One is limited, so when integrating the Wi-Fi/BT module, we used an interesting workaround.

A typical USB 3.0 host port includes both USB 2.0 pins and additional differential pairs for USB 3.0 (3.2 gen1, 3.2 gen2, etc). This design ensures backward compatibility, allowing USB 2.0 devices to operate through USB 3.0 ports. However, not all USB devices utilize both interfaces simultaneously.

Since the MT7921AUN chipset can operate **over the USB 3.0 differential pairs only**, we repurposed the USB 2.0 pins of the same port to provide a separate USB connection via the GPIO expansion connector.

### CPU wake-up via Wi-Fi/BT

The **WGPIO0** and **WGPIO1** pins of the WXT2AM2101 module are connected to two GPIO pins on the RK3576 and are used to wake the RK3576 in response to Wi-Fi and Bluetooth events.

### Module power management

The DC-DC converter powering the WXT2AM2101 module can be software-controlled via the `WIFI_HUB_PWR_EN` signal, which is managed by the MCU through a GPIO expander. The CPU can also instruct the MCU to turn the module’s power on or off via the [MCU↔CPU interconnect interface](../mcu-firmware/MCU-CPU-interconnect.md).
