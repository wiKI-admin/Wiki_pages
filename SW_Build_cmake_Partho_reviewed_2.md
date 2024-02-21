**SW Build  CMake** {#sw-build-cmake .TOC-Heading}
==================

  -------------------- -------------------
  **Creation date:**   08.01.2024
  **Version 1.0:**     1.0
  **Author:**          Chiragkumar Patel
  -------------------- -------------------

**Table of contents** {#table-of-contents .TOC-Heading}
=====================

[1. Introduction 2](#introduction)

[1.1 What is a Software Build? 2](#what-is-a-software-build)

[1.2 What is CMake? 2](#what-is-cmake)

[1.3 Features of Cmake 2](#features-of-cmake)

[1.4 CMake Commands 3](#cmake-commands)

[2. Install CMake on Ubuntu 4](#install-cmake-on-ubuntu)

[2.1 Install CMake with APT on Ubuntu
4](#install-cmake-with-apt-on-ubuntu)

[2.2 Install CMake via Compiling Source on Ubuntu
4](#install-cmake-via-compiling-source-on-ubuntu)

[3. Using CMake on Ubuntu 5](#using-cmake-on-ubuntu)

**Table of figures**

[Figure 1: CMakeLists.txt Snapshot 6](#_Toc155608360)

[Figure 2: main.cpp Snapshot 6](#_Toc155608361)

[Figure 3: myclass.cpp Snapshot 7](#_Toc155608362)

[Figure 4: myclass.hpp Snapshot 7](#_Toc155608363)

[Figure 5: Terminal window Snapshot 8](#_Toc155608364)

**[Purpose:]{.underline}**

> *The sole purpose of this document is to provide information related
> to cmake, which is generally used to configure and generate the built
> system for the software projects. This document covers the topics from
> basic information to how to test the cmake installation on Ubuntu
> using a very simple "Leap Year Checking" C++ program.*

*\
*

Introduction
------------

### What is a Software Build?

A build in software development is when the engineers convert the source
code into a functional, standalone program with executable code that can
be run on a desktop computer or a mobile device.

A software build is created when your project reaches a certain point in
development. First, your designers, software architects, and business
analysts outline their vision for product implementation. This vision is
then turned into project specifications that your developers base the
source code on. When the developers finish writing the source code, and
the backbone of your program meets your project specifications, this
usually means that the source code is deemed ready for implementation.
It will be turned into a software build and thoroughly tested before the
release.

Some of the software build tools are, Apache Maven, Gradle, BuildMaster,
Travis CI, Cmake, Grunt, MSBuild, etc., but in this document, we will be
only focusing on CMake.

### What is CMake?

CMake is a command used for configuration and generation of built
systems for the software projects. It Generates platform-specific build
files (e.g., Makefiles or Visual Studio project files) based on a
high-level configuration file. This allows developers to write
"CMakeLists.txt" files describing how the project should built, making
it easier to maintain and build software development on different
platforms. CMake can generate a native build environment that will
compile source code, create libraries, generate wrappers and build
executable binaries in arbitrary combinations. CMake supports in-place
and out-of-place builds and can therefore support multiple builds from a
single source tree.

It is mostly used in the C and C++ programming communities but can be
used for a variety of other Languages as well. Cmake is itself a
Software Program, so it should be invoked with the script file to
interpret and generate an actual build file. CMake can generate a native
build environment that will compile source code, create libraries,
generate wrappers, and build executable binaries in arbitrary
combinations.

### Features of Cmake

The features of Cmake are,

-   **Platform Independence:** CMake generates platform-specific build
    files (e.g., Makefiles for Unix-like systems, Visual Studio project
    files for Windows) from a single, cross-platform CMake
    configuration. This approach allows developers to write their build
    scripts once and then generate builds for various operating systems
    and development environments, ensuring better portability.

-   **Simplicity and Readability:** CMake provides a user-friendly,
    human-readable scripting language for defining build configurations.
    CMakeLists.txt files are typically easier to write and maintain in
    comparison to complex and platform-specific build scripts.

-   **Modularity and Extensibility: **CMake supports a modular project
    structure, making it simple to add new source files, libraries, or
    dependencies without the need to modify the entire build system.
    Custom functions and macros can be used to simplify intricate tasks
    and extend the build process.

-   **Dependency Management: **CMake simplifies the management of
    external dependencies through features like find\_package, which can
    automatically locate and configure required dependencies. Developers
    specify the libraries and components their project needs, and CMake
    handles the integration into the build process.

-   **Parallel Building: **CMake-generated build systems can efficiently
    use multi-core processors, resulting in faster parallel builds. This
    feature can significantly reduce compilation times for extensive
    projects.

### CMake Commands

CMake commands are similar to C++ methods or functions, which take
parameters as a list and perform certain task accordingly. CMake
commands are case sensitive. There are built-in commands, which can be
found on the CMake documentation:

<https://cmake.org/cmake/help/latest/manual/cmake-commands.7.html>

Some commonly used CMake commands are:

-   message: prints given message

-   cmake\_minimum\_required: sets minimum version of cmake to be used

-   add\_executable: adds executable targets with given name

-   add\_library: adds a library target to build from listed source
    files

-   add\_subdirectory: adds a subdirectory to build

### What is CMakeLists.txt?

A CMakeLists.txt file is a critical component in projects utilizing
CMake, a cross-platform build system. This file contains instructions
and metadata needed by CMake to generate build files for a project. A
well-crafted CMakeLists.txt file is essential for a smooth and portable
build process. Its structure and contents are tailored to the specific
needs of the project, including source files, dependencies, build
options, and other configurations. As a result, CMake can generate
platform-specific build files, allowing developers to build and maintain
projects consistently across various platforms and build systems.

Install CMake on Ubuntu
-----------------------

### Install CMake with APT on Ubuntu

To avoid any potential conflicts during the installation process, it is
recommended to perform a quick system update to ensure your system is
up-to-date before installation.

sudo apt update && sudo apt upgrade

Using Ubuntu's repository is the recommended method for installing
CMake. To initiate the Installation, use following command,

sudo apt install cmake

After installation, verify that CMake is installed by checking its
version with the following command:

cmake \--version

### Install CMake via Compiling Source on Ubuntu

If we wanted to install the latest version of CMake, an alternative
method is to download the source code and compiling it. While this
method enables the installation of the newest version, it is responsible
for manually downloading and recompiling for updates.

Before proceeding, installing the required dependencies on your system
using the following command is necessary.

sudo apt install build-essential checkinstall zlib1g-dev libssl-dev

The first step is to visit the CMake GitHub releases page and retrieve
the latest version link. It's important to note that the examples below
may become outdated over time, so obtaining the latest version link is
crucial.

To download the archive, use the wget command below as an example.

wget
https://github.com/Kitware/CMake/releases/download/v3.28.1/cmake-3.28.1.tar.gz

Selecting the correct package to avoid any issues during installation is
essential. If you encounter problems during installation, you've likely
selected the wrong package.

Extract the contents of the archive using the following command.

tar -zxvf cmake-3.28.1.tar.gz

Now navigate to the directory that was extracted:

cd cmake-3.28.1

> Ensure you have correctly installed the required dependencies before
> proceeding to the next step, which involves running the Bootstrap
> script. If you encounter difficulties during this stage, the correct
> installation of dependencies is crucial.
>
> Begin by running the bootstrap script,

./bootstrap

> The bootstrap script may take several minutes to complete. Once it is
> done use the make command to build the package.

gmake

> To install CMake, use the following command,

Sudo make install

> The installation process may take several minutes. After the
> installation is complete, you can verify the installation by using the
> command,

cmake \--version

> In conclusion, installing CMake on Ubuntu is a relatively
> straightforward process that provides software developers with a
> powerful tool for building and packaging their projects. With its
> cross-platform compatibility and versatility, CMake has become the
> go-to tool for developers worldwide. Whether you opt for the APT
> method or the manual installation process, CMake's range of features
> and user-friendly interface make it an essential tool for software
> development.

Using CMake on Ubuntu
---------------------

After installing CMake on your ubuntu system, you can test that it works
correctly by any C++ program. Here, in this example I've used a simple
program to check if the given year is Leap year or not.

First create a new directory and navigate to it using the terminal.

mkdir test-code && cd test-code

Create a new file called "CMakeLists.txt" using nano editor. Make sure
that the file name should not be changed and always be CMakeLists.txt.

sudo nano CMakeLists.txt

Once the file is created, add the following code,

![](media/image4.png){width="6.00844050743657in"
height="3.7565212160979877in"}

[]{#_Toc155608360 .anchor}Figure 1: CMakeLists.txt Snapshot

Exit the file with CTRL+X and then press Y to save.

Create a new file called "main.cpp" again with the nano editor:

sudo nano main.cpp

Add the following code to the "main.cpp" you just created and opened,

![](media/image5.png){width="4.141908355205599in"
height="2.8147255030621174in"}

[]{#_Toc155608361 .anchor}Figure 2: main.cpp Snapshot

Exit the file with CTRL+X and then press Y to save.

Create a new file called "myclass.cpp" again with the nano editor:

sudo nano myclass.cpp

Add the following code to the "myclass.cpp" you just created and opened,

![](media/image6.png){width="4.38686789151356in"
height="2.2420909886264218in"}

[]{#_Toc155608362 .anchor}Figure 3: myclass.cpp Snapshot

Exit the file with CTRL+X and then press Y to save.

Create a new file called "myclass.hpp" again with the nano editor:

sudo nano myclass.hpp

Add the following code to the "myclass.hpp" you just created and opened,

![](media/image7.png){width="3.436470909886264in"
height="2.382263779527559in"}

[]{#_Toc155608363 .anchor}Figure 4: myclass.hpp Snapshot

Generate the makefile by running the following command in the terminal:

cmake .

Build the program by running the following command,

make

Finally, run the program by running the following command,

./run

When the CMake functions correctly, the program will ask you to enter
the year and based on the year entered, you will be getting an answer.
The example is shown in the picture below.

![](media/image8.png){width="4.640820209973754in"
height="2.7304352580927382in"}

[]{#_Toc155608364 .anchor}Figure 5: Terminal window Snapshot
