---
title: About Docs
slug: resources/docs
docTags: 
createdAt: Tue Apr 07 2026 18:56:12 GMT+0000 (Coordinated Universal Time)
updatedAt: Wed Apr 08 2026 12:23:54 GMT+0000 (Coordinated Universal Time)
---

![TODO: replace with a proper splash image](files/pics/TODO-about-docs-splash.jpg)

This page explains how the Docs sub-project works — how the Developer Portal is structured, how source files are stored and published, and how you can contribute.

The Docs sub-project covers all documentation for Flipper One: this wiki, technical specs, datasheets, guides, and contribution instructions. Like all other Flipper One sub-projects, it is open for community contribution.

**On this page you'll find:**

- [How it works](./#how-it-works)
- [Repository structure](./#repository-structure)
- [Task tracker](./#task-tracker)
- [How to contribute](./#how-to-contribute)
---
# Docs sub-project structure

:::::LinkArray
::::LinkArrayItem{headerType="IMAGE" headerImage="files/pics/TODO-link-task-tracker.jpg"}

### [Task tracker](https://github.com/orgs/flipperdevices/projects/10)

Review the Docs team's tasks and comment on open tasks with suggestions.
:::

::::LinkArrayItem{headerType="IMAGE" headerImage="files/pics/TODO-link-github-repo.jpg"}

### [GitHub repository](https://github.com/flipperdevices/flipper-one-docs)

Source `.md` files from which this portal is generated. Fork and open a PR to contribute.
:::

::::LinkArrayItem{headerType="IMAGE" headerImage="files/pics/TODO-link-miro.jpg"}

### [Miro board](https://miro.com/app/board/uXjVJ6y839o=/)

Templates and diagrams for documentation graphics.
:::

::::LinkArrayItem{headerType="IMAGE" headerImage="files/pics/TODO-link-figma.jpg"}

### [Figma board](https://www.figma.com/design/HcwlmmIJlW4LoiQu4RtwwH/Flipper-One-%E2%80%94-Docs?node-id=0-1&p=f&t=aYrPCUA166BloJuV-0)

Design assets for documentation visuals.
:::
:::::

![TODO: replace with a block scheme of how the sub-project entities are interconnected](files/pics/TODO-docs-entities-diagram.jpg)

***

# How it works

The Flipper One Developer Portal is hosted on [Archbee](https://archbee.com), but all source files live in the [flipper-one-docs](https://github.com/flipperdevices/flipper-one-docs) GitHub repository. This is made possible by [Archbee's GitHub integration](https://www.archbee.com/docs/set-up-the-repository).

**In simple terms: GitHub stores all the text, images, and page hierarchy of the documentation. Archbee reads from GitHub and renders it into the live site at [docs.flipper.net/one](https://docs.flipper.net/one).**

Every time a pull request is merged into the `public-release` branch, Archbee automatically picks up the changes and rebuilds the live site.

***

# Repository structure

The repository contains the source files for the entire Developer Portal:

```none
flipperone-docs/
├── .archbee.json          # Archbee integration settings
├── README.md              # Repository overview
├── tools/
│   └── generate_open_tasks.py  # Generates Open-tasks.md from GitHub issues
└── docs/
    ├── Welcome.md         # Main page at docs.flipper.net/one
    ├── Summary.md         # Controls the sidebar hierarchy
    ├── How-to-join.md
    ├── Open-tasks.md      # Auto-generated — do not edit manually
    ├── files/
    │   └── pics/          # Images and other assets
    ├── general/
    ├── hardware/
    ├── mechanics/
    ├── mcu-firmware/
    ├── cpu-software/
    ├── user-interface/
    ├── testing/
    └── resources/
```

## Summary.md and sidebar hierarchy

The sidebar that readers see in the Developer Portal is controlled by `docs/Summary.md`. It defines sections, page names, file paths, and nesting levels. Ideally, nesting should not go deeper than two levels.

:::hint{style="warning"}
When adding a new page, always update `Summary.md` to include it. Without this, the page will not appear in the sidebar and readers won't be able to find it.
:::

:::hint{style="info"}
**Page names in the sidebar** come from the first H1 heading (`#`) in the `.md` file — not from the square brackets in `Summary.md`. Keep page titles short so they fit comfortably in the sidebar.
:::

***

# ✅ Task tracker

All Docs sub-project tasks are tracked in the GitHub project [Flipper One — Docs](https://github.com/orgs/flipperdevices/projects/10). There you can see what the team is working on and find open tasks where the community can help.

Tasks labeled **help wanted** are open for contribution. You're welcome to join discussions or submit changes — just read the contribution guide below first.

***

# How to contribute

Anyone can contribute to the Flipper One documentation via GitHub. You don't need write access to the repository — fork it, make your changes, and open a pull request.

::::WorkflowBlock
:::WorkflowBlockItem
Read the [Markup example](resources/Markup-example.md) page to learn the supported Markdown and Archbee syntax before writing or editing pages.
:::

:::WorkflowBlockItem
Go to the [flipper-one-docs](https://github.com/flipperdevices/flipper-one-docs) repository on GitHub and fork it to your account by clicking the **Fork** button in the upper-right corner.
:::

:::WorkflowBlockItem
In your forked repository, find the `.md` file you want to edit under `docs/`, or create a new one in the appropriate subfolder.
:::

:::WorkflowBlockItem
If you are **adding a new page**, also edit `docs/Summary.md` to register the new page in the sidebar hierarchy.
:::

:::WorkflowBlockItem
Commit your changes to a new branch in your fork.
:::

:::WorkflowBlockItem
Open a pull request to the `public-release` branch of the original repository. Add a clear title and description explaining what you changed.
:::
::::

:::hint{style="info"}
Once your pull request is merged, Archbee automatically picks up the changes and rebuilds the live site at [docs.flipper.net/one](https://docs.flipper.net/one).
:::
