---
title: Preview and test the docs
slug: resources/about-docs/how-to-preview-archbee
docTags: 
---

This page explains how to preview changes and run checks locally while you work on your contribution to the Flipper One documentation.

## When to preview and test the docs

Flipper One documentation is built from markdown sources and hosted on Archbee.
Changes are published automatically after merging a pull request to the default branch (`public-release`).

Archbee CLI allows you to preview your changes locally on an almost-exact website copy while you write, update, or review the documentation.

## Install the Archbee CLI

The Archbee CLI is required to preview documentation locally and run validation commands.


::::WorkflowBlock
:::WorkflowBlockItem
Install dependencies

- [Node.js](https://nodejs.org/en/download) 
- [npm](https://docs.npmjs.com/cli/v11/configuring-npm/install)
:::

:::WorkflowBlockItem
Install Archbee CLI

```bash
npm install --global @archbee/cli
```
:::

:::WorkflowBlockItem
Verify installation

```bash
archbee --version
```
:::

::::

If the command prints a version number, the installation completed successfully.

Archbee CLI is in beta phase and receives frequent patches (see [known issues](#known-issues)), so remember to update it often:

```bash
archbee update
```

## Run a live-reload server

After installing the Archbee CLI, you can start a local preview server that automatically reloads when files change.

::::WorkflowBlock
:::WorkflowBlockItem
Run a live-reload server

```bash
archbee dev
```

This command starts a local development server and opens the preview URL in your default browser.
:::
:::WorkflowBlockItem
Edit and preview the docs

Preview server automatically rebuilds and reloads the browser when you edit markdown files and `archbee.json`.
:::

:::WorkflowBlockItem
Stop the preview server

To stop the preview server, press `Ctrl+C` in the terminal.
:::
::::

### Known issues

If you see that documentation content is rendered incorrectly, first of all, restart the preview server.
  
- (CLI v0.1.33) Preview server may not show some images from the repository.
- (CLI v0.1.33) Complex formatting, such as lists inside table cells, may disappear on preview server. If markup syntax is correct, it will render correctly on docs.flipper.net.
- (CLI v0.1.33) If a page's URL does not match the file path, links to this page result in 404 on preview server.
  If `archbee broken-links` shows no errors, the links will work correctly on docs.flipper.net.

## Check the documentation structure

Documentation structure is defined in the `archbee.json` configuration file.
It changes when you add, move, rename, or delete documentation pages.

Use the `archbee validate` command to find all kinds of structure errors in archbee.json:

- Incorrect file paths (renamed, removed, typos in the path).
- Files in the `./docs` directory that are missing from archbee.json.
- Missing or incorrect configuration values.

```bash
archbee validate
```
Example output of a successful validation:
```none
Validating documentation project...

  Config:      OK (archbee.json)
  Parsing:     OK

  Space: Flipper One Documentation
    Docs path:   OK (docs/)
    Navigation:  OK (49 docs, 9 categories)

Validation passed.
```

:::hint{type="info"}
This check runs automatically on each pull request and is required to merge it.
:::

## Check the documentation links

You can check that internal documentation links are valid.
The check verifies links between documentation pages and links to headings (anchors).

```bash
archbee broken-links
```

Example output of a successful check:
```none
Scanned 49 documents for broken links...

No broken links found. (71 internal links checked)
```

:::hint{type="info"}
This check runs automatically on each pull request and is required to merge it.

External links in the documentation and all links in the README.md are not checked. Remember to verify and update them manually.
:::
