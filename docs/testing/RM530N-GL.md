---
title: RM530N-GL
slug: testing/m2-modules/cellular-modems/rm530n-gl
---

# test

![Quectel RM530N-GL cellular modem](/files/pics/rm530n-gl-cellular-modem.jpg "Quectel RM530N-GL installed in Flipper One")

We got the Quectel RM530N-GL 5G modem working with Flipper One.

## Test results

- **Download speed:** 18.5 MB/s on a real file download.
- **Connection mode:** the link negotiated as LTE (4G), not 5G.
- **Power:** ran entirely from Flipper One's battery — no external power required.
- **Thermals:** the modem has no heatsink.

:::ExpandableHeading
### Full logs and configuration

Source: [pastebin.com/raw/VztvBw1D](https://pastebin.com/raw/VztvBw1D)

**Configure RM530N-GL modem with Vodafone**

```bash
# nmcli connection add type gsm ifname "*" con-name 5g apn wap.vodafone.co.uk
# nmcli connection modify 5g connection.autoconnect yes
# nmcli connection modify 5g ipv4.method auto
# nmcli connection modify 5g ipv6.method auto
# nmcli connection up 5g
```

**Debug connection**

```text
# nmcli device status
DEVICE    TYPE      STATE                   CONNECTION
cdc-wdm0  gsm       connected               5g
lo        loopback  connected (externally)  lo
end0      ethernet  unavailable             --
end1      ethernet  unavailable             --

# ip a
4: wwu1u4i4: <POINTOPOINT,MULTICAST,NOARP,UP,LOWER_UP> mtu 1500 qdisc pfifo_fast state UNKNOWN group default qlen 1000
    link/none
    inet 10.215.167.77/30 brd 10.215.167.79 scope global noprefixroute wwu1u4i4
       valid_lft forever preferred_lft forever


# Download Vodafone Test file
# wget http://212.183.159.230/1GB.zip -O /dev/null
/dev/null               37%[========================>          ] 381.43M  18.5MB/s    eta 65s


# List modems
$ mmcli -L
    /org/freedesktop/ModemManager1/Modem/0 [Quectel] RM530N-GL

# Get info about modem
$ mmcli -m 0
  -----------------------------------
  General  |                    path: /org/freedesktop/ModemManager1/Modem/0
           |               device id: 3d56e561127a3db4414de74bb15a4601aa64de98
  -----------------------------------
  Hardware |            manufacturer: Quectel
           |                   model: RM530N-GL
           |       firmware revision: RM530NGLAAR05A01M4G
           |          carrier config: UK-VoLTE-Vodafone
           | carrier config revision: 0A010426
           |            h/w revision: 20000
           |               supported: gsm-umts, lte, 5gnr
           |                 current: gsm-umts, lte, 5gnr
           |            equipment id: 867978050021665
  -----------------------------------
  System   |                  device: /sys/devices/platform/soc/23400000.usb/xhci-hcd.0.auto/usb2/2-1/2-1.4
           |                 physdev: /sys/devices/platform/soc/23400000.usb/xhci-hcd.0.auto/usb2/2-1/2-1.4
           |                 drivers: qmi_wwan, option
           |                  plugin: quectel
           |            primary port: cdc-wdm0
           |                   ports: cdc-wdm0 (qmi), ttyUSB0 (ignored), ttyUSB1 (gps),
           |                          ttyUSB2 (at), ttyUSB3 (at), wwu1u4i4 (net)
  -----------------------------------
  Status   |          unlock retries: sim-pin (3), sim-puk (10), sim-pin2 (3), sim-puk2 (10)
           |                   state: connected
           |             power state: on
           |             access tech: lte, 5gnr
           |          signal quality: 83% (cached)
  -----------------------------------
  Modes    |               supported: allowed: 3g; preferred: none
           |                          allowed: 4g; preferred: none
           |                          allowed: 3g, 4g; preferred: 4g
           |                          allowed: 3g, 4g; preferred: 3g
           |                          allowed: 5g; preferred: none
           |                          allowed: 4g, 5g; preferred: 5g
           |                          allowed: 4g, 5g; preferred: 4g
           |                          allowed: 3g, 5g; preferred: 5g
           |                          allowed: 3g, 5g; preferred: 3g
           |                          allowed: 3g, 4g, 5g; preferred: 5g
           |                          allowed: 3g, 4g, 5g; preferred: 4g
           |                          allowed: 3g, 4g, 5g; preferred: 3g
           |                 current: allowed: 3g, 4g, 5g; preferred: 5g
  -----------------------------------
  Bands    |               supported: utran-1, utran-4, utran-6, utran-5, utran-8, utran-2,
           |                          eutran-1, eutran-2, eutran-3, eutran-4, eutran-5, eutran-7, eutran-8,
           |                          eutran-12, eutran-13, eutran-14, eutran-17, eutran-18, eutran-19,
           |                          eutran-20, eutran-25, eutran-26, eutran-28, eutran-29, eutran-30,
           |                          eutran-32, eutran-34, eutran-38, eutran-39, eutran-40, eutran-41,
           |                          eutran-42, eutran-43, eutran-46, eutran-48, eutran-66, eutran-71,
           |                          utran-19, ngran-1, ngran-2, ngran-3, ngran-5, ngran-7, ngran-8,
           |                          ngran-12, ngran-13, ngran-14, ngran-18, ngran-20, ngran-25, ngran-26,
           |                          ngran-28, ngran-29, ngran-30, ngran-38, ngran-40, ngran-41, ngran-48,
           |                          ngran-66, ngran-70, ngran-71, ngran-75, ngran-76, ngran-77, ngran-78,
           |                          ngran-79, ngran-257, ngran-258, (null), ngran-260, ngran-261
           |                 current: utran-1, utran-4, utran-5, utran-8, utran-2, eutran-1,
           |                          eutran-2, eutran-3, eutran-4, eutran-5, eutran-7, eutran-8,
           |                          eutran-12, eutran-13, eutran-14, eutran-17, eutran-18, eutran-19,
           |                          eutran-20, eutran-25, eutran-26, eutran-28, eutran-29, eutran-30,
           |                          eutran-32, eutran-34, eutran-38, eutran-39, eutran-40, eutran-41,
           |                          eutran-42, eutran-43, eutran-46, eutran-48, eutran-66, eutran-71,
           |                          utran-19, ngran-1, ngran-2, ngran-3, ngran-5, ngran-7, ngran-8,
           |                          ngran-12, ngran-13, ngran-14, ngran-18, ngran-20, ngran-25, ngran-26,
           |                          ngran-28, ngran-29, ngran-30, ngran-38, ngran-40, ngran-41, ngran-48,
           |                          ngran-66, ngran-70, ngran-71, ngran-75, ngran-76, ngran-77, ngran-78,
           |                          ngran-79
  -----------------------------------
  IP       |               supported: ipv4, ipv6, ipv4v6
  -----------------------------------
  3GPP     |                    imei: 867978050021665
           |             operator id: 23415
           |           operator name: vodafone UK
           |            registration: home
           |    packet service state: attached
  -----------------------------------
  3GPP EPS |    ue mode of operation: csps-2
           |     initial bearer path: /org/freedesktop/ModemManager1/Bearer/0
           |      initial bearer apn: WAP.VODAFONE.CO.UK
           |  initial bearer ip type: ipv4v6
  -----------------------------------
  SIM      |        primary sim path: /org/freedesktop/ModemManager1/SIM/0
           |          sim slot paths: slot 1: /org/freedesktop/ModemManager1/SIM/0 (active)
           |                          slot 2: none
  -----------------------------------
  Bearer   |                   paths: /org/freedesktop/ModemManager1/Bearer/1

##########
# Get info about Bearer (wtf is Bearer)
# Bearier — an active data session between your modem and the mobile network
$ mmcli -b 1
  ------------------------------------
  General            |           path: /org/freedesktop/ModemManager1/Bearer/1
                     |           type: default
  ------------------------------------
  Status             |      connected: yes
                     |      suspended: no
                     |    multiplexed: no
                     |      interface: wwu1u4i4
                     |     ip timeout: 20
  ------------------------------------
  Properties         |            apn: wap.vodafone.co.uk
                     |        roaming: allowed
                     |        ip type: ipv4v6
  ------------------------------------
  IPv4 configuration |         method: static
                     |        address: 10.200.91.89
                     |         prefix: 30
                     |        gateway: 10.200.91.90
                     |            dns: 192.168.253.11, 192.168.253.11
                     |            mtu: 1500
  ------------------------------------
  Statistics         |     start date: 2026-03-19T18:50:39Z
                     |       duration: 570
                     |       bytes rx: 432453378
                     |       bytes tx: 898786
                     |       attempts: 1
                     | total-duration: 570
                     | total-bytes rx: 432453378
                     | total-bytes tx: 898786
```

**Signal info using qmicli**

```text
# apt install libqmi-utils

# qmicli -d /dev/cdc-wdm0 --device-open-proxy --nas-get-signal-strength
[/dev/cdc-wdm0] Successfully got signal strength
Current:
  Network 'lte': '-62 dBm'
RSSI:
  Network 'lte': '-62 dBm'
ECIO:
  Network 'lte': '-2.5 dBm'
IO: '-106 dBm'
SINR (8): '9.0 dB'
RSRQ:
  Network 'lte': '-11 dB'
SNR:
  Network 'lte': '7.2 dB'
RSRP:
  Network 'lte': '-93 dBm'

# sudo qmicli -d /dev/cdc-wdm0 --device-open-proxy --nas-get-serving-system
[/dev/cdc-wdm0] Successfully got serving system:
  Registration state: 'registered'
  CS: 'attached'
  PS: 'attached'
  Selected network: '3gpp'
  Radio interfaces: '1'
    [0]: 'lte'
  Roaming status: 'off'
  Data service capabilities: '1'
    [0]: 'lte'
  Current PLMN:
    MCC: '234'
    MNC: '15'
    Description: 'voda UK'
  Roaming indicators: '1'
    [0]: 'off' (lte)
  3GPP cell ID: '3697446'
  Detailed status:
    Status: 'available'
    Capability: 'cs-ps'
    HDR Status: 'none'
    HDR Hybrid: 'no'
    Forbidden: 'no'
  LTE tracking area code: '12299'
  Full operator code info:
    MCC: '234'
    MNC: '15'
    MNC with PCS digit: 'no'

# sudo qmicli -d /dev/cdc-wdm0 --device-open-proxy --nas-get-cell-location-info
[/dev/cdc-wdm0] Successfully got cell location info
Intrafrequency LTE Info
  UE In Idle: 'yes'
  PLMN: '23415'
  Tracking Area Code: '12299'
  Global Cell ID: '3697446'
  EUTRA Absolute RF Channel Number: '2850' (E-UTRA band 7: 2600)
  Serving Cell ID: '177'
  Cell Reselection Priority: '5'
  S Non Intra Search Threshold: '8'
  Serving Cell Low Threshold: '6'
  S Intra Search Threshold: '62'
  Cell [0]:
    Physical Cell ID: '177'
    RSRQ: '-11.6' dB
    RSRP: '-92.9' dBm
    RSSI: '-60.9' dBm
    Cell Selection RX Level: '31'
  Cell [1]:
    Physical Cell ID: '295'
    RSRQ: '-15.0' dB
    RSRP: '-97.8' dBm
    RSSI: '-73.6' dBm
    Cell Selection RX Level: '26'
Interfrequency LTE Info
  UE In Idle: 'yes'
  Frequency [0]:
    EUTRA Absolute RF Channel Number: '223' (E-UTRA band 1: 2100)
    Selection RX Level Low Threshold: '8'
    Cell Selection RX Level High Threshold: '8'
    Cell Reselection Priority: '4'
  Frequency [1]:
    EUTRA Absolute RF Channel Number: '247' (E-UTRA band 1: 2100)
    Selection RX Level Low Threshold: '8'
    Cell Selection RX Level High Threshold: '8'
    Cell Reselection Priority: '4'
  Frequency [2]:
    EUTRA Absolute RF Channel Number: '6300' (E-UTRA band 20: 800 DD)
    Selection RX Level Low Threshold: '8'
    Cell Selection RX Level High Threshold: '8'
    Cell Reselection Priority: '3'
LTE Info Neighboring GSM
  UE In Idle: 'yes'
LTE Info Neighboring WCDMA
  UE In Idle: 'yes'
LTE Timing Advance: 'unavailable'



$ nmcli device show
GENERAL.DEVICE:                         cdc-wdm0
GENERAL.TYPE:                           gsm
GENERAL.HWADDR:                         (unknown)
GENERAL.MTU:                            1500
GENERAL.STATE:                          100 (connected)
GENERAL.CONNECTION:                     5g
GENERAL.CON-PATH:                       /org/freedesktop/NetworkManager/ActiveConnection/2
IP4.ADDRESS[1]:                         10.200.91.89/30
IP4.GATEWAY:                            10.200.91.90
IP4.ROUTE[1]:                           dst = 10.200.91.88/30, nh = 0.0.0.0, mt = 700
IP4.ROUTE[2]:                           dst = 0.0.0.0/0, nh = 10.200.91.90, mt = 700
IP4.DNS[1]:                             192.168.253.11
IP6.GATEWAY:                            --



user@one-rev-f0b0c1-debian13-build-892-test-dp:~$ lsusb
Bus 001 Device 001: ID 1d6b:0002 Linux Foundation 2.0 root hub
Bus 001 Device 004: ID 3431:6241 Corechips USB2.0 HUB
Bus 002 Device 001: ID 1d6b:0003 Linux Foundation 3.0 root hub
Bus 002 Device 003: ID 3431:6341 Corechips USB3.0 HUB
Bus 002 Device 004: ID 2c7c:0801 Quectel Wireless Solutions Co., Ltd. RM530N-GL
user@one-rev-f0b0c1-debian13-build-892-test-dp:~$ lsusb -v -d 2c7c:0801

Bus 002 Device 004: ID 2c7c:0801 Quectel Wireless Solutions Co., Ltd. RM530N-GL
Couldn't open device, some information will be missing
Negotiated speed: SuperSpeed (5Gbps)
Device Descriptor:
  bLength                18
  bDescriptorType         1
  bcdUSB               3.20
  bDeviceClass            0 [unknown]
  bDeviceSubClass         0 [unknown]
  bDeviceProtocol         0
  bMaxPacketSize0         9
  idVendor           0x2c7c Quectel Wireless Solutions Co., Ltd.
  idProduct          0x0801 RM530N-GL
  bcdDevice            5.04
  iManufacturer           1 Quectel
  iProduct                2 RM530N-GL
  iSerial                 3 5335c4cc
  bNumConfigurations      1
  Configuration Descriptor:
    bLength                 9
    bDescriptorType         2
    wTotalLength       0x0125
    bNumInterfaces          5
    bConfigurationValue     1
    iConfiguration          4
    bmAttributes         0xa0
      (Bus Powered)
      Remote Wakeup
    MaxPower              896mA
    Interface Descriptor:
      bLength                 9
      bDescriptorType         4
      bInterfaceNumber        0
      bAlternateSetting       0
      bNumEndpoints           2
      bInterfaceClass       255 Vendor Specific Class
      bInterfaceSubClass    255 Vendor Specific Subclass
      bInterfaceProtocol     48
      iInterface              0
      Endpoint Descriptor:
        bLength                 7
        bDescriptorType         5
        bEndpointAddress     0x01  EP 1 OUT
        bmAttributes            2
          Transfer Type            Bulk
          Synch Type               None
          Usage Type               Data
        wMaxPacketSize     0x0400  1x 1024 bytes
        bInterval               0
        bMaxBurst               0
      Endpoint Descriptor:
        bLength                 7
        bDescriptorType         5
        bEndpointAddress     0x81  EP 1 IN
        bmAttributes            2
          Transfer Type            Bulk
          Synch Type               None
          Usage Type               Data
        wMaxPacketSize     0x0400  1x 1024 bytes
        bInterval               0
        bMaxBurst               0
    Interface Descriptor:
      bLength                 9
      bDescriptorType         4
      bInterfaceNumber        1
      bAlternateSetting       0
      bNumEndpoints           3
      bInterfaceClass       255 Vendor Specific Class
      bInterfaceSubClass      0 [unknown]
      bInterfaceProtocol     64
      iInterface              0
      ** UNRECOGNIZED:  05 24 00 10 01
      ** UNRECOGNIZED:  05 24 01 00 00
      ** UNRECOGNIZED:  04 24 02 02
      ** UNRECOGNIZED:  05 24 06 00 00
      Endpoint Descriptor:
        bLength                 7
        bDescriptorType         5
        bEndpointAddress     0x83  EP 3 IN
        bmAttributes            3
          Transfer Type            Interrupt
          Synch Type               None
          Usage Type               Data
        wMaxPacketSize     0x000a  1x 10 bytes
        bInterval               9
        bMaxBurst               0
      Endpoint Descriptor:
        bLength                 7
        bDescriptorType         5
        bEndpointAddress     0x82  EP 2 IN
        bmAttributes            2
          Transfer Type            Bulk
          Synch Type               None
          Usage Type               Data
        wMaxPacketSize     0x0400  1x 1024 bytes
        bInterval               0
        bMaxBurst               0
      Endpoint Descriptor:
        bLength                 7
        bDescriptorType         5
        bEndpointAddress     0x02  EP 2 OUT
        bmAttributes            2
          Transfer Type            Bulk
          Synch Type               None
          Usage Type               Data
        wMaxPacketSize     0x0400  1x 1024 bytes
        bInterval               0
        bMaxBurst               0
    Interface Descriptor:
      bLength                 9
      bDescriptorType         4
      bInterfaceNumber        2
      bAlternateSetting       0
      bNumEndpoints           3
      bInterfaceClass       255 Vendor Specific Class
      bInterfaceSubClass      0 [unknown]
      bInterfaceProtocol      0
      iInterface              0
      ** UNRECOGNIZED:  05 24 00 10 01
      ** UNRECOGNIZED:  05 24 01 00 00
      ** UNRECOGNIZED:  04 24 02 02
      ** UNRECOGNIZED:  05 24 06 00 00
      Endpoint Descriptor:
        bLength                 7
        bDescriptorType         5
        bEndpointAddress     0x85  EP 5 IN
        bmAttributes            3
          Transfer Type            Interrupt
          Synch Type               None
          Usage Type               Data
        wMaxPacketSize     0x000a  1x 10 bytes
        bInterval               9
        bMaxBurst               0
      Endpoint Descriptor:
        bLength                 7
        bDescriptorType         5
        bEndpointAddress     0x84  EP 4 IN
        bmAttributes            2
          Transfer Type            Bulk
          Synch Type               None
          Usage Type               Data
        wMaxPacketSize     0x0400  1x 1024 bytes
        bInterval               0
        bMaxBurst               0
      Endpoint Descriptor:
        bLength                 7
        bDescriptorType         5
        bEndpointAddress     0x03  EP 3 OUT
        bmAttributes            2
          Transfer Type            Bulk
          Synch Type               None
          Usage Type               Data
        wMaxPacketSize     0x0400  1x 1024 bytes
        bInterval               0
        bMaxBurst               0
    Interface Descriptor:
      bLength                 9
      bDescriptorType         4
      bInterfaceNumber        3
      bAlternateSetting       0
      bNumEndpoints           3
      bInterfaceClass       255 Vendor Specific Class
      bInterfaceSubClass      0 [unknown]
      bInterfaceProtocol      0
      iInterface              0
      ** UNRECOGNIZED:  05 24 00 10 01
      ** UNRECOGNIZED:  05 24 01 00 00
      ** UNRECOGNIZED:  04 24 02 02
      ** UNRECOGNIZED:  05 24 06 00 00
      Endpoint Descriptor:
        bLength                 7
        bDescriptorType         5
        bEndpointAddress     0x87  EP 7 IN
        bmAttributes            3
          Transfer Type            Interrupt
          Synch Type               None
          Usage Type               Data
        wMaxPacketSize     0x000a  1x 10 bytes
        bInterval               9
        bMaxBurst               0
      Endpoint Descriptor:
        bLength                 7
        bDescriptorType         5
        bEndpointAddress     0x86  EP 6 IN
        bmAttributes            2
          Transfer Type            Bulk
          Synch Type               None
          Usage Type               Data
        wMaxPacketSize     0x0400  1x 1024 bytes
        bInterval               0
        bMaxBurst               0
      Endpoint Descriptor:
        bLength                 7
        bDescriptorType         5
        bEndpointAddress     0x04  EP 4 OUT
        bmAttributes            2
          Transfer Type            Bulk
          Synch Type               None
          Usage Type               Data
        wMaxPacketSize     0x0400  1x 1024 bytes
        bInterval               0
        bMaxBurst               0
    Interface Descriptor:
      bLength                 9
      bDescriptorType         4
      bInterfaceNumber        4
      bAlternateSetting       0
      bNumEndpoints           3
      bInterfaceClass       255 Vendor Specific Class
      bInterfaceSubClass    255 Vendor Specific Subclass
      bInterfaceProtocol    255 Vendor Specific Protocol
      iInterface              7
      Endpoint Descriptor:
        bLength                 7
        bDescriptorType         5
        bEndpointAddress     0x88  EP 8 IN
        bmAttributes            3
          Transfer Type            Interrupt
          Synch Type               None
          Usage Type               Data
        wMaxPacketSize     0x0008  1x 8 bytes
        bInterval               9
        bMaxBurst               0
      Endpoint Descriptor:
        bLength                 7
        bDescriptorType         5
        bEndpointAddress     0x8e  EP 14 IN
        bmAttributes            2
          Transfer Type            Bulk
          Synch Type               None
          Usage Type               Data
        wMaxPacketSize     0x0400  1x 1024 bytes
        bInterval               0
        bMaxBurst               6
      Endpoint Descriptor:
        bLength                 7
        bDescriptorType         5
        bEndpointAddress     0x0f  EP 15 OUT
        bmAttributes            2
          Transfer Type            Bulk
          Synch Type               None
          Usage Type               Data
        wMaxPacketSize     0x0400  1x 1024 bytes
        bInterval               0
        bMaxBurst               2
user@one-rev-f0b0c1-debian13-build-892-test-dp:~$
```
:::