---
title: About Testing
slug: testing/about
docTags: 
createdAt: Sun Apr 26 2026 18:22:16 GMT+0000 (Coordinated Universal Time)
updatedAt: Tue Apr 28 2026 13:41:00 GMT+0000 (Coordinated Universal Time)
---

This page explains the structure of the Testing sub-project, links to the public test scripts, and describes how testing notes in this section should be used.

The Testing sub-project covers checks for RK3576-based boards used in Flipper One development. Its goal is to turn each device feature into a repeatable test with a clear result. Testing currently prioritizes hardware verification, but test notes and assets can also cover user-interface or sound checks when those areas need repeatable pass/fail criteria.

The Testing sub-project consists of:

- 📁 [Testing scripts](https://github.com/flipperdevices/flipperone-testing)
- ✅ [Task tracker](https://github.com/orgs/flipperdevices/projects/14)
- 📚 Testing docs, listed below

***

## 📁 Testing scripts

The public [flipperone-testing](https://github.com/flipperdevices/flipperone-testing) repository contains scripts and test assets for RK3576-based boards. It includes a shared test runner, module directories for major subsystems, and a `results/` directory layout for generated reports.

The implemented test area is:

- temperature monitoring

Planned areas include:

- Power consumption monitoring
- CPU stress tests and benchmarks
- GPU performance tests
- Network throughput tests
- Disk I/O benchmarks
- NPU performance tests

The repository also contains sound and UI test assets. Some modules are still placeholders, so treat it as work in progress.

***

## 📚 Testing docs

The Testing section describes what should be checked for each subsystem. These pages are meant to complement the scripts: the docs explain the test goal, setup, expected result, and known gaps, while the repository contains runnable scripts or assets when they are available.

Docs in this section follow the same order as the navigation:

- [General](General.md) - boot targets, test images, and common setup notes.
- [Power](Power.md) - power-management testing notes.
- [Graphics](Graphics.md) - GPU, HDMI, USB-C DisplayPort, and no-graphics boot target checks.
  - [Video Decoding](Video-decoding.md) - video-decoding checks under graphics testing.
- [Network](Network.md) - Wi-Fi and Bluetooth test scenarios.
- [Expansion modules (M.2)](M_2.md) - M.2 expansion-module test notes.
  - [Cellular Modems](Cellular-Modems.md) - cellular modem tests for M.2 modules.

***

## Hardware verification

At this stage, testing is mainly used to verify whether each hardware component performs its intended function. A good test should answer a narrow question, for example:

- Does the interface come up?
- Does the expected device appear in Linux?
- Does the measured value stay inside the expected range?
- Does the output match the selected boot target?

Each test should end with a clear **YES/NO** or pass/fail result. When a result is not clear, document the exact observation and mark the open question instead of hiding it behind a vague pass.

***

## Testbench

A testing note should include enough context for another contributor to repeat the check. When possible, record:

- board or device revision
- OS image or firmware build
- boot target
- connected modules, cables, monitors, and peripherals
- command or script used to run the test
- expected result
- actual result
- logs, screenshots, or generated reports

For script-based tests, use the [`flipperone-testing`](https://github.com/flipperdevices/flipperone-testing) repository as the public source for commands and report formats. For manual tests, keep the steps short and write down the exact condition that makes the test pass or fail.

***

## How to contribute

Testing contributions can be made through documentation updates, issue comments, or pull requests to the testing scripts repository.

:::hint{type="info"}
Before opening a docs pull request, read [How to contribute to documentation](/resources/about-docs#how-to-contribute).
:::

Good contributions include:

- adding missing setup details to a Testing docs page
- turning a manual checklist into a repeatable script
- attaching logs or reports from a supported RK3576-based board
- documenting a failed test with the exact image, command, hardware setup, and output
- improving a script without changing the result format unnecessarily

For runnable tests, fork [flipperone-testing](https://github.com/flipperdevices/flipperone-testing), make the script change there, and include the command and result files in the pull request description. For docs-only changes, follow the guide: [How to contribute to documentation](/resources/about-docs#how-to-contribute).
