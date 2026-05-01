# How to build an image locally

This page describes how to build the OS image locally on your computer. This is useful for testing your changes in the OS components on Flipper One or any of the [supported boards](Supported-boards.md) before submitting pull request to the repository.

When building the image locally, the same workflow is used as on the Build Server. This workflow is described in the [Build system](Build-system.md) page.

## Prerequisites

:::hint{type="info"}
The OS image is built using a Docker container in a Linux environment to ensure cross-platform compatibility of the build process.
:::

Before starting the image build, the required components must be installed to ensure the container runs properly.

### For Linux and MacOS:

Install [Docker Desktop](https://www.docker.com/) and [git](https://git-scm.com/).

### For Windows 10/11:

:::::WorkflowBlock
:::WorkflowBlockItem
Install [git](https://git-scm.com/).
:::

:::WorkflowBlockItem
Open PowerShell as an administrator and install **WSL 2** (Windows Subsystem for Linux v2):

`wsl --install`
:::

:::WorkflowBlockItem
Download the Docker Desktop installer from the [official web site](https://www.docker.com/).
:::

:::WorkflowBlockItem
Run the **Docker Desktop** installer as an administrator.
In the installer, make sure the **Use WSL 2 instead of Hyper-V (recommended)** option is selected.

![Use WSL 2 instead of Hyper-V (recommended) option in the installer window](/files/pics/docker-desktop-installation-on-windows.png)

:::

:::WorkflowBlockItem
At the end of the installation, click **Restart Windows**.
:::

:::WorkflowBlockItem
After reboot, wait for WSL 2 installation to complete. During the setup process, you will be prompted to enter a Unix **username** and **password** for WSL 2.
:::

:::WorkflowBlockItem
Run Docker Desktop and go to **Settings → Resources → WSL Integration**. Enable the **Ubuntu** distribution, then click **Apply & Restart**.
:::
:::::

## OS image building

:::hint{type="info"}
Building the OS image is a long-running process that may take from several tens of minutes to over an hour.
:::

To build the OS image:

:::::WorkflowBlock
:::WorkflowBlockItem
1. Open the terminal (on Linux/MacOS) or PowerShell (on Windows) in the folder where you plan to save image build system.
:::

:::WorkflowBlockItem
2. Clone the build scripts repository:

`git clone https://github.com/flipperdevices/rk3576-linux-build`
:::

:::WorkflowBlockItem
3. Enter to the folder you just cloned:

`cd rk3576-linux-build`
:::

:::WorkflowBlockItem
4. Build the Docker image: 

`docker build -t rk3576-linux-build .`
:::

:::WorkflowBlockItem
5. Run the container

**On Linux/MacOS:**

`docker run --privileged --rm -v $(pwd)/out:/artifacts rk3576-linux-build`

**On Windows 10/11:**

`docker run --privileged --rm -v ${PWD}\out:/artifacts rk3576-linux-build`
:::

:::WorkflowBlockItem
6. Wait for the build to complete. 
:::
:::::

:::hint{type="success"}
The full-disk OS images are stored in the `rk3576-linux-build/out/images` directory. You can now [install the image to your board](How-to-install-an-image.md).
:::
