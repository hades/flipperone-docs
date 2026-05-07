---
title: About Linux (CPU Software)
slug: cpu-software/about
docTags: 
createdAt: Sun Apr 26 2026 18:22:16 GMT+0000 (Coordinated Universal Time)
updatedAt: Tue Apr 28 2026 13:34:10 GMT+0000 (Coordinated Universal Time)
---

This page explains the structure of the Linux (CPU Software) sub-project, provides links to all the repositories, and explains how they are used to build Flipper One's official Linux operating system.

![About Linux (CPU Software)](/files/pics/about-cpu-main-image.png)

Flipper One has two chips: a high-performance CPU and a low-power MCU. The CPU (Rockchip RK3576) runs the Linux operating system. It executes user applications, controls all networking interfaces, and manages high-speed peripherals including USB3 and PCIe. It also integrates an NPU for AI acceleration and a GPU for graphics output via HDMI and DisplayPort.

The MCU handles power management, display output, button and touchpad event processing, and Power Bank mode.

The CPU Software sub-project consists of:

- ✅ [Task tracker](https://github.com/orgs/flipperdevices/projects/11)
- 🏭 [OS images build server](https://linux-images.flipp.dev/)
- 📁 GitHub repositories:
  - [Linux build scripts](https://github.com/flipperdevices/flipperone-linux-build-scripts)
  - [Rkbin](https://github.com/flipperdevices/rkbin)
  - [U-Boot](https://github.com/flipperdevices/u-boot)
  - [Linux kernel](https://github.com/flipperdevices/flipper-linux-kernel)
  - [rkloader](https://github.com/flipperdevices/rkloader) & [gofastboot](https://github.com/flipperdevices/gofastboot)

![CPU software subproject structure](/files/pics/cpu-software-subproject-structure.jpg)

We'd love your feedback — look for tasks tagged **help wanted** in the task tracker, or contribute directly to the GitHub repositories via pull requests.

***

## ✅ Task tracker

All Linux (CPU Software) team tasks are tracked in the GitHub project [Flipper One — Linux (CPU Software)](https://github.com/orgs/flipperdevices/projects/11/). There, you can see what the engineering team is working on and follow progress and discussions.

![Linux (CPU Software) task tracker](/files/pics/cpu-task-tracker.png "Linux (CPU Software) task tracker")

**Some tasks are open** to the community and marked with a **help wanted** label. You’re welcome to join the discussion on these tasks or submit your code suggestions — just make sure to read the [Contribution guide](#how-to-contribute) first.

***

## 🏭 OS images build server

Our official OS image build server automatically builds a new OS image whenever changes are made to any of the GitHub repositories included in the build process. You can monitor the build status in the [server’s web interface](https://linux-images.flipp.dev/).

![OS buildbot](/files/pics/os-buildbot.png)

Once the build succeeds, full-disk images for all supported RK3576-based boards listed under [supported boards](Supported-boards.md) are published on the [web server](https://dl-linux-images.flipp.dev/full-img/), where they can be downloaded.

![OS build list](/files/pics/os-build-list.png)

**See also:**

- [Build system](Build-system.md) — build system architecture and image build flow.
- [How to build a Linux image](How-to-build-linux-image.md) — building the OS image locally.
- [How to install a Linux image](How-to-install-linux-image.md) — installing a full-disk OS image on a development board.

***

## 📁 GitHub repositories

The Linux (CPU Software) sub-project includes several public GitHub repositories containing Linux OS components and flashing tools:

- [Linux build scripts](https://github.com/flipperdevices/flipperone-linux-build-scripts) — Linux OS image build scripts for supported RK3576-based boards. These scripts can be used to build the OS image locally and are also used by the official OS image build server to produce release images.
- [Rkbin](https://github.com/flipperdevices/rkbin) — Rockchip RK3576 binaries, including DDR trainer and internal storage access binaries in MaskROM mode.
- [U-Boot](https://github.com/flipperdevices/u-boot) — Mirror of the official U-Boot bootloader sources with RK3576-specific patches not in mainline yet.
- [Linux kernel](https://github.com/flipperdevices/flipper-linux-kernel) — Our fork of the latest mainline Linux kernel release with patches not in mainline yet.
- [rkloader](https://github.com/flipperdevices/rkloader) & [gofastboot](https://github.com/flipperdevices/gofastboot) — Go tools for flashing images to Rockchip devices via fastboot protocol.

***

## How to contribute

The Linux (CPU Software) sub-project accepts contributions in two forms: **comments on open tasks** for ideas, suggestions, and improvements, and **pull requests for code changes** to OS components such as the bootloader, kernels, build scripts, or flashing tools.

***

### Suggest your change as a comment on an open task

::::hint{type="info"}
**⚠️ Contributions only — no flooding**

To keep collaboration productive, please keep comments on-topic. Open tasks are for contribution-related discussion only. If you have an idea or concern, first turn it into a concrete contribution and share it as a comment on a task. For general questions or discussions, you're always welcome to join the conversation on [social media](https://x.com/Flipper_RND) or [Discord](https://discord.com/invite/flipper)!
::::

![Contribute a comment on an open task](/files/pics/cpu-contribute-a-comment.jpg)

Open tasks that need the community's help are labeled **help wanted**. If you have ideas on how to improve OS components, you can contribute by commenting on the task and attaching screenshots, videos, code snippets, or links:

:::::WorkflowBlock
:::WorkflowBlockItem
**Pick a task.** In the [Linux (CPU Software) GitHub project](https://github.com/orgs/flipperdevices/projects/11), browse the open tasks and click the one labeled **help wanted** that you want to contribute to.
:::

::::WorkflowBlockItem
**Write your suggestion.** In the comments section, clearly describe your suggestion and, if helpful, attach a screenshot, video, code snippet, or link to a draft pull request.

![Good vs bad comment on a CPU Software task](/files/pics/cpu-good-vs-bad-comment.png)

**Attachment size limit:**

- Images: 10 MB
- Videos: 100 MB
::::

:::WorkflowBlockItem
**Click Comment** to submit.
:::
:::::

We review all comments carefully! We may ask additional questions about your idea in the task thread, so please follow notifications from GitHub in your email.

***

## Contribute to OS components via a pull request

![Contribute via a pull request](/files/pics/cpu-contribute-via-pr.jpg)

Contributing via pull requests allows anyone to propose changes to the components of our Linux OS. You don't need a Flipper One to test — any [supported RK3576-based development board](Supported-boards.md) works. Once a PR is merged, your changes become part of the official OS builds.

::::WorkflowBlock
:::WorkflowBlockItem
**Clone the** [Linux build scripts](https://github.com/flipperdevices/flipperone-linux-build-scripts) **repository.** During the build process, these scripts also clone several other repositories — see the [Build system](Build-system.md) page for details on the architecture.
:::

:::WorkflowBlockItem
**Fork and clone the build-process repositories you want to modify.**
:::

:::WorkflowBlockItem
**Point the build scripts at your local clones** so they use your forks instead of pulling the remote sources.
:::

:::WorkflowBlockItem
**Make your changes** in the forked repositories.
:::

:::WorkflowBlockItem
**Build the OS image locally.** Learn more on the [How to build a Linux image](How-to-build-linux-image.md) page.
:::

:::WorkflowBlockItem
**Flash the image and test your changes** on an RK3576-based board — see [How to install a Linux image](How-to-install-linux-image.md) for the steps.
:::

:::WorkflowBlockItem
**Open pull requests to all repositories you modified.**
:::
::::

We review all pull requests carefully! We may ask additional questions in the PR thread, so please follow notifications from GitHub in your email.
