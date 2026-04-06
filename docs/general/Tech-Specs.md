# Technical Specifications

This page describes the full technical specifications of the Flipper One. Since the device is under active development, specifications may change.

![Flipper One outline](files/pics/flipper_one_outline_no_screen.png "Flipper One")

## Main CPU — RK3576

<table isTableHeaderOn="false" columnWidths="220,441">
  <tr>
    <td>
      <p><strong>CPU</strong></p>
    </td>
    <td>
      <p>Rockchip RK3576</p>
    </td>
  </tr>
  <tr>
    <td>
      <p><strong>Cores</strong></p>
    </td>
    <td>
      <p>8 Cores up to 2.2 GHz<br><sub>(4x High-performance ARM Cortex-A72 + 4x Efficiency ARM Cortex-A53)</sub></p>
    </td>
  </tr>
  <tr>
    <td>
      <p><strong>L2 Cache</strong></p>
    </td>
    <td>
      <p>1 MB (Cortex-A72) + 512 KB (Cortex-A53)</p>
    </td>
  </tr>
  <tr>
    <td>
      <p><strong>GPU</strong></p>
    </td>
    <td>
      <p>ARM Mali G52 MC3 — OpenGL ES 1.1/2.0/3.2, OpenCL 2.1, Vulkan 1.2</p>
    </td>
  </tr>
  <tr>
    <td>
      <p><strong>NPU</strong></p>
    </td>
    <td>
      <p>6 TOPS @INT8 — supports int4/int8/int16/FP16/BF16/TF32</p>
    </td>
  </tr>
</table>

## Low-Power MCU — RP2350

<table isTableHeaderOn="false" columnWidths="220,441">
  <tr>
    <td>
      <p><strong>MCU</strong></p>
    </td>
    <td>
      <p>Raspberry Pi RP2350B</p>
    </td>
  </tr>
  <tr>
    <td>
      <p><strong>Cores</strong></p>
    </td>
    <td>
      <p>Dual ARM Cortex-M33 @ 150 MHz + Dual RISC-V Hazard3 @ 150 MHz</p>
    </td>
  </tr>
  <tr>
    <td>
      <p><strong>SRAM</strong></p>
    </td>
    <td>
      <p>520 KB</p>
    </td>
  </tr>
  <tr>
    <td>
      <p><strong>Flash</strong></p>
    </td>
    <td>
      <p>2 MB</p>
    </td>
  </tr>
</table>

## Memory and Storage

<table isTableHeaderOn="false" columnWidths="220,441">
  <tr>
    <td>
      <p><strong>RAM</strong></p>
    </td>
    <td>
      <p>8 GB LPDDR5</p>
    </td>
  </tr>
  <tr>
    <td>
      <p><strong>Internal Storage</strong></p>
    </td>
    <td>
      <p>64 GB UFS 2.0</p>
    </td>
  </tr>
  <tr>
    <td>
      <p><strong>MicroSD</strong></p>
    </td>
    <td>
      <p>MicroSD card slot (⚠️UHS-I SDR104???)</p>
    </td>
  </tr>
</table>

## Battery and Power

<table isTableHeaderOn="false" columnWidths="220,441">
  <tr>
    <td>
      <p><strong>Battery</strong></p>
    </td>
    <td>
      <p>Approximately 7000 mAh &#x26a0;&#xfe0f; NEEDS CLARIFICATION</p>
    </td>
  </tr>
  <tr>
    <td>
      <p><strong>Charger IC</strong></p>
    </td>
    <td>
      <p>TI BQ25792, up to 3.1 A</p>
    </td>
  </tr>
  <tr>
    <td>
      <p><strong>Fuel Gauge</strong></p>
    </td>
    <td>
      <p>TI BQ28Z610</p>
    </td>
  </tr>
  <tr>
    <td>
      <p><strong>Charging</strong></p>
    </td>
    <td>
      <p>USB-C Power Delivery up to 20V</p>
    </td>
  </tr>
</table>

## Monochrome LCD Display

<table isTableHeaderOn="false" columnWidths="220,441">
  <tr>
    <td>
      <p><strong>Resolution</strong></p>
    </td>
    <td>
      <p>256 x 144 pixels</p>
    </td>
  </tr>
  <tr>
    <td>
      <p><strong>Interface</strong></p>
    </td>
    <td>
      <p>SPI (driven by RP2350 MCU)</p>
    </td>
  </tr>
</table>

## Wi-Fi & Bluetooth

<table isTableHeaderOn="false" columnWidths="220,441">
  <tr>
    <td>
      <p><strong>Module</strong></p>
    </td>
    <td>
      <p>WXT2AM2101</p>
    </td>
  </tr>
  <tr>
    <td>
      <p><strong>Wi-Fi Chipset</strong></p>
    </td>
    <td>
      <p>MediaTek MT7921U</p>
    </td>
  </tr>
  <tr>
    <td>
      <p><strong>Wi-Fi Modes</strong></p>
    </td>
    <td>
      <p>WiFi 6 (802.11ax), Bands 2.4 GHz / 5 GHz / 6 GHz, 2x2 MIMO</p>
    </td>
  </tr>
  <tr>
    <td>
      <p><strong>Bluetooth</strong></p>
    </td>
    <td>
      <p>Bluetooth 5.2 (integrated in MT7921U)</p>
    </td>
  </tr>
</table>

## Gigabit Ethernet

<table isTableHeaderOn="false" columnWidths="220,441">
  <tr>
    <td>
      <p><strong>Ports</strong></p>
    </td>
    <td>
      <p>2x Ethernet (1 Gbit/s)</p>
    </td>
  </tr>
  <tr>
    <td>
      <p><strong>PHY IC</strong></p>
    </td>
    <td>
      <p>Realtek RTL8211F-CG</p>
    </td>
  </tr>
</table>

## Video Output

<table isTableHeaderOn="false" columnWidths="220,441">
  <tr>
    <td>
      <p><strong>HDMI</strong></p>
    </td>
    <td>
      <p>HDMI v2.1, full-size connector, CEC support, HDCP 2.x, up to 4K@120 Hz</p>
    </td>
  </tr>
  <tr>
    <td>
      <p><strong>DisplayPort over USB-C</strong></p>
    </td>
    <td>
      <p>DisplayPort v1.4 Alt Mode via USB-C1, up to 4K@120 Hz</p>
    </td>
  </tr>
</table>

## Audio

<table isTableHeaderOn="false" columnWidths="220,441">
  <tr>
    <td>
      <p><strong>Codec</strong></p>
    </td>
    <td>
      <p>Everest ES8327</p>
    </td>
  </tr>
  <tr>
    <td>
      <p><strong>Speaker</strong></p>
    </td>
    <td>
      <p>&#x26a0;&#xfe0f; NEEDS CLARIFICATION</p>
    </td>
  </tr>
  <tr>
    <td>
      <p><strong>3.5 Audio</strong></p>
    </td>
    <td>
      <p>3.5 mm Audio Jack, Stereo Out + Microphone Input (TRRS)</p>
    </td>
  </tr>
</table>

## Ports

![Flipper One ports — top](files/pics/flipper_one_ports_top.png "Flipper One ports — top")

![Flipper One ports — bottom](files/pics/flipper_one_ports_bottom.png "Flipper One ports — bottom")

<table isTableHeaderOn="false" columnWidths="220,441">
  <tr>
    <td>
      <p><strong>USB-C1</strong></p>
    </td>
    <td>
      <p>USB 3.1 + DisplayPort Alt Mode + USB Power Delivery charging</p>
    </td>
  </tr>
  <tr>
    <td>
      <p><strong>USB-C2</strong></p>
    </td>
    <td>
      <p>&#x26a0;&#xfe0f; NEEDS CLARIFICATION</p>
    </td>
  </tr>
  <tr>
    <td>
      <p><strong>USB-A</strong></p>
    </td>
    <td>
      <p>USB 3.0</p>
    </td>
  </tr>
  <tr>
    <td>
      <p><strong>HDMI</strong></p>
    </td>
    <td>
      <p>Full-size HDMI v2.1</p>
    </td>
  </tr>
  <tr>
    <td>
      <p><strong>Ethernet</strong></p>
    </td>
    <td>
      <p>2x RJ45 Gigabit Ethernet</p>
    </td>
  </tr>
  <tr>
    <td>
      <p><strong>3.5 Audio Out</strong></p>
    </td>
    <td>
      <p>3.5 mm Audio Jack</p>
    </td>
  </tr>
  <tr>
    <td>
      <p><strong>MicroSD</strong></p>
    </td>
    <td>
      <p>MicroSD card slot</p>
    </td>
  </tr>
  <tr>
    <td>
      <p><strong>SIM Card Slot</strong></p>
    </td>
    <td>
      <p>Nano SIM (4FF), passively connected to M.2 port</p>
    </td>
  </tr>
</table>

## M.2 Expansion Port

<table isTableHeaderOn="false" columnWidths="220,441">
  <tr>
    <td>
      <p><strong>M.2 Type</strong></p>
    </td>
    <td>
      <p>Key B (TODO: add sizes)</p>
    </td>
  </tr>
  <tr>
    <td>
      <p><strong>Interfaces</strong></p>
    </td>
    <td>
      <p>PCIe 2.1 / USB 3.0 / SATA3, SIM card</p>
    </td>
  </tr>
</table>

## GPIO Port
