# Constructors, Destructors and Inheritance

## Constructors

```C++
class Stack() {
private:
	int top;
public:
	Stack(); // Initialisng Constructor class
}

Stack::Stack() {
  top = 0;
}
```

### Invoking the constructor

- The code below shows all three of the constructors being invoked
- The parameters are placed inside round brackets after the class name,
- Function overloading

- **Overloading** is the practice of using the same name for different functions
  - The parameters must be different
  - In C++ a function is identified by name plus parameters and return type
    - This is often called the function's signature or specification
- You can provide different constructors for a class
  - These could be tailored for different circumstances
- It is often useful to supply data at the time that an object is created
  - But there may be cases that you do not want to do this
- Constructors are usually **overloaded** so that objects can be initialised in many ways

### Initialisation section 

- A constructor may have

## Destructors

```C++
class Stack() {
private:
	int top;
public:
	Stack(); // Initialisng Constructor class
}

// Constructor
Stack::Stack() {
  top = 0;
}

// Destructor
~Stack::Stack() {
  
}
```

- The destructor is automatically called when a class is destroyed
- You do not need to invoke 
- **TODO: finish**

### Why use destructors?

- A destructor is a 'cleaning up' function
- It is often the case that you have to clean up when a class ends
- It is common to create manager classes - a class which manages another class
  - An example of this is linked lists. A `LinkedList` class manages an Element class. When the `LinkeList` class ends it needs to clean up any Element objects left around
- It is common to see memory allocation in a class. Instances often need different amounts of data and so allocate memory on the fly
- **TODO: finish**

### Syntax



## Example

- Consider a system to record student marks
- Each student has a list of modules studied. Each module has an associated mark and a code
- A fixed array is inefficient - a student can take between 1 - 7 modules depending on the circumstances. The data for the modules is therefore stored using dynamic memory. The memory is allocated as modules are registered.
- **TODO: finish**

