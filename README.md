# Yocto Project

## What is Yocto?

Yocto, the smallest SI unit prefix, represents  10<sup>-24</sup>. In the embedded world, **Yocto** refers to the **Yocto Project**, an open-source collaboration project that provides templates, tools, and methods to create custom Linux-based systems. This project helps developers generate custom Linux distributions tailored specifically for their embedded hardware.

## Embedded Linux

**Embedded Linux** refers to a customized version of the Linux operating system designed to operate on embedded systems, such as routers, automotive systems, and other specialized devices. These systems typically have limited resources and require a streamlined version of Linux. Key components of an embedded Linux system include:

1. **Toolchain**: A set of programming tools used to compile and build software for a target system. It includes the compiler, linker, and libraries necessary to develop applications for the specific hardware.

2. **Boot Loader**: The initial software that runs when the system starts. It is responsible for initializing the hardware and loading the operating system kernel into memory. Examples include U-Boot and GRUB.

3. **Kernel**: The core component of the operating system that manages hardware resources such as CPU, memory, and peripherals. In embedded Linux, the kernel is often customized to include only the necessary drivers and modules for the target hardware.

4. **Root File System**: This contains the essential files and programs needed for the system to run. It includes system libraries, configuration files, and application-specific programs.

## What is the Yocto Project and Why Do We Need It?

The **Yocto Project** is an open-source initiative that simplifies the process of creating custom Linux distributions for embedded systems. It provides a comprehensive build framework, allowing developers to build, modify, and maintain a complete Linux software stack tailored to their specific hardware and application needs.

### Why Yocto?

- **Simplifies Embedded Linux Development**: Yocto provides a set of tools and metadata that streamline the process of creating custom Linux distributions. It abstracts the complexity of building a complete system from scratch.
  
- **Consistency and Reusability**: Yocto's build system ensures consistent builds and enables the reuse of components across different projects. This helps reduce development time and effort.
  
- **Flexibility and Customization**: Yocto allows developers to fine-tune every aspect of the system, from the kernel to user-space applications, making it possible to create highly optimized distributions for specific hardware.

## What is Poky?

**Poky** is the reference distribution of the Yocto Project. It serves as a starting point for building custom Linux images. Poky consists of:

- **BitBake**: The task execution engine and build tool used to process recipes and build software packages.
  
- **OpenEmbedded-Core (OE-Core)**: The build system that provides the core set of metadata and tools necessary to build a minimal Linux distribution.
  
- **Meta-Yocto-BSP**: A Board Support Package (BSP) layer that provides support for various hardware platforms.
  
- **Documentation**: Guides, manuals, and instructions that help developers understand and use the Yocto Project effectively.

### Difference Between Poky and Yocto

- **Yocto Project**: An overarching project that provides a build framework, tools, and metadata to create custom Linux distributions.
  
- **Poky**: A reference distribution created using the Yocto Project. It includes BitBake, OE-Core, and other essential layers, serving as an example and starting point for building custom distributions.

## Metadata In Yocto World

In Yocto, **metadata** defines how software packages are built, how the build system should behave, and how different components are configured. This metadata includes:

- **Recipes (`.bb` files)**: Define how to fetch, configure, compile, and install individual software packages. Each recipe provides the instructions and dependencies required to build a package.

- **Classes (`.bbclass` files)**: Define common build functionality that can be shared across multiple recipes. For example, a class might define how to build all software that uses the `autotools` build system.

- **Configuration Files (`local.conf`, `bblayers.conf`)**: Define machine and distribution-specific settings. These files configure the build environment and specify which layers and recipes to include.

- **Includes (`.inc` files)**: Provide common settings that can be shared across recipes. They are used to avoid duplication by including common variables and functions in multiple recipes.

## Poky Collection and OpenEmbedded Project

**Poky** is part of the **OpenEmbedded** project, which provides a larger set of metadata and layers for building embedded systems. While Yocto focuses on the build framework and core tools, OpenEmbedded extends this with a wide array of recipes and layers.

- **Yocto Project**: Provides the core build framework, tools, and essential metadata.

- **OpenEmbedded Project**: Offers an extensive set of metadata, recipes, and layers, enabling the creation of customized embedded Linux systems.

### OpenEmbedded-Core (OE-Core)

OE-Core is the foundation of the OpenEmbedded build system. It provides the core set of metadata, including essential system components and package recipes required to build a minimal Linux distribution. It forms the basis upon which Poky and other layers are built.

## What is BitBake?

**BitBake** is the core build engine and task scheduler used by the Yocto Project. It processes recipes, resolves dependencies, and executes tasks to build packages and images. BitBake can handle complex build environments, managing parallel builds and ensuring reproducibility.

### Useful BitBake Commands

- **`bitbake <recipe>`**: Builds the specified recipe or package.
  
- **`bitbake-layers`**: Manages layers, allowing you to add, remove, or show available layers in the build environment.
  
- **`bitbake -c clean <recipe>`**: Cleans the work directory for a specific recipe, removing intermediate build files.
  
- **`bitbake -s`**: Displays the state of available recipes and packages, listing them with their version information.

## What is BSP?

A **Board Support Package (BSP)** provides the necessary low-level drivers and configurations to support specific hardware platforms. It includes information about the processor, peripherals, memory, and other hardware-specific details.

### Meta-Yocto-BSP

The **Meta-Yocto-BSP** layer provides BSPs for various hardware platforms supported by the Yocto Project. It includes recipes and configurations for building images tailored to specific boards.

## QEMU and Core-Image-Minimal

- **QEMU**: An open-source hardware emulator used to simulate hardware platforms for testing and development purposes. It allows developers to test software in a virtual environment without needing physical hardware.
  
- **Core-Image-Minimal**: A minimal Linux image created by the Yocto Project, containing only the essential components needed to boot and run a basic Linux system. It is often used for testing and as a starting point for building custom images.

## Yocto Project Releases

The Yocto Project follows a regular release cycle to provide updates, new features, and improvements. Each release is named after a city and is versioned numerically. Understanding the release cycle and how it affects development can be crucial for maintaining stability and compatibility in embedded projects.

#### 1. **Release Cadence**

- **Regular Releases**: Yocto Project typically releases a new version every six months. These releases include new features, performance improvements, and bug fixes. The regular releases allow developers to stay up-to-date with the latest advancements in embedded Linux development.

- **Long-Term Support (LTS) Releases**: Some releases are designated as Long-Term Support (LTS) versions. LTS releases receive extended support and maintenance, including security updates and critical bug fixes, for several years. This makes them ideal for projects that require stability over a longer period.

#### 2. **Release Naming Convention**

- **City Names**: Each Yocto release is named after a city, with the names being chosen alphabetically. For instance, some of the recent releases include:
  - **Langdale** (Yocto 4.3)
  - **Kirkstone** (Yocto 4.2, LTS release)
  - **Honister** (Yocto 4.1)
  - **Hardknott** (Yocto 4.0)

- **Version Numbers**: Alongside the city names, each release has a version number (e.g., Yocto Project 4.2 for Kirkstone). This helps in identifying the chronological order and versioning system.

#### 3. **Types of Releases**

- **Major Releases**: These introduce significant new features, updates, and sometimes changes that may not be backward compatible. They often include improvements in build system efficiency, support for new architectures, updated toolchains, and more.

- **Minor Updates**: Minor updates to a major release (e.g., bug fixes or security patches) are released periodically. These updates maintain the release's stability without introducing new features that could affect existing functionality.

#### 4. **Maintenance and Support**

- **Maintenance Period**: Each release is maintained for a specific period, during which it receives updates and fixes. Regular releases are typically maintained for around one year, while LTS releases have a maintenance period of up to two years or more.

- **Security and Bug Fixes**: During the maintenance period, the Yocto Project team provides patches for security vulnerabilities and critical bugs. It's important for developers to apply these updates to ensure the security and reliability of their systems.

#### 5. **Choosing a Release for Development**

When starting a new project with the Yocto Project, selecting the right release is crucial:

- **For Cutting-Edge Features**: If you need the latest features or support for the newest hardware, choosing the most recent release is recommended. However, be prepared to update regularly to maintain support.

- **For Stability**: If your project requires long-term stability and minimal changes, an LTS release is the best choice. LTS releases offer a stable base with extended support, making them ideal for products with long life cycles.

#### 6. **Upgrading Between Releases**

- **Upgrade Path**: Yocto Project provides documentation and tools to assist in upgrading from one release to another. However, upgrading may require changes to your custom layers, recipes, and configurations to ensure compatibility with the new release.

## Getting Started with the Yocto Project

To start using the Yocto Project, developers typically follow a "Hello World" example to build and run a simple application. This involves setting up the build environment, writing a basic recipe, and using BitBake to build the package.

#### Host PC Requirements

* Minimum 50 GB free space
* Minimum 4 GB RAM

#### Supported Linux Distros

- Ubuntu 18.04 (LTS)
- Ubuntu 20.04 (LTS)
- Ubuntu 22.04 (LTS)
- Fedora 34
- Fedora 35
- AlmaLinux 8.5
- Debian GNU/Linux 10.x (Buster)
- Debian GNU/Linux 11.x (Bullseye)
- OpenSUSE Leap 15.3

**I've used Ubuntu 22.04 (LTS)**

#### Install Required Packages

```bash
sudo apt install gawk wget git diffstat unzip texinfo gcc build-essential chrpath socat cpio python3 python3-pip python3-pexpect xz-utils debianutils iputils-ping python3-git python3-jinja2 libegl1-mesa libsdl1.2-dev pylint3 xterm python3-subunit mesa-common-dev zstd liblz4-tool

```

This command installs a set of essential packages required to build and work with the Yocto Project on a host system running a Debian-based Linux distribution, like Ubuntu. Let's break down what each of these packages does and why they are needed:

#### **Packages Explanation:**

- **gawk**: An implementation of the AWK programming language, used for pattern scanning and processing. It's often required in build scripts for text processing.

- **wget**: A utility for downloading files from the web. It's used by Yocto to fetch source code and other resources during the build process.

- **git**: A version control system that allows you to clone repositories and track changes in the source code. Yocto uses Git to manage its source code and metadata.

- **diffstat**: Generates a summary of changes between files. Useful for reviewing patches and changes in the codebase.

- **unzip**: A utility for extracting ZIP archive files, which may be used to compress source files or build artifacts.

- **texinfo**: A documentation system that converts documentation written in Texinfo format into various formats like HTML and PDF. It's needed for generating documentation during the build process.

- **gcc**: The GNU Compiler Collection, which includes the `gcc` C and C++ compilers. It's essential for compiling the source code into executable binaries.

- **build-essential**: A package that includes essential tools for building software, such as the `make` utility and development tools needed for compiling.

- **chrpath**: A tool to modify the `rpath` of binaries. It's used to set or remove the library search path in binaries.

- **socat**: A utility for data transfer between two locations. It can be used in Yocto for setting up network communications during the build process.

- **cpio**: A utility to copy files to and from archives, often used for handling initial RAM filesystem (initramfs) images.

- **python3**: The Python 3 interpreter. Python is widely used in the Yocto Project for scripting and build tasks.

- **python3-pip**: A package manager for Python, used to install and manage Python packages.

- **python3-pexpect**: A Python module for spawning child applications and controlling them automatically. Useful for automation and scripting in Yocto.

- **xz-utils**: Provides utilities for compressing and decompressing files using the XZ compression format. It's used for handling compressed source files.

- **debianutils**: A set of useful utilities specific to Debian-based systems, often used in various build and packaging scripts.

- **iputils-ping**: Includes the `ping` command for network diagnostics, which can be used during network setup and testing.

- **python3-git**: A Python library for interacting with Git repositories. It's used by Yocto scripts to manipulate Git repositories programmatically.

- **python3-jinja2**: A templating engine for Python, used by Yocto to generate configuration files and scripts dynamically.

- **libegl1-mesa**: Provides an implementation of the EGL API, which interfaces between rendering APIs like OpenGL and the native window system.

- **libsdl1.2-dev**: The Simple DirectMedia Layer (SDL) library development files. SDL is used for low-level access to audio, keyboard, mouse, and graphics hardware.

- **pylint3**: A static code analysis tool for Python, useful for checking the quality of Python code and ensuring consistency in Yocto scripts.

- **xterm**: A terminal emulator for the X Window System. It may be required to run certain graphical applications or scripts during the build.

- **python3-subunit**: A Python module that allows Python unittest results to be reported in the Subunit protocol, useful for testing and automation.

- **mesa-common-dev**: Provides development files for the Mesa 3D Graphics Library, essential for graphics and rendering tasks.

- **zstd**: A fast compression tool used to compress and decompress files, providing an efficient way to handle large datasets.

- **liblz4-tool**: Provides the `lz4` compression utility, used for fast compression and decompression of files.

These packages cover a range of functionalities, including:

- **Development Tools**: `gcc`, `build-essential`, `libsdl1.2-dev`, `mesa-common-dev`
- **Python Environment**: `python3`, `python3-pip`, `python3-pexpect`, `python3-git`, `python3-jinja2`, `pylint3`, `python3-subunit`
- **Utilities and Compression Tools**: `wget`, `unzip`, `xz-utils`, `zstd`, `liblz4-tool`
- **Version Control**: `git`
- **Documentation**: `texinfo`
- **Networking**: `iputils-ping`, `socat`
- **Terminal Emulator**: `xterm`

Reference: https://docs.yoctoproject.org/4.0.7/brief-yoctoprojectqs/index.html#build-host-packages

## Hello World of Yocto Project

Follow these steps to build a custom Linux image using the Yocto Project. This guide will walk you through setting up the environment, configuring the build, and running the image using QEMU.

### 1. Create the Project Directory and Clone Poky

First, create a directory for your Yocto Project and clone the Poky repository:

```bash
mkdir yocto_tutorial
cd yocto_tutorial
git clone git://git.yoctoproject.org/poky -b kirkstone
```

- **yocto_tutorial**: Your project folder where all Yocto files and configurations will reside.
- **poky**: The Yocto Project’s reference system, providing the essential components to start building images.
- **kirkstone**: The branch of the Yocto Project to use. It's recommended to use a specific release branch for stability.

### 2. Initialize the Build Environment

Navigate to the `poky` directory and initialize the build environment:

```bash
cd poky
source oe-init-build-env
```

- This command sets up the environment variables and creates a `build` directory where all build output and configuration files will be stored.
- After running this, your terminal prompt will indicate you're in the Yocto build environment.

### 3. Understand the Build Directory

You’re now in the `build` directory. This directory contains several folders and files, but the most important at this stage is the `conf` folder, which holds configuration files like `local.conf` and `bblayers.conf`.

### 4. Available Image Targets

After initializing the environment, you’ll see a list of common build targets you can create using BitBake:

```
### Shell environment set up for builds. ###

You can now run 'bitbake <target>'

Common targets are:
    core-image-minimal
    core-image-full-cmdline
    core-image-sato
    core-image-weston
    meta-toolchain
    meta-ide-support
```

- **core-image-minimal**: A small, lightweight image that includes the basic components to boot into a shell.
- **core-image-full-cmdline**: A command-line image with more utilities.
- **core-image-sato**: A full graphical desktop environment.
- **core-image-weston**: An image with the Weston compositor for Wayland.
- **meta-toolchain**: A standalone toolchain for cross-compiling.
- **meta-ide-support**: Adds support for development IDEs.

### 5. Modify `local.conf` for Your Build

Before starting the build, let's make a few changes to `local.conf` to optimize the build process:

- Open `local.conf` in a text editor:
    ```bash
    vi conf/local.conf
    ```
- Add or modify the following lines:
    ```bash
    RM_OLD_IMAGE = "1"
    INHERIT += "rm_work"
    ```
    - **RM_OLD_IMAGE**: Removes old images to save space.
    - **INHERIT += "rm_work"**: Removes intermediate build files after the package is built to save disk space.

- Save and exit the file.

### 6. Build the Image

Run the following command to start building the `core-image-minimal`:

```bash
bitbake core-image-minimal
```

- **BitBake** is the build engine for Yocto. It processes the recipes and executes tasks to create the final image.
- This build process can take a significant amount of time, especially on the first run, as it downloads and compiles all the necessary components.
- Subsequent builds will be faster, as BitBake will only rebuild components that have changed.

### 7. Test the Image with QEMU

Once the build is complete, you can test the image using QEMU, an emulator that allows you to run the image in a virtual environment:

```bash
runqemu qemux86-64
```

- This command launches QEMU with the newly built image, allowing you to interact with the system as if it were running on actual hardware.
- Default login user name for yocto is ```root```.

### Additional Resources

For a more detailed "Hello World" example, including creating a custom recipe and integrating it into an image, you can refer to the guide available [here](https://github.com/Munawar-git/YoctoTutorials/blob/master/00_Yocto_Intro/00-Yocto-Intro.md). Ensure you are using the `kirkstone` branch of the repository to maintain compatibility with the instructions provided.

## Generating a Yocto Project Image for the BeagleBone

This guide will walk you through the process of building a custom Linux image for the BeagleBone using the Yocto Project.

```bash
sudo apt install gawk wget git diffstat unzip texinfo gcc build-essential chrpath socat cpio python3 python3-pip python3-pexpect xz-utils debianutils iputils-ping python3-git python3-jinja2 libegl1-mesa libsdl1.2-dev pylint3 xterm python3-subunit mesa-common-dev zstd liblz4-tool
```

### Steps to Build the Image

#### 1. Set Up the Yocto Project Environment

1. **Create a project directory and clone the Poky repository:**

    ```bash
    mkdir beaglebone_yocto
    cd beaglebone_yocto
    git clone git://git.yoctoproject.org/poky -b kirkstone
    ```

2. **Navigate to the `poky` directory and initialize the build environment:**

    ```bash
    cd poky
    source oe-init-build-env
    ```

    This command will create and switch to the `build` directory.

#### 2. Add the BeagleBone BSP Layer

1. **Clone the meta-ti layer**, which provides support for Texas Instruments boards, including the BeagleBone:

    ```bash
    git clone git://git.yoctoproject.org/meta-ti.git -b kirkstone
    ```

#### 3. Adding the `meta-ti-bsp` Layer to Your Build Environment

To include the `meta-ti-bsp` layer in your Yocto build, follow these steps. Note that `meta-ti-bsp` depends on `meta-arm`, which in turn depends on `meta-arm-toolchain`. Therefore, you need to add these layers in sequence.

##### Method 1: Using a Text Editor

1. **Clone the necessary layers:**

    Clone the `meta-arm` repositories:

    ```bash
    git clone git://git.openembedded.org/meta-arm -b kirkstone
    ```

2. **Open the `bblayers.conf` file** in a text editor:

    ```bash
    vi conf/bblayers.conf
    ```

3. **Add the paths to the `BBLAYERS` variable**:

    Locate the `BBLAYERS` variable in the file and append the paths to the layers in the following order:

    ```bash
    BBLAYERS += "${TOPDIR}/../meta-arm/meta-arm-toolchain"
    BBLAYERS += "${TOPDIR}/../meta-arm/meta-arm"
    BBLAYERS += "${TOPDIR}/../meta-ti/meta-ti-bsp"
    ```

4. **Save and exit** the text editor.

##### Method 2: Using `bitbake-layers` Command

1. **Add the layers using the `bitbake-layers` command**:

    Run the following commands from the `build` directory where the Yocto environment is initialized:

    ```bash
    bitbake-layers add-layer ../meta-arm/meta-arm-toolchain
    bitbake-layers add-layer ../meta-arm/meta-arm
    bitbake-layers add-layer ../meta-ti/meta-ti-bsp
    ```

    Ensure that you add the layers in the correct order to satisfy dependencies. You can give the absolute path for avoiding the errors.

    Make sure you run this command from the `build` directory where the Yocto environment is initialized.

#### 4. Verify Layer Addition

To confirm that the `meta-ti` layer has been added successfully, you can list the layers using:

```bash
bitbake-layers show-layers
```

This command will display all layers currently included in your build environment, including `meta-ti`.

This approach ensures that the `meta-ti` layer is properly included in your Yocto build environment, providing support for Texas Instruments hardware such as the BeagleBone.

#### 5. Configure the Build for BeagleBone

1. **Edit the `local.conf` file** to specify the BeagleBone machine:

    ```bash
    vi conf/local.conf
    ```

2. **Set the `MACHINE` variable** to `beaglebone`:

    ```bash
    MACHINE ?= "beaglebone"
    ```

3. **Optional: Optimize the build process** by adding or modifying the following lines:

    ```bash
    RM_OLD_IMAGE = "1"
    INHERIT += "rm_work"
    ```

#### 6. Build the Image

1. **Build the image using BitBake**:

    ```bash
    bitbake core-image-minimal
    ```

    - This process will take some time, especially the first time you run it, as it downloads and compiles all required components.

#### 7. Deploy the Image to the BeagleBone

1. **Locate the generated image** in the `tmp/deploy/images/beaglebone` directory. The file will be named something like `core-image-minimal-beaglebone.wic.xz`.

2. **Extract the `.wic.xz` file** to get the `.wic` image:

    ```bash
    xz -d core-image-minimal-beaglebone.wic.xz
    ```

3. **Write the image to an SD card**:

    - Insert an SD card into your host machine.
    - Find the device name for the SD card using the `lsblk` command (e.g., `/dev/sdX`).
    - Use `dd` to write the image to the SD card:

    ```bash
    sudo dd if=core-image-minimal-beaglebone.wic of=/dev/sdX bs=4M
    sync
    ```

    Replace `/dev/sdX` with the actual device name of your SD card.

#### 8. Boot the BeagleBone

1. **Insert the SD card** into the BeagleBone.
2. **Power on the BeagleBone**. It should boot from the SD card, loading the custom Yocto-built image.

### Testing and Further Customization

- **Test the image** on the BeagleBone to ensure it boots and works correctly.
- **Customize the image** by adding additional packages, modifying kernel configurations, or creating custom recipes.
- For additional Yocto Project customization and development, refer to the Yocto Project Documentation.

---

If there is any issue, feel free to reach out to me at [divyeshkapadiya25@gmail.com](mailto:divyeshkapadiya25@gmail.com) or connect with me on LinkedIn: [Divyesh Kapadiya](https://www.linkedin.com/in/divyeshkapadiya25/).
