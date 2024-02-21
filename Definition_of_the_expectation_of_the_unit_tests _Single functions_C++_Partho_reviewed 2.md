**Definition of the expectation of the unit tests: Single functions** {#definition-of-the-expectation-of-the-unit-tests-single-functions .TOC-Heading}
=====================================================================

** Guides and Standards** {#guides-and-standards .TOC-Heading}
=========================

  -------------------- ----------------
                       
                       
                       
                       
                       
                       
                       
                       
                       
                       
                       
                       
                       
  **Creation date:**   30.01.2024
  **Version 1.0:**     30.01.2024
  **Author:**          Andrej Cepygin
  -------------------- ----------------

**Contents** {#contents .TOC-Heading}
============

[1 Scope 4](#scope)

[1.1 Document Overview 4](#document-overview)

[1.2 Revisions 4](#revisions)

[2 Expectations for Unit tests for single functions
4](#expectations-for-unit-tests-for-single-functions)

[2.1 Independent 5](#independent)

[Isolation 5](#isolation)

[Single responsibility 5](#single-responsibility)

[2.2 Behavior Verification 5](#behavior-verification)

[2.3 Edge Cases 5](#edge-cases)

[2.4 Maintainability 5](#maintainability)

[2.5 Repeatable 5](#repeatable)

[2.6 Test Coverage 6](#test-coverage)

[2.7 Automation 6](#automation)

[3 Writing unit tests with python 6](#_Toc157503359)

[3.1 Unit test with PyTest 6](#_Toc157503360)

[3.2 Mocking dependencies properly 7](#_Toc157503361)

[3.3 Setting Environment Variables 9](#_Toc157503362)

[3.4 Exception 10](#_Toc157503363)

[4 Literatur 10](#literatur)

Scope {#scope .Akkodis-Überschrift-1}
=====

This document provides an overview of the expectations of a unit test
for single functions.

Document Overview {#document-overview .Akkodis-Überschrift-2}
-----------------

-   Expectations for Unit tests

-   Unit testing C++ with Google Test

Revisions {#revisions .Akkodis-Überschrift-2}
---------

  **Rev**   **Actions**   **Comment**
  --------- ------------- -------------
  \-        First Issue   
                          

Expectations for Unit tests for single functions {#expectations-for-unit-tests-for-single-functions .Akkodis-Überschrift-1}
================================================

The expectation of unit tests for single functions refers to the
anticipated behavior and outcomes of tests designed to assess the
correctness and functionality of individual functions in a software
program. Unit testing isolates the code in units to ensure each part
works as intended.

Unit testing consists of the following key components:

Independent {#independent .Akkodis-Überschrift-2}
-----------

### Isolation {#isolation .Akkodis-Überschrift-3}

Isolating the functions or methods from the rest of the code ensures
that the testing focuses on the behavior of the individual function
without interference from other parts of the program.

### Single responsibility {#single-responsibility .Akkodis-Überschrift-3}

Test should test only one thing at a time. Multiple assertions are
accepted as long as they are all testing one feature/behavior.

Behavior Verification {#behavior-verification .Akkodis-Überschrift-2}
---------------------

Unit tests should verify that the function behaves as expected under
different input conditions. This involves checking the function's
response to various input values and ensuring that it produced the
correct output.

Edge Cases {#edge-cases .Akkodis-Überschrift-2}
----------

Edge cases are scenarios where the function might be expected to behave
differently. This helps identify potential issues in boundary conditions
and ensures that the function handles them correctly.

Maintainability {#maintainability .Akkodis-Überschrift-2}
---------------

As the code evolves, tests may need to be updated to reflect changes in
the function's behavior. Expectations in the test should be reviewed and
adjusted accordingly during code modifications. Following same standards
for each test provides a professional test-environment.

Repeatable {#repeatable .Akkodis-Überschrift-2}
----------

Tests should produce the same results each time every time. They should
not rely on uncontrollable params.

Test Coverage {#test-coverage .Akkodis-Überschrift-2}
-------------

Unit tests should provide sufficient coverage for functions, ensuring
that a broad range of scenarios are tested to help catch potential bugs
and ensure robustness.

Automation {#automation .Akkodis-Überschrift-2}
----------

Unit tests should invoke automatically as part of a continuous
integration process. This ensures that these tests can be executed
regularly and quickly to provide rapid feedback to developers.

Unit testing C++ with google Test {#unit-testing-c-with-google-test .Akkodis-Überschrift-1}
=================================

Download and Build {#download-and-build .Akkodis-Überschrift-2}
------------------

### Option 1 {#option-1 .Akkodis-Überschrift-3}

Install Google Test from Nuget.

### Option2 {#option2 .Akkodis-Überschrift-3}

Download and build Google Test in local directory.

Google Test provides Visual Studio solutions ready to build in *\\msvc*.

Open the solutions e.g. *gtest.sln,* configure things how you want,
build and copy the library files and EXEs to a convenient location.

Open *%LOCALAPPDATA%\\Microsoft\\MSBuild\\v4.0* and edit the
*.user.props* files to always include Google Test paths

### Including Google Test {#including-google-test .Akkodis-Überschrift-3}

Google Test requires you to build an executable:

1: add the include header

##### \#include \<gtest/gtest.h\>

2: reference appropriate libraries:

*gtest.lib* for release build

*gtestd.lib* for debug

3: implement the main entry point with code similar to:

##### int main(int ac, char\* av\[\])

##### {

#####  testing::InitGoogleTest(&ac, av);

#####  return RUN\_ALL\_TESTS();

##### }

Properties of a test {#properties-of-a-test .Akkodis-Überschrift-2}
--------------------

*EXPECT\_TRUE()* and

##### EXPECT\_FALSE()

Can be used to test conditions:

##### TEST(Addition, CanAddTwoNumbers)

##### {

#####  EXPECT\_TRUE(add(2, 2) == 4);

##### }

The *TEST()* macro is necessary for Google Test so it knows that you are
writing a test.

Another variety is *EXPECT\_EQ():*

##### EXPECT\_EQ(4, add(2,2)) \<\< \"Two plus two must equal four\";

EXPECT\_EQ does not stop execution

Refinements of EXPECT\_EQ include comparisons:

-   EXPECT\_LT : less-than

-   EXPECT\_FLOAT\_EQ: comparison of floating point number

-   Many more

TEST() is runnable as long as it ends up being part of the build.

Test Fixtures {#test-fixtures .Akkodis-Überschrift-2}
-------------

A test fixture is a class that inherits from *::testing::test*

And its internal state is accessible to tests that use it. Instead of
being part of the test fixture class, the tests related to a fixture are
external.

A test fixture can define set-up and tear-down actions in either
*SetUp()/TearDown()*

Or in constructor and destructor.

For example we want to test a *BankAccount*, the test fixture might
appear as:

##### struct BankAccountTest : testing::Test

##### {

#####  BankAccount\* account;

#####  BankAccountTest()

#####  {

#####  account = new BankAccount;

#####  }

#####  virtual \~BankAccountTest()

#####  {

#####  delete account;

#####  }

##### };

Test fixtures are not an actual test: it's the rules for setting up and
destroying what we need for testing.

The actual test now uses *TEST\_F* and its first argument is the
fixture:

##### TEST\_F(BankAccountTest, CanDepositMoney)

##### {

#####  account-\>deposit(100);

#####  EXPECT\_EQ(100,account-\>balance);

##### }

Parameterized tests {#parameterized-tests .Akkodis-Überschrift-2}
-------------------

Parameterized tests can be used for Data-driven tests. Essentially, you
can set up a set of values and feed them consecutively into a test.

First, set up a structure for the test:

This is a statement of before-and-after states for a bank account.

R++ to generate operator\<\< is necessary because google test has no
idea how to print account\_state objects to the console

##### struct account\_state

##### {

#####  int initial\_balance;

#####  int withdraw\_amount;

#####  int final\_balance;

#####  bool success;

#####  friend std::ostream& operator\<\<(std::ostream& os, const account\_state& obj)

#####  {

#####  return os

#####  \<\< \"initial\_balance: \" \<\< obj.initial\_balance

#####  \<\< \" withdraw\_amount: \" \<\< obj.withdraw\_amount

#####  \<\< \" final\_balance: \" \<\< obj.final\_balance

#####  \<\< \" success: \" \<\< obj.success;

#####  }

##### };

We are testing the process of withdrawing money.

We want to reuse the previous BankAccountTest fixture and at the same
time account\_state instances to initialize the balance:

##### struct WithdrawAccountTest : BankAccountTest, testing::WithParamInterface\<account\_state\>

##### {

#####  WithdrawAccountTest()

#####  {

#####  account-\>balance = GetParam().initial\_balance;

#####  }

##### };

*WithParamInterface\<\>* and *GetParam()* yields the parameter being
used in the current test case.

##### TEST\_P(WithdrawAccountTest, FinalBalance)

##### {

#####  auto as = GetParam();

#####  auto success = account-\>withdraw(as.withdraw\_amount);

#####  EXPECT\_EQ(as.final\_balance,account-\>balance);

#####  EXPECT\_EQ(as.success,success);

##### }

Using uniform initialization, we can define the test cases:

##### INSTANTIATE\_TEST\_CASE\_P(Default, WithdrawAccountTest,

#####  testing::Values(

#####  account\_state{100,50,50,true},

#####  account\_state{100,200,100,false}

#####  ));

In parameterized test, each case takes up a separate line in the tree of
test cases.

Literatur {#literatur .Akkodis-Überschrift-1}
=========

[Unit Testing C++ with Google Test \| The ReSharper C++ Blog
(jetbrains.com)](https://blog.jetbrains.com/rscpp/2015/09/01/unit-testing-google-test/)
