# Verification & Validation

## The role of Verification  Validation

- Verification - Are we building the product correctly?
  - Does the product meet its specification?
- Validation - Are we building the correct product?
  - Does the product meet the customers needs?



- Verification and Validation (V&V) takes place at every stage of the project lifecycle
  - Includes: Requirements Reviews, Design review, Code Inspections and Testing
    - Heuristic evaluation of UI design is an example of V&V

## Fit for Purpose

The goal of V&V is increase confidence that our system is good enough for its indented use, based on:

- User Needs & Software Function
  - How critical is the operation of the software to the business?
  - How well does it work?
    - Freedom from errors, performance
- User Expectations
  - Ease of use, reliability
    - Will users accept failures if the system is generally beneficial?
- Marketing Environment
  - Competition? Price?

## Testing and Reviews

- Peer Reviews (Software Inspection)
  - Static Techniques *(this week)*
    - Applies to all artefacts (created things) throughout the life-cycle
    - Aspects can be automated
    - Can't demonstrate the system is operationally useful
- Testing 
  - **TODO: Finish**

## Static Techniques

- Software reviews / code walkthrough
  - A team checks one or more artefacts (code, design, spec)
- Software Inspection
  - A small team systematically checks the artefacts using a defined process & a checklist
  - May include a test engineer to look at the design from a testing perspective
- Static analysers
  - Software tools that process source code and highlight anomalies such as unreachable code, un-initialised variables and bad smells (poor style, bad programming) which may be the result of programming errors.

## Testing and Reviews

<img src="C:\Users\jackj\AppData\Roaming\Typora\typora-user-images\image-20211123102312355.png" alt="image-20211123102312355" style="zoom:50%;" />

Testing and inspections play complementary roles in the development process

- Testing can only start once a prototype exists
  - Incremental development is an advantage, since a testable "core" of the system is available earlier in the life-cycle
  - A 'Test Driven' approach to development can see us writing testing code before we have written any program code

## Advantages of Software Inspections

- A single inspection can discover many errors in a system
  - In dynamic testing, one error can mask another - or cause multiple symptoms
- Incomplete versions of a system can be inspected
  - Dynamically testing an incomplete system, requires effort to create a test harness for the completed components
  - However, there are mocking and testing tools to help this
- Inspections can consider aspects of software quality other than correctness
  - Style, efficiency, maintainability, portability adherence to standards

## Testing and Debugging

- Validation Testing (Is it useful?)
  - Showing the program does what the customer wants
    - Checking how it works under operational conditions
- Defect Testing (Verification - does it work?)
  - Revealing defects rather than simulating operational use
    - Finding inconsistencies between specification and program
- Testing: the process of making any defects visible
  - Not "showing that the program works"
  - A successful test is one which FALS(!) - finds a symtom
- Debugging: the process of locating and fixing defects
  - Identifying & removing the cause of a symptom

## Debugging process

- Locating an error may involve designing additional tests to reproduce the original fault conditions
- After making changes, the system must be tested again to check new faults have not been introduced
  - This is Regression Testing
- The **test plan** should indicate which tests should be run again as regression tests

