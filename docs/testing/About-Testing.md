---
title: About Testing
slug: testing/about
docTags: 
createdAt: Sun Apr 26 2026 18:22:16 GMT+0000 (Coordinated Universal Time)
updatedAt: Tue Apr 28 2026 13:41:00 GMT+0000 (Coordinated Universal Time)
---

This page explains the structure of the Testing sub-project, provides links to public testing resources, and describes how to contribute to the sub-project.

The Testing sub-project covers checks for RK3576-based boards used in Flipper One development. Its goal is to turn each device feature into a repeatable test with a clear result. Testing currently prioritizes hardware verification, but test notes and assets can also cover user-interface or sound checks when those areas need repeatable pass/fail criteria.

The Testing sub-project consists of:

- ✅ [Task tracker](https://github.com/orgs/flipperdevices/projects/14)
- 📚 [Descriptions for manual tests](./#descriptions-for-manual-tests)
- 📁 [Scripts for automated tests](https://github.com/flipperdevices/flipperone-testing)

***

## ✅ Task tracker

The public [Testing project board](https://github.com/orgs/flipperdevices/projects/14) tracks open work for the Testing sub-project. There, you can see what the team is working on, follow progress, and find tasks that need community help.

**Some tasks are open** to the community and marked with a **help wanted** label. You’re welcome to join the discussion on these tasks or submit test results when a task asks for them.

***

## 📚 Descriptions for manual tests

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

## 📁 Scripts for automated tests

The public [flipperone-testing](https://github.com/flipperdevices/flipperone-testing) repository contains scripts and test assets for RK3576-based boards. It includes a shared test runner, module directories for major subsystems, and a `results/` directory layout for generated reports.

To avoid duplicating a fast-changing list of implemented tests here, use the repository [README](https://github.com/flipperdevices/flipperone-testing/blob/dev/README.md) as the current index of available automated checks, supported modules, and report formats.

***

## How to contribute

The Testing sub-project accepts contributions in three forms: **comments on open tasks**, **new issues**, and **pull requests for code changes** to the automated testing scripts.

### Comment on an open task

::::hint{type="info"}
**⚠️ Contributions only — no flooding**

To keep collaboration productive, please keep issues and comments on-topic — they are for contribution-related discussion only. If you have an idea or concern, first turn it into a concrete contribution and share it as a comment on an existing task or as a new issue. For general questions or discussions, you're always welcome to join the conversation on [social media](https://x.com/Flipper_RND) or [Discord](https://discord.com/invite/flipper)!
::::

![Contribute a comment on an open task](/files/pics/cpu-contribute-a-comment.jpg)

If you have an idea on how to improve a test, add missing setup details, clarify expected results, or share a test report, comment on a **help wanted** task in the [Testing project board](https://github.com/orgs/flipperdevices/projects/14).

:::::WorkflowBlock
:::WorkflowBlockItem
**Pick a task.** In the [Testing GitHub project](https://github.com/orgs/flipperdevices/projects/14), browse the open tasks and click the one labeled **help wanted** that you want to contribute to.
:::

::::WorkflowBlockItem
**Write your suggestion or report.** In the comments section, clearly describe your contribution and, if helpful, attach screenshots, videos, code snippets, logs, result files, or links to a draft pull request.

**Attachment size limit:**

- Images: 10 MB
- Videos: 100 MB
::::

:::WorkflowBlockItem
**Click Comment** to submit.
:::
:::::

We review all comments carefully! We may ask additional questions about your idea in the task thread, so please watch for GitHub notifications in your email.

***

### Open a new issue

If you find a testing bug, missing automated check, or repeatable test idea that does not already have an open task, search the [flipperone-testing issues](https://github.com/flipperdevices/flipperone-testing/issues) first to confirm it has not already been reported, then open a new issue.

::::WorkflowBlock
:::WorkflowBlockItem
**Search existing issues** in the [flipperone-testing repository](https://github.com/flipperdevices/flipperone-testing/issues) to make sure your bug or proposal has not already been reported.
:::

:::WorkflowBlockItem
**Open a new issue.** Click **New issue** and provide enough detail to reproduce the problem or understand the proposal — board revision, OS image or firmware build, command, expected result, actual result, screenshots, logs, or generated reports where relevant.
:::

:::WorkflowBlockItem
**Follow the discussion.** Watch the issue for notifications — we may ask clarifying questions.
:::
::::

***

### Contribute to flipperone-testing via a pull request

![Contribute via a pull request](/files/pics/testing-contribute-via-pr.jpg)

Contributing via pull requests allows anyone to propose changes to the automated test scripts in the public [flipperone-testing](https://github.com/flipperdevices/flipperone-testing) repository.

::::WorkflowBlock
:::WorkflowBlockItem
**Fork and clone the** [flipperone-testing](https://github.com/flipperdevices/flipperone-testing) **repository.**
:::

:::WorkflowBlockItem
**Make your changes** in the cloned repository. Update the repository README or result format documentation if your script change needs it.
:::

:::WorkflowBlockItem
**Run the relevant test or script check** and save the command, result files, logs, or screenshots that show what changed.
:::

:::WorkflowBlockItem
**Open a pull request** to the flipperone-testing repository and include the command you ran plus the result files or logs in the pull request description.
:::
::::

We review all pull requests carefully! We may ask additional questions in the PR thread, so please watch for GitHub notifications in your email.
