# About Hardware

This section covers the hardware development of Flipper One. It includes the electronics (PCB, schematics) and mechanical (case, assembly, buttons) design.

# Tech specs

TODO: Finalize naming, description and tech specs of controls, ports and interfaces

![](https://api.archbee.com/api/optimize/3StCFqarJkJQZV-7N79yY/L9hw7RZXHbTHmSLBySl3x_flipperone-controls-and-indicators-v003.png)

### Controls description

<table isTableHeaderOn="true" columnWidths="[object Object]">
  <tr>
    <td align="center">
      <p><strong>Control</strong></p>
    </td>
    <td align="left">
      <p><strong>Description</strong></p>
    </td>
  </tr>
  <tr>
    <td align="center">
      <p><strong>PTT Button</strong></p>
      <p>🎤︎︎</p>
    </td>
    <td align="left">
      <p>Push-to-talk button to activate microphone in walkie-talkie mode, for voice control and more. ⚠️ Since this is software button that can be overrided in application there is a big chance that this button will be used in many different usecases beyond the microphone. </p>
      <p>TODO: choose more general icon, not microphone</p>
    </td>
  </tr>
  <tr>
    <td align="center">
      <p><strong>Touchpad</strong></p>
    </td>
    <td align="left">
      <p>Touchpad for on-screen keyboard and menu navigation, content scrolling. Support horizontal and vertical scroll. Most likely will be always duplicate D-pad navigation and will be used for quick move in long lists.</p>
    </td>
  </tr>
  <tr>
    <td align="center">
      <p><strong>Escape button</strong></p>
      <p>╳</p>
    </td>
    <td align="left">
      <p>App defined button. Recommended UI actions: cancel, stop, pause, breake, abort, back, discard.</p>
      <p>TODO: finalize name? </p>
    </td>
  </tr>
  <tr>
    <td align="center" colSpan="1" rowSpan="1">
      <p><strong>View button</strong></p>
    </td>
    <td align="left" colSpan="1" rowSpan="1">
      <p>App defined button. Recommended UI actions: help, search, view, </p>
      <p>TODO: finalize icon and name </p>
    </td>
  </tr>
  <tr>
    <td align="center" colSpan="1" rowSpan="1">
      <p><strong>Power button</strong></p>
      <p>+ </p>
      <p><strong>Power LED</strong></p>
    </td>
    <td align="left" colSpan="1" rowSpan="1">
      <p>Control device modes, turn ON/OFF, boot OS. </p>
      <p>TODO: Full description needed. What long press do? LED colors and modes. Only soft button or connected to some hardware triggers?</p>
    </td>
  </tr>
  <tr>
    <td align="center" colSpan="1" rowSpan="1">
      <p><strong>Edit button</strong></p>
    </td>
    <td align="left" colSpan="1" rowSpan="1">
      <p>App defined button. Recommended UI actions: more, edit, extra, config, rename.</p>
    </td>
  </tr>
  <tr>
    <td align="center" colSpan="1" rowSpan="1">
      <p><strong>Run button</strong></p>
    </td>
    <td align="left" colSpan="1" rowSpan="1">
      <p>App defined button. Recommended UI actions: start, run, enter, save</p>
    </td>
  </tr>
  <tr>
    <td align="center" colSpan="1" rowSpan="1">
      <p><strong>App Switcher</strong></p>
    </td>
    <td align="left" colSpan="1" rowSpan="1">
      <p>ALT+TAB like button, list all opened apps windows. Works only inside runned Linux, not in MCU mode? </p>
    </td>
  </tr>
  <tr>
    <td align="center" colSpan="1" rowSpan="1">
      <p><strong>Back button</strong></p>
    </td>
    <td align="left" colSpan="1" rowSpan="1">
      <p>Back, exit in menus and apps.</p>
    </td>
  </tr>
  <tr>
    <td align="center" colSpan="1" rowSpan="1">
      <p><strong>D-pad</strong></p>
    </td>
    <td align="left" colSpan="1" rowSpan="1">
      <p>Main navigation D-pad with 5-buttons: UP, DOWN, LEFT, RIGHT and OK in center.</p>
    </td>
  </tr>
</table>

### Ports description

<table isTableHeaderOn="true" columnWidths="[object Object]">
  <tr>
    <td>
      <p><strong>Port</strong></p>
    </td>
    <td>
      <p><strong>Description</strong></p>
    </td>
  </tr>
  <tr>
    <td>
      <p><strong>USB-C Main</strong></p>
    </td>
    <td>
      <p>Main USB-C port for charging and device emulation. Can work as 4K video out for monitor connection.</p>
      <p>TODO: better name, full tech spec:</p>
      <p>Modes: host, device</p>
      <p>Video out: Display port version?</p>
      <p>Speed: ?</p>
      <p>Charging:?</p>
    </td>
  </tr>
  <tr>
    <td>
      <p><strong>3.5 Audio</strong></p>
    </td>
    <td>
      <p>Analog stereo audio out + microphone input.</p>
      <p>TODO: better name (3.5 Audio Jack? Audio Jack? 3.5 Jack?). Full tech spec:</p>
      <p>TRRS: what? </p>
      <p>Needs Pinout + compatible male jacks schematics</p>
      <p>What I can connect? </p>
    </td>
  </tr>
  <tr>
    <td>
      <p><strong>USB-A</strong></p>
    </td>
    <td>
      <p>TODO: better name, full tech spec</p>
    </td>
  </tr>
  <tr>
    <td colSpan="1" rowSpan="1">
      <p><strong>USB-C </strong></p>
    </td>
    <td colSpan="1" rowSpan="1">
      <p>TODO: better name, full tech spec</p>
    </td>
  </tr>
  <tr>
    <td colSpan="1" rowSpan="1">
      <p><strong>HDMI Out</strong></p>
    </td>
    <td colSpan="1" rowSpan="1">
      <p>TODO: full tech spec</p>
    </td>
  </tr>
  <tr>
    <td colSpan="1" rowSpan="1">
      <p><strong>2x Ethernet</strong></p>
    </td>
    <td colSpan="1" rowSpan="1">
      <p>TODO: full tech spec</p>
    </td>
  </tr>
  <tr>
    <td colSpan="1" rowSpan="1">
      <p><strong>GPIO</strong></p>
    </td>
    <td colSpan="1" rowSpan="1">
      <p>TODO: full tech spec</p>
    </td>
  </tr>
  <tr>
    <td colSpan="1" rowSpan="1">
      <p><strong>Micro SD slot</strong></p>
    </td>
    <td colSpan="1" rowSpan="1">
      <p>TODO: full tech spec</p>
    </td>
  </tr>
  <tr>
    <td colSpan="1" rowSpan="1">
      <p><strong>SIM-card slot</strong></p>
    </td>
    <td colSpan="1" rowSpan="1">
      <p>TODO: better name (Nano SIM feels confusing), full tech spec</p>
    </td>
  </tr>
  <tr>
    <td colSpan="1" rowSpan="1">
      <p><strong>M.2 module port</strong></p>
    </td>
    <td colSpan="1" rowSpan="1">
      <p>TODO: better name (Expansion port?), full tech spec. Needs a separate block with description</p>
    </td>
  </tr>
  <tr>
    <td colSpan="1" rowSpan="1">
      <p><strong>Debug port?</strong></p>
    </td>
    <td colSpan="1" rowSpan="1">
      <p>Will we leave JTAG port?</p>
      <p>TODO: better name, full tech spec</p>
    </td>
  </tr>
</table>

![](https://api.archbee.com/api/optimize/3StCFqarJkJQZV-7N79yY/1SR0qCQMBYbxlUvYFxMX9_flipperone-ports-and-interfaces-v003.png)

![](https://api.archbee.com/api/optimize/3StCFqarJkJQZV-7N79yY/nrxW81cCiJfuPqbDarJAs_flipperone-ports-and-interfaces-m2-v003.png)

### Electronics Schematics

Electrical schematics of all Flipper One boards. TODO: INTERNAL LINK TO Schematics.md

### Mechanics

Mechanical design of the external surfaces of the front panel and rear cover with Flipper One modules.

### Modules

Modules for Flipper One, divided into two categories: GPIO and M.2 modules.

### GPIO modules

GPIO modules connect via the external GPIO port on the rear panel without the need to open the cover. These are DIY modules for enthusiasts that can be built on a prototyping board using off-the-shelf components.

### M.2 modules

M.2 modules are expansion boards in the M.2 form factor (formerly called NGFF). Such modules are often used in laptops and industrial computers. In this format, you commonly find SSD drives, cellular modems, Wi-Fi adapters, SDR radios, and more.
