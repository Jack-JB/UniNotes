# Test Driven Development

 ## Static Analysis

- Automated code review
  - A program that reads your source
    - Analogous to grammar or spell checker
  - Detects (potential) semantic errors and bad practice
    - Dereferencing null pointers
    - Use of global variables
  - Check formatting standards (names/layout)
  - Calculate Metrics: a numerical measure of a property
    - E.g. number of parameters, size of functions, complexity of functions
    - Number of loops and branches

### Advantages & Disadvantages

- **Advantages**
  - Full code coverage, including rarely used code
  - Independent of compiler/environment
    - Will find problems hidden by compiler-specific behaviour
      - So you don't get bitten when you change compiler
    - quick and cheap to use and detect problems early
- **Disadvantages**
  - Limited
    - Can't detect many types of problems (e.g. wrong algorithm)
    - Can't detect all problems it's looking for (false negatives)
  - Can mistakenly highlight good code (false positives)
  - Can highlight lots of trivial issues (but can switch rules off)

## Standards

- Guidelines that capture good practice
  - E.g. Programming standards
    - OWASP secure programming practices
      - Writing safe code
  - E.g. How to hold a review
    - Why do security reviews and vulnerabilities to look for
  - C++ Core Guidelines
    - To help developers to adopt modern C++ features
- Static Analysis may be able to check compliance
  - E.g. C++ Core Checker

### Example: C++ Core Guidelines

**NL.16:** Use a conventional  class member declaration order

**Reason:**

A conventional order of members improves readability.

When declaring a class use the following order

1. Types: classes, enums, and aliases (using)
2. Constructors, assignments, destructor
3. Functions
4. Data

Use the *public* before *protected* before *private* order.

**Enforcement**

Flag departures from the suggested order. There will be a lot of old code that doesn't follow this rule.

## Testing - The Need for a Strategy

- Software always has defects - Testing is necessary
  - Reduces errors
    - maintenance costs & damage to reputation
  - Increase confidence in product
- Testing is a costly part of the total project effort
  - Requires a systematic management strategy
    - Planned by a project manager, developers, & testing specialists
    - How should we conduct the tests & record results?
    - Do we need a formal plan?
    - Do we need to re-run tests when adding new components?
    - When should we involve the customer?
    - How much effort, time and resources will be required?

### Overall Testing Approach

- **Traditional:** small to the large
  - Unit Testing: a single component
  - Integration Testing: a group of related components
    - Interface integrity, functional, performance
  - System Testing: the complete integrated system
- **Continuous Integration:** "its all integration testing"
  - Developers check out and work on full system
  - Integrate code into full system in a shared repository daily
  - Verify with an automated build and test
- **Continuous Deployment:** “Release every good build”
  - Allows constant validation

## Stub Functions and Test Harnesses

- A Stub replaces an unwritten module lower in the hierarchy, and is as simple (cheap to write) as possible
  - Allows the higher-level module to function enough to be tested independently
- A Test Harness replaces higher-level modules in the hierarchy. It calls functionality in the module under test
  - A mini-application that initialises, provides data to the to and consumes results from the lower level module
- In OO systems, Mock Objects may be used like Stubs
  - They must have the same interface as the real object
  - Mock Objects which do very little processing are sometimes  known as Fake Objects

## Test Suites

- A test suite is a collection of test scenarios which  themselves are a collection of test cases
- Test cases consist of a set of test data, test programs  (test harnesses) and a set of expected results
- In OO architectures for example, a test suite may consist  of a test scenario for each class. The test scenario may  consist of a series of test cases for each of the member  functions

## Using Test Cases

- Typically a set of test cases (a scenario) is prepared
- A file of input test data an expected results for example is ready by the test harness (test driven program)
- for example is called with the test data and the  results are compared with the expected results. A function (unit of code - so is often referred to as a unit test) 
- The success or failure of the test is reported and the next  test is carried out.
- This method of testing tends to be totally automated if  possible…

## Automated Testing

- Software tools to test software were among the first  CASE tools to be developed:
  - This enables test repeatability and is faster as the user is not  generally required to enter lots of data manually
  - Using as much automated testing as possible greatly reduces  the cost of testing
- If the code is changed in a single module, all the tests  would be re-run on the whole application to ensure that  the changes have not impacted on any other modules.
  - Retesting everything in this way is often referred to as  “regression testing”

## Unit Testing

- Tests cover:
  - The interface (of the module, not user interface!)
  - Local data structure
  - Boundary conditions
  - Independent paths through methods
  - Error handling paths

## Integration (sub-system Testing)

- Integration testing checks combinations of modules in the decomposition hierarchy, after each has been successfully tested individually
  - Reveals defects in the interface between modules
    - Including their interaction
  - Some modules may be off-the-shelf components
  - Still require stubs or test harnesses
- The main problem with integration is localising errors
  - An incremental approach is necessary
- The order of integrating components is important
  - A rule of thumb is to integrate the most frequently used functionality first, so that it gets the most testing

## System and Validation Testing

- Validation is successful when software functions in a way that  can be reasonably expected by the customer.
  - It is achieved through a series of tests that demonstrate conformity  with requirements.
  - A test plan outlines the types of tests to be conducted, and a test  procedure defines specific test cases.
- System testing also includes:
  - Recovery testing
  - Security testing
  - Stress testing
  - Performance testing

## Acceptance Testing

- The test performed by users of a new or changed system  in order to approve the system and go live
- Usually carried out at the customer’s premises or using  customer’s data with the customer being present
- This is usually the final phase of development and results  in the handover of the software product to the customer