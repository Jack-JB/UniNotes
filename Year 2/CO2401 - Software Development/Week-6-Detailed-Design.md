# Detailed Design & Code Generation

## Uses for UML

- UML models can sketch a high-level OO design
  - Supports thinking - key part of design
- Detailed UML models define software in detail:
  - Getting it right before committing to implementation
    - UML diagram is language independent
  - Possibly generate code automatically
    - Round-tripping

## Creating the Design Class Diagram

- Use domain class diagram and interaction diagrams

  - Add newly discovered lasses to the diagram

    - Remove classes that are not used

    Check that all associations are present

    ​	Remove associations that are not used

  - Work out the <u>navigability</u> of each association

  - Make sure all operation and attributes are present

  - Add type information to attributes and operations

  - Add descriptive information to each class

    - E.g. Class Responsibility Collaboration information for the class, and information about each attribute and operation

## Domain vs Design Class Diagrams

<img src="D:\UniNotes\Year 2\CO2401 - Software Development\Images\image-20211109101436213.png" alt="image-20211109101436213" style="zoom:50%;" />

## Specifying Attributes & Operations

- Attributes and Operations are called class Members
- To be fully specified on a design class diagram:
  - Attributes should have
    - Name; Description; Type; Default value
  - Operations should have
    - Name; Description; Parameter types; Return type
  - All members should have visibility information: • + Public – visible to “users” of the class • - Private – not visible outside the class • # Protected – visible to children of the class (inheritance)

## Programming Associations

- Associations in UML denote collections of links between two or more objects

  - OO languages don't have a concept of association

  - They provide references (pointers) allowing one object to store a 'handle/pointer' to another object

    - References are unidirectional (one way), and link 2 objects

    - Collection objects can store references to several other objects

      - Examples of collection objects?

        

## Navigation

- To collaborate, objects must know about each other

  - At least one object will hold a reference to the other
  - In a 'many to one' association, objects at the 'many' end may hold a reference to the other 'one' object they are associated with
  - <img src="C:\Users\jackj\AppData\Roaming\Typora\typora-user-images\image-20211109102321682.png" alt="image-20211109102321682" style="zoom:50%;" />
  - So an object of class A can call class B 

- If the navigation is towards the many end, a collection of references will need to be maintained

  - The object of class B could then traverse its collection

  ```
  for i=1 to myAs.count()
  	myAs.item(i).doSomethin()
  ```

  **finish**

  

