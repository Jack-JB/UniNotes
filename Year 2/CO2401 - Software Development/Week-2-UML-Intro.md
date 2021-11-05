# UML Introduction and CRC Cards

## Object Oriented Analysis & Design

- What is it?
  - Analysis & design based on objects: grouping items with related properties (data/state) & methods (behaviour)
- Purpose
  - Correctness
  - Expandability
  - Reusability
  - Maintainability
- Abstraction & Decomposition
  - Based on a 'Real World' approach

## UML & Development Activities

- Analysis
  - User interactions with system (Use Cases)
  - Business processes (Activity Diagrams)
  - Entities & relationships (Class & Object Diagrams)
  - Architecture (Deployment Diagrams: location of software on networked physical components)

----

## Class Diagrams

- Class Diagrams are used when developing an object-oriented system model to show the classes in a system and the associations between these classes
- an object class can be thought of an a general definition of one kind of system object.
- An association is a link between classes that indicates that there is some  relationship between these classes.
- When you are developing models during the early stages of the software  engineering process, objects represent something in the real world, such  as a patient, a prescription, doctor, etc.

### Class Diagrams / Class Model

- Class models show
  - Classes (objects) in the system
  - Their operations & attributes
  - Their inter-relationships
    - E.g. inheritance, aggregation, association
- Can be used at high-level & detailed level
- Concept design
  - Classes with little detail, key relationships
- Detailed Design
  - Methods, proerties, access rights, multiplicity

----

## CRC Cards

- A collaborative approach to determining overall  system architecture
- Class, Responsibilities and Collaborators
- Describe each class on a small card
  - Name of class
  - Purpose
  - List of responsibilities
    - Things it Knows
    - Things it Does
  - Collaborators (related classes)
    - Other classes used by this class

### Purpose of CRC Cards

- Used as a collaborative tool to brainstorm division of a  programs components
- Allows the team to build a common mental model of  how a program might work
  - Allows quick visual test of alternative  approaches/architectures before development begins
- Can be useful when changing/restructuring a program 

### CRC  Cards Advantages

- Suited to iterative development
  - Easy to add/remove and rearrange cards
    - Good for collaborative communication
- Can be used very early in development stage
  - E.g. in foundations stage of DSDM
- Finished OO analysis with CRC cards can provide architectural design  guidelines
- Encourages development team to ‘role play’ through different usage  scenarios
  - New issues can be identified e..g missing component

### CRC  Cards Disadvantages

- Requires team participation
  - Both from business side and developers
- Can become difficult to manage with very large systems
  - Too many cards to manage
- Does not track sequence when running through scenarios
- Lacks Detail
  - Some organisations will require more formal representation of overall  architecture

----

## Summary

- UML provides notation for modelling system
- An object is some entity relevant to a system
  - It has behaviour – methods
  - It has state – properties / attributes
- A class is a blueprint for objects
  - Defines the properties and methods of objects
- Class diagram shows types of entity and their  relationships
- CRC cards allow developers to role-play objects in a  system walkthrough.

