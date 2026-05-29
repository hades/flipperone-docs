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
- 📚 [Manual test descriptions](./#manual-test-descriptions)
- 📁 [Automated test scripts](https://github.com/flipperdevices/flipperone-testing)

***

## ✅ Task tracker

The public [Testing project board](https://github.com/orgs/flipperdevices/projects/14) tracks open work for the Testing sub-project. Use it to find tasks, share progress, and see which areas already need help.

***

## 📚 Manual test descriptions

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

## 📁 Automated test scripts

The public [flipperone-testing](https://github.com/flipperdevices/flipperone-testing) repository contains scripts and test assets for RK3576-based boards. It includes a shared test runner, module directories for major subsystems, and a `results/` directory layout for generated reports.

To avoid duplicating a fast-changing list of implemented tests here, use the repository README as the current index of available automated checks, supported modules, and report formats.

***

## How to contribute

The Testing sub-project accepts contributions in three forms:
* **Comments on open tasks** with ideas, suggestions, and improvements;
* **Testing and reporting test results**; 
* **Pull requests for code changes** to automated testing scripts.

‎ 

### Comment on an open task

If you have an idea on how to improve a test, add missing setup details, or clarify expected results, comment on a relevant task in the [Testing project board](https://github.com/orgs/flipperdevices/projects/14).

::::hint{type="info"}
**⚠️ Contributions only — no flooding**

To keep collaboration productive, please keep comments on-topic. Open tasks are for contribution-related discussion only. If you have an idea or concern, first turn it into a concrete contribution and share it as a comment on a task. For general questions or discussions, you're always welcome to join the conversation on [social media](https://x.com/Flipper_RND) or [Discord](https://discord.com/invite/flipper)!
::::

![Contribute a comment on an open task](/files/pics/cpu-contribute-a-comment.jpg)

Open tasks that need the community's help are labeled **help wanted**. If you have an idea on how to improve a test, add missing setup details, or clarify expected results, you can contribute by commenting on the task and attaching screenshots, videos, code snippets, or links:

:::::WorkflowBlock
:::WorkflowBlockItem
**Pick a task.** In the [Testing GitHub project](https://github.com/orgs/flipperdevices/projects/14), browse the open tasks and click the one labeled **help wanted** that you want to contribute to.
:::

::::WorkflowBlockItem
**Write your suggestion.** In the comments section, clearly describe your suggestion and, if helpful, attach a screenshot, video, code snippet, or link to a draft pull request.

**Attachment size limit:**

- Images: 10 MB
- Videos: 100 MB
::::

:::WorkflowBlockItem
**Click Comment** to submit.
:::
:::::

We review all comments carefully! We may ask additional questions about your idea in the task thread, so please watch for GitHub notifications in your email.

‎

***

### Testing and reporting test results

Testing tasks are published in the [Task Tracker](https://github.com/orgs/flipperdevices/projects/14) with the help **wanted label**. Each testing task contains all essential testing requirements, as well as the expected format for submitting a test report.

Review the testing requirements and perform the test. Attach your test report as a comment in the task thread.

‎

***

### Contribute to flipperone-testing via a pull request

![Contribute via a pull request](/files/pics/testing-contribute-via-pr.jpg)

Contributing via pull requests allows anyone to propose changes to the automated test scripts or to the manual test descriptions.
Для изменений в manual test descriptions pull requests следует отправлять в репозиторий flipperone-docs] allows anyone to propose changes to the automated test scripts.

::::WorkflowBlock
:::WorkflowBlockItem
**Fork and clone the repository** ([flipperone-testing](https://github.com/flipperdevices/flipperone-testing) for changing testing scripts or [flipperone-docs](https://github.com/flipperdevices/flipperone-docs) for changing manual test descriptions)
:::

:::WorkflowBlockItem
**Edit scripts** in the cloned repository. Edit the repository README if needed.
:::

:::WorkflowBlockItem
**Open a pull request** to the repository.
:::
::::

We review all pull requests carefully! We may ask additional questions in the PR thread, so please watch for GitHub notifications in your email.
