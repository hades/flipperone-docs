---
title: About User Interface
slug: user-interface/about
docTags: 
createdAt: Sun Apr 26 2026 18:22:16 GMT+0000 (Coordinated Universal Time)
updatedAt: Tue Apr 28 2026 13:36:25 GMT+0000 (Coordinated Universal Time)
---

This page explains resources for developing graphic user interfaces for Flipper One:

 ### UI constaints:
- Pixel perfect UI elements to avoid sub pixels
- 256x144 px screen resolution
- 64 color shades of black
- Orange LCD backlight

The User Interface sub-project consists of:
- [Flipper One UI asset library](https://www.figma.com/design/U4k0qHkl9JdCu17MEtLFdI/Flipper-One-UI-Assets-library?node-id=0-1&t=zfmlKGksE4iBQ57H-1)
- [Flipper One UI — Main board](https://www.figma.com/design/PhlEqdtgjFfcizdVV0qNSR/Flipper-One-UI---Main-board?node-id=368-270&t=YcLCv1SFsc4TCTiV-1)
- [Task tracker](https://github.com/orgs/flipperdevices/projects/12)

***

### Flipper One UI asset library
Core Figma components for building UI
<img width="3584" height="1993" alt="" src="https://github.com/user-attachments/assets/1f6f3bf5-8707-49f5-816f-913ab0d0e775" />

[Asset library in Figma](https://www.figma.com/design/U4k0qHkl9JdCu17MEtLFdI/Flipper-One-UI-Assets-library?node-id=0-1&t=zfmlKGksE4iBQ57H-1) includes the following pages:
1. `UI - Prototype Assets` - comonents for mockups and testing hypotheses inside Figma. Oragne and black screen like colors to mimic Flipper One screen.
2. `UI - Dev ready` - components for building UI that will be shipped to the Flipper One screen

If you have a paid Figma plan, you can add these assets to your libraries. Check the [official Figma guide](https://help.figma.com/hc/en-us/articles/360041051154-Guide-to-libraries-in-Figma).

<img width="1156" height="472" alt="" src="https://github.com/user-attachments/assets/6f015f05-927b-4f50-a74a-1516996c18cc" />

***

### Flipper One UI — Main board
Interface development, design assets, illustrations, and source graphics files.

<img width="1640" height="557" alt="" src="https://github.com/user-attachments/assets/c5c9a9c7-2447-421a-9b4e-8eb994586c7a" />

[Main board](https://www.figma.com/design/PhlEqdtgjFfcizdVV0qNSR/Flipper-One-UI---Main-board?node-id=368-270&t=YcLCv1SFsc4TCTiV-1) includes the following pages:
1. `Documentation` — Illustrations and technical drawings
2. `UI OUT` — Development-ready, assembled UI layouts
3. `UI Live Preview` — Pre-assembled UI layouts for look and feel tests on device

***

# Fonts

Currently in UI use two fonts:
<img width="585" height="81" alt="" src="https://github.com/user-attachments/assets/096c2da7-e36b-42dc-8e7c-2cb8a04f8165" />
[Born2bSportyV2](https://github.com/olikraus/u8g2/blob/master/tools/font/ttf/Born2bSportyV2.ttf)

<img width="376" height="56" alt="" src="https://github.com/user-attachments/assets/e33fd268-b0e8-4034-8311-580d539458a1" />

[haxrcorp4089](https://github.com/olikraus/u8g2/blob/master/tools/font/ttf/haxrcorp4089.ttf)

***

### Prototypes
Prototypes based on ProtoPie are deprecated and were used at the stage when we were not able to prototype directly on the Flipper One screen. But they are still accessible in the [flipperone-ui repository](https://github.com/flipperdevices/flipperone-ui).

***

# How to contibute

### Step 1
Finf the issue with `Help wanted` tag
<img width="700" height="212" alt="" src="https://github.com/user-attachments/assets/977619ef-6838-43f7-b1d8-8e6b5b348cbe" />

### Step 2
Using comonents from [Asset library](https://www.figma.com/design/U4k0qHkl9JdCu17MEtLFdI/Flipper-One-UI-Assets-library?node-id=0-1&t=zfmlKGksE4iBQ57H-1) as a base for designs. Feel free to duplicate [Main board](https://www.figma.com/design/PhlEqdtgjFfcizdVV0qNSR/Flipper-One-UI---Main-board?node-id=368-270&t=YcLCv1SFsc4TCTiV-1) to reuse ready screens.

**How to duplicate board:**

Select `Duplicate to your drafts` inside the dropdown menu next to the board name.

<img width="799" height="581" alt="" src="https://github.com/user-attachments/assets/5b09c48b-856e-4ec5-979d-f44324c57115" />

### Step 3
Allow anyone to **View** your board

<img width="1787" height="547" alt="image" src="https://github.com/user-attachments/assets/87baceb0-d9c0-4078-ac36-8cd3aace3705" />


### Step 4
Submit design to issue providing screenshot and link to the source file.
<img width="1850" height="662" alt="image" src="https://github.com/user-attachments/assets/9febf2c0-4e15-4fdb-adb2-bad8c6d137d7" />

