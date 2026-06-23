---
title: AP+STA SCC
slug: testing/network/wifi/ap-sta-scc
---

Tests for **STA+AP SCC** — Station + Access Point Single-Channel Concurrency: running client (STA) and hotspot (AP) modes at the same time on the **same band and same channel**.

## Tests

1. Bring up an access point and connect to an external access point as a client, both on the same channel.
2. Confirm both interfaces stay associated simultaneously.
3. Measure throughput on each interface with `iperf3`.
4. Repeat on each band (2.4 GHz, 5 GHz, 6 GHz).
