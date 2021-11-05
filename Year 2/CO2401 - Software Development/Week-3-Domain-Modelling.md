# Object Oriented Software Development & Domain Modelling

## Key Software Development Concepts

- Abstraction

- - Using the right level of detail: hiding irrelevant details

- Modularity 

- - Structuring a system into interaction components (modules)
  - **Decomposition** breaks a system down into components

- Coupling

- - Links between modules

- Cohesion

- - Simplicity of purpose of module

---

## Object Oriented Design

- Break system into classes of objects with

- - Data (attributes)
  - Functionality (methods)

- Helps provide a better match to reality than other development approaches

- Objects interact(collaborate)

- - By calling each other's methods
  - Must not fiddle directly  with another object's data

- Requirements are captures by a set of use cases

- - Objects collaborate to deliver each use case

## Advantages of Object Orientation

Encourages good software engineering principles:

- Abstraction

- - Modelling of only appropriate domain entities in the code
  - Design level (focus on the 'what')

- Encapsulation

- - Combining data and functionality in one entity
  - Hiding of inner workings from other entities that don't need to see it 
  - Implementation level (focus on the 'how')

- Loose coupling

- - Objects have minimum knowledge of each other

- Tight cohesion

- - A good object has a single purpose

----

## Identifying Classes

- Choosing suitable classes and attributes is crucial
- Avoid adding unnecessary complexity to the system
- Creative process
- There will be changes as you learn about the domain

## Identifying Attributes

- Some of the attributes will have been identified

- - i.e. rejected as classes because they were attributes

- Whether something is a class or an attribute will often depend on the system context:

- - If further information about the 'thing' other than its name or value is required, then it will have to be a class - otherwise it will be an attribute

  - e.g. the make and model of my car may be

  - - An attribute in the university car -parking admin system
    - A class in my insurance company's system (where the model may have properties such as insurance band, etc.)

- ## Identifying Associations

- - Some associations will be obvious when classes are first identified, but study the requirements carefully to find all the associations

  - Look at the way the nouns which represent classes are connected in the text - e.g.

  - The car hire company stocks cars of a number of different models. It may gave any number of cars of each model. The system should, for each model, hold the models name and engine size. No two models have the same name

  - Some relationships are not represented

  - - E.g. Between classes and their attributes, or things beyond the system boundary.