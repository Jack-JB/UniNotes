# Requirements

## Syntax of Requirements

- **[Condition] [Subject] [Action] [Object] [Constraint]**

- - [When a hostile plane is detected], 	[the system] 	[shall launch]	 [the missile] 	[within 0.002 seconds]
  - [If the student is enrolled],  [the system]  [shall register]  [the student]  [on the module]
  - [The system]  [shall display]  [the results]  [at midnight]
  - [The light]  [shall flash]  [every 2 seconds]

----

## Requirement Language

- **Shall**: Mandatory
- **Should**: Desirable goals
- **May**: Suggestions

## Writing a Requirement

* Consistency, clearly understood

* Standard format throughout

* Identify key parts of the requirement

* Avoid complex terminology

* Include explanations

## What is a requirement?

- It may range from a high-level abstract statement of a service or of a system constraint to a detailed mathematical functional specification

- This is inevitable as requirements may server a dual function

- - May be the basis for a bid for a contract - therefore must be open to interpretation

  - May be the basis for the contract itself - therefore must be defined in detail

  - Both these statements may be called requirements

    

## Types of Requirements

- User requirements

- - Statements in natural language plus diagrams of the services the system provides and its operational constraints. Written for customers

- A structured document setting out detailed descriptions of the system's function, services and operational constraints. Defines what should be implemented so may be part of a contract between client and contractor.

- User requirements are much more concise whereas system requirements are more specific.

## Guidelines for Writing Requirements

- Invent a standard format and use it for all requirements.
- Use language in a consistent way. Use shall for mandatory requirements, should for desirable requirements.
- Use text highlighting to identify key parts of the requirement.
- Avoid the use of computer jargon.
- Include an explanation (rationale) of why a requirement is necessary.

## Requirements Should be

- Necessary
- Implementation-free
- Unambiguous
- Consistent with other requirements
- Complete: measurable and fully detailed
- Includes only one requirement
- Feasible
- Traceable to higher & lower requirements
- verifiable

----

## Functional Requirements

- The system shall generate each day, for each clinic, a list of patients who are expected to attend appointments that day.

- Each staff member using the system shall be uniquely identified by his or her 8-digit employee number.

- Problems arise when functional requirements are not precisely stated.

- Ambiguous requirements may be interpreted in different ways by developers and users.

- Consider the term 'search' in first requirement

- - User intention - search for a patient name across all appointments in all clinics;
  - Developer interpretation- search for a patient name in an individual clinic. User chooses clinic then search.

## Non Functional Requirements

- These define system properties and constraints e.g. reliability, response time and storage requirements. Process requirements may al so be specified mandating a particular IUDE, programming language or development method.
- Non-functional requirements may be more critical than functional requirements. These are not met, the system may be useless.