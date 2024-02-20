Coding Standards and Guidelines for C++

> **Kunde:** Intern
> 
> **Integrationstermin:** 19.06.2023

| **Projektleader:**    | Parth Panchal     |
| --------------------- | ----------------- |
| **Abteilungsleiter:** | Andreas Scheffing |
|                       |                   |
| **Entwickler:**       | Ravi Jayanagara   |
|                       |                   |
|                       |                   |
| **Erstellungsdatum:** | 29.06.2023        |
| **Versionsnummer:**   | 1.2               |

|  |
|  |
|  |

**Revision Details**

| **Rev** | **Description** | **Date**   |
| ------- | --------------- | ---------- |
| 1.0     | Draft Version   | 13.06.2023 |
|         |                 |            |

**  
**

**Table of Contents**

# 

# Contents

[**1.** PURPOSE 3](#purpose)

[**2.** SCOPE 3](#scope)

[**3.** RESPONSIBILITY 3](#responsibility)

[**4.** REFERENCES 3](#references)

[**5.** ABBREVIATIONS, ACRONYMS, AND DEFINITIONS 3](#_Toc138931685)

[**6.** REQUIREMENTS 4](#requirements)

[6.1 Standards for Source Code 4](#standards-for-source-code)

[6.1.1 File Standards 4](#file-standards)

[6.1.2 Function/Routine Standards 6](#functionroutine-standards)

[6.1.3 Variable Naming Standards 7](#variable-naming-standards)

[6.1.4 C++ Language Coding Standards 7](#c-language-coding-standards)

[**7.** PROCESS FOR DEVIATIONS / EXCEPTIONS
24](#process-for-deviations-exceptions)

# List Of Tables

Table 1: Reference Documents 3

Table 2: Abbreviations, Acronyms, and Definitions 3

Table 3: C++ Basic Type Naming Conventions 13

**  
**

# PURPOSE

The purpose of this Work Instruction (WI) is to establish the C++ and
Assembly programming language coding standards to be used in the
development of software for systems developed by Akkodis Consultancy
GmbH and to provide the criteria for acceptability for software source
code in compliance with applicable supplements.

# SCOPE

The standards within this Work Instruction apply to software developed
by the Akkodis Consultancy GmbH for use in commercial/military systems
in the C++ and/or Assembly programming languages.

# RESPONSIBILITY

The software organization is responsible for the implementation and
management of this Work Instruction.

# REFERENCES

<table>
<thead>
<tr class="header">
<th><strong>Document Number</strong></th>
<th><strong>Document Title</strong></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td>MISRA C++:2008</td>
<td>Guidelines for the use of the C++ language in critical systems<br />
The Motor Industry Software Reliability Association, June-2008.</td>
</tr>
<tr class="even">
<td>AUTOSAR</td>
<td>Guidelines for the use of the C++14 language in critical and safety-related systems, March-2017</td>
</tr>
<tr class="odd">
<td>ISO/IEC 14882:2014</td>
<td>ISO International Standard ISO/IEC 14822:2014(E) "Information technology - Programming languages -C++".</td>
</tr>
<tr class="even">
<td>IEEE Std 754-1985</td>
<td>IEEE Standard for Binary Floating-Point Arithmetic</td>
</tr>
</tbody>
</table>

<span id="_Toc138931685" class="anchor"></span>Table 1: Reference
Documents

# ABBREVIATIONS, ACRONYMS, AND DEFINITIONS

| **Item** | **Meaning**                                          |
| -------- | ---------------------------------------------------- |
| ANSI     | American National Standard for Programming Languages |
| ASM      | Assembly                                             |
| CSCI     | computer software configuration item                 |
| EAR      | Export Administration Regulations                    |
| IEC      | International Electrotechnical Commission            |
| IEEE     | Institute of Electrical and Electronics Engineers    |
| ISO      | International Organization for Standardization       |
| MISRA    | Motor Industry Software Reliability Association      |
| MMU      | Memory Management Unit                               |
| NaN      | Not a Number                                         |
| PRO      | Procedure                                            |
| SPI      | Serial Peripheral Interface                          |
| SW       | Software                                             |
| WI       | Work Instruction                                     |

Table 2: Abbreviations, Acronyms, and Definitions

# REQUIREMENTS

The primary goal of these coding standards and guidelines is to increase
the readability, portability, maintainability, reusability and
reliability of the source code product. In addition, adherence to these
standards will expedite acceptance of the system by certification
authorities by eliminating software language features identified as
unsafe or otherwise certification sensitive.

Coding standards were developed to minimize risk of unforeseen errors in
the source code; however, strict adherence to these standards does not
ensure error-free code.

The standards (i.e., the rules enforced by the checklist) are contained
within the various REQUIREMENT boxes. Rationale and explanation for the
standards is provided in the same section below.

## Standards for Source Code

### File Standards

This section outlines general rules for source code files regardless of
the language used. These rules apply to all manually written (i.e.,
hand-coded) software source files, including source code and
header/include files.

#### File Comment Block

REQUIREMENT

1\. Each software source file shall have a file comment block

at the beginning of the file containing the following information:

> • Copyright Statement
> 
> • File information
> 
> • Description
> 
> • Changes

Rule (1) – Each software file (i.e., header/include, source code,
supporting file) must have a file comment block at the beginning of the
file to aide in orienting the reader to the file’s contents, purpose,
and development history, as well as protect the company’s intellectual
property and comply with governmental export regulations. The Copyright
statement is controlled and approved by the company’s legal
organization. Any and all text-based software files (e.g., configuration
files) needed to create the executable software should contain a file
comment block, unless a file comment block is prohibited by the tool or
interferes with the tool’s usage of the file. Refer to 1.1.1.1APPENDIX A
for example templates for manually written source code. The following
guidelines should be used for the content of the file comment block:

> • File information – This should contain the source code Project,
> filename, revision, author, and date.
> 
> • Description – This should provide a high-level description of the
> purpose and function of the source code contained in the file.

• Revision History – A brief list of changes made to the file.

#### File Naming Conventions

REQUIREMENT

1\. Each C++ language source code file shall have a file extension of
“.cpp”.

2\. Each C++ language header file shall have a file extension of “.hpp”.

3\. Each Assembly language source/include file shall have the file
extensions expected by the assembler.

4\. The set of files which implement a software module shall be
associated by name.

5\. Each filename (header, source code, or supporting files) shall be
named as follows:

a. Using mixed-case notation with a single uppercase letter at word
breaks.

b. Acronyms within the filename are all uppercase separated by a single
underscore character.

6\. Each filename shall begin with an alphabetic character.

7\. The filename of the C++ source code file containing the entry point
for a computer software configuration item (CSCI) shall contain the word
“Main”.

Rule (1), Rule (2), Rule (3) – Consistency in file name extensions makes
the source code files easily identifiable and avoids confusion about
which tool should be used to work with the file. It is recommended to
separate the header files and source code files into separate
subdirectories, especially if the set of header files contains the
external API for a CSCI. Oftentimes manufacturers supply source code
files for use in development (e.g. header files with structure types for
accessing the processor registers). As an exception to the file naming
rules, if tool vendor files are utilized, it is recommended to retain
the original file names and extensions, unless changing them aids in
clarity.

Rule (3) – The preferred file extensions for various Assemblers vary
based on the target computer. If the assembly tools do not mandate a
specific extension naming, the assembly header files should have the
filename extension “.inc” and the assembly source code files should have
the filename extension “.asm”.

Rule (4) – If a software module is implemented in multiple files (e.g.
C/Assembly, code/header/include), then all files associated with the
software module should be associated by name. What this means is that
some part of the filenames of all associated files should be the same.
Associating files by name helps in navigating and managing the software.
For example, the software files which implement the SPI driver, could be
associated by name as SPI.cpp, SPI.hpp, SPI\_Tables.cpp, and
SPI\_Types.hpp, where “SPI” is the name association.

Rule (5), Rule (6) – File naming conventions help provide context and
understanding to a software function as well as ensure compatibility
with development and configuration management tools. It is recommended
that filenames begin with an uppercase alphabetic character (i.e. “A”
through “Z”), but beginning with any alphabetic character is acceptable.
Consistent file naming allows source code files associated with a
function to be accessed much more quickly, since they will generally be
sorted and displayed near each other in the file system(s) they exist
in. Consistency throughout the entire software project is very important
to realize the benefits of file naming conventions. Often target
computer manufacturers supply source code files for use by developers
(such as a header file defining types to access the processor
registers). For manufacturer-provided source code files, the original
filenames should be retained, unless there are particular conflicts with
the build tools or the names create confusion with other
non-manufacturer-provided source code files.

Rule (7) – The software build tools for a C++ language project require a
function “main()” to serve as the execution entry point for each
software application. The “main()” entry point function should be
contained within a separate source code file whose filename contains the
word “Main”, so as to identify and isolate this required function for
ease in debugging and verifying the software.

Example C++ language source code filenames:

Interrupt.hpp, NVM\_Reset.cpp, NVM.hpp, NVM.cpp, SpeedRegulator.cpp

Example Assembly filenames:

SS\_API\_Table.asm, SS\_API\_Types.inc.

#### File Formatting

REQUIREMENT

1\. Source code shall be consistently formatted such that is it easy to
read.

2\. Each statement shall start on a new line.

Rule (1), Rule (2) – One of the primary contributors to coding mistakes
is poor readability of the source code. Indentation and alignment of
braces helps to make is clearly visible the scope of a construct or
function, especially when there is nested conditional logic. To provide
consistency in file formatting and enhance readability of the source
code the following best practices should be adhered to:

• Nested constructs shall be aligned and indented using spaces.

> • Keywords and operators should have one or more space(s) before and
> after, except for pointer and unary operators.
> 
> • The line length should not exceed 80 characters and should end with
> a hard carriage return. This is more of a goal than a rule, meaning it
> is acceptable to exceed 80 characters if doing so improves
> readability.
> 
> • Code modules should be formatted such that the code is readable when
> printed and viewed in any editor. Tab characters should not be used in
> source code files. The use of tabs causes the source code alignment to
> vary depending on the editor configuration, which decreases
> readability and defeats the purpose of the indentation formatting
> standards. Spaces (i.e. blank space characters) should be used instead
> of tabs, since they are displayed consistently in all editors.
> 
> • Each level of indentation should be indented with 2-4 spaces
> (whatever is used should be consistently applied).
> 
> • All logical blocks should be separated by at least one blank line.
> 
> • Indentation, blank lines, and comments should be used to make the
> code more readable and understandable.

###  Function/Routine Standards

#### Function/Routine Comment Block

REQUIREMENT

1\. All functions/routines shall have a comment block immediately before
the function/routine that contains the following information:

• Function/Routine Name

• Description.

Rule (1) - Function comment blocks (a.k.a. function headers) are
intended to aid in the understanding of each function by assuring that
critical information about the function is presented in a consistent
format.

> • If a function parameters section is included in the header, the
> function parameters section should identify each parameter, including
> name, type, description, and units (if applicable).
> 
> • If a global inputs and outputs section is included in the header,
> the global inputs and outputs section should identify each global data
> item and type that is used by the function.
> 
> • If a return parameter section is included in the header, the return
> parameter section should identify the return parameter type and
> provide a description of the return parameter.
> 
> • If a prerequisites section is included in the header, the
> prerequisites section should list events that need to occur before the
> function can be called.
> 
> • If a constraints section is included in the header, the constraints
> section should identify any conditions or limitations imposed upon the
> function which constrain its implementation (timing, memory, response
> time, synchronization, order of execution, etc.).

###  Variable Naming Standards

Source code data/variable names affect the ease of understanding of the
source code. Variable names should be chosen according to the following
criteria:

> • Member variables from a class should start with “m\_” to indicate
> that they are not local variables.  
> Ex.: m\_bSystemStatus
> 
> • Variables should be named using the camel case convention, starting
> with lower case.  
> Ex.: bThisIsAVariable
> 
> • Variables should have a “type identifier” at the beginning of its
> name. This helps the programmer to easily identify its data type and
> consequently better understand the code. Ex.:

| **Bool**        | **b**Variable   |
| --------------- | --------------- |
| **Integer**     | **n**Variable   |
| **Double**      | **d**Variable   |
| **Float**       | **f**Variable   |
| **String**      | **str**Variable |
| **Struct**      | **s**Variable   |
| **Enumeration** | **e**Variable   |
| **Pointer**     | **ptr**Variable |
| **Vector**      | **v**Variable   |

> • Consistent with the low-level requirements. To make it easy to
> correlate and search for signals used in the requirements, it is a
> best practice to use identical variable names to the signal names used
> in the requirements, where feasible. The signal naming standards
> within the Software Requirements Standards and Guidelines should be
> used as a guide when naming source code variables and constants. It is
> understood that the use of data structures as well as language syntax
> constraints may make it impossible to maintain the variable names
> exactly matching to the signal names in the requirements. For example,
> if an array or structure is used, it will require the addition of
> dereferencing operators and/or removal/addition of a portion of the
> signal name used in the requirements.
> 
> • Easily distinguished from other variables in the same scope. The use
> of longer variable names that are only distinguished by a single
> character or characters which look similar is highly discouraged. For
> example, the variable names “UpperThresholdLimitO” and
> “UpperThresholdLimit0” would not be appropriate in the same scope,
> as these variable names are very difficult to distinguish.

###  C++ Language Coding Standards

#### Standards

All source code shall conform to the MISRA C++:2008 Guidelines for the
use of the C++ language in critical systems and AUTOSAR: Guidelines for
the use of the C++14 language in critical and safety-related system
listed in 1.1.1.1APPENDIX A.

An automated qualified tool should be used to check the MISRA C++:2008
Guidelines for the use of the C++ language in critical systems and
AUTOSAR: Guidelines for the use of the C++14 language in critical and
safety-related system listed in 0. It is preferable to have all
“Mandatory”, “Required” and “Advisory” rules as the basis of
compliance.

The document Refers to Standards and rules of both the documents, the
Prefix under rule starts with

a. “Rule/M” referred for MISRA C++:2008 Guidelines for the use of the
C++ language in critical systems.

b. “A” referred for AUTOSAR: Guidelines for the use of the C++14
language in critical and safety-related system.

#### General

**Rule A1-1-1** (required, implementation, automated)

*All code shall conform to ISO/IEC 14882:2014 - Programming Language C++
and shall not use deprecated features.*

**Rule M1-0-2** (required, implementation, non-automated)

*Multiple compilers shall only be used if they have a common, defined
interface.*

**Rule A1-1-2** (required, toolchain, non-automated)

*A warning level of the compilation process shall be set in compliance
with project policies.*

**Rule A1-1-3** (required, implementation, automated)

*An optimization option that disregards strict standard compliance shall
not be turned on in the chosen compiler.*

**Rule A1-2-1** (required, implementation, non-automated)

*When using a compiler toolchain (including preprocessor, compiler
itself, linker, C++ standard libraries) in safety-related software, the
tool confidence level (TCL) shall be determined. In case of TCL2 or
TCL3, the compiler shall undergo a “Qualification of a software tool”,
as per ISO 26262-8.11.4.6 \[5\].*

**Rule A1-4-1** (required, implementation, non-automated)

*Code metrics and their valid boundaries shall be defined.*

**Rule A1-4-2** (required, implementation, non-automated)

*All code shall comply with defined boundaries of code metrics.*

For detailed rules Refer AUTOSAR C++ 2017 \[6.1\]., Refer MISRA C++ 2008
\[6.5\].

#### Comments

REQUIREMENT

1\. Code comments shall be used to describe functionality, to explain
the purpose of variables and constants, and to aid in the understanding
of the code.

Rule (1) - Comments or blocks of comments should be present throughout
the code. The programmer should use a consistent comment style. To
ensure that there are sufficient comments, the total number of source
code comment lines should be at least 20% of the total number of source
code lines. The comments should provide additional understanding to the
source code instructions (e.g. not say things that are self-evident like
“initialize XYZ variable to 0”). Comments should not describe values if
the values do not exist directly in the code being described (e.g. do
not say “check the 10 knot limit” if the value of 10 knots is actually
defined elsewhere).

The following examples demonstrate the desired style for comments:

Example 1 – Comments for Declarations

> // This is an example of a multi-line comment about
> 
> // the myData\[\] constant array which contains the data
> 
> // initialization values for the CAN interface.
> 
> const EXAMPLE\_DATA\_STRUCT canConfigData\[MAX\_DATA\_ITEMS\] =
> 
> {
> 
>    // enable, rxData
> 
>    {TRUE,  {0x1A00, 0x001A, 0xFACE}}     // 0x1A00 - Setup for TX Mode
> 
>                                          // 0x001A - Config for 26
> Mailboxes
> 
>                                          // 0xFACE - Config for smile
> mode.\*/
> 
> };
> 
> Example 2 – Comments for Functions
> 
> //
> \*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*
> 
> // FUNCTION NAME:
> 
> //    CanDriver\_Initialize
> 
> //
> 
> // DESCRIPTION:
> 
> //     This function initializes the CAN interface. This consists of
> the
> 
> //     following tasks:
> 
> //     1. Clearing all message buffers.
> 
> //     2. Setting all register settings to the initial CAN Config
> values.
> 
> //
> \*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*
> 
> void CanDriver\_Initialize(void)
> 
> {
> 
>    CSA\_UINT32 index;
> 
>    // Initialize all entries within the message buffer to default
> values.
> 
>    for (index=0;                      // Start at first element
> 
>         index \< MAX\_BUFFER\_SIZE;      // Constrain loop to array
> size
> 
>         index++)
> 
>    {
> 
>       canData.msgBuffer\[index\].msgId   = 0;
> 
>       canData.msgBuffer\[index\].msgType = xx;
> 
>       canData.msgBuffer\[index\].data    = 0;
> 
>    } // end for
> 
>    // Initialize messaging data control parameters
> 
>    canData.msgBufferIdx = NULL\_PTR;
> 
>    canData.fifoIdx = 0;
> 
> } // end function CanDriver\_Initialize()

Rule **A2-8-1** (required, implementation, automated)

*The character \\ shall not occur as a last character of a C++ comment.*

Rule **A2-8-2** (required, implementation, non-automated)

*Sections of code shall not be “commented out”.*

Rule **A2-8-3** (required, implementation, automated)

*All declarations of “user-defined” types, static and non-static data
members, functions and methods shall be preceded by documentation using
“///”comments and “@tag” tags.*

Rule **A2-8-4** (required, implementation, automated)

*C-style comments shall not be used.*

For detailed rules Refer AUTOSAR C++ 2017 \[6.2.8\].

#### Function Formatting

REQUIREMENT

1\. Function parameters shall be separated by a comma followed by a
single space or aligned vertically on separate lines.

2\. Braces at the starting and ending of functions or code blocks shall
be aligned with the first character of the current level of code and on
a line by themselves.

3\. Functions shall always be declared at file scope.

Rule (1) – Consistent formatting in the source code in the function
parameters definition enhances understanding of the function interface.
The following guidelines should be followed for function parameters:

> • Function prototypes and function declarations containing more than 3
> parameters should place each parameter on its own line, with all
> function parameters being aligned vertically.
> 
> • Any function parameter that is passed by reference and is not
> intended to have its value modified should be defined using the const
> qualifier.

• Functions with a variable number of arguments should not be used.

Rule (2) - The following source code formatting guidelines for the use
of braces should be adhered to within functions:

> • Loop and conditional statements should be aligned with the beginning
> of the previous line for clarity.
> 
> • Opening and closing braces should be aligned with the first
> character of the parent construct.
> 
> • Source code statements within the function should be aligned within
> the opening and closing braces at one level of indentation from the
> opening brace.
> 
> • The case labels in a switch statement should be indented one level;
> with the case code indented another level.

• Closing braces should have a comment field describing what they close.

Rule (3) – Declaring all functions at file scope will ensure that access
to all functions for verification purposes is achieved. It will also
ensure that all functions are visible and uniquely named across the
software project.

Example of switch statement formatting:

> switch(x)
> 
> {
> 
>     case 1:                 // Complaint
> 
>         // Do Something...
> 
>         //...
> 
>         break;
> 
>     case 2:
> 
>         if\*(...){
> 
>             case 3:        // Non-Complaint  
> 
>             DoIt();
> 
>         }
> 
>         break;
> 
>    
> 
>     default:
> 
>         // Do Something...
> 
>         //...
> 
>         break;
> 
> } /\* end switch \*/

For detailed rules Refer AUTOSAR C++ 2017 \[6.6\].

Example of for loop formatting:

> \#include \<cstdint\>
> 
> \#include \<iterator\>
> 
> void fn() noexcept
> 
> {
> 
>     constexpr std::int8\_t arraySize = 7;
> 
>     std::uint32\_t array\[arraySize\] = {0, 1, 2, 3, 4, 5, 6};
> 
>     for (std::int8\_t idx = 0; idx \< arraySize; ++idx) // Compliant
> 
>     {
> 
>         array\[idx\] = idx;
> 
>     }
> 
>     for (std::int8\_t idx = 0; idx \< arraySize / 2;
> 
>     ++idx) // Compliant - for does not loop though all elements
> 
>     {
> 
>         // ...
> 
>     }
> 
>     for (std::uint32\_t\* iter = std::begin(array); iter \!=
> std::end(array);
> 
>     ++iter) // Non-compliant
> 
>     {
> 
>         // ...
> 
>     }
> 
>     for (std::int8\_t idx = 0; idx \< arraySize; ++idx) //
> Non-compliant
> 
>     {
> 
>         // ...
> 
>     }
> 
>     for (std::uint32\_t value :
> 
>     array) // Compliant - equivalent to non-compliant loops above
> 
>     {
> 
>         // ...
> 
>     }
> 
>     for (std::int8\_t idx = 0; idx \< arraySize; ++idx) // Compliant
> 
>     {
> 
>     if ((idx % 2) == 0)
> 
>         {
> 
>             // ...
> 
>         }
> 
>     }
> 
> }

For detailed rules Refer AUTOSAR C++ 2017 \[6.6.5\].

Example of function declaration:

> \#include \<cstdint\>
> 
> std::int32\_t pow1(std::int32\_t number)
> 
> {
> 
>     return (number \* number);
> 
> }
> 
> constexpr std::int32\_t pow2(
> 
> std::int32\_t number) // Possible compile-time computing
> 
> // because of constexpr specifier
> 
> {
> 
>     return (number \* number);
> 
> }
> 
> void fn()
> 
> {
> 
>     constexpr std::int16\_t i1 = 20; // Compliant, evaluated at
> compile-time
> 
>     const std::int16\_t i2 = 20; // Non-compliant, possible run-time
> evaluation
> 
>     std::int32\_t twoSquare =
> 
>     pow1(2); // Non-compliant, possible run-time evaluation
> 
>     const std::int32\_t threeSquare =
> 
>     pow1(3); // Non-compliant, possible run-time evaluation
> 
>     // static\_assert(threeSquare == 9, "pow1(3) did not succeed.");
> // Value
> 
>     // can not be static\_assert-ed
> 
>     constexpr std::int32\_t fiveSquare =
> 
>     pow2(5); // Compliant, evaluated at compile time
> 
>     static\_assert(fiveSquare == 25,
> 
>     "pow2(5) did not succeed."); // Compliant, constexpr
> 
>     // evaluated at compile time
> 
>     // constexpr std::int32\_t int32Max =
> 
>     // std::numeric\_limits\<std::int32\_t\>::max() + 1; //
> 
>     // Compliant - compilation error due to
> 
>     // compile-time evaluation (integer overflow)
> 
> }
> 
> class A
> 
> {
> 
>     public:
> 
>     static constexpr double pi = 3.14159265; // Compliant - value of
> PI can be
> 
>     // determined in compile time
> 
>     // constexpr double e = 2.71828182; // Non-compliant - constexprs
> need
> 
>     // to be static members, compilation error
> 
>     constexpr A() = default; // Compliant
> 
> };

For detailed rules Refer AUTOSAR C++ 2017 \[6.7\].

#### Data Type Naming Conventions

Naming conventions for data types provides a common look and feel for
the software source code files and allows for easy navigation.

REQUIREMENT

1\. Type definitions specified in Table 3 shall be used instead of the
C++ basic types

2\. All constants, enumerated types, typedefs and macro names shall use
all uppercase characters, separated by a single underscore character at
word boundaries.

3\. Type definition (i.e. typedef) names shall contain a suffix as
follows:

• Structure: “\_STRUCT”

• Enumerated: “\_ENUM”

• Union: “\_UNION”

• Pointer: “\_PTR”.

Rule (1) – The physical representation (i.e. size) of the C language
standard types varies based upon the processor architecture (i.e.
processor native bus width). In order to make the C source code portable
between various processor targets, the standard types are re-defined
using the naming conventions listed in Table 3 which include an
indication of the physical representation in the type definition.

Rule (2) – The use of all capital letters and underscores provides a way
to clearly distinguish constant software data from data variables. This
adds clarity in reading the source code, especially in identifying
conditional statement test values. Care must be taken when defining
members of global type structures, enumerations, and macros so as to
avoid conflicts between types used by different software modules within
the system. Generic names such as PASS, FAIL, GOOD, BAD, ERROR, etc…
should be avoided (or defined once within a single global types header
file); otherwise, these names will conflict, since all structure member
names, enumerations, and macros are contained within the global
namespace in C++.

Rule (3) - The addition of a fixed suffix to certain type definitions
increases readability and understanding of the source code. By
identifying each type definition as a structure type, enumerated type,
union type, or pointer type architectural incompatibilities can be more
easily identified and avoided.

Table 3: C++ Basic Type Naming Conventions

| **Type**       | **SIZE (BITS)** | **TYPE DEFINITION** |
| -------------- | --------------- | ------------------- |
| unsigned char  | 8               | UINT8               |
| unsigned short | 16              | UINT16              |
| unsigned int   | 32              | UINT32              |
| unsigned int   | 32 (note 1)     | BOOLEAN             |
| unsigned long  | 64              | UINT64              |
| signed char    | 8               | INT8                |
| signed short   | 16              | INT16               |
| signed int     | 32              | INT32               |
| signed long    | 64              | INT64               |
| Float          | 32              | FLOAT32             |
| Double         | 64              | FLOAT64             |
| (bit field)    | 1 to 32         | N/A                 |

Note 1: The size (in bits) of the BOOLEAN type should be set to the
native size of the processor, which could be 8, 16, 32, 64, etc bits.

#### Hex and Binary numbers representation

REQUIREMENT

1\. Hexadecimal numbers shall be prefixed with the number “0” and the
lower case character “x” with all alphabetical characters (A, B, C, D,
E, F) in uppercase.

2\. Single-precision floating-point constant values shall be suffixed
with the character "f" or “F”.

Rule (1) – Definition and usage of literals in the C language can be
very confusing if the type qualifier is not specified. This rule ensures
the type qualifier for hexadecimal data is “0x”, which eliminates
confusion between decimal, hexadecimal and octal literals.

Examples of hexadecimal and floating point literal usage:

> \#define RadiansToDegrees\_WRONG 57.296f      // Violation – Not all
> capitals
> 
> \#define RAD2DEG\_WRONG          57.296       // Violation – missing
> “f”
> 
> \#define RAD2DEG                57.296f      // Compliant
> 
> \#define AVACADO\_NUM            6.02214E+23f // Compliant
> 
> \#define BIT12\_MASK             0x0800       // Compliant
> 
> \#define REG\_MASK1              x0800        // Violation – missing
> ‘0’
> 
> \#define REG\_MASK1              0x0800       // Compliant
> 
> UINT32  a;
> 
> UINT32  b;
> 
> FLOAT32 c;
> 
> FLOAT32 d;
> 
> a = 0x1234U;                       // Compliant
> 
> a &= \~BIT12\_MASK;                  // Compliant
> 
> c = 25.0f;                         // Compliant
> 
> c |= 2048;                         // Violation – should be 0x0800U
> 
> c \*= RAD2DEG;                      // Compliant
> 
> c += 5.6f;                         // Compliant

#### Declaration

REQUIREMENT

1\. Declaration of data variables shall be compatible with the software
architecture.

Rule (1) – When declaring variables, consideration should be given to
the memory constraints of the software architecture as follows:

> • The allocation of memory for data variables should be verified to be
> within the stack memory allocation under worst-case conditions, so as
> to not cause stack overflow. Since stack memory is usually
> highly-constrained in real-time systems, larger data variables should
> be defined at file scope as static which will allocate them into data
> memory.
> 
> • The register storage class should generally not be used, unless rare
> circumstances require such. In these rare cases, where register
> storage is needed, the compiled output should be analyzed to ensure
> that the required register storage was obtained, since the C keyword
> “register” does not guarantee a register will be used for storing
> the data variable.

For detailed rules Refer AUTOSAR C++ 2017 \[6.7\].and MISRA C++ 2008
\[6.8\].

#### Variable Initialization

REQUIREMENT

1\. Each variable shall be initialized outside of its declaration
statement.

2\. The definition of an enumeration list shall always initialize the
first enumeration constant in the list.

Rule (1) - Variables should not be initialized in the declaration for
the following reasons:

> • Initialization may need to be different depending on whether the
> unit has experienced a cold start or a warm start (hard reset vs. a
> soft reset).
> 
> • This avoids coding mistakes that have occurred in the past due to
> static vs. non-static variable initialization.
> 
> • Initialization at declaration may be incompatible with the software
> architecture. For example, the initialization values for declare-time
> initialization are stored in a separate memory section and this
> initialization may not occur depending on the order of initialization
> of the CSCIs at run-time.

Example of variable initialization:

> FLOAT32 Speed1 = 1.0f;        // Violation – initialized at
> declaration
> 
> FLOAT32 Speed2;               // Compliant
> 
> void initializeSpeeds(void)
> 
> {
> 
> Speed1 = 1.0f;              // Compliant
> 
> Speed2 = 1.0f;              // Compliant
> 
> }

Rule (2) - If an enumerated list is given with no explicit
initialization of members, then C++ allocates a sequence of integers
starting at zero for the first element and increasing by one for each
subsequent element. The following guidelines should be followed for
enumerations:

> • Explicitly initializing the first element, as indicated by the above
> rule, forces the allocation of integers to start at the given value.
> It is the responsibility of the programmer to ensure that no value in
> the list will exceed the int storage used by enumeration constants.
> 
> • Source code which uses enumerated data types should never be
> designed to depend on the numeric value of an enumeration. Use of the
> relational operators “greater than”, “less than” as well as bitwise
> operators (i.e. “|”, “&”, “\~”) are prohibited on enumerated data
> types, because these practices lead to unintended functionality,
> especially when the code is updated and maintained later.

#### Operators

The increment (++) and decrement (--) operators should not be used on
floating point variables. The increment and decrement operators are
applicable to floating point values and will increment or decrement the
floating point variable by 1.0, however this definition is not clear and
may be confusing. The preferred method of incrementing/decrementing
floats is shown below:

> FLOAT32 x = 1.0f; // Violation – initialized at declaration
> 
> FLOAT32 y = 2.0f; // Violation – initialized at declaration
> 
> x += 1.0f;        // Compliant
> 
> x = x - 1.0f;     // Compliant
> 
> y--;              // Violation – use of -- on floating point type
> 
> y++;             // Violation – use of ++ on floating point type
> 
> \++((int)x);       // Violation – Do not use casting to try and
> circumvent this rule.

#### Preprocessor Directives

REQUIREMENT

1\. Preprocessor logic shall be used in each header file to prevent
double-inclusion.

2\. \#define macros shall not be used to define statements or parts of
statements.

3\. \#define directives shall not be placed within a block.

4\. When \#ifdef and \#if are used, the justification for its use shall
be documented and explained.

5\. Each usage of the \#pragma directive shall be documented and
explained.

Rule (1) – Preprocessor directives \#ifndef \<tag\> followed by \#define
\<tag\> and \#endif should be used to prevent multiple inclusion of all
header files. This eliminates conflicts in header inclusion and
eliminates the need to manage the exact inclusion order of all header
files in a project.

Rule (2) - \#define macros should only be used for symbolic constants,
function-like macros, type qualifiers and storage class specifiers. Use
of macros for source code instructions can obfuscate the source code,
decrease readability, and induce functional errors.

Rule (3) Placing \#define directives within a block (e.g. between curly
braces) implies that the macro has a scope restricted to that block.
Macro definitions are independent of block structure and are effective
through the end of the compilation unit or through a corresponding
\#undef. Identifiers in preprocessor directives should be defined before
using \#define. Otherwise, the preprocessor may assume a value for an
undefined identifier in a preprocessor directive.

Rule (4), Rule (5) – Use of preprocessor directives can cause confusion
about the context of definitions and unexpected behavior of source code.
As such, it should be documented and explained in the accompanying
source code comments.

For detailed rules Refer AUTOSAR C++ 2017 \[6.16\].

#### Function-like Macros

REQUIREMENT

1\. All function-like macros shall be documented and explained.

Rule (1) - A function should be used rather than a function-like macro,
wherever possible. While function-like macros can provide a speed
advantage over functions, functions provide a more robust mechanism
especially with respect to type checking parameters. Additionally,
function-like macros often cause verification difficulties for
structural coverage analysis tools. Since macros are inlined during
compilation, most structural coverage tools are unable to instrument the
inlined statements such that structural coverage data can be obtained
during execution.

#### Floating Point usage

When writing code that contains floating point operations, the following
should be considered:

• Values that are input to a calculation are valid (rational, in the
required range, compatible with the data types used within the
calculation).

• Values that are produced by a calculation are valid (rational, in the
required range, compatible with the data types to which the result is
assigned).

• The relative magnitudes of values that are input to a calculation do
not cause unacceptable loss of data.

• Intermediate calculations do not produce unacceptable accumulation of
error.

• Intermediate calculations preserve sufficient range and resolution for
required final result accuracy.

REQUIREMENT

1\. Floating point operations shall be constrained by design to prevent

generation of Not-A-Number (NaN), wherever possible.

2\. A loop counter variable shall not be of type floating point.

Rule (1) – The use of floating point numbers should be carefully
considered and designs should be implemented which address the
following:

• Wherever possible, use of floating point numbers should be avoided.
The reason for this is that floating point numbers present various
pitfalls for computational inaccuracies (such as truncation, rounding,
overflow/underflow) as well as processor exceptions. If they must be
used, the programmer should never rely on the physical representation of
floating point values memory because this may vary depending on the
target architecture. Rather, the floating point size and precision
should be defined and represented as a specific length equivalent (e.g.
32-bit single precision).

• Generation of Not a Number (NaN) occurs when an invalid operation
exception has occurred. It indicates +/- infinity was permitted as an
input to a calculation, or zero (or near-zero) was permitted as the
divisor in a division, or NaN was permitted in a calculation.

• Evaluate all inputs to floating point operations to detect invalid
inputs values (e.g. +/- infinity or NaN) and handle appropriately. If
this is not possible, add code to determine at runtime whether an input
to a calculation has the value +/- infinity or NaN, or if a divisor is
zero or near-zero. If detected, bypass the operation and assign to the
result a useful valid result (perhaps the maximum or minimum value that
is permitted). NaN is an Institute of Electrical and Electronics
Engineers (IEEE) constant that indicates an invalid operation exception
has occurred. It is represented by a number with all 1’s in the
exponent, and NOT all 0’s in the mantissa. The use of a NaN value in a
calculation will produce another NaN.

• If there is risk that a function has been passed NaN as a parameter,
that parameter will be checked at runtime. If the parameter is found to
be NaN, the function will take some safe action instead (e.g. return a
useful valid result, indicate a bad status to the caller, etc.).

• Floating point values have limited precision. For example, a
single-precision floating point value can represent approximately 7.3
decimal digits of precision. Keep in mind that the result of a floating
point operation will only be as precise (in significant digits) as the
least-precise input to the operation. For example, a very large floating
point number added to a very small floating point number will likely
equal the value of the very large floating point number due to lack of
precision. Similarly, care must be taken when using floating point types
to represent integer counters which could be incremented to large
values, because large integer values will lose precision as they become
non-representable in floating point format. Refer to the floating point
format used by your target compiler (e.g. IEEE-754, etc) for more
details on the limits of precision in floating point format.

Rule (2) – Undefined behavior can result when a floating point variable
is used as a loop counter, and should thus be avoided. although full
compliance to this rule is unable to be obtained from static analysis by
a tool, so this rule remains as a manual check as a matter of best
practice.

#### Loop Blocks

REQUIREMENT

1\. Conditional statements shall be free of negative logic.

2\. Use of the ternary operator (“?:”) shall be prohibited.

3\. Use of a ‘break’ within iterative loops shall be avoided if
feasible; otherwise, documented and explained.

Rule (1) – Negative logic is a known source of misunderstanding and
coding errors, and should be avoided whenever possible. Negative logic
is when the source code is implemented to represent the complement of
the logic stated in the requirements. Use of negative logic can cause
issues with verification at the boundary values, especially when
floating point data types are used.

Example of negative logic for conditional logic:

Requirement: Do something while a is not equal to b.

> while (\!(std::int32\_t a == std::int32\_t b))  // Violation
> 
> {
> 
>     // doSomething();
> 
> } // end while
> 
> while (std::int32\_t a \!= std::int32\_t b);    // Compliant
> 
> {
> 
>     // doSomething();
> 
> } // end while

Example of negative logic for range/value checks:

Requirement: Do something if a is greater than b

> if (std::int32\_t b \<= std::int32\_t a)          // Violation
> 
> {
> 
>     // doSomething();
> 
> } // end if
> 
> if (std::int32\_t a \> std::int32\_t b)          // Compliant
> 
> {
> 
>     // doSomething();
> 
> } // end if

Rule (2) – The ternary operator (“?:”) should not be used. This is due
to a proven history of issues relating to the misunderstanding of this
construct, especially when nested within other ternary operator
constructs.

Refer AUTOSAR C++ 2017 \[6.5.16\].

Rule (3) - The use of (“break”) or (“continue”) in an iterative loop
results in multiple exit points in the loop. It is a better coding
practice to design the code so that it has a single loop exit point. The
documentation and justification for using break and/or continue can
either be in the code as a comment or in the design documentation.

Refer MISRA C++ 2008 \[6.4.5\].

Rule (3) - The (“for”) loop construct should be used as the preferred
looping construct for all looping operations, where feasible. When using
“for” loop constructs, the loop index variable should not be modified by
the source code statements within the loop. Use of the “do-while”
looping construct should be avoided.

Refer AUTOSAR C++ 2017 \[6.6.5\].

#### Explicit Casting

Any conversion to a narrower type should be explicitly cast.

C++ performs many type conversions silently to harmonize types within an
expression before evaluating it. Some of these conversions can result in
loss of information (e.g. conversions to a lesser storage size). Such
implicit conversions will not be used, but explicit casts should be used
instead to identify the potential for loss of information.

Explicit casts should not be used unnecessarily or redundantly between
identical types. Overuse of explicit type casting may prevent static
checker tools from detecting some errors. Explicit casts should normally
only be used in the case where the programmer specifically requires a
conversion that could result in a loss of information.

#### Integer Division

The desired behavior for rounding during integer division should be
determined and documented within the software design documentation.
Integer division and rounding rules are specific to the compiler in use.
A compiler may do one of two things when dividing two signed integers,
one of which is positive and one negative. It may either round up with a
negative remainder (e.g. -5/3 = -1 remainder -2) or round down with a
positive remainder (e.g. -5/3 = -2 remainder +1).

#### Unsigned Integer Wrap-around

REQUIREMENT

1\. Any use of data wrap-around in a variable shall be explicitly
commented and documented.

Rule (1) - The constant unsigned integer expressions should not be
written so that they may lead to wrap-around. Unsigned integer
expressions do not strictly overflow, they wrap around in a modular way.
This will not be detected by the compiler and can lead to undefined
behavior.

#### Nesting Levels

The maximum nesting of control structures should be no more than ten
(10) levels unless otherwise specified in project specific documentation
(e.g. Software Design Description (SDD) or a code standards supplement).

Note: Deeply nested code adds complexity to the worst case execution
timing analysis and control and data coupling.

#### Pointers and Arrays

REQUIREMENT

1\. All function pointers shall have the same number and type of
parameters and the same return type as the function they point to.

2\. The address operator (&) along with an array subscript (\[ \]) shall
be used when referencing an array element using a pointer.

Rule (1) – It is imperative that a function pointer have the same
function signature as the function it is referencing. If this is not
maintained, stack corruption and unpredictable behavior will likely
occur.

Rule (2) – Arrays in the C language are essentially a pointer, and as
such can be accessed and manipulated using pointers. This can cause
confusion and unintended behavior if inconsistent dereferencing styles
used. The following pointer usage conventions should be adhered to:

• The structure reference operator (-\>) should be used when referencing
a structure element via a pointer although there may be instances where
dereferencing instead is preferred.

• In order to ensure consistency between pointer variables and their
target variables, pointers should not be set to point to variables whose
type differs from that of the pointer.

• Assigning data to an uninitialized pointer will have unpredictable
results; hence, all pointers should be initialized before being used.
Some compilers will assign an address to the pointer randomly which
means that the pointer could be included in code space or data space.

• Only declared pointer variables should be used to store pointer
values. This ensures that latent errors are not manifested when the code
is augmented in the future.

Example of Pointer Usage:

> UINT8 data\[10\];
> 
> UINT8 \*myDataPtr = data;      // Violation
> 
> UINT8 \*myDataPtr = \&data\[0\];  // Compliant
> 
> MSG\_BUFFER\_STRUCT \*txMsg;
> 
> (\*txMsg).type = READ\_MSG;     // Violation
> 
> txMsg-\>type = READ\_MSG;       // Compliant

#### Dynamic Memory Allocation

REQUIREMENT

1\. Memory shall not be dynamically allocated or de-allocated.

Rule (1) - This precludes the use of the functions calloc, malloc,
realloc and free. Using dynamic memory allocation in embedded systems
may lead to unspecified, undefined and implementation-defined behavior,
as well as a number of other potential pitfalls. If run-time memory
allocation is required, it should be implemented using a
statically-allocated pool of memory, where portions are allocated for a
specific use with designed control for over-allocation and
under-allocation conditions.

Refer AUTOSAR C++ 2017 \[6.18.5\].

#### Dead Code and Commented Out Code

There should be no code that is commented out. {A2-8-2}

Dead code is executable object code (or data) which, as a result of
design error, cannot be executed (code) or used (data). Dead code is
restricted by { Rule 0–1–9}. Deactivated code is acceptable. Deactivated
code is executable object code (or data) designed either not to be
executed (e.g. part of a previously developed software component) or is
only to be executed in certain configurations of the target environment
(e.g. enabled by a hardware pin selection or software programmed
options).

Refer AUTOSAR C++ 2017 \[6.2.8\].

#### Structures, Unions and Bit Fields

REQUIREMENT

1\. Unions shall not be used. {M9-5-1}

2\. When the absolute positioning of bits representing a bit-field is
required, then the behaviour and packing of bit-fields shall be
documented. . {M9-6-1}

Example:

> struct message                  // Struct is for bit-fields only
> 
> {  
> 
>     signed int little: 4;       // Note: use of basic types is
> required
> 
>     unsigned int x\_set: 1;
> 
>     unsigned int y\_set: 1;
> 
> } message\_chunk;

3\. Bit-fields shall be either unsigned integral, or enumeration (with
underlying type of unsigned integral type). {A9-6-1}

Example:

> \#include \<cstdint\>
> 
> enum class E1 : std::uint8\_t
> 
> {
> 
>     E11,
> 
>     E12,
> 
>     E13
> 
> };
> 
> enum class E2 : std::int16\_t
> 
> {
> 
>     E21,
> 
>     E22,
> 
>     E23
> 
> };
> 
> enum class E3
> 
> {
> 
>     E31,
> 
>     E32,
> 
>     E33
> 
> };
> 
> enum E4
> 
> {
> 
>     E41,
> 
>     E42,
> 
>     E43
> 
> };
> 
> class C
> 
> {
> 
>     public:
> 
>     std::int32\_t a : 2;     // Non-compliant - signed integral type
> 
>     std::uint8\_t b : 2U;    // Compliant
> 
>     bool c : 1;             // Non-compliant - it is
> implementation-defined whether
> 
>                             // bool is signed or unsigned
> 
>     char d : 2;             // Non-compliant
> 
>     wchar\_t e : 2;          // Non-compliant
> 
>     E1 f1 : 2;              // Compliant
> 
>     E2 f2 : 2;              // Non-compliant - E2 enum class
> underlying type is
> 
>                             // signed int
> 
>     E3 f3 : 2;              // Non-compliant - E3 enum class does not
> explicitly
> 
>                             // define underlying type
> 
>     E4 f4 : 2;              // Non-compliant - E4 enum does not
> explicitly define
> 
>                             // underlying type
> 
> };
> 
> void fn() noexcept
> 
> {
> 
>     C c;
> 
>     c.f1 = E1::E11;
> 
> }

Rule (2) - The structure member names should be independent of the
structure name.

#### ANSI/ISO compiler standards considerations

The compiler used should conform to the C++14 language as defined by
ISO/IEC 14882:2014 \[3\].

However, it does not list them in the way that the C standard does in
its “Portability issues” annex. To aid in ensuring coverage of the
issues and to allow traceability, they have been extracted and are shown
in Appendix B of MISRA C++ 2008.

A language compiler (and associated linker etc.) is itself a software
tool. Compilers may not always compile code correctly. They may, for
example, not comply with the language standard in certain situations, or
they may simply contain “bugs”.

Because there are aspects of the C++ language that are hard to
understand, compiler writers have been known to misinterpret the
standard and implement it incorrectly. Some areas of the language are
more prone to this than others. In addition, compiler writers sometimes
consciously choose to vary from the standard.

The compiler/linker flags should be assessed during the software
integration phase when the software build is readied to check on the
target.

#### Language Compatibility

Code written in languages other than C++ should only be used if there is
a defined interface standard for object code to which the compilers/
assemblers for both languages conform. It is essential to ensure that
the C++ code integrates correctly with any function that is implemented
in a different language. It is important to ensure that stack usage,
parameter passing and data storage methods are compatible between
languages.

#### Multi-byte Characters and Wide String Literals

Multi-byte characters and wide string literals should not be used. Only
those escape sequences that are defined in ISO/IEC 14882:2014 shall be
used {A2-14-1}. There are various undefined and implementation-defined
behaviors associated with multi-byte characters and wide string
literals.

The use of an undefined escape sequence leads to undefined behavior. The
defined

escape sequences (ISO/IEC 14882:2014) are: \\’, \\", \\?, \\\\, \\a,
\\b, \\f, \\n, \\r, \\t, \\v, \\\<Octal

Number\>, \\x\<Hexadecimal Number\>, \\U\<Unicode Character Name\>

Example

    \#include \<string\>

    void f()

    {

        const std::string a = "\\k";         // Non-compliant

        const std::string b = "\\n";         // Compliant

        const std::string c = "\\U0001f34c"; // Compliant

    }

Refer AUTOSAR C++ 2017 \[6.2.14\].

#### Compilation errors:

• Check for missing or incorrect header file inclusions.

• Verify that function and variable names are spelled correctly.

• Ensure that all required libraries are linked correctly.

• Each error or warning message generated by tool shall be addressed and
resolved.

#### Initialization and assignment:

⦁ Verify that all variables are properly initialized before use.

⦁ Check for accidental assignment (=) instead of equality comparison
(==).

⦁ Ensure that pointers are initialized to valid memory addresses.

#### Memory management:

⦁ Check for proper allocation and deallocation of dynamic memory using
new and delete or new\[\] and delete\[\].

⦁ Avoid memory leaks by ensuring all allocated memory is properly
released.

#### Array handling:

⦁ Verify that array indices are within bounds to avoid out-of-bounds
access.

⦁ Ensure that multidimensional arrays are declared and accessed
correctly.

#### Logic and control flow:

⦁ Check for logical errors in conditional statements, loops, and switch
statements.

⦁ Verify that loops have proper termination conditions to avoid infinite
loops.

⦁ Ensure that break statements are used correctly in switch statements.

#### Function usage:

⦁ Verify that function calls have the correct number and type of
arguments.

⦁ Check for missing return statements in non-void functions.

⦁ Ensure that function prototypes and definitions match.

⦁ A function shall have a single point of exit at the end of the
function.

⦁ All exits paths from a function with non-void return type have an
explicit return statement with an expression.

#### Error handling:

⦁ Check for error codes or exceptions returned by functions and handle
them appropriately.

⦁ Include meaningful error messages or logging to aid in debugging and
troubleshooting

⦁ Verify that error conditions are properly checked and handled in your
code.

#### Variable scope and lifetime:

⦁ Check for variables used outside their intended scope.

⦁ Ensure that variables are not used after they have gone out of scope.

#### Type mismatches:

⦁ Check for incompatible types in assignments, function calls, and
expressions.

⦁ Verify that the correct type specifiers are used for variables and
function return types.

#### Const correctness:

⦁ Check for missing or incorrect usage of the const keyword for
variables and function parameters.

The operands of a logical && or || shall be primary expressions.

Do not allow usage of ^ (XOR) operand in logical operations.

Primary expressions are either a single identifier, or a constant, or a
parenthesized expression. The effect of this rule is to require that if
an operand is other than a single identifier or constant then it must be
parenthesized.

*Unacceptable:*  
if (x == 0 && ishigh);  
if (x || y && z);  
*Acceptable:*  
If ((x == 0) && ishigh);  
if (x || (y && z));

#### Object-oriented programming guidelines:

⦁ Follow the principles of encapsulation, inheritance, and polymorphism.

⦁ Use appropriate access modifiers (public, private, protected) for
class members.

⦁ Implement proper class relationships and dependencies.

⦁ Avoid excessive coupling between classes.

#### Testing and Debugging:

⦁ Include thorough unit tests for your code.

⦁ Use a debugger to identify and fix issues.

⦁ Consider using assertions to verify assumptions and catch potential
bugs.

⦁ Document known limitations or known issues in your code.

#### Performance considerations:

⦁ Optimize critical sections of code for efficiency.

⦁ Avoid unnecessary computations or redundant operations.

⦁ Use appropriate data structures and algorithms to improve performance.

#### Version Control and Documentation:

⦁ Utilize a version control system to track changes and collaborate with
others.

⦁ Maintain clear and up-to-date documentation for your code, including
API documentation if applicable.

⦁ Include code comments or docstrings to explain complex algorithms or
important concepts

#### Precedence and Evaluation Order

Limited dependence should be placed on C++ operator precedence rules in
expressions. {M5-0-2}

Source code should be implemented such that dependence on execution
order and/or operator precedence is eliminated. A common coding mistake
is when multiple logical operators of equal precedence are combined in a
single conditional statement without the use of parenthesis, which makes
the outcome of the expression dependent on execution order (i.e.
left-to-right, or right-to-left) as well as the C++ language precedence
rules for the operators “&&”, “||”, and “==”. although full compliance
to this rule is unable to be obtained from static analysis by a tool, so
this rule remains as a manual check as a matter of best practice.

Examples for Rule (1):

> if (A == 1 && B == 2 || C == 2)             // Violation
> 
> if (((A == 1) && (B == 2)) || (C == 3))     // Compliant

#### Library introduction

This section outlines rule regarding the use of the C++ standard
libraries. The C++ standard libraries provide functions for file/stream
I/O, dynamic memory allocation, string parsing, mathematical functions,
time, date, binary tree sort/search, and more

It is generally bad practice to \#undef a macro that is defined in the
standard library. It is also bad practice to \#define a macro name that
is a C++ reserved identifier, or C++ keyword or the name of any macro,
object or function in the standard library. For example, there are some
specific reserved words and function names that are known to give rise
to undefined behavior if they are redefined or undefined, including
defined, \_\_LINE\_\_, \_\_FILE\_\_, \_\_DATE\_\_, \_\_TIME\_\_,
\_\_STDC\_\_, errno and assert. Refer to C++ Language Standard for a
list of the identifiers that are reserved. Generally, all identifiers
that begin with the underscore character are reserved.

Note that this rule applies regardless of which header files, if any,
are actually included.

Example

\#undef \_\_TIME\_\_     // Non-compliant

\#define \_\_LINE\_\_ 20 // Non-compliant

Refer AUTOSAR C++ 2017 \[6.17\].

#### Exception handling

“The exception handling mechanism can provide an effective and clear
means of handling error conditions, particularly where a function needs
to return both some desired result together with an indication of
success or failure. However, because of its ability to transfer control
back up the call tree, it can also lead to code that is difficult to
understand. Hence it is required that the mechanism is only used to
capture behavior that is in some sense undesirable, and which is not
expected to be seen in normal program execution.” \[MISRA C++ 2008\]

“The preferred mechanism for reporting errors in a C++ program is
exceptions rather than using error codes. A number of core language
facilities, including dynamic\_cast, operator new(), and typeid, report
failures by throwing exceptions. In addition, the C++ standard library
makes heavy use of exceptions to report several different kinds of
failures. Few C++ programs manage to avoid using some of these
facilities.” \[ISO C++ Core Guidelines\]. Consequently, C++ programs
need to be prepared for exceptions to occur and need to handle each
appropriately.

Refer AUTOSAR C++ 2017 \[6.15\].

# PROCESS FOR DEVIATIONS / EXCEPTIONS

The process for documentation and approval of program-specific
deviations and/or exceptions to the software requirements standards is
defined within the program-specific software planning documents.

Deviations may occur for a specific instance, i.e. a one-off occurrence
in a single file, or for a class of circumstances, i.e. a systematic use
of a particular construct in a particular circumstance, for example the
use of a particular language extension to implement an input/output
operation in files that handle serial communications. Strict adherence
to all rules is unlikely and, in practice, deviations associated with
individual situations, are admissible. There are two categories of
deviation.

• Project Deviation: A Project Deviation is defined as a permitted
relaxation of rule requirements to be applied in specified
circumstances. In practice, Project Deviations will usually be agreed at
the start of a project.

• Specific Deviation: A Specific Deviation will be defined for a
specific instance of a rule violation in a single file and will
typically be raised in response to circumstances that arise during the
development process. Project deviations should be reviewed regularly and
this review should be a part of the formal deviation process.

A Project Deviation Request should include the following:

> • Details of the deviation, i.e. the rule that is being violated;
> 
> • Circumstances in which the need for the deviation arises;
> 
> • Potential consequences which may result from the deviation;
> 
> • Justification for the deviation;
> 
> • A demonstration of how safety is assured.

When the need for a deviation arises during or at the end of the
development process, the software developer should submit a written
Specific Deviation Request.

A Specific Deviation Request should include the following:

> • Details of the deviation, i.e. the rule that is being violated;
> 
> • Potential consequences which may result from the deviation;
> 
> • Justification for the deviation;
> 
> • A demonstration of how safety is assured.

Detailed implementation of these procedures is left to the discretion of
the user

A list of the deviations / exceptions should be maintained by the
program in such a way that each is uniquely identified such that each
can be easily referred.

See MISRA 2008 section 4.3.2 “Deviation procedure” for a discussion
about deviations. The deviation must be justified on the basis of both
necessity and safety.

Ideally the code should also be updated with a consistent comment
identifying the deviation / exception in order to simplify searching for
the deviations / exceptions at a later time and simplify future code
reviews.

##### EXAMPLE TEMPLATES FOR SOURCE CODE

Template for Source file:

//
\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*

// Copyright:

//     COPYRIGHT (C) 2023: Akkodis Consultancy GmbH.

//

//
\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*

// Project      XXX

//\! \\file       XXX.h

//\! \\date       DD.MM.YYYY

//\! \\version    1

// Author       AUTHOR / AKKA

//

//
\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*

// Description:

//      \<add description details here\>.

//

//
\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*

//                                    CHANGES

// Version      Description

// ----------  
---------------------------------------------------------------

// 1            Initial Revision

// 2            Updated function Func1() for xxx

//

//
\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*

Example:

//
\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*

// Copyright:

// COPYRIGHT (C) 2023: Akkodis Consultancy GmbH.

//

//
\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*

// Project      XXX

//\! \\file       calcSpeed.cpp

//\! \\date       15.06.2023

//\! \\version    1

// Author       AUTHOR / AKKA

//

//
\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*

//  Description:

//      This file calculates the speed with given inputs read from CAN
bus.

//

//
\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*

//                                    CHANGES

// Version      Description

// ----------  
---------------------------------------------------------------

// 1            Initial Revision

//

//
\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*

TEMPLATES FOR C/ASSEMBLY FUNCTION HEADER

C.1 Example Source File Function Header:

//
\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*

// FUNCTION NAME:

//     \<Add function name here\>

//

// DESCRIPTION:

//     \<Add function description here\>

//
\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*

Example:

//
\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*

// FUNCTION NAME:

//     calcSpeedMetricSystem

//

// DESCRIPTION:

//     This function calculates the speed and returns in Metric System
format

//
\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*

##### 

##### PROGRAMMING STANDARDS

Note: Advisory, Mandatory, and Required rules are included to allow for
easy maintenance of the document during future revisions that may change
the level. The data in the tables below is from "MISRA C++:2008
Guidelines for the use of the C++ language in critical systems" ©
Copyright MISRA and AUTOSAR C++: Guidelines for the use of the C++14
language in critical and safety-related systems, March-2017

Table 7: MISRA-C++: 2008 Rules with AUTOSAR C++ 2017 Traceability

<table>
<thead>
<tr class="header">
<th><strong>Section</strong></th>
<th><strong>MISRA C++ 2008 Rule Number</strong></th>
<th><strong>Catagary</strong></th>
<th><strong>Rule Text</strong></th>
<th><strong>Relation type with AUTOSAR C++ 2017</strong></th>
<th><strong>Related rule:</strong></th>
<th><strong>Comment:</strong></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td>Unnecessary constructs</td>
<td><a href="file:///C:/Users/ravi.jayanagara/AppData/Local/Microsoft/Windows/INetCache/Content.MSO/CC42CAF5.tmp#RANGE!A1">M0–1–1</a></td>
<td>Required</td>
<td>A project shall not contain unreachable code.</td>
<td>1-Identical</td>
<td>M0-1-1</td>
<td>-</td>
</tr>
<tr class="even">
<td>Unnecessary constructs</td>
<td>M0–1–2</td>
<td>Required</td>
<td>A project shall not contain infeasible paths.</td>
<td>2-Smalldifferences</td>
<td>M0-1-2</td>
<td>Note about const expr functions added.</td>
</tr>
<tr class="odd">
<td>Unnecessary constructs</td>
<td>M0–1–3</td>
<td>Required</td>
<td>A project shall not contain unused variables.</td>
<td>1-Identical</td>
<td>M0-1-3</td>
<td>-</td>
</tr>
<tr class="even">
<td>Unnecessary constructs</td>
<td>M0–1–4</td>
<td>Required</td>
<td>A project shall not contain non-volatile POD variables having only one use.</td>
<td>1-Identical</td>
<td>M0-1-4</td>
<td>-</td>
</tr>
<tr class="odd">
<td>Unnecessary constructs</td>
<td>M0–1–5</td>
<td>Required</td>
<td>A project shall not contain unused type declarations.</td>
<td>1-Identical</td>
<td>M0-1-5</td>
<td>-</td>
</tr>
<tr class="even">
<td>Unnecessary constructs</td>
<td>M0–1–6</td>
<td>Required</td>
<td>A project shall not contain instances of non-volatile variables being given values that are never subsequently used.</td>
<td>2-Smalldifferences</td>
<td>A0-1-1</td>
<td>Example re worked.</td>
</tr>
<tr class="odd">
<td>Unnecessary constructs</td>
<td>M0–1–7</td>
<td>Required</td>
<td>The value returned by a function having a non-void return type that is not an overloaded operator shall always be used.</td>
<td>2-Smalldifferences</td>
<td>A0-1-2</td>
<td>Rationale reformulated.</td>
</tr>
<tr class="even">
<td>Unnecessary constructs</td>
<td>M0–1–8</td>
<td>Required</td>
<td>All functions with void return type shall have external side effect(s).</td>
<td>1-Identical</td>
<td>M0-1-8</td>
<td>-</td>
</tr>
<tr class="odd">
<td>Unnecessary constructs</td>
<td>M0–1–9</td>
<td>Required</td>
<td>There shall be no dead code.</td>
<td>1-Identical</td>
<td>M0-1-9</td>
<td>-</td>
</tr>
<tr class="even">
<td>Unnecessary constructs</td>
<td>M0–1–10</td>
<td>Required</td>
<td>Every defined function shall be called at least once.</td>
<td>3-Significantdifferences</td>
<td>M0-1-10,<br />
A0-1-2</td>
<td><p>Rule divided into:<br />
(1) Identical rule with obligation level “Advisory”,</p>
<p>(2) Rule with obligation level “Required” which to applies static functions and private methods.</p></td>
</tr>
<tr class="odd">
<td>Unnecessary constructs</td>
<td>M0–1–11</td>
<td>Required</td>
<td>There shall be no unused parameters (named or unnamed) in nonvirtual functions.</td>
<td>1-Identical</td>
<td>M0-1-11</td>
<td>-</td>
</tr>
<tr class="even">
<td>Unnecessary constructs</td>
<td>M0–1–12</td>
<td>Required</td>
<td>There shall be no unused parameters (named or unnamed) in the set of parameters for a virtual function and all the functions that override it.</td>
<td>1-Identical</td>
<td>M0-1-12</td>
<td>-</td>
</tr>
<tr class="odd">
<td>Storage</td>
<td>M0–2–1</td>
<td>Required</td>
<td>An object shall not be assigned to an overlapping object.</td>
<td>1-Identical</td>
<td>M0-2-1</td>
<td>-</td>
</tr>
<tr class="even">
<td>Runtime failures</td>
<td>M0–3–1</td>
<td>Document</td>
<td>Minimization of run-time failures shall be ensured by the use of at least one of: (a) static analysis tools/techniques; (b) dynamic analysis tools/techniques; (c) explicit coding of checks to handle run-time faults.</td>
<td>1-Identical</td>
<td>M0-3-1</td>
<td>-</td>
</tr>
<tr class="odd">
<td>Runtime failures</td>
<td>M0–3–2</td>
<td>Required</td>
<td>If a function generates error information, then that error information shall be tested.</td>
<td>1-Identical</td>
<td>M0-3-2</td>
<td>-</td>
</tr>
<tr class="even">
<td>Arithmetic</td>
<td>M0–4–1</td>
<td>Document</td>
<td>Use of scaled-integer or fixed-point arithmetic shall be documented.</td>
<td>1-Identical</td>
<td>M0-4-1</td>
<td>-</td>
</tr>
<tr class="odd">
<td>Arithmetic</td>
<td>M0–4–2</td>
<td>Document</td>
<td>Use of floating-point arithmetic shall be documented.</td>
<td>1-Identical</td>
<td>M0-4-2</td>
<td>-</td>
</tr>
<tr class="even">
<td>Arithmetic</td>
<td>M0–4–3</td>
<td>Document</td>
<td>Floating-point implementationsshall comply with a defined floatingpoint standard.</td>
<td>3-Significantdifferences</td>
<td>A0-4-1</td>
<td>Specified that floating-point implementations need to comply with IEEE754 standard.</td>
</tr>
<tr class="odd">
<td>Language</td>
<td>M1–0–1</td>
<td>Required</td>
<td>All code shall conform to ISO/IEC 14882:2003 “The C++ Standard Incorporating Technical Corrigendum 1”.</td>
<td>2-Smalldifferences</td>
<td>A1-1-1</td>
<td>Specified that the code shall conform to ISO /IEC 14882:2014.</td>
</tr>
<tr class="even">
<td>Language</td>
<td>M1–0–2</td>
<td>Document</td>
<td>Multiple compilers shall only be used if they have a common, defined interface.</td>
<td>1-Identical</td>
<td>M1-0-2</td>
<td>-</td>
</tr>
<tr class="odd">
<td>Language</td>
<td>M1–0–3</td>
<td>Document</td>
<td>The implementation of integer division in the chosen compiler shall be determined and documented.</td>
<td>3-Significantdifferences</td>
<td>A0-4-2</td>
<td>Specified that the implementation of integer division shall comply with the C++Language Standard.</td>
</tr>
<tr class="even">
<td>Character sets</td>
<td>M2–2–1</td>
<td>Document</td>
<td>The character set and the corresponding encoding shall be documented.</td>
<td>4-Rejected</td>
<td>-</td>
<td>Rule rejected. The character set explicitly specified in A2-2-1.</td>
</tr>
<tr class="odd">
<td>Trigraph sequences</td>
<td>M2–3–1</td>
<td>Required</td>
<td>Trigraphs shall not be used.</td>
<td>2-Smalldifferences</td>
<td>A2-5-1</td>
<td>All trigraphs listed in rationale. Example extended.</td>
</tr>
<tr class="even">
<td>Alternative tokens</td>
<td>M2–5–1</td>
<td>Advisory</td>
<td>Digraphs should not be used.</td>
<td>3-Significantdifferences</td>
<td>A2-6-1</td>
<td>Obligation level changed to “Required”.</td>
</tr>
<tr class="odd">
<td>Comments</td>
<td>M2–7–1</td>
<td>Required</td>
<td>The character sequence /* shall not be used within a C-style comment.</td>
<td>3-Significantdifferences</td>
<td>A2-8-4</td>
<td>Using the C-style comments is not allowed.</td>
</tr>
<tr class="even">
<td>Comments</td>
<td>M2–7–2</td>
<td>Required</td>
<td>Sections of code shall not be “commented out” using C-style comments.</td>
<td>2-Smalldifferences</td>
<td>A2-8-1</td>
<td>Commenting-out code sections is not allowed.</td>
</tr>
<tr class="odd">
<td>Comments</td>
<td>M2–7–3</td>
<td>Advisory</td>
<td>Sections of code should not be “commented out” using C++ comments.</td>
<td>2-Smalldifferences</td>
<td>A2-8-1</td>
<td>Obligation level changed to “Required”. Commenting-out code sections is not allowed.</td>
</tr>
<tr class="even">
<td>Identifiers</td>
<td>M2–10–1</td>
<td>Required</td>
<td>Different identifiers shall be typographically unambiguous.</td>
<td>1-Identical</td>
<td>M2-10-1</td>
<td>-</td>
</tr>
<tr class="odd">
<td>Identifiers</td>
<td>M2–10–2</td>
<td>Required</td>
<td>Identifiers declared in an inner scope shall not hide an identifier declared in an outer scope.</td>
<td>2-Smalldifferences</td>
<td>A2-11-1</td>
<td>Added a note to rationale. Example extended.</td>
</tr>
<tr class="even">
<td>Identifiers</td>
<td>M2–10–3</td>
<td>Required</td>
<td>A typedef name (including qualification, if any) shall be a unique identifier.</td>
<td>1-Identical</td>
<td>M2-10-3</td>
<td>-</td>
</tr>
<tr class="odd">
<td>Identifiers</td>
<td>M2–10–4</td>
<td>Required</td>
<td>A class, union or enum name (including qualification, if any) shall be a unique identifier.</td>
<td>2-Smalldifferences</td>
<td>A2-11-3</td>
<td>“A class, union or enum name” changed to “A user-defined type name”. Example extended.</td>
</tr>
<tr class="even">
<td>Identifiers</td>
<td>M2–10–5</td>
<td>Advisory</td>
<td>The identifier name of a non-member object or function with static storage duration should not be reused.</td>
<td>3-Significantdifferences</td>
<td>A2-11-4</td>
<td>Obligation level changed to “Required”. Rationale reformulated.</td>
</tr>
<tr class="odd">
<td>Identifiers</td>
<td>M2–10–6</td>
<td>Required</td>
<td>If an identifier refers to a type, it shall not also refer to an object or a function in the same scope.</td>
<td>1-Identical</td>
<td>M2-10-6</td>
<td>-</td>
</tr>
<tr class="even">
<td>Literals</td>
<td>M2–13–1</td>
<td>Required</td>
<td>Only those escape sequencesthat are defined in ISO/IEC14882:2003 shall be used.</td>
<td>2-Smalldifferences</td>
<td>A2-14-1</td>
<td>Standard changed to ISO/IEC 14882:2014.</td>
</tr>
<tr class="odd">
<td>Literals</td>
<td>M2–13–2</td>
<td>Required</td>
<td>Octal constants (other than zero) and octal escape sequences (other than “\0”) shall not be used.</td>
<td>1-Identical</td>
<td>M2-13-2</td>
<td>-</td>
</tr>
<tr class="even">
<td>Literals</td>
<td>M2–13–3</td>
<td>Required</td>
<td>A “U” suffix shall be applied to all octal or hexadecimal integer literals of unsigned type.</td>
<td>1-Identical</td>
<td>M2-13-3</td>
<td>-</td>
</tr>
<tr class="odd">
<td>Literals</td>
<td>M2–13–4</td>
<td>Required</td>
<td>Literal suffixes shall be upper case.</td>
<td>1-Identical</td>
<td>M2-13-4</td>
<td>-</td>
</tr>
<tr class="even">
<td>Literals</td>
<td>M2–13–5</td>
<td>Required</td>
<td>Narrow and wide string literals shall not be concatenated.</td>
<td>2-Smalldifferences</td>
<td>A2-14-2</td>
<td>Example extended.</td>
</tr>
<tr class="odd">
<td>Declarations and definitions</td>
<td>M3–1–1</td>
<td>Required</td>
<td>It shall be possible to include any header file in multiple translation units without violating the One Definition Rule.</td>
<td>3-Significantdifferences</td>
<td>A3-1-1</td>
<td>Rationale reformulated. Example extended.</td>
</tr>
<tr class="even">
<td>Declarations and definitions</td>
<td>M3–1–2</td>
<td>Required</td>
<td>Functions shall not be declared at block scope.</td>
<td>1-Identical</td>
<td>M3-1-2</td>
<td>-</td>
</tr>
<tr class="odd">
<td>Declarations and definitions</td>
<td>M3–1–3</td>
<td>Required</td>
<td>When an array is declared, its size shall either be stated explicitly or defined implicitly by initialization.</td>
<td>2-Smalldifferences</td>
<td>A3-1-4</td>
<td>Specified that this rule applies to arrays with external link age only.</td>
</tr>
<tr class="even">
<td>One Definition Rule.</td>
<td>M3–2–1</td>
<td>Required</td>
<td>All declarations of an object or function shall have compatible types.</td>
<td>1-Identical</td>
<td>M3-2-1</td>
<td>-</td>
</tr>
<tr class="odd">
<td>One Definition Rule.</td>
<td>M3–2–2</td>
<td>Required</td>
<td>The One Definition Rule. shall not be violated.</td>
<td>1-Identical</td>
<td>M3-2-2</td>
<td>-</td>
</tr>
<tr class="even">
<td>One Definition Rule.</td>
<td>M3–2–3</td>
<td>Required</td>
<td>A type, object or function that is used in multiple translation units shall be declared in one and only one file.</td>
<td>1-Identical</td>
<td>M3-2-3</td>
<td>-</td>
</tr>
<tr class="odd">
<td>One Definition Rule.</td>
<td>M3–2–4</td>
<td>Required</td>
<td>An identifier with external linkage shall have exactly one definition.</td>
<td>1-Identical</td>
<td>M3-2-4</td>
<td>-</td>
</tr>
<tr class="even">
<td>Declarative regions and scope</td>
<td>M3–3–1</td>
<td>Required</td>
<td>Objects or functions with external linkage shall be declared in a header file.</td>
<td>2-Smalldifferences</td>
<td>A3-3-1</td>
<td>Added a note to rationale. Example extended.</td>
</tr>
<tr class="odd">
<td>Declarative regions and scope</td>
<td>M3–3–2</td>
<td>Required</td>
<td>If a function has internal linkage then all re-declarations shall include the static storage class specifier.</td>
<td>1-Identical</td>
<td>M3-3-2</td>
<td>-</td>
</tr>
<tr class="even">
<td>Name lookup</td>
<td>M3–4–1</td>
<td>Required</td>
<td>An identifier declared to be an object or type shall be defined in a block that minimizes its visibility.</td>
<td>1-Identical</td>
<td>M3-4-1</td>
<td>-</td>
</tr>
<tr class="odd">
<td>Types</td>
<td>M3–9–1</td>
<td>Required</td>
<td>The types used for an object, a function return type, or a function parameter shall be token-for-token identical in all declarations and re-declarations.</td>
<td>1-Identical</td>
<td>M3-9-1</td>
<td>-</td>
</tr>
<tr class="even">
<td>Types</td>
<td>M3–9–2</td>
<td>Advisory</td>
<td>typedefs that indicate size and signedness should be used in place of the basic numerical types.</td>
<td>3-Significantdifferences</td>
<td>M3-9-1</td>
<td>Rule title and rationale reformulatedtouse types from &lt;cstdint&gt; header file. Alltypesthat should be used were listed. Examplechanged.</td>
</tr>
<tr class="odd">
<td>Types</td>
<td>M3–9–3</td>
<td>Required</td>
<td>The underlying bit representations of floating-point values shall not be used.</td>
<td>1-Identical</td>
<td>M3-9-3</td>
<td>-</td>
</tr>
<tr class="even">
<td>Integral promotions</td>
<td>M4–5–1</td>
<td>Required</td>
<td>Expressions with type bool shall not be used as operands to built-in operators other than the assignment operator =, the logical operators &amp;&amp;, ||, !, the equality operators == and !=, the unary &amp; operator, and the conditional operator.</td>
<td>1-Identical</td>
<td>M4-5-1</td>
<td>-</td>
</tr>
<tr class="odd">
<td>Integral promotions</td>
<td>M4–5–2</td>
<td>Required</td>
<td>Expressions with type enum shall not be used as operands to builtin operators other than the subscript operator [ ], the assignment operator =, the equality operators == and !=, the unary &amp; operator, and the relational operators &lt;, &lt;=, &gt;, &gt;=.</td>
<td>3-Significantdifferences</td>
<td>A4-5-1</td>
<td>Changed the rule so it applies to enum classes too. Rationale reformulated. Example extended.</td>
</tr>
<tr class="even">
<td>Integral promotions</td>
<td>M4–5–3</td>
<td>Required</td>
<td>Expressions with type (plain) char and wchar_t shall not be used as operands to built-in operators other than the assignment operator =, the equality operators == and !=, and the unary &amp; operator.</td>
<td>1-Identical</td>
<td>M4-5-3</td>
<td>-</td>
</tr>
<tr class="odd">
<td>Pointer conversions</td>
<td>M4–10–1</td>
<td>Required</td>
<td>NULL shall not be used as an integer value.</td>
<td>1-Identical</td>
<td>M4-10-1</td>
<td>-</td>
</tr>
<tr class="even">
<td>Pointer conversions</td>
<td>M4–10–2</td>
<td>Required</td>
<td>Literal zero (0) shall not be used as the null-pointer-constant.</td>
<td>1-Identical</td>
<td>M4-10-2</td>
<td>-</td>
</tr>
<tr class="odd">
<td>Expressions</td>
<td>M5–0–1</td>
<td>Required</td>
<td>The value of an expression shall be the same under any order of evaluation that the standard permits.</td>
<td>1-Identical</td>
<td>A5-0-1</td>
<td>Example rewritten to compile withC++compiler</td>
</tr>
<tr class="even">
<td>Expressions</td>
<td>M5–0–2</td>
<td>Advisory</td>
<td>Limited dependence should be placed on C++ operator precedence rules in expressions.</td>
<td>1-Identical</td>
<td>M5-0-2</td>
<td>-</td>
</tr>
<tr class="odd">
<td>Expressions</td>
<td>M5–0–3</td>
<td>Required</td>
<td>A cvalue expression shall not be implicitly converted to a different underlying type.</td>
<td>1-Identical</td>
<td>M5-0-3</td>
<td>-</td>
</tr>
<tr class="even">
<td>Expressions</td>
<td>M5–0–4</td>
<td>Required</td>
<td>An implicit integral conversion shall not change the signedness of the underlying type.</td>
<td>1-Identical</td>
<td>M5-0-4</td>
<td>-</td>
</tr>
<tr class="odd">
<td>Expressions</td>
<td>M5–0–5</td>
<td>Required</td>
<td>There shall be no implicit floating-integral conversions.</td>
<td>1-Identical</td>
<td>M5-0-5</td>
<td>-</td>
</tr>
<tr class="even">
<td>Expressions</td>
<td>M5–0–6</td>
<td>Required</td>
<td>An implicit integral or floating-point conversion shall not reduce the size of the underlying type.</td>
<td>1-Identical</td>
<td>M5-0-6</td>
<td>-</td>
</tr>
<tr class="odd">
<td>Expressions</td>
<td>M5–0–7</td>
<td>Required</td>
<td>There shall be no explicit floating-integral conversions of a cvalue expression.</td>
<td>1-Identical</td>
<td>M5-0-7</td>
<td>-</td>
</tr>
<tr class="even">
<td>Expressions</td>
<td>M5–0–8</td>
<td>Required</td>
<td>An explicit integral or floating-point conversion shall not increase the size of the underlying type of a cvalue expression.</td>
<td>1-Identical</td>
<td>M5-0-8</td>
<td>-</td>
</tr>
<tr class="odd">
<td>Expressions</td>
<td>M5–0–9</td>
<td>Required</td>
<td>An explicit integral conversion shall not change the signedness of the underlying type of a cvalue expression.</td>
<td>1-Identical</td>
<td>M5-0-9</td>
<td>-</td>
</tr>
<tr class="even">
<td>Expressions</td>
<td>M5–0–10</td>
<td>Required</td>
<td>If the bitwise operators ~ and &lt;&lt; are applied to an operand with an underlying type of unsigned char or unsigned short, the result shall be immediately cast to the underlying type of the operand.</td>
<td>1-Identical</td>
<td>M5-0-10</td>
<td>-</td>
</tr>
<tr class="odd">
<td>Expressions</td>
<td>M5–0–11</td>
<td>Required</td>
<td>The plain char type shall only be used for the storage and use of character values.</td>
<td>1-Identical</td>
<td>M5-0-11</td>
<td>-</td>
</tr>
<tr class="even">
<td>Expressions</td>
<td>M5–0–12</td>
<td>Required</td>
<td>signed char and unsigned char type shall only be used for the storage and use of numeric values.</td>
<td>1-Identical</td>
<td>M5-0-12</td>
<td>-</td>
</tr>
<tr class="odd">
<td>Expressions</td>
<td>M5–0–13</td>
<td>Required</td>
<td>The condition of an if-statement and the condition of an iterationstatement shall have type bool.</td>
<td>2-Smalldifferences</td>
<td>A5-0-2</td>
<td>Example extended.</td>
</tr>
<tr class="even">
<td>Expressions</td>
<td>M5–0–14</td>
<td>Required</td>
<td>The first operand of a conditional-operator shall have type bool.</td>
<td>1-Identical</td>
<td>M5-0-14</td>
<td>-</td>
</tr>
<tr class="odd">
<td>Expressions</td>
<td>M5–0–15</td>
<td>Required</td>
<td>Array indexing shall be the only form of pointer arithmetic.</td>
<td>1-Identical</td>
<td>M5-0-15</td>
<td>-</td>
</tr>
<tr class="even">
<td>Expressions</td>
<td>M5–0–16</td>
<td>Required</td>
<td>A pointer operand and any pointer resulting from pointer arithmetic using that operand shall both address elements of the same array.</td>
<td>1-Identical</td>
<td>M5-0-16</td>
<td>-</td>
</tr>
<tr class="odd">
<td>Expressions</td>
<td>M5–0–17</td>
<td>Required</td>
<td>Subtraction between pointers shall only be applied to pointers that address elements of the same array.</td>
<td>1-Identical</td>
<td>M5-0-17</td>
<td>-</td>
</tr>
<tr class="even">
<td>Expressions</td>
<td>M5–0–18</td>
<td>Required</td>
<td>&gt;, &gt;=, &lt;, &lt;= shall not be applied to objects of pointer type, except where they point to the same array.</td>
<td>1-Identical</td>
<td>M5-0-18</td>
<td>-</td>
</tr>
<tr class="odd">
<td>Expressions</td>
<td>M5–0–19</td>
<td>Required</td>
<td>The declaration of objects shall contain no more than two levels of pointer indirection.</td>
<td>2-Smalldifferences</td>
<td>A5-0-3</td>
<td>Example changed - typedef replaced with using.</td>
</tr>
<tr class="even">
<td>Expressions</td>
<td>M5–0–20</td>
<td>Required</td>
<td>Non-constant operands to a binary bitwise operator shall have the same underlying type.</td>
<td>1-Identical</td>
<td>M5-0-20</td>
<td>-</td>
</tr>
<tr class="odd">
<td>Expressions</td>
<td>M5–0–21</td>
<td>Required</td>
<td>Bitwise operators shall only be applied to operands of unsigned underlying type.</td>
<td>1-Identical</td>
<td>M5-0-21</td>
<td>-</td>
</tr>
<tr class="even">
<td>Postfix expressions</td>
<td>M5–2–1</td>
<td>Required</td>
<td>Each operand of a logical &amp;&amp; or || shall be a postfix‑expression.</td>
<td>1-Identical</td>
<td>M5-2-1</td>
<td>-</td>
</tr>
<tr class="odd">
<td>Postfix expressions</td>
<td>M5–2–2</td>
<td>Required</td>
<td>A pointer to a virtual base class shall only be cast to a pointer to a derived class by means of dynamic_cast.</td>
<td>1-Identical</td>
<td>M5-2-2</td>
<td>-</td>
</tr>
<tr class="even">
<td>Postfix expressions</td>
<td>M5–2–3</td>
<td>Advisory</td>
<td>Casts from a base class to a derived class should not be performed on polymorphic types.</td>
<td>1-Identical</td>
<td>M5-2-3</td>
<td>-</td>
</tr>
<tr class="odd">
<td>Postfix expressions</td>
<td>M5–2–4</td>
<td>Required</td>
<td>C-style casts (other than void casts) and functional notation casts (other than explicit constructor calls) shall not be used.</td>
<td>3-Significantdifferences</td>
<td>A5-2-2</td>
<td>Rule title and rationale reformulated, detailed explanation and possible alternatives added. Example reworked.</td>
</tr>
<tr class="even">
<td>Postfix expressions</td>
<td>M5–2–5</td>
<td>Required</td>
<td>A cast shall not remove any const or volatile qualification from the type of a pointer or reference.</td>
<td>2-Smalldifferences</td>
<td>A5-2-3</td>
<td>Added a note to rationale. Example reworked.</td>
</tr>
<tr class="odd">
<td>Postfix expressions</td>
<td>M5–2–6</td>
<td>Required</td>
<td>A cast shall not convert a pointer to a function to any other pointer type, including a pointer to function type.</td>
<td>1-Identical</td>
<td>M5-2-6</td>
<td>-</td>
</tr>
<tr class="even">
<td>Postfix expressions</td>
<td>M5–2–7</td>
<td>Required</td>
<td>An object with pointer type shall not be converted to an unrelated pointer type, either directly or indirectly.</td>
<td>3-Significantdifferences</td>
<td>A5-2-4</td>
<td>Rule title and rationale reformulated to prohibit re interpret_cast usage. Example reworked.</td>
</tr>
<tr class="odd">
<td>Postfix expressions</td>
<td>M5–2–8</td>
<td>Required</td>
<td>An object with integer type or pointer to void type shall not be converted to an object with pointer type.</td>
<td>1-Identical</td>
<td>M5-2-8</td>
<td>-</td>
</tr>
<tr class="even">
<td>Postfix expressions</td>
<td>M5–2–9</td>
<td>Advisory</td>
<td>A cast should not convert a pointer type to an integral type.</td>
<td>2-Smalldifferences</td>
<td>M5-2-9</td>
<td>Obligation level changed to “Required”.</td>
</tr>
<tr class="odd">
<td>Postfix expressions</td>
<td>M5–2–10</td>
<td>Advisory</td>
<td>The increment (++) and decrement (--) operators should not be mixed with other operators in an expression.</td>
<td>2-Smalldifferences</td>
<td>M5-2-10</td>
<td>Obligation level changed to “Required”.</td>
</tr>
<tr class="even">
<td>Postfix expressions</td>
<td>M5–2–11</td>
<td>Required</td>
<td>The comma operator, &amp;&amp; operator and the || operator shall not be overloaded.</td>
<td>1-Identical</td>
<td>M5-2-11</td>
<td>-</td>
</tr>
<tr class="odd">
<td>Postfix expressions</td>
<td>M5–2–12</td>
<td>Required</td>
<td>An identifier with array type passed as a function argument shall not decay to a pointer.</td>
<td>1-Identical</td>
<td>M5-2-12</td>
<td>-</td>
</tr>
<tr class="even">
<td>Unary expressions</td>
<td>M5–3–1</td>
<td>Required</td>
<td>Each operand of the ! operator, the logical &amp;&amp; or the logical || operators shall have type bool.</td>
<td>1-Identical</td>
<td>M5-3-1</td>
<td>-</td>
</tr>
<tr class="odd">
<td>Unary expressions</td>
<td>M5–3–2</td>
<td>Required</td>
<td>The unary minus operator shall not be applied to an expression whose underlying type is unsigned.</td>
<td>1-Identical</td>
<td>M5-3-2</td>
<td>-</td>
</tr>
<tr class="even">
<td>Unary expressions</td>
<td>M5–3–3</td>
<td>Required</td>
<td>The unary &amp; operator shall not be overloaded.</td>
<td>1-Identical</td>
<td>M5-3-3</td>
<td>-</td>
</tr>
<tr class="odd">
<td>Unary expressions</td>
<td>M5–3–4</td>
<td>Required</td>
<td>Evaluation of the operand to the sizeof operator shall not contain side effects.</td>
<td>1-Identical</td>
<td>M5-3-4</td>
<td>-</td>
</tr>
<tr class="even">
<td>Shift operators</td>
<td>M5–8–1</td>
<td>Required</td>
<td>The right hand operand of a shift operator shall lie between zero and one less than the width in bits of the underlying type of the left hand operand.</td>
<td>1-Identical</td>
<td>M5-8-1</td>
<td>-</td>
</tr>
<tr class="odd">
<td>Logical AND operator</td>
<td>M5–14–1</td>
<td>Required</td>
<td>The right hand operand of a logical &amp;&amp; or || operator shall not contain side effects.</td>
<td>1-Identical</td>
<td>M5-14-1</td>
<td>-</td>
</tr>
<tr class="even">
<td>Assignment operators</td>
<td>M5–17–1</td>
<td>Required</td>
<td>The semantic equivalence between a binary operator and its assignment operator form shall be preserved.</td>
<td>1-Identical</td>
<td>M5-17-1</td>
<td>-</td>
</tr>
<tr class="odd">
<td>Comma operator</td>
<td>M5–18–1</td>
<td>Required</td>
<td>The comma operator shall not be used.</td>
<td>1-Identical</td>
<td>M5-18-1</td>
<td>-</td>
</tr>
<tr class="even">
<td>Constant expressions</td>
<td>M5–19–1</td>
<td>Advisory</td>
<td>Evaluation of constant unsigned integer expressions should not lead to wrap-around.</td>
<td>2-Smalldifferences</td>
<td>M5-19-1</td>
<td>Obligation level changed to “Required”.</td>
</tr>
<tr class="odd">
<td>Expression statement</td>
<td>M6–2–1</td>
<td>Required</td>
<td>Assignment operators shall not be used in sub-expressions.</td>
<td>1-Identical</td>
<td>M6-2-1</td>
<td>-</td>
</tr>
<tr class="even">
<td>Expression statement</td>
<td>M6–2–2</td>
<td>Required</td>
<td>Floating-point expressions shall not be directly or indirectly tested for equality or inequality.</td>
<td>1-Identical</td>
<td>M6-2-2</td>
<td>-</td>
</tr>
<tr class="odd">
<td>Expression statement</td>
<td>M6–2–3</td>
<td>Required</td>
<td>Before preprocessing, a null statement shall only occur on a line by itself; it may be followed by a comment, provided that the first character following the null statement is a white-space character.</td>
<td>1-Identical</td>
<td>M6-2-3</td>
<td>-</td>
</tr>
<tr class="even">
<td>Compound statement</td>
<td>M6–3–1</td>
<td>Required</td>
<td>The statement forming the body of a switch, while, do ... while or for statement shall be a compound statement.</td>
<td>1-Identical</td>
<td>M6-3-1</td>
<td>-</td>
</tr>
<tr class="odd">
<td>Selection statements</td>
<td>M6–4–1</td>
<td>Required</td>
<td>An if ( condition ) construct shall be followed by a compound statement. The else keyword shall be followed by either a compound statement, or another if statement.</td>
<td>1-Identical</td>
<td>M6-4-1</td>
<td>-</td>
</tr>
<tr class="even">
<td>Selection statements</td>
<td>M6–4–2</td>
<td>Required</td>
<td>All if … else if constructs shall be terminated with an else clause.</td>
<td>1-Identical</td>
<td>M6-4-2</td>
<td>-</td>
</tr>
<tr class="odd">
<td>Selection statements</td>
<td>M6–4–3</td>
<td>Required</td>
<td>A switch statement shall be a well-formed switch statement.</td>
<td>1-Identical</td>
<td>M6-4-3</td>
<td>-</td>
</tr>
<tr class="even">
<td>Selection statements</td>
<td>M6–4–4</td>
<td>Required</td>
<td>A switch-label shall only be used when the most closely-enclosing compound statement is the body of a switch statement.</td>
<td>1-Identical</td>
<td>M6-4-4</td>
<td>-</td>
</tr>
<tr class="odd">
<td>Selection statements</td>
<td>M6–4–5</td>
<td>Required</td>
<td>An unconditional throw or break statement shall terminate every non-empty switch-clause.</td>
<td>1-Identical</td>
<td>M6-4-5</td>
<td>-</td>
</tr>
<tr class="even">
<td>Selection statements</td>
<td>M6–4–6</td>
<td>Required</td>
<td>The final clause of a switch statement shall be the default-clause.</td>
<td>1-Identical</td>
<td>M6-4-6</td>
<td>-</td>
</tr>
<tr class="odd">
<td>Selection statements</td>
<td>M6–4–7</td>
<td>Required</td>
<td>The condition of a switch statement shall not have bool type.</td>
<td>1-Identical</td>
<td>M6-4-7</td>
<td>-</td>
</tr>
<tr class="even">
<td>Selection statements</td>
<td>M6–4–8</td>
<td>Required</td>
<td>Every switch statement shall have at least one case-clause.</td>
<td>3-Significantdifferences</td>
<td>A6-4-1</td>
<td>Rule reformulated. Example reworked.</td>
</tr>
<tr class="odd">
<td>Iteration statements</td>
<td>M6–5–1</td>
<td>Required</td>
<td>A for loop shall contain a single loop-counter which shall not have floating type.</td>
<td>2-Smalldifferences</td>
<td>A6-5-2</td>
<td>Additional note about floating types added. Rule extended.</td>
</tr>
<tr class="even">
<td>Iteration statements</td>
<td>M6–5–2</td>
<td>Required</td>
<td>If loop-counter is not modified by -- or ++, then, within condition, the loop-counter shall only be used as an operand to &lt;=, &lt;, &gt; or &gt;=.</td>
<td>1-Identical</td>
<td>M6-5-2</td>
<td>-</td>
</tr>
<tr class="odd">
<td>Iteration statements</td>
<td>M6–5–3</td>
<td>Required</td>
<td>The loop-counter shall not be modified within condition or statement.</td>
<td>1-Identical</td>
<td>M6-5-3</td>
<td>-</td>
</tr>
<tr class="even">
<td>Iteration statements</td>
<td>M6–5–4</td>
<td>Required</td>
<td>The loop-counter shall be modified by one of: --, ++, -=n, or +=n; where n remains constant for the duration of the loop.</td>
<td>1-Identical</td>
<td>M6-5-4</td>
<td>-</td>
</tr>
<tr class="odd">
<td>Iteration statements</td>
<td>M6–5–5</td>
<td>Required</td>
<td>A loop-control-variable other than the loop-counter shall not be modified within condition or expression.</td>
<td>1-Identical</td>
<td>M6-5-5</td>
<td>-</td>
</tr>
<tr class="even">
<td>Iteration statements</td>
<td>M6–5–6</td>
<td>Required</td>
<td>A loop-control-variable other than the loop-counter which is modified in statement shall have type bool.</td>
<td>1-Identical</td>
<td>M6-5-6</td>
<td>-</td>
</tr>
<tr class="odd">
<td>Jump statements</td>
<td>M6–6–1</td>
<td>Required</td>
<td>Any label referenced by a goto statement shall be declared in the same block, or in a block enclosing the goto statement.</td>
<td>1-Identical</td>
<td>M6-6-1</td>
<td>-</td>
</tr>
<tr class="even">
<td>Jump statements</td>
<td>M6–6–2</td>
<td>Required</td>
<td>The goto statement shall jump to a label declared later in the same function body.</td>
<td>1-Identical</td>
<td>M6-6-2</td>
<td>-</td>
</tr>
<tr class="odd">
<td>Jump statements</td>
<td>M6–6–3</td>
<td>Required</td>
<td>The continue statement shall only be used within a well-formed for loop.</td>
<td>1-Identical</td>
<td>M6-6-3</td>
<td>-</td>
</tr>
<tr class="even">
<td>Jump statements</td>
<td>M6–6–4</td>
<td>Required</td>
<td>For any iteration statement there shall be no more than one break or goto statement used for loop termination.</td>
<td>4-Rejected</td>
<td>-</td>
<td>The goto statement shall not be used, see: A6-6-1.There can be more than one break in an iteration statement.</td>
</tr>
<tr class="odd">
<td>Jump statements</td>
<td>M6–6–5</td>
<td>Required</td>
<td>A function shall have a single point of exit at the end of the function.</td>
<td>4-Rejected</td>
<td>-</td>
<td>Single point of exit approach doesnot necessarily improve readability, maintainability and testability. A function can have multiple of points exit.</td>
</tr>
<tr class="even">
<td>Specifiers</td>
<td>M7–1–1</td>
<td>Required</td>
<td>A variable which is not modified shall be const qualified.</td>
<td>4-Rejected</td>
<td>-</td>
<td>Rule replaced with A7-1-1, A7-1-2 that concern const expr and const specifiers.</td>
</tr>
<tr class="odd">
<td>Specifiers</td>
<td>M7–1–2</td>
<td>Required</td>
<td>A pointer or reference parameter in a function shall be declared as pointer to const or reference to const if the corresponding object is not modified.</td>
<td>1-Identical</td>
<td>M7-1-2</td>
<td>-</td>
</tr>
<tr class="even">
<td>Enumeration declarations</td>
<td>M7–2–1</td>
<td>Required</td>
<td>An expression with enum underlying type shall only have values corresponding to the enumerators of the enumeration. Namespaces</td>
<td>2-Smalldifferences</td>
<td>A7-1-2</td>
<td>Example extended.</td>
</tr>
<tr class="odd">
<td>Enumeration declarations</td>
<td>M7–3–1</td>
<td>Required</td>
<td>The global namespace shall only contain main, namespace declarations and extern "C" declarations.</td>
<td>1-Identical</td>
<td>M7-3-1</td>
<td>-</td>
</tr>
<tr class="even">
<td>Enumeration declarations</td>
<td>M7–3–2</td>
<td>Required</td>
<td>The identifier main shall not be used for a function other than the global function main.</td>
<td>1-Identical</td>
<td>M7-3-2</td>
<td>-</td>
</tr>
<tr class="odd">
<td>Enumeration declarations</td>
<td>M7–3–3</td>
<td>Required</td>
<td>There shall be no unnamed namespaces in header files.</td>
<td>1-Identical</td>
<td>M7-3-3</td>
<td>-</td>
</tr>
<tr class="even">
<td>Enumeration declarations</td>
<td>M7–3–4</td>
<td>Required</td>
<td>using-directives shall not be used.</td>
<td>1-Identical</td>
<td>M7-3-4</td>
<td>-</td>
</tr>
<tr class="odd">
<td>Enumeration declarations</td>
<td>M7–3–5</td>
<td>Required</td>
<td>Multiple declarations for an identifier in the same namespace shall not straddle a using-declaration for that identifier.</td>
<td>1-Identical</td>
<td>M7-3-5</td>
<td>-</td>
</tr>
<tr class="even">
<td>Enumeration declarations</td>
<td>M7–3–6</td>
<td>Required</td>
<td>using-directives and using-declarations (excluding class scope or function scope using-declarations) shall not be used in header files.</td>
<td>1-Identical</td>
<td>M7-3-6</td>
<td>-</td>
</tr>
<tr class="odd">
<td>The asm declaration</td>
<td>M7–4–1</td>
<td>Document</td>
<td>All usage of assembler shall be documented.</td>
<td>1-Identical</td>
<td>M7-4-1</td>
<td>-</td>
</tr>
<tr class="even">
<td>The asm declaration</td>
<td>M7–4–2</td>
<td>Required</td>
<td>Assembler instructions shall only be introduced using the asm declaration.</td>
<td>1-Identical</td>
<td>M7-4-2</td>
<td>-</td>
</tr>
<tr class="odd">
<td>The asm declaration</td>
<td>M7–4–3</td>
<td>Required</td>
<td>Assembly language shall be encapsulated and isolated.</td>
<td>1-Identical</td>
<td>M7-4-3</td>
<td>-</td>
</tr>
<tr class="even">
<td>Linkage specifications</td>
<td>M7–5–1</td>
<td>Required</td>
<td>A function shall not return a reference or a pointer to an automatic variable (including parameters), defined within the function.</td>
<td>1-Identical</td>
<td>M7-5-1</td>
<td>-</td>
</tr>
<tr class="odd">
<td>Linkage specifications</td>
<td>M7–5–2</td>
<td>Required</td>
<td>The address of an object with automatic storage shall not be assigned to another object that may persist after the first object has ceased to exist.</td>
<td>2-Smalldifferences</td>
<td>M7-5-2</td>
<td>Added a note saying that the rule applies to std::unique_ptr, std::shared_ptr and std::weak_ptr too.</td>
</tr>
<tr class="even">
<td>Linkage specifications</td>
<td>M7–5–3</td>
<td>Required</td>
<td>A function shall not return a reference or a pointer to a parameter that is passed by reference or const reference.</td>
<td>3-Significantdifferences</td>
<td>A7-5-2</td>
<td>Rule reformulated so it is allowed to return a reference or pointer to non-const reference parameter. Rationale reformulated. Example reworked.</td>
</tr>
<tr class="odd">
<td>Linkage specifications</td>
<td>M7–5–4</td>
<td>Advisory</td>
<td>Functions should not call themselves, either directly or indirectly.</td>
<td>2-Smalldifferences</td>
<td>A7-5-1</td>
<td>Obligation level changed to “Required”. Examplere worked.</td>
</tr>
<tr class="even">
<td>Declarators — General</td>
<td>M8–0–1</td>
<td>Required</td>
<td>An init-declarator-list or a member-declarator-list shall consist of a single init-declarator or member-declarator respectively.</td>
<td>1-Identical</td>
<td>M8-0-1</td>
<td>-</td>
</tr>
<tr class="odd">
<td>Meaning of declarators</td>
<td>M8–3–1</td>
<td>Required</td>
<td>Parameters in an overriding virtual function shall either use the same default arguments as the function they override, or else shall not specify any default arguments.</td>
<td>1-Identical</td>
<td>M8-3-1</td>
<td>-</td>
</tr>
<tr class="even">
<td>Function definitions</td>
<td>M8–4–1</td>
<td>Required</td>
<td>Functions shall not be defined using the ellipsis notation.</td>
<td>3-Significantdifferences</td>
<td>A8-4-1</td>
<td>Rationale reformulated. Added a note that variadic templates should be used instead. Example extended.</td>
</tr>
<tr class="odd">
<td>Function definitions</td>
<td>M8–4–2</td>
<td>Required</td>
<td>The identifiers used for the parameters in a re-declaration of a function shall be identical to those in the declaration.</td>
<td>1-Identical</td>
<td>M8-4-2</td>
<td>-</td>
</tr>
<tr class="even">
<td>Function definitions</td>
<td>M8–4–3</td>
<td>Required</td>
<td>All exit paths from a function with non-void return type shall have an explicit return statement with an expression.</td>
<td>2-Smalldifferences</td>
<td>A8-4-2</td>
<td>Rule reformulated so it applies to void return type functions. Example reworked so there is no throwing an exception of type int.</td>
</tr>
<tr class="odd">
<td>Function definitions</td>
<td>M8–4–4</td>
<td>Required</td>
<td>A function identifier shall either be used to call the function or it shall be preceded by &amp;.</td>
<td>1-Identical</td>
<td>M8-4-4</td>
<td>-</td>
</tr>
<tr class="even">
<td>Declarators — Initializers</td>
<td>M8–5–1</td>
<td>Required</td>
<td>All variables shall have a defined value before they are used.</td>
<td>1-Identical</td>
<td>M8-5-1</td>
<td>-</td>
</tr>
<tr class="odd">
<td>Declarators — Initializers</td>
<td>M8–5–2</td>
<td>Required</td>
<td>Braces shall be used to indicate and match the structure in the nonzero initialization of arrays and structures.</td>
<td>1-Identical</td>
<td>M8-5-2</td>
<td>-</td>
</tr>
<tr class="even">
<td>Declarators — Initializers</td>
<td>M8–5–3</td>
<td>Required</td>
<td>In an enumerator list, the = construct shall not be used to explicitly initialize members other than the first, unless all items are explicitly initialized.</td>
<td>3-Significantdifferences</td>
<td>A7-2-4</td>
<td>Rule and rationale reformulated. Example reworked.</td>
</tr>
<tr class="odd">
<td>Member functions</td>
<td>M9–3–1</td>
<td>Required</td>
<td>const member functions shall not return non-const pointers or references to class-data.</td>
<td>1-Identical</td>
<td>M9-3-1</td>
<td>-</td>
</tr>
<tr class="even">
<td>Member functions</td>
<td>M9–3–2</td>
<td>Required</td>
<td>Member functions shall not return non-const handles to class-data.</td>
<td>2-Smalldifferences</td>
<td>A9-3-1</td>
<td>Explanation improved. Example reworked.</td>
</tr>
<tr class="odd">
<td>Member functions</td>
<td>M9–3–3</td>
<td>Required</td>
<td>If a member function can be made static then it shall be made static, otherwise if it can be made const then it shall be made const.</td>
<td>1-Identical</td>
<td>M9-3-3</td>
<td>-</td>
</tr>
<tr class="even">
<td>Unions</td>
<td>M9–5–1</td>
<td>Required</td>
<td>Unions shall not be used.</td>
<td>1-Identical</td>
<td>M9-5-1</td>
<td>-</td>
</tr>
<tr class="odd">
<td>Bit-fields</td>
<td>M9–6–1</td>
<td>Document</td>
<td>When the absolute positioning of bits representing a bit-field is required, then the behaviour and packing of bit-fields shall be documented.</td>
<td>1-Identical</td>
<td>M9-6-1</td>
<td>-</td>
</tr>
<tr class="even">
<td>Bit-fields</td>
<td>M9–6–2</td>
<td>Required</td>
<td>Bit-fieldsshall be either bool type or an explicitly unsigned or signed integral type.</td>
<td>4-Rejected</td>
<td>-</td>
<td>Permitted types changed. New rule introduced: A9-6-1.</td>
</tr>
<tr class="odd">
<td>Bit-fields</td>
<td>M9–6–3</td>
<td>Required</td>
<td>Bit-fields shall not have enum type.</td>
<td>4-Rejected</td>
<td>-</td>
<td>Permitted types changed. New rule introduced: A9-6-1.</td>
</tr>
<tr class="even">
<td>Bit-fields</td>
<td>M9–6–4</td>
<td>Required</td>
<td>Named bit-fields with signed integer type shall have a length of more than one bit.</td>
<td>4-Rejected</td>
<td>-</td>
<td>Permitted types changed. New rule introduced: A9-6-1.</td>
</tr>
<tr class="odd">
<td>Multiple base classes</td>
<td>M10–1–1</td>
<td>Advisory</td>
<td>Classes should not be derived from virtual bases.</td>
<td>1-Identical</td>
<td>M10-1-1</td>
<td>-</td>
</tr>
<tr class="even">
<td>Multiple base classes</td>
<td>M10–1–2</td>
<td>Required</td>
<td>A base class shall only be declared virtual if it is used in a diamond hierarchy.</td>
<td>4-Rejected</td>
<td>-</td>
<td>Multiple inheritance is not allowed.</td>
</tr>
<tr class="odd">
<td>Multiple base classes</td>
<td>M10–1–3</td>
<td>Required</td>
<td>An accessible base class shall not be both virtual and non-virtual in the same hierarchy.</td>
<td>1-Identical</td>
<td>M10-1-3</td>
<td>-</td>
</tr>
<tr class="even">
<td>Member name lookup</td>
<td>M10–2–1</td>
<td>Advisory</td>
<td>All accessible entity names within a multiple inheritance hierarchy should be unique.</td>
<td>1-Identical</td>
<td>M10-2-1</td>
<td>-</td>
</tr>
<tr class="odd">
<td>Virtual functions</td>
<td>M10–3–1</td>
<td>Required</td>
<td>There shall be no more than one definition of each virtual function on each path through the inheritance hierarchy.</td>
<td>4-Rejected</td>
<td>-</td>
<td>Rule already covered by A10-1-1 and A10-3-1</td>
</tr>
<tr class="even">
<td>Virtual functions</td>
<td>M10–3–2</td>
<td>Required</td>
<td>Each overriding virtual function shall be declared with the virtual keyword.</td>
<td>3-Significantdifferences</td>
<td>A10-3-2</td>
<td>Rule and rationale reformulated so the override specifier should e used instead of virtual keyword. Example reworked.</td>
</tr>
<tr class="odd">
<td>Virtual functions</td>
<td>M10–3–3</td>
<td>Required</td>
<td>A virtual function shall only be overridden by a pure virtual function if it is itself declared as pure virtual.</td>
<td>1-Identical</td>
<td>M10-3-3</td>
<td>-</td>
</tr>
<tr class="even">
<td>Member access control — General</td>
<td>M11–0–1</td>
<td>Required</td>
<td>Member data in non-POD class types shall be private.</td>
<td>1-Identical</td>
<td>M11-0-1</td>
<td>-</td>
</tr>
<tr class="odd">
<td>Constructors</td>
<td>M12–1–1</td>
<td>Required</td>
<td>An object’s dynamic type shall not be used from the body of its constructor or destructor.</td>
<td>1-Identical</td>
<td>M12-1-1</td>
<td>-</td>
</tr>
<tr class="even">
<td>Constructors</td>
<td>M12–1–2</td>
<td>Advisory</td>
<td>All constructors of a class should explicitly call a constructor for all of its immediate base classes and all virtual base classes.</td>
<td>3-Significantdifferences</td>
<td>A12-1-1</td>
<td>Obligation level changed to “Required”. Rule reformulated to cover non-static class data members. Rationale reformulated. Example reworked.</td>
</tr>
<tr class="odd">
<td>Constructors</td>
<td>M12–1–3</td>
<td>Required</td>
<td>All constructors that are callable with a single argument of fundamental type shall be declared explicit.</td>
<td>2-Smalldifferences</td>
<td>A12-1-4</td>
<td>Example reworked.</td>
</tr>
<tr class="even">
<td>Copying class objects</td>
<td>M12–8–1</td>
<td>Required</td>
<td>A copy constructor shall only initialize its base classes and the nonstatic members of the class of which it is a member.</td>
<td>3-Significantdifferences</td>
<td>A12-8-1</td>
<td>Rule reformulated to cover move constructors, too. Rationale reformulated. Example reworked.</td>
</tr>
<tr class="odd">
<td>Copying class objects</td>
<td>M12–8–2</td>
<td>Required</td>
<td>The copy assignment operator shall be declared protected or private in an abstract class.</td>
<td>3-Significantdifferences</td>
<td>A12-8-6<br />
A12-8-1</td>
<td>Rule reformulated to cover move assignment operators and all base classes. Rationale reformulated. Example reworked. Rule reformulated to cover move constructors, too. Rationale reformulated. Examplere worked.</td>
</tr>
<tr class="even">
<td>Template declarations</td>
<td>M14–5–1</td>
<td>Required</td>
<td>A non-member generic function shall only be declared in a namespace that is not an associated namespace.</td>
<td>4-Rejected</td>
<td>-</td>
<td>Usage of the ADL functionality is allowed. It is also used in STL for overloaded operators lookup in e.g. out streams, STL containers.</td>
</tr>
<tr class="odd">
<td>Template declarations</td>
<td>M14–5–2</td>
<td>Required</td>
<td>A copy constructor shall be declared when there is a template constructor with a single parameter that is a generic parameter.</td>
<td>1-Identical</td>
<td>M14-5-2</td>
<td>-</td>
</tr>
<tr class="even">
<td>Template declarations</td>
<td>M14–5–3</td>
<td>Required</td>
<td>A copy assignment operator shall be declared when there is a template assignment operator with a parameter that is a generic parameter.</td>
<td>1-Identical</td>
<td>M14-5-3</td>
<td>-</td>
</tr>
<tr class="odd">
<td>Name resolution</td>
<td>M14–6–1</td>
<td>Required</td>
<td>In a class template with a dependent base, any name that may be found in that dependent base shall be referred to using a qualified-id or this-&gt;</td>
<td>1-Identical</td>
<td>M14-6-1</td>
<td>-</td>
</tr>
<tr class="even">
<td>Name resolution</td>
<td>M14–6–2</td>
<td>Required</td>
<td>The function chosen by overload resolution shall resolve to a function declared previously in the translation unit.</td>
<td>4-Rejected</td>
<td>-</td>
<td>Usage of the ADL functionality is allowed. It is also used in STL for over loaded operator’s lookup in e.g. out streams, STL containers.</td>
</tr>
<tr class="odd">
<td>Template instantiation and specialization</td>
<td>M14–7–1</td>
<td>Required</td>
<td>All class templates, function templates, class template member functions and class template static members shall be instantiated at least once.</td>
<td>4-Rejected</td>
<td>-</td>
<td>It is allowed to not use all of the public methods of a class.</td>
</tr>
<tr class="even">
<td>Template instantiation and specialization</td>
<td>M14–7–2</td>
<td>Required</td>
<td>For any given template specialization, an explicit instantiation of the template with the template-arguments used in the specialization shall not render the program ill-formed.</td>
<td>3-Significantdifferences</td>
<td>A14-7-1</td>
<td>Rule reformulated to explicitly state what is required. Example reworked.</td>
</tr>
<tr class="odd">
<td>Template instantiation and specialization</td>
<td>M14–7–3</td>
<td>Required</td>
<td>All partial and explicit specializations for a template shall be declared in the same file as the declaration of their primary template.</td>
<td>1-Identical</td>
<td>M14-7-3</td>
<td>-</td>
</tr>
<tr class="even">
<td>Function template specialization</td>
<td>M14–8–1</td>
<td>Required</td>
<td>Overloaded function templates shall not be explicitly specialized.</td>
<td>1-Identical</td>
<td>M14-8-1</td>
<td>-</td>
</tr>
<tr class="odd">
<td>Function template specialization</td>
<td>M14–8–2</td>
<td>Advisory</td>
<td>The viable function set for a function call should either contain no function specializations, or only contain function specializations.</td>
<td>2-Smalldifferences</td>
<td>A14-8-1</td>
<td>Rule slightly reformulated. Example significantly reworked.</td>
</tr>
<tr class="even">
<td>Exception handling — General</td>
<td>M15–0–1</td>
<td>Document</td>
<td>Exceptions shall only be used for error handling.</td>
<td>3-Significantdifferences</td>
<td>A15-0-1</td>
<td>Rule reformulated, example significantly extended.</td>
</tr>
<tr class="odd">
<td>Exception handling — General</td>
<td>M15–0–2</td>
<td>Advisory</td>
<td>An exception object should not have pointer type.</td>
<td>3-Significantdifferences</td>
<td>A15-1-2</td>
<td>Obligation level changed, rule re formulated.</td>
</tr>
<tr class="even">
<td>Exception handling — General</td>
<td>M15–0–3</td>
<td>Required</td>
<td>Control shall not be transferred into a try or catch block using a goto or a switch statement.</td>
<td>1-Identical</td>
<td>M15-0-3</td>
<td>-</td>
</tr>
<tr class="odd">
<td>Throwing an exception</td>
<td>M15–1–1</td>
<td>Required</td>
<td>The assignment-expression of a throw statement shall not itself cause an exception to be thrown.</td>
<td>1-Identical</td>
<td>M15-1-1</td>
<td>-</td>
</tr>
<tr class="even">
<td>Throwing an exception</td>
<td>M15–1–2</td>
<td>Required</td>
<td>NULL shall not be thrown explicitly.</td>
<td>1-Identical</td>
<td>M15-1-2</td>
<td>-</td>
</tr>
<tr class="odd">
<td>Throwing an exception</td>
<td>M15–1–3</td>
<td>Required</td>
<td>An empty throw (throw;) shall only be used in the compoundstatement of a catch handler.</td>
<td>1-Identical</td>
<td>M15-1-3</td>
<td>-</td>
</tr>
<tr class="even">
<td>Handling an exception</td>
<td>M15–3–1</td>
<td>Required</td>
<td>Exceptions shall be raised only after start-up and before termination of the program.</td>
<td>1-Identical</td>
<td>M15-3-1</td>
<td>-</td>
</tr>
<tr class="odd">
<td>Handling an exception</td>
<td>M15–3–2</td>
<td>Advisory</td>
<td>There should be at least one exception handler to catch all otherwise unhandled exceptions</td>
<td>2-Smalldifferences</td>
<td>A15-3-3</td>
<td>Obligation level changed. Rule extended to cover multi-threading.</td>
</tr>
<tr class="even">
<td>Handling an exception</td>
<td>M15–3–3</td>
<td>Required</td>
<td>Handlers of a function-try-block implementation of a class constructor or destructor shall not reference non-static members from this class or its bases.</td>
<td>1-Identical</td>
<td>M15-3-3</td>
<td>-</td>
</tr>
<tr class="odd">
<td>Handling an exception</td>
<td>M15–3–4</td>
<td>Required</td>
<td>Each exception explicitly thrown in the code shall have a handler of a compatible type in all call paths that could lead to that point.</td>
<td>1-Identical</td>
<td>M15-3-4</td>
<td>-</td>
</tr>
<tr class="even">
<td>Handling an exception</td>
<td>M15–3–5</td>
<td>Required</td>
<td>A class type exception shall always be caught by reference.</td>
<td>2-Smalldifferences</td>
<td>A15-3-5</td>
<td>Possibility to catch by const reference added</td>
</tr>
<tr class="odd">
<td>Handling an exception</td>
<td>M15–3–6</td>
<td>Required</td>
<td>Where multiple handlers are provided in a single try-catch statement or function-try-block for a derived class and some or all of its bases, the handlers shall be ordered most-derived to base class.</td>
<td>1-Identical</td>
<td>M15-3-6</td>
<td>-</td>
</tr>
<tr class="even">
<td>Handling an exception</td>
<td>M15–3–7</td>
<td>Required</td>
<td>Where multiple handlers are provided in a single try-catch statement or function-try-block, any ellipsis (catch-all) handler shall occur last.</td>
<td>1-Identical</td>
<td>M15-3-7</td>
<td>-</td>
</tr>
<tr class="odd">
<td>Exception specifications</td>
<td>M15–4–1</td>
<td>Required</td>
<td>If a function is declared with an exception-specification, then all declarations of the same function (in other translation units) shall be declared with the same set of type-ids.</td>
<td>4-Rejected</td>
<td>-</td>
<td>Dynamic exception specification was prohibited. No except specifier shall be used instead.</td>
</tr>
<tr class="even">
<td>Exception handling — Special functions</td>
<td>M15–5–1</td>
<td>Required</td>
<td>A class destructor shall not exit with an exception.</td>
<td>3-Significantdifferences</td>
<td>A15-5-1</td>
<td>Rule significantly extended with other special functions and operators.</td>
</tr>
<tr class="odd">
<td>Exception handling — Special functions</td>
<td>M15–5–2</td>
<td>Required</td>
<td>Where a function’s declaration includes an exception-specification, the function shall only be capable of throwing exceptions of the indicated type(s).</td>
<td>4-Rejected</td>
<td>-</td>
<td>Dynamic exception specification was prohibited.</td>
</tr>
<tr class="even">
<td>Exception handling — Special functions</td>
<td>M15–5–3</td>
<td>Required</td>
<td>The terminate() function shall not be called implicitly</td>
<td>2-Smalldifferences</td>
<td>A15-5-3</td>
<td>Rationale and example extended.</td>
</tr>
<tr class="odd">
<td>Preprocessing directives — General</td>
<td>M16–0–1</td>
<td>Required</td>
<td>#include directives in a file shall only be preceded by other preprocessor directives or comments.</td>
<td>1-Identical</td>
<td>M16-0-1</td>
<td>-</td>
</tr>
<tr class="even">
<td>Preprocessing directives — General</td>
<td>M16–0–2</td>
<td>Required</td>
<td>Macros shall only be #define’d or #undef’d in the global namespace.</td>
<td>1-Identical</td>
<td>M16-0-2</td>
<td>-</td>
</tr>
<tr class="odd">
<td>Preprocessing directives — General</td>
<td>M16–0–3</td>
<td>Required</td>
<td>#undef shall not be used.</td>
<td>4-Rejected</td>
<td>-</td>
<td>The rule replaced with global rule: A16-0-1.</td>
</tr>
<tr class="even">
<td>Preprocessing directives — General</td>
<td>M16–0–4</td>
<td>Required</td>
<td>Function-like macros shall not be defined.</td>
<td>4-Rejected</td>
<td>-</td>
<td>The rule replaced with global rule: A16-0-1.</td>
</tr>
<tr class="odd">
<td>Preprocessing directives — General</td>
<td>M16–0–5</td>
<td>Required</td>
<td>Arguments to a function-like macro shall not contain tokens that look like preprocessing directives.</td>
<td>1-Identical</td>
<td>M16-0-5</td>
<td>-</td>
</tr>
<tr class="even">
<td>Preprocessing directives — General</td>
<td>M16–0–6</td>
<td>Required</td>
<td>In the definition of a function-like macro, each instance of a parameter shall be enclosed in parentheses, unless it is used as the operand of # or ##.</td>
<td>1-Identical</td>
<td>M16-0-6</td>
<td>-</td>
</tr>
<tr class="odd">
<td>Preprocessing directives — General</td>
<td>M16–0–7</td>
<td>Required</td>
<td>Undefined macro identifiers shall not be used in #if or #elif preprocessor directives, except as operands to the defined operator.</td>
<td>1-Identical</td>
<td>M16-0-7</td>
<td>-</td>
</tr>
<tr class="even">
<td>Preprocessing directives — General</td>
<td>M16–0–8</td>
<td>Required</td>
<td>If the # token appears as the first token on a line, then it shall be immediately followed by a preprocessing token.</td>
<td>1-Identical</td>
<td>M16-0-8</td>
<td>-</td>
</tr>
<tr class="odd">
<td>Conditional inclusion</td>
<td>M16–1–1</td>
<td>Required</td>
<td>The defined preprocessor operator shall only be used in one of the two standard forms.</td>
<td>1-Identical</td>
<td>M16-1-1</td>
<td>-</td>
</tr>
<tr class="even">
<td>Conditional inclusion</td>
<td>M16–1–2</td>
<td>Required</td>
<td>All #else, #elif and #endif preprocessor directives shall reside in the same file as the #if or #ifdef directive to which they are related.</td>
<td>1-Identical</td>
<td>M16-1-2</td>
<td>-</td>
</tr>
<tr class="odd">
<td>Source file inclusion</td>
<td>M16–2–1</td>
<td>Required</td>
<td>The pre-processor shall only be used for file inclusion and include guards.</td>
<td>4-Rejected</td>
<td>-</td>
<td>The rule replaced with global rule: A16-0-1.</td>
</tr>
<tr class="even">
<td>Source file inclusion</td>
<td>M16–2–2</td>
<td>Required</td>
<td>C++ macros shall only be used for: include guards, type qualifiers, or storage class specifiers.</td>
<td>4-Rejected</td>
<td>-</td>
<td>The rule replaced with global rule: A16-0-1.</td>
</tr>
<tr class="odd">
<td>Source file inclusion</td>
<td>M16–2–3</td>
<td>Required</td>
<td>Include guards shall be provided.</td>
<td>1-Identical</td>
<td>M16-2-3</td>
<td>-</td>
</tr>
<tr class="even">
<td>Source file inclusion</td>
<td>M16–2–4</td>
<td>Required</td>
<td>The ', ", /* or // characters shall not occur in a header file name.</td>
<td>2-Smalldifferences</td>
<td>A16-2-1</td>
<td>Merged with MISRA Rule 16-2-5.</td>
</tr>
<tr class="odd">
<td>Source file inclusion</td>
<td>M16–2–5</td>
<td>Advisory</td>
<td>The \ character should not occur in a header file name.</td>
<td>2-Smalldifferences</td>
<td>A16-2-1</td>
<td>Obligation level changed to “Required”. Merged with MISRA Rule 16-2-4.</td>
</tr>
<tr class="even">
<td>Source file inclusion</td>
<td>M16–2–6</td>
<td>Required</td>
<td>The #include directive shall be followed by either a &lt;filename&gt; or "filename" sequence.</td>
<td>4-Rejected</td>
<td>-</td>
<td>These are the only forms allowed by the C++ Language Standard; No need for a new rule.</td>
</tr>
<tr class="odd">
<td>Macro replacement</td>
<td>M16–3–1</td>
<td>Required</td>
<td>There shall be at most one occurrence of the # or ## operators in a single macro definition.</td>
<td>1-Identical</td>
<td>M16-3-1</td>
<td>-</td>
</tr>
<tr class="even">
<td>Macro replacement</td>
<td>M16–3–2</td>
<td>Advisory</td>
<td>The # and ## operators should not be used.</td>
<td>1-Identical</td>
<td>M16-3-2</td>
<td>-</td>
</tr>
<tr class="odd">
<td>Pragma directive</td>
<td>M16–6–1</td>
<td>Document</td>
<td>All uses of the #pragma directive shall be documented.</td>
<td>4-Rejected</td>
<td>-</td>
<td>The #pragma directive shall not be used, see: A16-7-1.</td>
</tr>
<tr class="even">
<td>Library introduction — General</td>
<td>M17–0–1</td>
<td>Required</td>
<td>Reserved identifiers, macros and functions in the standard library shall not be defined, redefined or undefined.</td>
<td>2-Smalldifferences</td>
<td>A17-0-1</td>
<td>Example extended</td>
</tr>
<tr class="odd">
<td>Library introduction — General</td>
<td>M17–0–2</td>
<td>Required</td>
<td>The names of standard library macros and objects shall not be reused.</td>
<td>1-Identical</td>
<td>M17-0-2</td>
<td>-</td>
</tr>
<tr class="even">
<td>Library introduction — General</td>
<td>M17–0–3</td>
<td>Required</td>
<td>The names of standard library functions shall not be overridden.</td>
<td>1-Identical</td>
<td>M17-0-3</td>
<td>-</td>
</tr>
<tr class="odd">
<td>Library introduction — General</td>
<td>M17–0–4</td>
<td>Document</td>
<td>All library code shall conform to MISRA C++.</td>
<td>4-Rejected</td>
<td>-</td>
<td>The rule replaced with A17-0-2 saying that all code shall conform to AUTOSAR C++14 Coding Guidelines.</td>
</tr>
<tr class="even">
<td>Library introduction — General</td>
<td>M17–0–5</td>
<td>Required</td>
<td>The setjmp macro and the longjmp function shall not be used.</td>
<td>1-Identical</td>
<td>M17-0-5</td>
<td>-</td>
</tr>
<tr class="odd">
<td>Language support library — General</td>
<td>M18–0–1</td>
<td>Required</td>
<td>The C library shall not be used.</td>
<td>2-Smalldifferences</td>
<td>A18-0-1</td>
<td>Rule re formulated.</td>
</tr>
<tr class="even">
<td>Language support library — General</td>
<td>M18–0–2</td>
<td>Required</td>
<td>The library functions atof, atoi and atol from library &lt;cstdlib&gt; shall not be used.</td>
<td>2-Smalldifferences</td>
<td>A18-0-2</td>
<td>Compliant alternatives into rationale.</td>
</tr>
<tr class="odd">
<td>Language support library — General</td>
<td>M18–0–3</td>
<td>Required</td>
<td>The library functions abort, exit, getenv and system from library &lt;cstdlib&gt; shall not be used.</td>
<td>1-Identical</td>
<td>M18-0-3</td>
<td>-</td>
</tr>
<tr class="even">
<td>Language support library — General</td>
<td>M18–0–4</td>
<td>Required</td>
<td>The time handling functions of library &lt;ctime&gt; shall not be used.</td>
<td>1-Identical</td>
<td>M18-0-4</td>
<td>-</td>
</tr>
<tr class="odd">
<td>Language support library — General</td>
<td>M18–0–5</td>
<td>Required</td>
<td>The unbounded functions of library &lt;cstring&gt; shall not be used.</td>
<td>1-Identical</td>
<td>M18-0-5</td>
<td>-</td>
</tr>
<tr class="even">
<td>Language support library — Implementation properties</td>
<td>M18–2–1</td>
<td>Required</td>
<td>The macro offsetof shall not be used.</td>
<td>1-Identical</td>
<td>M18-2-1</td>
<td>-</td>
</tr>
<tr class="odd">
<td>Language support library — Dynamic memory management</td>
<td>M18–4–1</td>
<td>Required</td>
<td>Dynamic heap memory allocation shall not be used.</td>
<td>4-Rejected</td>
<td>-</td>
<td>Dynamic heap memory allocation usage is allowed conditionally, see: A18-5-1, A18-5-2, A18-5-3.</td>
</tr>
<tr class="even">
<td>Language support library — Other runtime support</td>
<td>M18–7–1</td>
<td>Required</td>
<td>The signal handling facilities of &lt;csignal&gt; shall not be used.</td>
<td>1-Identical</td>
<td>M18-7-1</td>
<td>-</td>
</tr>
<tr class="odd">
<td>Diagnostics library — Error numbers</td>
<td>M19–3–1</td>
<td>Required</td>
<td>The error indicator errno shall not be used.</td>
<td>1-Identical</td>
<td>M19-3-1</td>
<td>-</td>
</tr>
<tr class="even">
<td>Input/output library — General</td>
<td>M27–0–1</td>
<td>Required</td>
<td>The stream input/output library &lt;cstdio&gt; shall not be used.</td>
<td>1-Identical</td>
<td>M27-0-1</td>
<td>-</td>
</tr>
</tbody>
</table>
