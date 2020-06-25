# Unit 3: Unit Testing
## Introduction to Testing
- Two goals
  1. Verification
     - Does it work?
     - Are we building the product right?
  2. Validation
     -  Does it do what it needs to do?
     -  Are we building the right product?
- What are we testing for?
  - Fault
    - A static defect in the system
    - Bug
  - Error
    - Incorrect state caused by a fault
    - Unobserved
  - Failure
    - Observed incorrect behaviour
- Testing can uncover faults
  - Not debugging
    - Which is finding a fault that caused failure
  - Good testing reduces debugging
- Two general approaches
  1. Structural testing
    - White box
  2. Functional testing
    - Black box
    - Test interface
- Terminology
  - System under test (SUT)
    - Part of the program/system that the test is testing
  - Fixtures/Scaffolding
    - Data/resources/code required to run the tests
  - Test harness
    - Fixtures & code that execute the tests
- Use automated tests
  - Use a testing library/framework
- Complex systems are tested at different levels
  - Unit testing
    - Test individual components of the system in isolation
  - Integration testing
    - Test communication between components
  - Acceptance testing
    - Test if system satisfies requirements
## Unit Testing
- Test each individual component of our system in isolation
  - Component: method or class
  - Isolation: focus on testing that component
  - Each: testable parts (make as much testable as possible)
- Test code is organized to match components
  - Ex. TestA to test class A, TestB to test class B, etc
  - Multiple test methods in each test class
  - Starts with `test_`
  - Avoid organizing test methods to match SUT
    - no testConstructor, toString
  - Package organization
    - myproject.a -> myproject.tests.a
  - Test suite
    - Execute all the tests in each package
      - At each level of packages
