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

### Function overloading

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