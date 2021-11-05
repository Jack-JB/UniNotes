# Pointers & Memory

## Why is memory important?

- You need to know the size of data of data types for certain operations

- - e.g. qsort() requires the exact size of bytes of the array

- Memory size has important implications for efficiency

- Some systems are memory constrained

- - e.g. mobile devices, embedded chips, hand-held consoles
  - A question often seen on job tests

## Dynamic memory allocation

- Allows the program to request memory from the OS whilst it is running

- Often do not know how much memory is required

- - Often do not know when an object will be created or destroyed

- Wasteful to allocate large chunks of unused memory

- - e.g. a large database which is unpopulated

- Dynamic memory allocation is the standard way to create objects or instances of a class

## Variables and addresses

- A variable has an address in memory. This is the case with all variables
- The address of a variable is given by placing an ampersand in front of the variable
- A pointer stores the memory location of another variable
- Pointers 'point at' variables

---

## Using Pointers

> ```c++
> // Stack pointer allocation (static memory)
> int age = 21;
> int* agePtr = &age;
> ```
>
> **age** variable - stores integer value
>
> **agePtr** variable - stores address of integer

> ``` c++
> // Heap pointer allocation (dymanic memory)
> int* age = new int*;
> *age = 21;
> 
> delete(age);
> ```
>
> **age** variable - stores integer value
>
> **agePtr** variable - stores address of integer
>
> **Delete** age after use

## Pointers and Objects

- Instances of classes and structures can be declared using pointers and memory allocation
- The arrow operator s used to access the member functions and data members of a class or structure

```cpp
Stack* myStack = new Stack;
myStack->initialiseStack();

myStack->push("red");
```

---

## Delete

- The delete operator releases memory

- Requires the address of an object

- Typically it called a function called free()

- - One again, for general use, you do not need to access the underlining memory deallocation
  - Invokes the destructor (if exists)

- If the pointer being delete is zero then nothing happens

- - i.e. delete is safe to call even if the pointer is not pointing at anything

---

## Dynamic Arrays

- Arrays can be created dynamically using pointers
- **Must** tell the compiler to delete the whole array using square brackets [ ]

``` cpp
int* arrPtr = new int[100];
delete[] arrPtr; // Good
delete arrPtr; // Bad
```