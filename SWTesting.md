# **THE DIFFERENT TYPES OF SOFTWARE TESTING**

Software testing is the systemmatic examination of software artifacts
and the actions performed by the software being tested. This process
involves validation and verification, offering an impartial perspective
on the software to confirm that code modifications function as intended
and to assess the potential risks associated with implementing the
software. A key objective of testing is the identification of software
failures, allowing for the detection and rectification of defects.
Various testing techniques, though not restricted to these, encompass:

  - analyzing the product requirements for completeness and correctness
    in various contexts

  - reviewing the product architecture and the overall design of the
    program

  - working on overall improvement in coding techniques, design patterns
    and tests

  - executing a program or application with the intent of examining
    behavior

  - reviewing the deployment infrastructure and associated scripts and
    automation

  - take part in production activities by using monitoring and
    observability techniques

## **Manual vs. Automated testing**

Manual testing is done in person, by clicking through the application or
interacting with the software and APIs with the appropriate tooling.
This is very expensive since it requires someone to setup an environment
and execute the tests themselves, and it can be prone to the human error
as the tester might make typos or omit steps in the test script.

Automated tests, on the other hand, are much more robust and reliable
than manual tests. Performed by a machine that executes a test script
that was written in advance. These tests can vary in complexity, from
checking a single method in a class to making sure that performing a
sequence of complex actions in the UI leads to the same results. It's a
great way to scale your QA process as you add new features to your
application.

## **The different types of Testing levels**

**1. UNIT TESTING**

They are very low level and close to the source of an application. They
consist in testing individual methods and functions of the classes,
components, or modules used by your software. The constructors and
destroyers are covered by the bare minimum unit tests in an
object-oriented system, where this is often done at the class level. To
make that the individual function is operating as intended, these tests
are typically written by developers as they work on the code (white-box
approach).

To catch edge cases or other branches in the code, one function could
undergo a number of tests.The functioning of a piece of software cannot
be verified by unit testing alone; rather, it is used to make sure that
the product's component parts perform independently of one another. A
synchronized application is used in the process of unit testing
software. Unit tests are generally quite cheap to automate and can run
very quickly by a continuous integration server. Unit testing is the
practice of verifying the functioning of a single line of code,
typically at the function level.

Unit testing may include static code analysis, data-flow analysis,
metrics analysis, peer code reviews, code coverage analysis, and other
software testing techniques depending on the organization's expectations
for software development.

**2. INTEGRATION TESTING**

It is the stage of software testing where the entire software module is
tested, or if it is made up of many software modules, they are merged
and tested together. Integration testing is done to determine whether a
system or component complies with a list of functional requirements.
Before system testing and following unit testing, it happens. The goal
of integration testing is to produce an integrated system that is ready
for system testing by taking as input modules that have undergone unit
testing, grouping them into bigger aggregates, applying the tests
outlined in an integration test plan to those aggregates. These types of
tests are more expensive to run as they require multiple parts of the
application to be up and running.

**Approach**

Integration testing can be done in a variety of ways, including
big-bang, mixed (sandwich), risky-hardest, top-down, and bottom-up.
Other integration patterns include collaboration integration, backbone
integration, layer integration, client-server integration, distributed
services integration, and high-frequency integration.

**In big-bang testing,** the majority of the generated modules are
connected to create a whole software system or significant portion of
the system, which is then utilized for integration testing. The
integration testing procedure can be sped up significantly with this
technique. However, the integration process will be made more difficult
and the testing team may not be able to accomplish the purpose of
integration testing if the test cases and their findings are not
correctly recorded.

**Bottom-up testing** involves testing the lowest level components first
and using the results to help test the higher level components. Up till
the component at the top of the hierarchy is tested, the process is
repeated. The integration and testing of all the bottom-level or
low-level modules, processes, or functions. The next level of integrated
modules will be generated and can be used for integration testing when
the lower level integrated modules have undergone integration testing.
This strategy only works when all or the majority of the modules at the
same stage of development are completed. This approach also makes it
simpler to provide testing progress as a percentage and aids in
identifying the software development levels.

**Top-down testing** is an approach used in software testing to evaluate
the interactions between higher-level modules or components before
testing the lower-level ones. It's a systematic way of testing the
integration of various parts of a software system from the top
(higher-level) to the bottom (lower-level)..

**Sandwich testing** combines top-down testing with bottom up testing.
One limitation to this sort of testing is that any conditions not stated
in specified integration tests, outside of the confirmation of the
execution of design items, will generally not be tested.

## **3. SYSTEM TESTING**

System testing is a important phase in the software testing process. It
focuses on evaluating the entire software system as a whole to ensure
that it meets the specified requirements and functions correctly in its
intended environment. During system testing, the software is tested in
an environment that closely resembles the production environment,
simulating real-world conditions.

System testing utilizes the integrated components that have successfully
passed integration testing as its input. Its primary aim is to identify
any discrepancies or issues that may arise when these integrated units
are combined. System testing aims to uncover defects not only within
these integrated components but also within the entire system. It is
performed on the entire system in the context of functional requirement
specifications. System testing not only tests the design, but also the
behaviour and even the believed expectations of the customer. It is also
intended to test up to and beyond the bounds defined in the software or
hardware requirements specifications. It is very important because it
verifies that the application meets the technical, functional, and
business requirements that were set by the customer. The goal at this
level is to evaluate whether the system has complied with all of the
outlined requirements and to see that it meets Quality Standards.

**4. ACCEPTANCE TESTING**

It serves as a critical step in assessing the system's readiness for
release. Within the Software development llife cycle, alterations to
requirements can sometimes lead to misunderstandings that fail to align
with users' intended needs. In this concluding phasse, users put the
system to the test to confirm its alignment with their business
requirements. Once this evaluation concludes successfully and the
software gains approval, it proceeds to production. The Quality
Assurance (QA) team conducts acceptance tests to validate that the
softwware or application aligns with both business requirements and
end-user expectations. The outcome of an acceptance test is binary: pass
or fail. A failed result indicates the presence of flaws, necessitating
further refinement before production deployment. Acceptance testting
serves the valuable purpose of involving end users in the testing
process, gathering their feedback for developers. This feedback aids QA
in identifying any deficiencies that may have been overlooked during
earlier development-stage tests, such as unit and functional testing.
Furthermore, acceptance testing ensures that the software or application
complies with established compliance standards.
