# Welcome

This is Welcome.md file


This is image from assets

![](files/pics/scam_cars.jpg)

Testing markdown syntax and how it's rendered in Archbee.

**Quick jump:**
- [Headings](#headings)
- [Text styles](#text-styles)
- [Links](#links)
- [Images](#images)
- [Videos & audio](#videos)
- [Lists](#lists)
- [Tables](#tables)
- [Code & syntax highlighting](#code--syntax-highlighting)
- [Quotes & callouts](#quotes--callouts)
- [Details / accordion](#details--accordion)
- [Math](#math)
- [Mermaid diagrams](#mermaid-diagrams)
- [Footnotes](#footnotes)
- [Rules, escapes, emoji](#rules-escapes-emoji)
- [Inline HTML test](#inline-html-test)

---

## Headings

# H1 Heading
## H2 Heading
### H3 Heading
#### H4 Heading

Paragraph under headings. Line breaks work with two spaces at end.  
This is a second line.

---

## Text styles

- Regular text 
- **bold**
- *italic*
- ***bold italic***
- ~~strikethrough~~
- `inline code` 
- $10^6$
- $H_2O$

Block of text with soft-wrap and hard-wrap differences.  
This line intentionally ends with two spaces to force a break.

---

## Links

- Inline link: [Archbee](https://archbee.com "Archbee site")
- Reference link: [GitHub][gh]
- Autolink: <https://example.com>
- Email: <mailto:hello@example.com>
- Anchor to a section: [Jump to Tables](#tables)
- Image-as-a-link: [![Badge demo](files/pics/Flipper_Mobile_App_add_widget.jpg)](https://shields.io)

[gh]: https://github.com "GitHub Home"

---

## Images

Markdown images with alt + title:

![Remote placeholder banner](https://placehold.co/800x180/png?text=Remote+Banner+800x180 "Remote Banner")

Relative image path (may 404 in some viewers):

![Local image](files/pics/Flipper_Mobile_App_add_widget.jpg "Local asset example")

Reference-style image:

![Ref image][ref-img]

HTML image with width control:

<img src="files/pics/Flipper_Mobile_App_add_widget.jpg" alt="HTML img" width="320" />

[ref-img]: https://placehold.co/640x200?text=Reference+Image

---

## Videos

**YouTube via linked thumbnail (common Markdown pattern):**

[![Watch the demo](https://img.youtube.com/vi/dQw4w9WgXcQ/hqdefault.jpg)](https://www.youtube.com/watch?v=dQw4w9WgXcQ)

---

## Lists

Unordered list:
- Item A
  - Nested A.1
    - Nested A.1.a
- Item B

Ordered list (start at 3):
3. Three
4. Four
5. Five

Mixed list:
- First
1. Second (numbered inside bullets)
- Third

---

## Tables

Basic table:

| Feature     | Supported | Notes              |
|-------------|:---------:|--------------------|
| Bold        | ✅        | `**text**`         |
| Italic      | ✅        | `*text*`           |
| Footnotes   | ✅        | See [below](#footnotes) |

Table with images & links:

| Avatar | User            | Link                                 |
|:------:|-----------------|--------------------------------------|
| ![](https://placehold.co/48x48) | **Alice**         | [Profile](https://example.com/alice) |
| ![](https://placehold.co/48x48) | **Bob**           | [Website](https://example.com)       |

---

## Code & syntax highlighting

Inline: `const hi = "world";`

Fenced (JavaScript):
```javascript
export function greet(name) {
  return `Hello, ${name}!`;
}
console.log(greet("Archbee"));
```

Fenced (Python):
```python
def fib(n):
    a, b = 0, 1
    seq = []
    while len(seq) < n:
        a, b = b, a + b
        seq.append(a)
    return seq

print(fib(10))
```

Fenced (Bash):
```bash
#!/usr/bin/env bash
set -euo pipefail
curl -I https://archbee.com
```

Diff block:
```diff
+ Added line
- Removed line
! Changed line (not standard, but some themes show this)
```

JSON block:
```json
{
  "name": "archbee-md-test",
  "private": true,
  "scripts": { "start": "node index.js" }
}
```

YAML block:
```yaml
name: archbee-md-test
on:
  push:
    branches: [ main ]
```

---

## Quotes & callouts

Regular blockquote:

> “Documentation is a love letter that you write to your future self.” — Damian Conway

GitHub/Docs-style admonitions (blockquote + label):

> [!NOTE]
> This is a note-style callout.

> [!TIP]
> Tips can sit under the same block.

> [!IMPORTANT]
> Important things deserve clear emphasis.

> [!WARNING]
> Warnings highlight risky steps.

> [!CAUTION]
> Use with care.

> 💡 **Tip:** Remember to save your work often.

:::hint{type="info"}
Archbee uses its own syntax for callouts.
:::

---

## Details / accordion

<details>
  <summary>Click to expand details</summary>
  
  Hidden content with **bold**, code `x = 42`, and a small list:
  - Point 1
  - Point 2
  
  Another paragraph.
</details>

---

## Math

Inline math: $E=mc^2$ and $\alpha + \beta = \gamma$.

Display math (used Archbee syntax):

```tex
\int_{-\infty}^{\infty} e^{-x^2} \, dx = \sqrt{\pi}
```

---

## Mermaid diagrams

Flowchart:

```mermaid
flowchart TD
  A[Start] --> B{Is it Markdown?}
  B -- Yes --> C[Render nicely]
  B -- No  --> D[Fallback]
  C --> E[Ship it]
  D --> E
```

Sequence diagram:

```mermaid
sequenceDiagram
  participant U as User
  participant S as System
  U->>S: Sends Markdown
  S-->>U: Renders page
```

---

## Footnotes

Here is a statement that needs a footnote.[^1] And another one.[^long]

[^1]: Short footnote text.
[^long]: This is a longer footnote with **formatting**, links like [example](https://example.com), and even `inline code`.

---

## Rules, escapes, emoji

Horizontal rules:

---
***
___

Escaped characters: \*literal asterisks\*, \_underscores\_, \`backticks\`, \#hash.

Emoji shortcodes: :rocket: :tada: :zap: :warning:

---
# Testing archbee syntax

::::WorkflowBlock
:::WorkflowBlockItem
Item 1

1. Subitem 1
2. Subitem 2
:::

:::WorkflowBlockItem
Item 2
:::

:::WorkflowBlockItem
Item 3
:::
::::

```tex
int_0^infty x^2 dx
```

:::hint{type="info"}
Test
:::

::::VerticalSplit{layout="middle"}
:::VerticalSplitItem
**Left side**

Text
:::

:::VerticalSplitItem
**Right side**

Text
:::
::::
