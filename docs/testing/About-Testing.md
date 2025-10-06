# About Testing

Since our goal is to make Flipper One a truly high-quality product, every feature of the device must be thoroughly tested. This section describes the testing procedures for each subsystem.

# Hardware verification 

At this stage, we need to verify whether each hardware component of Flipper One can perform its intended functions. The purpose is to confirm that the selected components meet our design requirements.

Each test should produce a clear **YES/NO** result, allowing us to decide whether a given component is suitable for production.

## General system
- **Cold boot time** — if remove all delays, what is the minimum boot speed we can achive? From cold start to complete boot in minimal system with all heavy services turned off? 


## CPU 
- **General CPU perfomance** — in a perfect conditions what score we can get in sbc-bench https://github.com/ThomasKaiser/sbc-bench in comparasion with Raspberry Pi

## USB
- **USB Device emulation** — can we emulate USB Ethernet, Mass storage, Serial? How stable is this? 

- **USB Host perfomance** — what is general perfomance of each USB host ports? Speed?

## Internal storage

- **UFS perfomance** — what average perfomance do we have? And what aiming to? 

## SD Card
- **General microSD Card perfomance** — what is the average SD card perfomance? 

## RAM 
- **General RAM perfomance** — what perfomance do we have in comparasion with others

## Power
- **Thermal throtling planner** — we want to control thermal throtling to aim into specific temperature of CPU using characteritstics of our cooling device https://docs.kernel.org/driver-api/thermal/power_allocator.html For example we want to lock max temperature to 60C, 70C and so on.

- **Stand-by power consumption** — what minimum power consumption we can get on runned system? Can we activate power save mode and lower the CPU freq? Our aim is 500-800mW in standby mode. 

- **Sleep mode** — how it works? What power consumption? How stable and fast sleep/wake up? 


## Ethernet 
- **Ethernet port speed** — max download/upload speed of each port one by one and both simultaniously. iperf3 statistics is enough. Do we support all 10/100/1000BASE-TX? How much CPU loaded on 1Gbit/s port utilization? 

- **LAN + WAN router** — 2 ethernet cables connected and NAT activated. What is routing perfomance? How this affects system load

- **Promiscious mode** — can we turn both ethernet ports into passive sniffers? 

- **Transparent bridge** — ethernet sniffer for MiTM analysis. Wiretap ethernet cable by insertion in the midle of cable and dump all traffic to console + by pcap mask + dump to disk. What speed we can get? 

- **Ethernet to USB Ethernet adapter** — connect physical ethernet to ETH1 port and make a transparent bridge to virtual USB Ethernet adapter. What max speed we can get in this setup? 

## WiFi 
- **WiFi AP/STA general perfomance**  — what perfomance on access point and client mode we can deliver. Can we be simultanious STA+AP? Can we use different bands (2,4GHz, 5GHz, 6GHz) as different PHY? 

- **PMKID capture** — is it works? 

- **Monitor mode** — is it works? On what channels? 

## Graphics 
- **Stable 4K 120Hz video OUT** — can we do stable 4K@120hz video out via both USB DisplayPort and HDMI (separately)? Reboot to switch video code is OK.  

- **HDMI CEC + sound** — does HDMI CEC works? Sound via HDMI? 

- **DisplayPort over USB Type-C** — is this works? With USB host? With charging? Connect 1 cable from monitor and run complete desktop. 

- **Hardware video decoding** — can we decode H264/H265 to watch movies in low power mode? What is the lower power consumption decoding h264 and displaying over HDMI? 

- **OpenGL perfomance** — what OpenGL perfomance do we have? For example in glmark2 compare to other boards. 

## Analog sound
- **Built-in speakers + microphone** — doest it works? How it looks like in a system? How to play and record audio? 

- **3,5 Jack** — can we do stereo out + mic input? 

## M.2 module
- **USB module** — We need reference 5G modem to check

- **PCIe module** — can we run sSDR over PCIe? 

