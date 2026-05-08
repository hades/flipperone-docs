---
title: About MCU Firmware
slug: mcu-firmware/about
docTags: 
createdAt: Sun Apr 26 2026 18:22:16 GMT+0000 (Coordinated Universal Time)
updatedAt: Tue Apr 28 2026 13:35:13 GMT+0000 (Coordinated Universal Time)
---

This page explains the structure of the MCU Firmware sub-project, provides links to all the resources and explains how to contribute to the sub-project.

![MCU Firmware on Flipper One](/files/pics/mcu-flipper-one.png)

Flipper One has two processors. The low-power MCU (RP2350) manages power, the display, button and touchpad input, and Power Bank mode. The high-performance CPU runs Linux and handles user applications, networking, high-speed peripherals (USB3, PCIe), AI acceleration (NPU), and graphics output (HDMI, DisplayPort).

The MCU Firmware sub-project consists of:

- ✅ [Task tracker](https://github.com/orgs/flipperdevices/projects/8)
- 📁 [Firmware sources](https://github.com/flipperdevices/flipperone-mcu-firmware)
- 🏭 [Firmware update server](https://update.flipperzero.one/builds/flipper-one-mcu/dev/)

We'd love your feedback — look for tasks tagged **help wanted** in the task tracker, or contribute directly to the GitHub repository via pull requests.

![MCU firmware subproject structure](/files/pics/mcu-firmware-subproject-structure.jpg)

***

## ✅  Task tracker

All MCU Firmware team tasks are tracked in the GitHub project [Flipper One — MCU Firmware](https://github.com/orgs/flipperdevices/projects/8). There, you can see what the engineering team is working on and follow progress and discussions.

![MCU Firmware sub-project task tracker on GitHub](/files/pics/mcu-firmware-board-explainer.png "MCU Firmware sub-project task tracker on GitHub")

**Some tasks are open** to the community and marked with a **help wanted** label. You’re welcome to join the discussion on these tasks or submit your design proposals.

***

## 📁 Firmware sources

This sub-project includes a public [MCU Firmware](https://github.com/flipperdevices/flipperone-mcu-firmware) GitHub repository containing RP2350 firmware sources. You can [build the firmware](How-to-build-firmware.md) locally from sources. The resulting `.UF2` firmware file can be flashed to the MCU via USB by following the instructions in [Firmware update](Firmware-update.md).


Learn more about the firmware architecture on the [Firmware architecture](Architecture.md) page.

***

## 🔄 Firmware update server

Every merge into the `dev` branch, as well as every pull request in the firmware repository, triggers an automated build on the firmware build server and uploads `.UF2` files to the [Firmware Update Server](https://update.flipperzero.one/builds/flipper-one-mcu/dev/).

![MCU firmware update server](/files/pics/mcu-firmware-update-server.png "MCU firmware build server web interface")

***

## How to contribute

The MCU Firmware sub-project accepts contributions in two forms: **issues and comments** to report bugs, propose features, or share ideas on existing tasks, and **pull requests for code changes** to the MCU firmware sources. See the [Contribution guide](https://github.com/flipperdevices/flipperone-mcu-firmware/blob/dev/CONTRIBUTING.md) in the MCU Firmware repository for the full workflow, including issue handling, AI-assisted development rules, and PR conventions.

‎ 

### Comment on an open task or open a new issue

::::hint{type="info"}
**⚠️ Contributions only — no flooding**

To keep collaboration productive, please keep issues and comments on-topic — they are for contribution-related discussion only. If you have an idea or concern, first turn it into a concrete contribution and share it as a comment on an existing task or as a new issue. For general questions or discussions, you're always welcome to join the conversation on [social media](https://x.com/Flipper_RND) or [Discord](https://discord.com/invite/flipper)!
::::

![Contribute a comment on an open task](/files/pics/cpu-contribute-a-comment.jpg)

You can contribute by **commenting on an open task** to share an idea, suggestion, or design proposal, or by **opening a new issue** to report a bug or propose a feature. Open tasks that need the community's help are labeled **help wanted**.

#### Comment on an open task

If you have ideas on how to improve the MCU firmware, you can contribute by commenting on a **help wanted** task and attaching screenshots, videos, code snippets, or links:

:::::WorkflowBlock
:::WorkflowBlockItem
**Pick a task.** In the [MCU Firmware GitHub project](https://github.com/orgs/flipperdevices/projects/8), browse the open tasks and click the one labeled **help wanted** that you want to contribute to.
:::

::::WorkflowBlockItem
**Write your suggestion.** In the comments section, clearly describe your suggestion and, if helpful, attach a screenshot, video, code snippet, or link to a draft pull request.

![Good vs bad comment on an MCU Firmware task](/files/pics/cpu-good-vs-bad-comment.png)

**Attachment size limit:**

- Images: 10 MB
- Videos: 100 MB

::::

:::WorkflowBlockItem
**Click Comment** to submit.
:::
:::::

#### Open a new issue

If you find a bug or have a feature idea, search the [MCU Firmware issues](https://github.com/flipperdevices/flipperone-mcu-firmware/issues) first to confirm it hasn't already been reported, then open a new one.

::::WorkflowBlock
:::WorkflowBlockItem
**Search existing issues** in the [MCU Firmware repository](https://github.com/flipperdevices/flipperone-mcu-firmware/issues) to make sure your bug or proposal hasn't already been reported.
:::

:::WorkflowBlockItem
**Open a new issue.** Click **New issue** and provide enough detail to reproduce the bug or understand the proposal — steps, expected vs. actual behavior, hardware revision, firmware version, screenshots, or logs where relevant.
:::

:::WorkflowBlockItem
**Follow the discussion.** Watch the issue for notifications — we may ask clarifying questions or triage it into the [Project tracker](https://github.com/orgs/flipperdevices/projects/8).
:::
::::

We review all issues and comments carefully! We may ask additional questions in the thread, so please follow notifications from GitHub in your email.

‎ 

***

## Contribute to MCU Firmware via a pull request

![Contribute via a pull request](/files/pics/mcu-contribute-via-pr.jpg)

Contributing via pull requests allows anyone to propose changes to the MCU firmware sources. Once a PR is merged, your changes become part of the official MCU firmware builds.

::::WorkflowBlock
:::WorkflowBlockItem
**Fork and clone the** [MCU Firmware](https://github.com/flipperdevices/flipperone-mcu-firmware) **repository.**
:::

:::WorkflowBlockItem
**Make your changes** in the cloned repository.
:::

:::WorkflowBlockItem
**Build the firmware locally** to make sure the firmware still builds with your changes. Learn more on the [How to build firmware](How-to-build-firmware.md) page.
:::

:::WorkflowBlockItem
**Open a pull request** to the MCU Firmware repository.
:::
::::

We review all pull requests carefully! We may ask additional questions in the PR thread, so please follow notifications from GitHub in your email.
