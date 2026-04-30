---
title: About Hardware
slug: hardware/about
docTags: 
createdAt: Sun Apr 26 2026 18:22:16 GMT+0000 (Coordinated Universal Time)
updatedAt: Tue Apr 28 2026 13:32:40 GMT+0000 (Coordinated Universal Time)
---
# f

This page explains the structure of the Hardware sub-project, provides links to its resources, and outlines how to contribute to Flipper One's electrical hardware development.

TODO: Add hero image (e.g., Hardware sub-project structure diagram).

The Hardware sub-project covers electrical hardware development: printed circuit boards (PCBs), antennas, schematics, and everything related to the electrical connections of chips, connectors, and processors. The Hardware team works closely with the Mechanics team to ensure the electronics are compatible with the enclosure.

The Hardware sub-project consists of:

- ✅ :Link[Task tracker]{href="https://github.com/orgs/flipperdevices/projects/9" newTab="true" hasDisabledNofollow="false"}
- ⚡ :Link[Schematics and PCB design on Altium 365]{href="TODO" newTab="true" hasDisabledNofollow="false"}
- 📚 **Docs**: this 🔌 **Hardware section** and :Link[🧪 Testing section]{href="https://docs.flipper.net/one/testing/about" newTab="true" hasDisabledNofollow="false"}

We'd love your feedback — look for tasks tagged **help wanted** in the task tracker, share your ideas in the comments, or contribute directly to the docs.

![Hardware sub-project structure](/files/pics/hardware-sub-project-structure.jpg)

***

## ✅  Tasks tracker

All Hardware team tasks are tracked in the GitHub project :Link[Flipper One — Hardware]{href="https://github.com/orgs/flipperdevices/projects/9" newTab="true" hasDisabledNofollow="false"}. There, you can see what the engineering team is working on and follow progress and discussions.

![Hardware board explainer](/files/pics/hardware-board-explainer.png "How the Hardware task tracker is organized")

**Some tasks are open** to the community and marked with a **help wanted** label. You're welcome to join the discussion on these tasks or submit your design proposals — just make sure to read the :Link[Contribution guide]{href="https://docs.flipper.net/one/hardware/about#how-to-contribute" newTab="false" hasDisabledNofollow="true"} first.

***

## ⚡ Schematics and PCB design on Altium 365

Selected parts of Flipper One's electrical design — schematics, PCB layouts, and BOM — are hosted on :Link[Altium 365]{href="TODO" newTab="true" hasDisabledNofollow="false"}, the cloud collaboration platform for Altium, the industry-standard EDA tool for circuit design. Altium 365 hosts the latest version of the shared design files; you can view them in your browser without installing any software.

TODO: Add a brief description of what's accessible (which boards, antennas, etc.) and a hero image or screenshot of the Altium 365 project.

:::hint{type="info"}
Shared schematics and PCB layouts match the real product, allowing development of accessories, modules, and external hardware for Flipper One.
:::

***

### How to view the design files

TODO: Document the steps for opening the Altium 365 project in a browser, navigating schematics, and inspecting the PCB.

***

### How to export the design files

TODO: Document supported export formats (PDF, Gerber, STEP, BOM, etc.) and the export workflow.

***

## 📚 Docs

Hardware-related documentation lives across two sections of the Developer Portal:

- 🔌 **Hardware section** (you are here) — references for ports, modules, and subsystems: GPIO and M.2 port pinouts, power subsystem, Wi-Fi & Bluetooth, and the GPIO and M.2 modules supported by Flipper One.
- :Link[🧪 Testing section]{href="https://docs.flipper.net/one/testing/about" newTab="true" hasDisabledNofollow="false"} — hardware verification procedures for each subsystem (power, graphics, network, M.2, video decoding) so we can confirm components meet design requirements before production.

The :Link[Tech specs]{href="https://docs.flipper.net/one/general/tech-specs" newTab="true" hasDisabledNofollow="false"} page consolidates the full hardware specifications in one place, including controls, ports, dimensions, and pinouts.

***

## How to contribute

:::hint{type="info"}
To view the schematics and PCB design, you need an Altium 365 account. Create one on the :Link[Altium website]{href="https://www.altium.com/" newTab="true" hasDisabledNofollow="false"}.
:::

The Hardware sub-project accepts contributions in two forms: **comments on open tasks** for ideas, suggestions, and improvements, and **edits to the docs** for documenting hardware experiments, findings, or external module designs.

***

### Suggest your change as a comment on an open task

::::hint{type="info"}
**⚠️ Contributions only — no flooding**

To keep collaboration productive, please keep comments on-topic. Open tasks are for contribution-related discussion only. If you have an idea or concern, first turn it into a concrete contribution and share it as a comment on a task. For general questions or discussions, you're always welcome to join the conversation on :Link[social media]{href="https://x.com/Flipper_RND" newTab="true" hasDisabledNofollow="false"} or :Link[Discord]{href="https://discord.com/invite/flipper" newTab="true" hasDisabledNofollow="false"}!

::::

![Contribute a comment on an open task](/files/pics/contribute-a-comment.jpg)

Open tasks that need the community's help are labeled **help wanted**. If you have ideas on how to improve the design, you can contribute by commenting on the task and attaching screenshots, schematics, or links:

:::::WorkflowBlock
:::WorkflowBlockItem
**Pick a task.** In the :Link[Hardware GitHub project]{href="https://github.com/orgs/flipperdevices/projects/9" newTab="true" hasDisabledNofollow="false"}, browse the open tasks and click the one labeled **help wanted** that you want to contribute to.
:::

::::WorkflowBlockItem
**Write your suggestion.** In the comments section, clearly describe your suggestion and attach a screenshot, schematic snippet, or a link to your design on Altium 365. Ensure your design is accessible for others to view.

![Good vs bad comment on a Hardware task](/files/pics/hardware-good-vs-bad-comment.png "Good vs bad comment on a Hardware task")

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

### Contribute to the docs

If you've spotted an error in the Hardware section, want to clarify something, or want to share your hardware experiments and findings, you're welcome to contribute by editing the docs. The fastest way to jump straight to a page's source is the **Edit on GitHub** button on the live site — it opens the page's `.md` file directly in the GitHub editor.

![Contribute to the Hardware docs](/files/pics/hardware-contribute-to-docs.jpg)

For a longer change, fork the repository, make your edits on a new branch, and open a pull request:

::::WorkflowBlock
:::WorkflowBlockItem
**Read the&#x20;**:Link[Markup example]{href="https://docs.flipper.net/one/resources/about-docs/markup-example" newTab="true"}**&#x20;page** to learn the supported Markdown and Archbee syntax.
:::

:::WorkflowBlockItem
**Fork the repository.** Go to :Link[flipperone-docs]{href="https://github.com/flipperdevices/flipperone-docs" newTab="true"} and click **Fork** in the upper-right corner. Your fork opens on the `dev` branch — our staging branch for contributions. All your work happens here.
:::

:::WorkflowBlockItem
**Edit or create your&#x20;**`.md`**&#x20;file.** In your fork, find the file you want to edit under `docs/hardware/`, or create a new one in the appropriate subfolder. Follow the syntax shown on the Markup example page — some Markdown features behave differently in Archbee.
:::

:::WorkflowBlockItem
**(Optional) Add images.** If your change includes images, diagrams, or screenshots, upload them to `docs/files/pics/` and reference them with a relative path:

```markdown
![Alt text](/files/pics/your-image.png "Caption")
```

Use descriptive, lowercase filenames with hyphens (e.g. `gpio-pinout.png`). Keep images under 1 MB.
:::

:::WorkflowBlockItem
**(Optional) Register the new page in&#x20;**:Link[archbee.json]{href="https://github.com/flipperdevices/flipperone-docs/blob/public-release/archbee.json" newTab="true"}**.** Place it in the sidebar hierarchy (no deeper than two levels) — see :Link[How archbee.json works]{href="https://docs.flipper.net/one/resources/about-docs#how-archbee-json-works" newTab="true"} for the syntax. It's okay to skip — we'll update the file after merging your PR.
:::

:::WorkflowBlockItem
**Create a branch and commit.** Name the branch `nickname/what-changed` (e.g. `john/gpio-module-experiment`). Keep commit messages concise — e.g. `Add: GPIO module pinout reference`.
:::

:::WorkflowBlockItem
**Open a pull request from your branch to the original repository.** The target is pre-selected to `dev` — leave it as is. Add a clear title and description, and ideally attach screenshots and a link to the related open task.

After review, we promote your changes from `dev` to `public-release`, which publishes them to the live site.
:::
::::

Once your pull request is merged into `dev` and later promoted to `public-release`, Archbee automatically picks up the changes and rebuilds the live site at :Link[docs.flipper.net/one]{href="https://docs.flipper.net/one" newTab="true"}.
