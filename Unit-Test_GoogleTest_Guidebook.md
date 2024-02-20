# **Google Tests - Unit-Test  
**

# **Standard Tool Guidebook**

| **Department:**        | Defense              |
| ---------------------- | -------------------- |
| **Team:**              | Software Development |
|                        |                      |
|                        |                      |
| **Department Leader:** | SCHEFFING, Andreas   |
| **Team Leader:**       | PANCHAL, Parth       |
|                        |                      |
|                        |                      |
|                        |                      |
|                        |                      |
|                        |                      |
| **Creation date:**     | 00.00.000            |
| **Version:**           | 1.0                  |

# **Table of contents**

[1. General 1](#general)

[About the guidebook 1](#about-the-guidebook)

[2. Installation 1](#installation)

[3. Preparing a Class 1](#preparing-a-class)

[4. Preparing a Test File 2](#preparing-a-test-file)

[5. Preparing a CMakeLists.txt File 3](#preparing-a-cmakelists.txt-file)

[6. Executing a Unit-Test 4](#executing-a-unit-test)

## General

### About the guidebook

This guidebook goes through the steps necessary to execute a Unit-Test
for C++ code using Google Tests. It covers everything from installation
all the way to preparing and executing a test.

## Installation

We have used the Unix system example for this document. The setup needs
root access to run some installations. In real world scenario, this is
highly likely that the customer VMWare Image is already prepared to
handle this task.

Following steps mentioned above will make the necessary installation.
First command only gets the necessary tools and sources for compiling
gtest-suit.

## Preparing a Class

Below is an example of a new class where we have 2 public methods for
math operations. Save this file as calculator.cpp in the project folder.

## Preparing a Test File

To test the function from the Calculator class defined in
calculator.cpp, make a new file with name testcase.cpp in the same
project folder. Following is the code which shall be used in the current
scenario for this example.

This block of code defines a test case using the TEST macro provided by
Google Test. The first argument to TEST is the test suite name
(CalculatorTest in this case), and the second argument is the name of
the individual test case (Addition in this case).

Inside the test case, we create an instance of the Calculator class
using the following command:

Calculator calculator;

Then, we call the add function on the calculator object with arguments 2
and 3 and store the result in the result variable. Finally, we use the
ASSERT\_EQ macro to compare the result with the expected value 5. If the
comparison fails, the test case will fail, and an appropriate error
message will be displayed.

## Preparing a CMakeLists.txt File

A CMakeLists.txt file is used to configure the CMake build system for
your project. It describes how your project should be built, including
source files, dependencies, compiler options, and other build settings.
Here is our CMakeLists.txt for this project. This file can be hosted
alongside the sources, but we recommend making a directory – build
inside the project folder and host the file there.

## Executing a Unit-Test

Open the terminal and change the directory to the build in the project.
What command are to be followed is given in the code block below.

After this the executable is available in the build directory. Run this
and it will print the result on the terminal for the unit-tests.
