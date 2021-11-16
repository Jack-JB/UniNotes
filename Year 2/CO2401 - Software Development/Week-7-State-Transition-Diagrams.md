# State Transition Diagrams

## The State Model

- Some entities can exist in different states
  - A light switch - its state can be on or off
  - A frog can be an egg, tadpole, a frog or dead
- Events trigger the transition from one state to another
  - Pressing the switch turns it on or off
  - In transitioning from one state to another, one entity might trigger an event for another entity
    - Turning on too many lights at once might cause the fuse to blow
- Modelling states and transitions can capture and enforce certain business rules of processes and entities

## Model Dependencies (Revisited)

<img src="C:\Users\jackj\AppData\Roaming\Typora\typora-user-images\image-20211116100452275.png" alt="image-20211116100452275" style="zoom:50%;" />

## State Transition Diagrams

- Type of Behaviour Diagram
- For each relevant class
  - Show possible states of the class
  - Events that cause the object to change state
  - Actions that occur when the object state changes
- Can represent the lifespan of the class
  - From being created, to being destroyed

<img src="C:\Users\jackj\AppData\Roaming\Typora\typora-user-images\image-20211116100536080.png" alt="image-20211116100536080" style="zoom:50%;" />

## Simple Example: Gothic Castle

- Controller for a secret panel in a gothic castle
- Want to keep valuables in hard to find safe
- To reveal lock have to remove strategic candle from holder
  - Will only reveal lock when door is closed
  - When I can see the lock I can insert my key to open the safe
  - I can only open the safe if I have replaced the candle back in its holder first
    - If a thief forgets this step a monster will be released to dispatch them

## Basic UML State Diagram Notation

<img src="C:\Users\jackj\AppData\Roaming\Typora\typora-user-images\image-20211116101315367.png" alt="image-20211116101315367" style="zoom:50%;" />

## Simple Example: Gothic Castle

**State transition diagram** for the controller class that directs my security system

<img src="C:\Users\jackj\AppData\Roaming\Typora\typora-user-images\image-20211116101459736.png" alt="image-20211116101459736" style="zoom:50%;" />

## Example: Registry Office

- Consider the Registry of Births, Marriages and Deaths
  - We might wish to record certain events which happen in people's lives, such as:
    - Being born
    - Growing up
    - Getting married
    - Getting divorced
    - Becoming widowed
    - Dying
- Each event may trigger a change in a person's state
  - The state changes can be recorded in a simple table

<img src="C:\Users\jackj\AppData\Roaming\Typora\typora-user-images\image-20211116102232015.png" alt="image-20211116102232015" style="zoom:50%;" />

- A state model can capture business rules: A person:
  - Cannot get married unless Adult, Divorced or Widowed
  - Cannot become an Adult unless they are a child

<img src="C:\Users\jackj\AppData\Roaming\Typora\typora-user-images\image-20211116102401911.png" alt="image-20211116102401911" style="zoom:50%;" />

## State Diagrams are NOT Flowcharts

- State charts and flow charts show different things
  - A flow chart is a good way of modelling a business process
    - In UML this is done with an activity diagram
    - STDs do not show algorithms
      - Single class
- External **events** trigger **transitions** between **states**. **Actions** can occur during transitions or while the system is in a state
  - Depending on the system, you can sometimes think of it as 'resting' when it has arrived in any given state
    - The names you choose for states should reflect this...
  - In flow or activity diagrams, boxes show 'processing'

## Super States

- Use a super state to show an event which causes the same transition to a further state from many states:

<img src="C:\Users\jackj\AppData\Roaming\Typora\typora-user-images\image-20211116102617982.png" alt="image-20211116102617982" style="zoom:50%;" />

## Combinatorial Explosion

- Represent the following in a state transition diagram
  - A person can be rich or poor
  - A person can be a child, an adult or a retiree
- What happens if you want to add the following:
  - A person can be in a relationship, single or "it's complicated"
- How do you work out how many states are needed?

## Transition Actions

- An event, can trigger an action
  - e.g. do something internal / call another object's method
- Can show any actions on the transitions
- Actions that always occur shown as entry/exit actions inside the state

<img src="C:\Users\jackj\AppData\Roaming\Typora\typora-user-images\image-20211116103057880.png" alt="image-20211116103057880" style="zoom:50%;" />

## Conditional Transition

- Sometimes transitions are only possible under certain circumstances
  - Conditions (or guards) are shown in square brackets
- For example, if it was not possible to get re-married until a year after the divorce:

<img src="C:\Users\jackj\AppData\Roaming\Typora\typora-user-images\image-20211116104701846.png" alt="image-20211116104701846" style="zoom: 50%;" />

## State & Sequence Diagrams

- A class "does something" in response to receiving a message from another part of the system.
  - Messages passing on sequence diagrams correspond to transitions (at the receiving end) and actions (from the sending end) on state diagrams
  - The state diagram for a class will show all messages it receives from **all** the sequence diagrams it appears on

<img src="C:\src\UniNotes\Year 2\CO2401 - Software Development\Images\image-20211116104904768.png" alt="image-20211116104904768" style="zoom:50%;" />

## STD's a programming perspective

- Transitions may show any or all of:
  - Events: a method being called on this object
  - Guard(s): a condition which must be true before the object responds to that event
  - Actions: a method being called by this object on itself or on another object
- The STD can be used as a specification of **when** (in an object's life) its methods are allowed to be executed, and some of **what** the object should then do.
- Often, a **state variable** is used in the implementation of the class, whose value can be consulted when any method is called.

## When to use State Diagrams

- Good at describing object behaviour across several different use cases
  - Not good at describing behaviour involving multiple objects collaborating
    - Can use a sequence diagram for this
  - Use state diagrams only for objects that exhibit interesting behaviour
    - Where building the state diagram helps you understand what is going on
    - Drawing a state diagram for every class in your system is almost always a waste of effort
    - UI and Control objects often have the kind of behaviour that is useful to describe in a state diagram

## State Transition Diagram Summary

- Model classes that respond differently to the same event
  - Depending on history
- Based on States, Transitions, Events, Actions
- Must be drawn at the right level
  - To capture useful information without excessive complexity
- Use Harel Statechart notation to reduce complexity
  - Superstates
  - Composite states
  - Actions on enter/exit; activities in states (do)

