# **SW Packaging  
  
Conan**

<table>
<tbody>
<tr class="odd">
<td><strong>Creation date:</strong></td>
<td>24.01.2024</td>
</tr>
<tr class="even">
<td><p><strong>Version 1.0:</strong></p>
<p><strong>Author:</strong></p></td>
<td><p>24.01.2024</p>
<p>Chiragkumar Patel</p></td>
</tr>
</tbody>
</table>

# **Table of contents**

[1. Introduction 2](#introduction)

[1.1 What is Conan? 2](#what-is-conan)

[1.2 Key Features 2](#key-features)

[1.3 Why to use Conan? 2](#why-to-use-conan)

[2. Getting Started 3](#getting-started)

[2.1 Installation 3](#installation)

[2.2 Basic Concepts 3](#basic-concepts)

[2.3 Configuring Conan 3](#configuring-conan)

[3. Creating a Conan Package 4](#creating-a-conan-package)

[3.1 Package Recipe 4](#package-recipe)

[3.2 Building Package 4](#building-package)

[3.3 Uploading Package 5](#uploading-package)

[4. Working with Remote Repositories
5](#working-with-remote-repositories)

[5. Integration with CMake 5](#integration-with-cmake)

[6. Build and test Conan Packages 6](#build-and-test-conan-packages)

[7. Conan Project Structure 6](#conan-project-structure)

[8. A simple Conan Example 8](#a-simple-conan-example)

[8.1 Project Structure 8](#_Toc156382423)

[8.2 Project Files 8](#project-files)

[8.3 Build & Test 11](#build-test)

**<span class="underline">Purpose:</span>**

*The purpose of this documentation is to empower developers with the
knowledge and skills needed to effectively use Conan for software
packaging on Ubuntu, fostering a more efficient and collaborative
development environment.  
*

## Introduction

### What is Conan?

In the realm of C and C++ development, efficient package management is
paramount. This comprehensive guide dives into the world of software
packaging, focusing on the Conan package manager and its seamless
integration with the Ubuntu platform. From installation to repository
upload, developers will gain a deep understanding of how to harness the
power of Conan for their projects.

Conan, a decentralized package manager, revolutionizes the way C and C++
dependencies are managed. Unlike traditional package managers, Conan
empowers developers to create, share, and consume packages with ease,
fostering reusability and consistency across different environments.

### Key Features

  - Decentralized Nature

> Conan's decentralized approach liberates developers from a
> single-source dependency model. Instead, it allows the retrieval of
> dependencies from various repositories or even locally. This
> flexibility accommodates diverse project requirements and fosters a
> more modular and adaptable development ecosystem.

  - Cross-Platform Support

> Conan shines in its ability to provide consistent support across
> different operating systems. Whether your project is targeting
> Windows, Linux, macOS, or other platforms, Conan ensures a unified
> approach to managing dependencies, reducing platform-specific
> complexities.

  - Dependency Management Mastery

> Conan excels in navigating the intricate landscape of dependency
> management. It possesses the intelligence to handle version conflicts,
> resolve dependencies, and manage diverse build configurations
> seamlessly, ensuring a smooth and reliable development experience.

### Why to use Conan?

Conan becomes indispensable in scenarios where C and C++ developers face
challenges related to library compatibility, version mismatches, and
complex build configurations. By embracing Conan, developers pave the
way for more streamlined, reproducible, and manageable builds, enhancing
overall project reliability.

## Getting Started

### Installation

To embark on the Conan journey, you first need to install it on your
development machine. You can install Conan in your Ubuntu system by
using following pip command:

pip install conan

### Basic Concepts

  - Packages

> In Conan, a package is a unit of distributable software, including
> compiled binaries, headers, and any necessary files. Think of it as a
> neatly wrapped box containing everything your project needs from a
> specific library.

  - Package Recipes

> A package recipe is a set of instructions on how to build and package
> a library. It's like a cooking recipe that details the ingredients
> (source code, dependencies) and the steps to produce the final dish
> (compiled binaries).

### Configuring Conan

Configuring Conan involves creating a conanfile.txt or conanfile.py file
in your project directory. This file specifies your project's
dependencies, settings, and options. Let's look at a basic
“conanfile.txt” example:

> \[requires\]
> 
> mylibrary/1.0@
> 
> \[generators\]
> 
> cmake

Here, we declare a dependency on a hypothetical library named
“mylibrary” version 1.0. The “generators” section indicates that we
want to generate CMake files for our project.

## Creating a Conan Package

### Package Recipe

Creating a Conan package involves crafting a package recipe. Let's take
a simple example of a “conanfile.py” for a hypothetical “mylibrary”:

> from conans import ConanFile, CMake
> 
> class MyLibraryConan(ConanFile):
> 
> name = "mylibrary"
> 
> version = "1.0"
> 
> settings = "os", "compiler", "build\_type", "arch"
> 
> generators = "cmake"
> 
> requires = "boost/1.75.0"
> 
> def build(self):
> 
> cmake = CMake(self)
> 
> cmake.configure()
> 
> cmake.build()
> 
> def package(self):
> 
> self.copy("\*.h", dst="include", src="include")
> 
> self.copy("\*.lib", dst="lib", keep\_path=False)
> 
> self.copy("\*.dll", dst="bin", keep\_path=False)

This “conanfile.py” describes how to build and package the “mylibrary”
project. It declares settings, specifies the build system (CMake), and
defines how to copy files during the packaging process.

### Building Package

To build the package, execute the following command in the directory
containing your “conanfile.py”:

conan create . user/channel

This command tells Conan to create a package using the recipe in the
current directory and to upload it to the specified user/channel on a
remote repository.

### Uploading Package

Once your package is built, you might want to share it. To upload the
package to a remote repository:

conan upload mylibrary/1.0@user/channel --all

This uploads all package configurations (“—all”) for the “mylibrary”
version 1.0 to the specified user/channel on the remote repository.

## Working with Remote Repositories

  - Create a remote Repository using:

> conan remote add my\_remote <http://myrepo.com>
> 
> This adds a remote named “my\_remote” with the URL <http://myrepo.com>

  - After building your package, publish it to the remote repository:

> conan upload mylibrary/1.0@user/channel --all -r=my\_remote
> 
> This uploads all configurations of the “mylibrary” version 1.0 to the
> remote named “my\_remote”.

  - Accessing Remote Package

> To use packages from a remote repository, configure a Conan setup:
> 
> conan remote add my\_remote <http://myrepo.com>
> 
> Now, when you declare dependencies in your project, Conan will look
> for them in your added remote repository.

## Integration with CMake

Conan integrates smoothly with CMake. Create a “CMakeLists.txt” file
like this:

> project(MyProject)
> 
> include(${CMAKE\_BINARY\_DIR}/conanbuildinfo.cmake)
> 
> conan\_basic\_setup()
> 
> add\_executable(myapp main.cpp)
> 
> target\_link\_libraries(myapp ${CONAN\_LIBS})

This CMake file includes Conan-generated information and links the
executable with the libraries specified in your Conan dependencies.

## Build and test Conan Packages

Create a build directory:

mkdir build && cd build

Generate the build files using CMake:

cmake ..

Build the project:

cmake --build .

Run the executable:

./Executable

Create a build directory for the test package:

mkdir test\_package/build && cd test\_package/build

Generate the build files for the test package:

conan install ..

cmake ..

Build and run the test package:

cmake --build .

./bin/test\_package

## Conan Project Structure

The project structure for a Conan package typically follows a standard
layout. Here's a basic project structure for a Conan package:

> my\_conan\_package/
> 
> ├── conanfile.py
> 
> ├── test\_package/
> 
> │ ├── conanfile.py
> 
> │ └── test\_package.cpp
> 
> ├── src/
> 
> │ └── my\_library\_source\_files.cpp
> 
> ├── include/
> 
> │ └── my\_library\_header\_files.h
> 
> ├── test/
> 
> │ └── unit\_tests.cpp
> 
> ├── build/
> 
> ├── CMakeLists.txt
> 
> └── README.md

Let's go through each component of the files in project structure:

  - conanfile.py:

> This is the main configuration file for your Conan package. It
> contains information about your package, its dependencies, build
> settings, and any other necessary configurations.

  - test\_package/:

> This directory contains a minimal Conan package recipe and a simple
> test application. The test application may include the main
> functionality of your library or at least cover basic use cases.

  - src/:

> This directory contains the source code of your library or project.
> Include all your library's source files here.

  - include/:

> This directory contains header files for your library. If your library
> is a header-only library, this directory may be the same as the src/
> directory.

  - test/:

> This directory contains additional test files, such as unit tests,
> that are separate from the test\_package/ directory. These tests may
> cover more extensive cases and are not meant to be included in the
> package itself.

  - build/:

> This directory is used for the build artifacts. When building the
> package, Conan may generate build files, and they are typically placed
> in this directory.

  - CMakeLists.txt:

> If you're using CMake to build your project, include a CMakeLists.txt
> file for building your library. This file should define how to compile
> your library and set any necessary compiler flags.

  - README.md:

> A documentation file that provides information about your library, how
> to use it, and any other relevant details.

## A simple Conan Example

<span id="_Toc156382423" class="anchor"></span>This project demonstrates
a simple C++ application structured with Conan, CMake, and a
hypothetical library named "mylib". The C++ program uses the "mylib"
library that we have defined. We'll assume that the "mylib" library
provides a simple function that prints a message. Let’s understand this
by a simple program to print “Hello from mylib\!”.

### Project Structure

The project structure would be,

> Conan\_Project/
> 
> ├── CMakeLists.txt
> 
> ├── app.cpp
> 
> ├── conanfile.py
> 
> └── src/
> 
> ├── CMakeLists.txt
> 
> ├── mylib.h
> 
> └── main.cpp

### Project Files

Enter the following code in the project files. main.cpp, myclass.hpp and
myclass.cpp are same as we have used in CMake example.

  - mylib.h

> // src/mylib.h
> 
> \#pragma once
> 
> \#include \<iostream\>
> 
> void mylib\_print\_message() {
> 
> std::cout \<\< "Hello from mylib\!" \<\< std::endl;
> 
> }

  - conanfile.py

> \# conanfile.py
> 
> from conans import ConanFile, CMake
> 
> class MyLibConan(ConanFile):
> 
> name = "mylib"
> 
> version = "1.0.0"
> 
> settings = "os", "compiler", "build\_type", "arch"
> 
> generators = "cmake"
> 
> def build(self):
> 
> cmake = CMake(self)
> 
> cmake.configure()
> 
> cmake.build()
> 
> def package(self):
> 
> self.copy("\*.h", dst="include", src="src")
> 
> self.copy("\*.lib", dst="lib", keep\_path=False)
> 
> self.copy("\*.dll", dst="bin", keep\_path=False)
> 
> self.copy("\*.so", dst="lib", keep\_path=False)
> 
> self.copy("\*.dylib", dst="lib", keep\_path=False)
> 
> self.copy("\*.a", dst="lib", keep\_path=False)

  - CMakeLists.txt for Library

> \# CMakeLists.txt for mylib
> 
> cmake\_minimum\_required(VERSION 3.12)
> 
> project(MyLib)
> 
> add\_library(mylib mylib.h)

  - main.cpp for Library

> // src/main.cpp
> 
> \#include "mylib.h"
> 
> int main() {
> 
> mylib\_print\_message();
> 
> return 0;
> 
> }

  - CMakeLists.txt for the project

> \# CMakeLists.txt for the project
> 
> cmake\_minimum\_required(VERSION 3.12)
> 
> project(MyConanProject)
> 
> include(${CMAKE\_BINARY\_DIR}/conanbuildinfo.cmake)
> 
> conan\_basic\_setup(TARGETS)
> 
> add\_subdirectory(src)
> 
> add\_executable(myapp app.cpp)

  - app.cpp

> // app.cpp
> 
> \#include "mylib.h"
> 
> int main() {
> 
> mylib\_print\_message();
> 
> return 0;
> 
> }

### Build & Test

Install Dependencies and generate build files with Conan

conan install .

Build the project with CMake

cmake .

cmake --build .

Run the executable

./bin/myapp

You should see the output: “Hello from mylib\!”
