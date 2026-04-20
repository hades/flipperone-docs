# Build system

A build system is a framework for producing OS full disk images for various supported hardware platforms. It consists of build scripts and several GitHub repositories containing OS components such as the bootloader, Linux kernel, patches, packages, and more. The output of the build system is a disk image file that can be written to a microSD card or flashed directly to a device's internal flash memory via USB using Rockchip’s built-in MaskROM mode.

Disk images include two Linux kernels (Mainline kernel 7.0 and BSP kernel 6.1), between which you can switch from the terminal or via the U-Boot menu.

You can either download a prebuilt OS image from our [public build server](./#public-build-server) or [build your own image locally](./#local-build-of-the-os).

## OS disk image build flow

The OS images are built using scripts from the [flipperone-linux-build-scripts](https://github.com/flipperdevices/flipperone-linux-build-scripts) repository. These scripts fetch sources from multiple additional repositories, compile the code, and assemble the resulting artifacts into full disk images for all supported boards.

![OS disk image build flow diagram](/files/pics/os-disk-image-build-flow.jpg "OS disk image build flow")

Build system flow consists of steps required for building a full disk image from scratch:

1. **Build the U-Boot bootloader image.** It includes Rockchip RK3576 binaries, trusted firmware for ARM and opensource upstream U-Boot sources. Each supported board needs separate U-Boot image.

2. **Get & compile Mainline Linux kernel.** We use last release (7.0.0 as for now) fork sources from Linus Torvalds with some our patches not in mainline yet.

3. **Get & compile BSP Linux kernel.** This kernel (6.1.118 for now) includes Rockchip's kernel sources, DTS (device tree source) file for each supported board and our patches for BSP kernel.

4. **Build a full disk images.** It uses debos to build the image that includes all of the above, and drop in some of the extra testing scripts (temperature monitoring and tests for power consumption, CPU, GPU, network, disk IO performance).

The Flipper OS image files are stored in the `out/images` directory.

## OS image file naming

::Image[]{src="/files/pics/os-image-file-name.jpg" size="100" position="center" caption="OS image file name structure"}
![OS disk image build flow diagram](/files/pics/os-image-file-name.jpg "OS image file name")

The OS image filename consists of several parts. Let’s break them down using the example above:

* `debian` — indicates that the image is based on the Debian Linux distribution.

* `4096` — the data block size in bytes. This can be either 512 for SD card images or 4096 for images intended for eMMC or UFS storage.

* `nanopi-m5` — the target name of the board for which the image is built. A list of supported target names can be found on the [Supported Boards](Supported-boards.md) page.

* `build` — a keyword indicating that the following value represents the build ID.

* `1034` — the build ID. It consists of a sequential build number and an optional textual label, such as `test-dp`, `test-interconnect`, etc.

Each disk image is accompanied by a `.bmap` file that contains a map of the used data blocks. Using the `.img.gz` image together with the `.bmap` file speeds up the flashing process by skipping unused blocks.

## Public build server

The official OS build server web-interface is available at https://linux-images.flipp.dev/. We use **Buildbot** as our continuous integration (CI) framework to automate the build process. This web interface allows you to monitor the status of OS image builds.

![BuildBot web interface](/files/pics/os-buildbot.png "BuildBot web interface")

The images produced by each build are uploaded to a public web server, where they can be downloaded: https://dl-linux-images.flipp.dev/full-img/

![Web server interface with build list](/files/pics/os-build-list.png "Web server interface with build list")

Each build is stored in a separate directory, where the directory name matches the build ID.

By default, the Buildbot monitors each of the Git repositories labeled with ⚡ icon on the image build diagram for any changes (by polling them every 5 minutes), and rebuild any components affected by a change.

## Local build of the OS

Using the same build scripts as the official build server, you can build a Flipper OS image locally on your machine. This is useful for testing your changes on Flipper One or any [supported SBC](Supported-boards.md) before submitting pull requests with modifications to the repository.

:::hint{style="warning"}
Now image building is supported **only on Linux** (on EXT4 or XFS file system) due to limitations related to sparse images handling.
:::

To build Flipper OS images locally:

1. Install [**docker**](https://www.docker.com/) and [**git**](https://git-scm.com/).
2. Clone the build scripts repository: 

`git clone https://github.com/flipperdevices/rk3576-linux-build && cd rk3576-linux-build`

3. Build the Docker image: 

`docker build -t rk3576-linux-build .`

4. Run the container:

`docker run --privileged --rm -v $(pwd)/out:/artifacts rk3576-linux-build`

5. Wait for the build to complete. This is a long-running process that may take from several tens of minutes to over an hour.

The Flipper OS full disk images will be saved in the `rk3576-linux-build/out/images` directory.
