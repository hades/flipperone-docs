---
title: DBDC
slug: testing/network/wifi/dbdc
---

Tests for **DBDC** — Dual-Band Dual-Concurrent operation: running two interfaces on two different bands at the same time (for example, an access point on 5 GHz while a client runs on 2.4 GHz).

## Tests

1. Bring up two interfaces on two different bands simultaneously.
2. Confirm both operate independently without interference.
3. Measure throughput on each band with `iperf3`.
4. Test combinations: AP + STA, AP + AP, STA + STA across band pairs.
