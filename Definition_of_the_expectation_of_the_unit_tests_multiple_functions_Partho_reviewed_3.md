# **Definition of the expectation of the unit tests: multiple functions**

# **  
Guides and Standards**

<table>
<tbody>
<tr class="odd">
<td></td>
<td></td>
</tr>
<tr class="even">
<td></td>
<td></td>
</tr>
<tr class="odd">
<td></td>
<td></td>
</tr>
<tr class="even">
<td></td>
<td></td>
</tr>
<tr class="odd">
<td></td>
<td></td>
</tr>
<tr class="even">
<td></td>
<td></td>
</tr>
<tr class="odd">
<td></td>
<td></td>
</tr>
<tr class="even">
<td></td>
<td></td>
</tr>
<tr class="odd">
<td></td>
<td></td>
</tr>
<tr class="even">
<td></td>
<td></td>
</tr>
<tr class="odd">
<td></td>
<td></td>
</tr>
<tr class="even">
<td></td>
<td></td>
</tr>
<tr class="odd">
<td><strong>Creation date:</strong></td>
<td>30.01.2024</td>
</tr>
<tr class="even">
<td><strong>Version 1.0:</strong></td>
<td>30.01.2024</td>
</tr>
<tr class="odd">
<td><strong>Author:</strong></td>
<td><p>Andrej Cepygin</p>
<p>Marina Rodrigues Crespo</p></td>
</tr>
</tbody>
</table>

# **Contents**

[1 Scope 3](#scope)

[1.1 Document Overview 3](#_Toc154755256)

[1.2 Abbreviations 4](#_Toc154755257)

[1.3 Revisions 4](#revisions)

[1.4 Referenced Documents 4](#referenced-documents)

[2 Expectations for Unit Tests for multiple functions 5](#_Toc154755260)

[2.1 Callback Mechanism 5](#_Toc154755261)

[3 Setting Up the Environment 5](#_Toc154755263)

2.2 Chain of Responsibility……………………………………………………………………….52.3 Conditional
Function Calls……………………………………………………………………54 Writing Test cases
………………………………………………………………………………..65 Tips for
General Use………………………………………………………………………………7

# Scope

This document provides an overview of the expectations of a unit test
for multiple functions.

## Revisions

| **Rev** | **Actions** | **Comment** |
| ------- | ----------- | ----------- |
| \-      | First Issue |             |
|         |             |             |

## Referenced Documents

Add to the table other documents related to the topic that are
cited/quoted in the text. For example, if the document is about general
aspects of Linux, other more in-depth documents on the subject may be
cited (for example, a how-to on a specific aspect of Linux). If no other
documents are cited, this heading can be deleted.

| **Reference and Title** | **Document Type** | **(Rev./Date)** | **Publisher** |
| ----------------------- | ----------------- | --------------- | ------------- |
|                         |                   |                 |               |
|                         |                   |                 |               |

# Expectations for Unit tests for multiple functions

The expectation of unit tests for multiple functions refers to the
anticipated behavior and outcomes of tests that assess the interactions
and collaborations between different functions within a software
program. While unit tests for single functions focus on isolating and
testing individual pieces of code, tests for multiple functions examine
how these functions work together to achieve broader functionality.

### Some examples of interactions between functions:

  - **Callback Mechanism:** A function A accepts a callback function B
    and calls it under certain conditions.

  - Testing: Use a mock object to test that A calls B with the correct
    arguments and at the right time.

  - **Chain of Responsibility:** A function A calls function B, and then
    B calls function C.

  - Testing: Verify that A calls B, and B in turn calls C. Use mocks to
    ensure each function is called in the correct order with the right
    arguments.

  - **Conditional Function Calls:** A function A calls function B or C
    based on some condition.

  - Testing: Test both branches of the condition, ensuring that A
    correctly decides whether to call B or C.

### Key components to the expectation of unit tests for multiple functions 

  - **Isolation:** Each test should focus on a specific aspect or
    behavior of the system. It's important to isolate the function or
    interaction being tested to ensure that the test results are
    reliable and not influenced by external factors or states from other
    tests.

  - **Mocking and Stubs:** Using mocks and stubs is essential for
    isolating the function under test and controlling its environment.
    They allow you to simulate the behavior of dependencies and verify
    interactions between components, making your tests more focused and
    reliable.

  - **Coverage:** Adequate test coverage is important to ensure that all
    relevant code paths and scenarios are tested. This includes not only
    the "happy path" but also edge cases, boundary conditions, and error
    handling scenarios.

# Setting Up the Environment

  - **Include Google Test and Google Mock:** Ensure you have Google Test
    and Google Mock included in your project.

  - **Define Mock Classes:** For the components you're testing, define
    mock classes that inherit from the interfaces or base classes of the
    components you want to mock.

  - **Use Mock Objects:** In your test, use these mock objects to
    simulate the behavior of the real components.

# Writing Test Cases

When writing test cases for multifunction interactions, consider the
following as an example how they can interact:

**Function Call Order:** If the order of function calls is important,
use \`In Sequence\` to enforce that calls happen in a specific order.

**Expecting Calls with Specific Arguments:** Use \`EXPECT\_CALL\` with
matchers to specify expected arguments.

**Expecting Calls a Certain Number of Times:** Use \`. Times(n)\` to
expect that a function is called \`n\` times.

**Setting Return Values:** Use \`.WillOnce\` or \`.WillRepeatedly\` to
define return values for function calls.

### Example

Let's consider an example where you have two components: \`ComponentA\`
and \`ComponentB\`. \`ComponentA\` has a function \`foo()\` and
\`ComponentB\` has a function \`bar()\`. You want to test a function
\`testFunction()\` that uses these components.

First, define the mock classes:

> class MockComponentA : public ComponentA {
> 
> public:
> 
> MOCK\_METHOD(int, foo, (), (override));
> 
> };
> 
> class MockComponentB : public ComponentB {
> 
> public:
> 
> MOCK\_METHOD(void, bar, (int), (override));
> 
> };

Now, write a test case:

> <span class="smallcaps">TEST(MyTestSuite, TestFunction) {</span>
> 
> <span class="smallcaps">MockComponentA mockA;</span>
> 
> <span class="smallcaps">MockComponentB mockB;</span>
> 
> <span class="smallcaps">Sequence s;</span>
> 
> <span class="smallcaps">// Expect foo() to be called once and return
> 42</span>
> 
> <span class="smallcaps">EXPECT\_CALL(mockA, foo())</span>
> 
> <span class="smallcaps">.Times(1)</span>
> 
> <span class="smallcaps">.WillOnce(Return(42));</span>
> 
> <span class="smallcaps">// Expect bar() to be called with the result
> of foo()</span>
> 
> <span class="smallcaps">EXPECT\_CALL(mockB, bar(42))</span>
> 
> <span class="smallcaps">.Times(1);</span>
> 
> <span class="smallcaps">testFunction(mockA, mockB);</span>
> 
> <span class="smallcaps">}</span>

In this example, \`testFunction\` is the function you're testing. It
takes \`mockA\` and \`mockB\` as arguments, calls \`mockA.foo()\`, and
then calls \`mockB.bar()\` with the result of \`foo()\`.

# Tips for General Use 

  - **Flexibility with Matchers:** Google Mock provides a range of
    matchers for arguments. Use them to create flexible and robust
    tests.

  - **Dealing with Non-Deterministic Behavior:** If your functions have
    non-deterministic behavior (like generating random numbers),
    consider how to mock or control these aspects to make your tests
    predictable.

  - **Test for Failure Conditions:** In addition to testing the expected
    flow, write tests for failure conditions and ensure your code
    handles them gracefully.

  - **Isolate Tests:** Each test should be independent and not rely on
    the state from previous tests.
