# Function overriding and Polymorphism

**Inheritance**

- A reminder of some terminology:
  - The original class is called the **base** class (the **parent**)

## Function names

- Remember function overloading?
  - Two functions with the same name, but different parameter lists?
- It is possibly and useful for a function in a derived class to have the same name and parameters as a function in its base class
  - This is only possibly because the functions exist in different scopes
- It is not immediately obvious what happens at run-time
  - Which version of the function will be executed?
- This is fiddly but no other way to approach the subject except by looking at

## An overridden function

```cpp
class CBase {
public:
  void DisplayMessage();
};

void::CBase::DisplayMessage() {
  std::cout << "Message from base class\n";
}
```

```cpp

```



### Classing an overridden function

- If you have an object of `CBase` and call the function

  - The base class version of the function will be called

  ```cpp
  CBase myBase;
  myBase.DisplayMessage();
  ```

- If, however you have an object of `CDerived`

  - The overridden version will be called by default
  - You can explicitly call the base class version by using the `::` (scope) operator

  ```cpp
  myDerived.CBase::DisplayMessage()
  ```

- Things get more complicated when pointers are involved

  - The type of the pointer, rather than the type of the object pointed to determines which version of the function

### `CDerived` pointer point at `CDerived` object

```cpp
CDerived* pDerived = new CDerived;
pDerived -> DisplayMessage()
```

- Output: "Message from base class"
- A pointer of the base class, pointing at an object of the derived class, invokes the method from the **base** class
- the type of the **pointer**, not the type of the object being pointed at determines which version of the method gets called (except when...)

# Polymorphism

- It can be the case that the derived classes are related to one another and we want to use them together
- It is natural to want to have an array of such related derived objects
- Wouldn't it be nice if they could all exhibit their own overridden behaviour, but we didn't need to know or care which derived class they belonged to when we invoked that behaviour?
- This type of behaviour can be created using the keyword `virtual` in the base class
- The keyword is not repeated in the function definition

```cpp
virtual dataType FunctionName();
```

