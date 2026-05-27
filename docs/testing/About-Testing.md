---
title: About Testing
slug: testing/about
docTags: 
createdAt: Sun Apr 26 2026 18:22:16 GMT+0000 (Coordinated Universal Time)
updatedAt: Tue Apr 28 2026 13:41:00 GMT+0000 (Coordinated Universal Time)
---

This page explains the structure of the Testing sub-project, links to the public task tracker and test scripts, and describes how testing notes in this section should be used.

The Testing sub-project covers checks for RK3576-based boards used in Flipper One development. Its goal is to turn each device feature into a repeatable test with a clear result. Testing currently prioritizes hardware verification, but test notes and assets can also cover user-interface or sound checks when those areas need repeatable pass/fail criteria.

The Testing sub-project consists of:

- ✅ [Task tracker](https://github.com/orgs/flipperdevices/projects/14)
- 📚 Descriptions for manual tests
- 📁 [Scripts for automated tests](https://github.com/flipperdevices/flipperone-testing)
- 🤝 How to contribute

***

## Task tracker

The public [Testing project board](https://github.com/orgs/flipperdevices/projects/14) tracks open work for the Testing sub-project. Use it to find tasks, share progress, and see which areas already need help.

***

## Descriptions for manual tests

The Testing docs explain what should be checked for each subsystem. These pages are meant to complement the scripts: the docs describe the test goal, setup, expected result, and known gaps, while the repository contains runnable scripts or assets when they are available.

Docs in this section follow the same order as the navigation:

- [General](General.md) - boot targets, test images, and common setup notes.
- [Power](Power.md) - power-management testing notes.
- [Graphics](Graphics.md) - GPU, HDMI, USB-C DisplayPort, and no-graphics boot target checks.
  - [Video Decoding](Video-decoding.md) - video-decoding checks under graphics testing.
- [Network](Network.md) - Wi-Fi and Bluetooth test scenarios.
- [Expansion modules (M.2)](M_2.md) - M.2 expansion-module test notes.
  - [Cellular Modems](Cellular-Modems.md) - cellular modem tests for M.2 modules.

### Hardware verification

At this stage, testing is mainly used to verify whether each hardware component performs its intended function. A good test should answer a narrow question, for example:

- Does the interface come up?
- Does the expected device appear in Linux?
- Does the measured value stay inside the expected range?
- Does the output match the selected boot target?

Each test should end with a clear **YES/NO** or pass/fail result. When a result is not clear, document the exact observation and mark the open question instead of hiding it behind a vague pass.

### Test bench

TODO: Describe publicly available test setup.

***

## Scripts for automated tests

The public [flipperone-testing](https://github.com/flipperdevices/flipperone-testing) repository contains scripts and test assets for RK3576-based boards. It includes a shared test runner, module directories for major subsystems, and a `results/` directory layout for generated reports.

To avoid duplicating a fast-changing list of implemented tests here, use the repository README as the current index of available automated checks, supported modules, and report formats.

***

## How to contribute

The Testing sub-project accepts contributions in three forms: **comments on open tasks** for ideas and improvements, **issues** for bugs or proposals that need their own thread, and **pull requests** for either testing-script changes or docs updates.

:::hint{type="info"}
Before opening a docs pull request, read [How to contribute to documentation](/resources/about-docs#how-to-contribute).
:::

### Comment on an open task

If you have an idea on how to improve a test, add missing setup details, or clarify expected results, comment on a relevant task in the [Testing project board](https://github.com/orgs/flipperdevices/projects/14).

### Open a new issue

If you find a bug in the testing scripts or a gap that does not already have a task, search the [flipperone-testing issues](https://github.com/flipperdevices/flipperone-testing/issues) first, then open a new issue with enough detail to reproduce the problem or understand the proposal.

### Contribute to flipperone-testing via a pull request

For runnable tests, fork [flipperone-testing](https://github.com/flipperdevices/flipperone-testing), make the script change there, and include the command and result files in the pull request description. For docs-only changes, follow the guide: [How to contribute to documentation](/resources/about-docs#how-to-contribute).
