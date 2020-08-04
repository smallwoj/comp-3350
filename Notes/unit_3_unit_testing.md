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
    - Ex. Leaving a bank vault unlocked
  - Error
    - Incorrect state caused by a fault
    - Unobserved
    - Ex. Someone taking all the money
  - Failure
    - Observed incorrect behaviour
    - Ex. Someone can't take out money cause it's all gone
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
## What Tests Do
- Unit tests should reveal faults and give observable results
- Exercise the SUT in new ways
- Ideally exhaustive
  - Not possible
- Choose a thorough set of representative test cases
- Each test method is independent
  - Not sequential
- Outcomes are predictable and reproducable
  - Randomness is worse than useless
  - Minimize dependencies
    - Ex. Avoid using external resources
- Keep test code simple
- Tests must test something
  - Must check outcomes
  - Look for specific results
  - Check side effects as well as direct outputs
- Check outcomes with assertions
  - Not like C/Java `assert`
  - Testing assertions log failures but keep going
## Test Coverage
- The amount of code in the SUT that is tested
- Want to cover as much as reasonably possible
  - Ex. if we have an `if/else`, write tests for both execution paths
    - White box perspective
- Choose the kind of test data that will give this kind of coverage
  - Valid data
    - Simple data
    - More typical (complex) data
      - Covers different situations
    - Empty data
    - Edge cases
  - Invalid data
  - Null data or missing data
  - Failures noticed later
## Test Cases
- Examples
- Binary Search
- `[1, 2, 4, 7, 10, 11, 23, 57]`
  - Look for 10
  - Look for 11 (one off)
  - Look for 7 (other way)
  - Look for 9 (not in there)
  - Look for 5 (not in)
  - Look for 1 and 57 (edge cases)
  - Look for 0 and 58 (one offs)
  - Look for -3 or 68 (a bit further)
  - Even size
  - Odd size
  - Empty list
  - Small list (1 and 2 elements)
  - lLists with duplicates
  - Lists with negative numbers
  - Null list
  - Null values in list
  - Null search key
  - Unsorted list? very tough to test, don't even test
- Title case captializer
  - `"title case CAPTIALizer"` -> `"Title Case Captializer"`
  - empty string
  - one word
    - `"HELLO", "hello", "hELLO"` -> `"Hello"`
  - two words
  - punctuation
  - multiple punctuation
  - non letters
  - null
- Don't reinvent the wheel
## Testing Techniques
- Where do you start?
  - Simple cases
  - "happy path"
    - Valid data first
  - Or invalid first
  - "big picture" or "breadth first" 
  - "depth search
    - details
- How to organize/structure tests?
  - Focus on situations & scenarios
    - `testEmptyList`
    - `testShortLists`
    - `testTypicalList`
    - `testNullList`
    - `testFound`
    - `testEdgeCases`
    - `testNotFound`
    - `testInvalidKeys`
  - Organization may be determined by approach
  - Focus on one aspect or kind of test in each method
- Test code must be good code
    - Avoid duplicate code -> move to a shared method
    - Keep test code simple
      - Linear
      - Avoid if/else & loops
- Name tests appropriately
  - Good names -> avoid comments
  - Keep names up to date
- Testing to-dos
  - Instead of a note, force a fail
    - `fail("need test for null list")`
  - That way you still need to do it
- Testing exceptions
  - Use try catches for specific exceptions
  - ```java
    try 
    {
        method(bad data)
        fail("expected exception")
    }
    catch (ExpectedException ignored)
    {
        //cool
    }
    ```
## Test Driven Development
- TDD
- A "test-first" approach
- Iteratively:
  1. Write one <ins>simple</ins> test that fails
     - RED
  2. Write <ins>just enough code</ins> for that test to pass
     - GREEN
  3. Clean up the code you've written
     - Both SUT & test
     - REFACTOR
   - Repeat steps until complete
- Makes sure the tests are written
- Makes writing tests less of a chore
- Helps test coverage
- Encourages careful consideration before coding
  - Understanding the problem
  - Tests are "executable requirements"
  - YAGNI
    - Focus on core problem by writing tests
## Outcomes of Testing
- Verification & validation
- Uncover & fix latent faults
- During development
  - Helps collaboration
  - Testable code <-> good design
  - Careful consideration
- After development
  - Act as documentation for SUT
  - After changes (features/fixes) tests act as invariants
    - Regression testing
      - Ensures changes don't introduce errors
  - Monitors system health
  - Standards compliance
  - Assure code reusability
- Ensure code is <ins>done</ins>
