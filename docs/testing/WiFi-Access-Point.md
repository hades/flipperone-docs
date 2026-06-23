---
title: Access Point (AP)
slug: testing/network/wifi/access-point
---

Tests for single Wi-Fi access point mode — the classic hotspot/router role, where Flipper One broadcasts a network that clients connect to. Coverage spans every band, channel, output power level, and encryption mode.

## Tests

1. Configure an access point on each band (2.4 GHz, 5 GHz, 6 GHz).
2. Bring up an AP on every channel within each band and confirm clients can associate.
3. Measure throughput with `iperf3` on each band and channel.
4. Sweep TX output power levels and confirm the configured power is applied.
5. Repeat across encryption modes (Open, WPA2, WPA3) and confirm each negotiates correctly.
