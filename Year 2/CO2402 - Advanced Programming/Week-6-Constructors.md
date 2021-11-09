# Constructors, Destructors and Inheritance

A Constructor in C++ is a **special method** that is automatically called when an object of a class is created. A Constructor is initialised by creating a method with the same name as the Class.

## Constructors

```C++
class Stack() {
private:
	int top;
  int id;
public:
	Stack(); // Initialisng Default Constructor method
  Stack(int newID);
}

// Default constructor
Stack::Stack() {
  top = 0;
}

// Declaring another constructor (function overloading)
Stack::Stack(int newID) {
  top = 0;
  id = newID;
}

// Alternative way (preferred)
Stack::Stack(int newID) : top(0), id(newID) { }
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
	Stack(); // Initialisng Constructor method
 	~Stack(); // Initialising Destructor method
} 

// Constructor
Stack::Stack() {
  top = 0;
}

// Destructor
Stack::~Stack() {
  
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

> If an object contains **dynamic memory** and the destructor is invoked, all of that memory will still remain and cause a memory leak.

### Syntax



## Example

- Consider a system to record student marks
- Each student has a list of modules studied. Each module has an associated mark and a code
- A fixed array is inefficient - a student can take between 1 - 7 modules depending on the circumstances. The data for the modules is therefore stored using dynamic memory. The memory is allocated as modules are registered.
- **TODO: finish**

