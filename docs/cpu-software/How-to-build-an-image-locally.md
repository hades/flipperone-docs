# How to build an image locally

This page describes how to build the OS image locally on your computer. This is useful for testing your changes in the OS components on Flipper One or any of the [supported boards](Supported-boards.md) before submitting pull request to the repository.

When building the image locally, the same workflow is used as on the Build Server. This workflow is described in the [Build system](Build-system.md) page.

## Prerequisites

Before starting the image build, the required components must be installed to ensure the container runs properly.

:::hint{type="info"}
The operating system image is built inside a Docker container in a Linux environment, ensuring cross-platform compatibility of the build process.
:::

### On Linux/macOS:

:::::WorkflowBlock

:::WorkflowBlockItem
Install [Docker Desktop](https://www.docker.com/)
:::

:::WorkflowBlockItem
Install [git](https://git-scm.com/).
:::

:::::

### On Windows 10/11:

:::::WorkflowBlock
:::WorkflowBlockItem
Open terminal and install **WSL 2** (Windows Subsystem for Linux v2) with default Ubintu distribution:

`wsl --install`

During the installation, you will be prompted to enter a Unix **username** and **password** for WSL 2.
:::

:::WorkflowBlockItem
Download the Docker Desktop installer from the [official web site](https://www.docker.com/).
:::

:::WorkflowBlockItem
Run the **Docker Desktop** installer as an administrator. In the installer, make sure the **Use WSL 2 instead of Hyper-V (recommended)** option is selected.

![Use WSL 2 instead of Hyper-V (recommended) option in the installer window](/files/pics/docker-desktop-installation-on-windows.png)

:::

:::WorkflowBlockItem
At the end of the installation, click **Restart Windows**.
:::

:::WorkflowBlockItem
After reboot run Docker Desktop and go to **Settings → Resources → WSL Integration**. Enable the **Ubuntu** distribution, then click **Apply & Restart**.

![Docker Desktop Ubuntu option in the app settings](/files/pics/docker-desktop-integration-with-ubuntu-distro.png)

:::

:::WorkflowBlockItem
Install [git](https://git-scm.com/).
:::

:::::

## OS image building

:::hint{type="info"}
Building the OS image is a long-running process that may take from several tens of minutes to over an hour.
:::

To build the OS image:

:::::WorkflowBlock
:::WorkflowBlockItem
Open the terminal (on Linux/MacOS) or PowerShell (on Windows) in the folder where you plan to save image build system.
:::

:::WorkflowBlockItem
Clone the build scripts repository:

`git clone https://github.com/flipperdevices/rk3576-linux-build`
:::

:::WorkflowBlockItem
Enter the folder you just cloned:

`cd rk3576-linux-build`
:::

:::WorkflowBlockItem
Build the Docker image: 

`docker build -t rk3576-linux-build .`
:::

:::WorkflowBlockItem
Run the container

**On Linux/macOS:**

`docker run --privileged --rm -v $(pwd)/out:/artifacts rk3576-linux-build`

**On Windows 10/11:**

`docker run --privileged --rm -v ${PWD}\out:/artifacts rk3576-linux-build`
:::

:::WorkflowBlockItem
Wait for the build to complete. 
:::
:::::

:::hint{type="success"}
The full-disk OS images are stored in the `rk3576-linux-build/out/images` directory. You can now [install the image to your board](How-to-install-an-image.md).
:::
