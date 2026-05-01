---
title: About Hardware
slug: hardware/about
docTags: 
createdAt: Sun Apr 26 2026 18:22:16 GMT+0000 (Coordinated Universal Time)
updatedAt: Tue Apr 28 2026 13:32:40 GMT+0000 (Coordinated Universal Time)
---

# Title

This page explains the structure of the Hardware sub-project, provides links to its resources, and outlines how to contribute to Flipper One's electrical hardware development.

![About Hardware](/files/pics/about-hardware-main.png)

The Hardware sub-project covers electrical hardware development: printed circuit boards (PCBs), antennas, schematics, and everything related to the electrical connections of chips, connectors, and processors. The Hardware team works closely with the Mechanics team to ensure the electronics are compatible with the enclosure.

The Hardware sub-project consists of:

- ✅ :Link[Task tracker]{href="https://github.com/orgs/flipperdevices/projects/9" newTab="true" hasDisabledNofollow="false"}
- ⚡ :Link[Schematics and PCB design on Altium 365]{href="https://flipper.365.altium.com/designs/folder-7D774A8C-512F-4F4E-8518-0403C2316421" newTab="true" hasDisabledNofollow="false"}
- 📁 :Link[GitHub repository]{href="https://github.com/flipperdevices/flipperone-hardware" newTab="true" hasDisabledNofollow="false"} — currently README only
- 📚 Docs: 🔌 **Hardware section** (you're here) and :Link[🧪 Testing section]{href="https://docs.flipper.net/one/testing/about" newTab="true" hasDisabledNofollow="false"}

We'd love your feedback — look for tasks tagged **help wanted** in the task tracker, share your ideas in the comments, or contribute directly to the docs.

![Hardware sub-project structure](/files/pics/hardware-sub-project-structure.jpg)

***

## ✅  Tasks tracker

All Hardware team tasks are tracked in the GitHub project :Link[Flipper One — Hardware]{href="https://github.com/orgs/flipperdevices/projects/9" newTab="true" hasDisabledNofollow="false"}. There, you can see what the engineering team is working on and follow progress and discussions.

![Hardware board explainer](/files/pics/hardware-board-explainer.png "How the Hardware task tracker is organized")

**Some tasks are open** to the community and marked with a **help wanted** label. You're welcome to join the discussion on these tasks or submit your design proposals — just make sure to read the :Link[Contribution guide]{href="https://docs.flipper.net/one/hardware/about#how-to-contribute" newTab="false" hasDisabledNofollow="true"} first.

***

## ⚡ Schematics and PCB design on Altium 365

Selected parts of Flipper One's electrical design — schematics, PCB layouts, and BOM — are hosted on :Link[Altium 365]{href="https://flipper.365.altium.com/designs/folder-7D774A8C-512F-4F4E-8518-0403C2316421" newTab="true" hasDisabledNofollow="false"}, the cloud collaboration platform for for circuit design. Altium 365 hosts the latest version of the shared design files; you can view them in your browser without installing any software.

![Altium 365 Web Viewer interface](/files/pics/altium-ui-general.png)

:::hint{type="info"}
Shared schematics and PCB layouts match the real product, allowing development of accessories, modules, and external hardware for Flipper One.
:::

***

### Altium 365 folder structure

Shared Flipper hardware projects live in the **Flipper Public Altium365 Space** workspace, organized into a folder hierarchy:

```none
Flipper Public Altium365 Space/
└── Projects/
    ├── Flipper One/                   # Flipper One hardware projects
    └── Flipper Zero/                  # Flipper Zero hardware projects
```

Open the **Flipper One** folder to access Flipper One hardware projects and click any project to open it in the Web Viewer.

![Altium 365 workspace folder view](/files/pics/altium-ui-projects.png "Flipper One folder")

Each project opens in the Web Viewer with five view tabs along the top — **SCH** (schematic), **PCB** (2D layout), **3D** (interactive 3D render), **Draftsman** (fabrication documentation), and **BOM** (Bill of Materials).

![Altium 365 open project — schematic view](/files/pics/altium-ui-view.png "Altium 365 open project — schematic view")

***

### How to view the design files

The Altium 365 Web Viewer gives interactive, read-only access to the project directly in your browser — no Altium Designer install required.

::::WorkflowBlock
:::WorkflowBlockItem
**Open the shared workspace.** Go to the :Link[Flipper Public Altium365 Space]{href="https://flipper.365.altium.com/designs/folder-7D774A8C-512F-4F4E-8518-0403C2316421" newTab="true" hasDisabledNofollow="false"}.
:::

:::WorkflowBlockItem
**Sign in with your Altium account.** You can also sign in with your Google account. If you don't have an Altium account, create one on the :Link[Altium website]{href="https://www.altium.com/" newTab="true" hasDisabledNofollow="false"} — it's free for viewing shared projects.

![Altium 365 sign-in](/files/pics/altium-ui-login.png "Altium 365 sign-in")
:::

:::WorkflowBlockItem
**Open a project.** In **Projects → Flipper One**, click the project you want to inspect (for example, `SDIO-JTAG_ADAPTER` or `Flipper_One_Debug_Probe_V1`).
:::

:::WorkflowBlockItem
**Switch between views.** Use the tabs at the top of the viewer to move between **SCH**, **PCB**, **3D**, **Draftsman**, and **BOM**.
:::

:::WorkflowBlockItem
**Inspect components and nets.** All views support pan and zoom, plus search and cross-probing — click a component on the schematic to highlight it on the PCB, or select a net to trace it across the design.
:::
::::

Available views in the Web Viewer:

- Schematic sheets
- 2D PCB layout
- 3D board
- Bill of Materials (BOM)
- Draftsman documents

***

### How to export the design files

The Web Viewer includes a download control whose available formats depend on the view you're in. From the schematic, PCB, or BOM views you can download a copy of the document for offline reference. For the exact list of supported export formats, see Altium's :Link[Web Viewer documentation]{href="https://www.altium.com/documentation/altium-365/viewers/web-viewer#downloading" newTab="true" hasDisabledNofollow="false"}.

![Altium 365 Web Viewer download control](/files/pics/altium-ui-download.png "Altium 365 Web Viewer download control")

***

## 📚 Docs

Hardware-related documentation lives across two sections of the Developer Portal:

- 🔌 **Hardware section** (you're here) — references for ports, modules, and subsystems: GPIO and M.2 port pinouts, power subsystem, Wi-Fi & Bluetooth, and the GPIO and M.2 modules supported by Flipper One.
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
**(Optional) Register the new page in&#x20;**:Link[archbee.json]{href="https://github.com/flipperdevices/flipperone-docs/blob/public-release/archbee.json" newTab="true"}**.** Place it in the sidebar hierarchy (no deeper than two levels) — see :Link[How archbee.json works]{href="https://docs.flipper.net/one/resources/about-docs#how-archbeejson-works" newTab="true"} for the syntax. It's okay to skip — we'll update the file after merging your PR.
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
