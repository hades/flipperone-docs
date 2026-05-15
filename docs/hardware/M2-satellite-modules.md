---
title: Satellite modules
slug: hardware/m2-modules/satellite
docTags: 
createdAt: Sun Apr 26 2026 18:22:16 GMT+0000 (Coordinated Universal Time)
updatedAt: Tue Apr 28 2026 12:57:35 GMT+0000 (Coordinated Universal Time)
---

![](/files/pics/flipper-one-satellite-ntn-module.png)

## NTN modems

NTN (Non-Terrestrial Network) modems provide connectivity through satellites and high-altitude platforms, enabling data transmission outside terrestrial cellular coverage. NTN was standardized by 3GPP (3rd Generation Partnership Project) as part of 5G and LTE specifications. It uses the standard cellular stack, including SIM/eSIM authentication, roaming, and regular IP traffic.

The NTN market is currently transitioning from early pilot deployments to the first commercial rollouts. The technology is generally divided into two main categories:

* **NB-NTN** (Narrowband Non-Terrestrial Network) — a satellite extension of NB-IoT / LTE-M designed for low-bandwidth IoT applications such as telemetry, asset tracking, and remote sensors. This is currently the most mature part of the NTN technology. Commercial embedded NB-NTN modules are already available, for example [Quectel BG770A-SN](https://www.quectel.com/product/bg770a-sn-satellite-communication-module/). M.2 modules are not yet available, but are expected to appear within the next few years.

* **NR-NTN** (New Radio Non-Terrestrial Network) — full broadband satellite 5G. The technology is only beginning to enter early commercial deployment. Qualcomm [has announced the X105](https://www.qualcomm.com/news/releases/2026/03/qualcomm-announces-5g-advanced-leap-with-qualcomm-x105-5g-modem-) - a unified terrestrial + satellite modem supporting LTE/5G cellular networks, satellite NR-NTN and NB-NTN connectivity and includes GNSS receiver for positioning. Commercial availability of 5G + NTN modems, including M.2 modules, is expected within the next several years.

***

## GNSS receivers

GNSS (Global Navigation Satellite System) modules can be used for satellite-based positioning (GPS, GLONASS, Galileo, BeiDou), as well as for receiving precise timing signals from satellites when no Internet connection is available. 

Reliable GNSS reception typically requires an external antenna, which can be connected to Flipper One through the antenna connector integrated into the antenna rail.

Commercially available GNSS M.2 modules are offered by [ANavS](https://anavs.com/), [Antzer Tech](https://www.antzer-tech.com/), [Ardusimple](https://www.ardusimple.com), [Connect Tech](https://connecttech.com/), [DFI](https://www.dfi.com/), [LOCOSYS](https://www.locosystech.com/), and others.

GNSS receivers are also commonly integrated into combined cellular + GNSS solutions. M.2 modules of this type are available from [Quectel](https://www.quectel.com/), [Telit](https://www.telit.com/), [SIMCom](https://www.simcom.com/).

***

