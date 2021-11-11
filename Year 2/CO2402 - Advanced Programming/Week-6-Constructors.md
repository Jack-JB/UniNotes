# Constructors, Destructors and Inheritance

A Constructor in C++ is a **special method** that is automatically called when an object of a class is created. A Constructor is initialised by creating a method with the same name as the Class.

- All classes have at least one **constructor**. If you do not created one, the compiler will generate a default constructor
- a class can have multiple constructors

## Constructors

- A constructor has no return type.
- The constructor shares the same name as the class (see below)
- Constructors should always be used, this will stop any unwanted behaviour that could be caused by the constructor created by the compiler

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

### Function Overloading

- **Overloading** is using the same name for <u>different</u> functions
  - The parameters **must** be different.
  - In C++ a function is identified by its name, parameters and return type
    - This is called the functions **signature**, **specification** or **prototype**
- Different **constructors** can be provided for a class
  - These could be for different uses
- Constructors are generally **overloaded** so that objects can be initialised in multiple ways

```C++
// Initialising a constructor
Record::Record() {
  value = 0;
}
// Overloading the constructor
Record::Record(int num) {
  value = num
}

// Invoking the constructor
Record* newRecord = new Record;

Record* anotherRecord = new Record(10);
```

- This code above uses both constructors. 
  - `newRecord` takes no parameters, just like the first constructor
  - `anotherRecord` takes an `integer`, just like the second constructor 

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
- You do **not** need to invoke a destructor yourself, this is done automatically
- A class is destroyed when:
  - A reference object is deallocated using **delete**
  - A value object goes out of scope


### Why use destructors?

- A destructor is a 'cleaning up' function
- It is often the case that you have to clean up when a class ends
- It is common to create manager classes - a class which manages another class
  - An example of this is linked lists. A `LinkedList` class manages an Element class. When the `LinkeList` class ends it needs to clean up any Element objects left around
- It is common to see memory allocation in a class. Instances often need different amounts of data and so allocate memory on the fly

> If an object contains **dynamic memory** and the destructor is invoked, all of that memory will still remain and cause a memory leak.

### Syntax

- A **tilde** (~) is placed before a function name
- The **destructor** shares the same name as the **class**
- The **destructor** has no return type
- A class can only have **one** destructor
- Destructors take **no** arguments 

``` C++
// Destructor
Stack::~Stack() {
  std::cout << "Destructor called\n";
}
```

