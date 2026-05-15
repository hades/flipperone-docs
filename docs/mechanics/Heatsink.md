---
title: Heatsink
slug: mechanics/heatsink
docTags: 
createdAt: Sun Apr 26 2026 18:22:16 GMT+0000 (Coordinated Universal Time)
updatedAt: Tue Apr 28 2026 13:05:22 GMT+0000 (Coordinated Universal Time)
---

Inside Flipper One, several components generate a significant amount of heat. This heat cannot be trapped inside a plastic enclosure, otherwise some parts operating under sustained heavy load could reach high temperatures and gradually degrade over time.

The device also contains a Li-Ion battery, which should not be heated above 60 °C, as excessive heat accelerates battery degradation and negatively affects its lifespan and safety.

The main heat sources inside Flipper One are:

* **RK3576 SoC.** Up to **5.5 W** under maximum load (CPU + GPU + NPU simultaneously).
* **RK806S PMIC.** Up to around **2 W** at peak SoC load.
* **DDR5 RAM.** Up to **1.5 W** during memory-intensive operations.
* **BQ25798 battery charger.** Up to 1 W while fast-charging the battery.

!["Location of the main heat-generating chips on the Flipper One PCB"](/files/pics/flipper-one-hot-chips.png "Location of the main heat-generating chips on the Flipper One PCB")

In real-world use, reaching the maximum heat output is difficult. During heatsink testing, we use a synthetic workload designed to push the hardware to its thermal limits.

## Integrated aluminum heatsink

Flipper One dissipates heat from its hottest chips through a aluminum heatsink. In addition to thermal management, the heatsink also serves as a structural element, mechanically integrating with the enclosure and the main PCB.

!["Shape of the integrated aluminum heatsink in Flipper One (HW rev F0B0C1)"](/files/pics/flipper-one-heatsink.png "Shape of the integrated aluminum heatsink in Flipper One (HW rev F0B0C1)")

We cannot use the entire rear surface of the device enclosure for a heatsink because it must also accommodate a removable antenna rail and a back plate covering the cable routing to the antenna connectors and the M.2 module.

We cannot use the entire rear surface of the device enclosure for heatsink because it must also accommodate a removable antenna rail and a back plate, covering the cable routing to the antenna connectors, and a the M.2 module.

!["Rear surface of Flipper One with an integrated heatsink"](/files/pics/flipper-one-heatsink-in-body.png "Rear surface of Flipper One with an integrated heatsink")

Our preliminary simulations and real-world prototype testing show that this heatsink can keep the radiator temperature below 50 °C under realistic (non-synthetic) workloads with a thermal load of about 6 W.

At higher loads, the SoC will reduce CPU core frequencies, while the MCU will disable low-priority loads and notify the user via the display.

At higher loads or high ambient temperatures, the SoC will reduce CPU core frequencies, while the MCU will disable low-priority peripheral loads, limit charging power, and notify the user of these limits on the display.

---
