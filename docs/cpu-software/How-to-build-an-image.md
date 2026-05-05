# How to build an image

This page describes how to build the OS image locally on your computer. This is useful for testing your changes in the OS components on Flipper One or any of the [supported boards](Supported-boards.md) before submitting pull request to the repository.

When building the image locally, the same workflow is used as on the Build Server. This workflow is described in the [Build system](Build-system.md) page.

## Prerequisites

Before starting the image build, the required components must be installed to ensure the container runs properly.

:::hint{type="info"}
The operating system image is built inside a Docker container, ensuring cross-platform compatibility of the build process.
:::

### On macOS

Install [Docker Desktop](https://www.docker.com/) and [git](https://git-scm.com/install/mac).

### On Linux

:::::WorkflowBlock
:::WorkflowBlockItem
Install the required packages:

`apt install -y docker.io docker-cli git sudo passwd qemu-user-binfmt`
:::

:::WorkflowBlockItem
Add the current user to the **docker** group and apply it in the current session:

`sudo usermod -aG docker $USER && newgrp docker`
:::

:::::

### On Windows 10/11

:::::WorkflowBlock
:::WorkflowBlockItem
Open a terminal and install **WSL 2** (Windows Subsystem for Linux v2) with Debian distribution:

`wsl --install -d Debian`
:::

:::WorkflowBlockItem
Restart your computer. After rebooting, the Debian distribution installation will start automatically. You’ll be prompted to create a Unix **username** and **password** during installation.
:::

:::WorkflowBlockItem
Install the required packages:
`apt install -y docker.io docker-cli git`
:::

:::WorkflowBlockItem
Add the current user to the **docker** group and apply it in the current session:

`sudo usermod -aG docker $USER && newgrp docker`
:::

:::WorkflowBlockItem
Close the terminal.
:::

:::::

## Building an OS Image

:::hint{type="info"}
Building the OS image is a long-running process that may take from several tens of minutes to over an hour.
:::

To build the OS image:

:::::WorkflowBlock
:::WorkflowBlockItem
Open the terminal in the folder where you plan to save image build system.
:::

:::WorkflowBlockItem
**On Linux/macOS:** skip this step.

**On Windows:** Enter the Debian terminal:

`wsl -d Debian`

Go to the Debian user’s home directory:

`cd ˜`
:::

:::WorkflowBlockItem
Clone the OS image build scripts repository:

`git clone https://github.com/flipperdevices/rk3576-linux-build && cd rk3576-linux-build`
:::

:::WorkflowBlockItem
Build the Docker image: 

`docker build -t rk3576-linux-build .`
:::

:::WorkflowBlockItem
Run the container

`docker run --privileged --rm -v $(pwd)/out:/artifacts rk3576-linux-build`
:::

:::WorkflowBlockItem
Wait for the build to complete. 
:::
:::::

:::hint{type="success"}
The full-disk OS images are stored in:

* **Linux and macOS:** `rk3576-linux-build/out/images`. 
* **Windows 10/11:** `Linux/Debian/home/[wsl user]/rk3576-linux-build/out/images`.

You can now [install the image to your board](How-to-install-an-image.md).
:::
