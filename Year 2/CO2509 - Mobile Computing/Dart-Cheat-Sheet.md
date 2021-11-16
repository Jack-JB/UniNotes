# Dart / Flutter Cheat Sheet

Similar to other languages Dart begins with a `main` function

```dart
main() {
  print("Hello, World!");
}
```

## Data Types

- **Number**:
  - Integer
  - Double
- **String**
- **Boolean**
- **List** - Can contain different types
- **Map**
- **Dynamic** - Can change type at any time
- **Const** - Value cannot be changed

## Optional Parameters

In Dart we can also have functions that pass optional parameters. In some instances when you don't know how many parameters you will have to pass; you can make certain ones optional. This is achieved by encapsulating the parameter in square brackets `[ ]`

```dart
String myGradeCalc(int n, int n2, [int n3]) {
  print(n);
  print(n2);
  print(n3); // Optional
}
```

### Arrays
```dart
// Arrays are dynmaic, size isnt required
var arr = ['1', '2', '3', '4'];
```
### Maps
```dart
// ---- Map literal ----
// Create a map variable
var student = {"id": 001, "name": 'jack', "email": "name@email.com"};
// Add to the map
student["course"] = "Software Engineering";
// ---- Map constructor ----
// Create map constructor
var student = new Map();
// Add values
student["id"] = 001;
student["name"] = "Jack";
student["email"] = "name@mail.com";
student["course"] = "Software Engineering";
```
Maps contain a number of functions for example; 
- `Keys` - Returns an iterable object representing `keys`
- `Values` - Returns an iterable objects representing `values`
- `Length` - Returns the size of the `map`
- `isEmpty` - Returns `true` if the `map` is empty
- `isNotEmpty` - Returns `true` if the `map` is empty
- `addAll()` - Adds all `key value pairs` of the other to this `map`
- `clear()` - Removes all pairs from the `map`
- `Remove()` - Removes `key` and its `value` if present, from the `map`
- `forEach()` - Applies `f` to each key-value pair of the `map`
### Type Inference

```dart
var i = 10; // i is defined as an int
i = 12; // still defined as an int
i = "twelve"; // does not work as i is considered an int
```

### String Interpolation with $

```dart
String fullName = '$first $last $suffix'; // preferred way
// is the same as
String fullName = first + " " + last " " + suffix;
// if the variable is part of an object
String fullName = '${name['first']} ${'name['last']}'; 
```

## Conditional Expressions

```dart
int x = 10;
if ( x < 100) {
  print("Yes")
} 
else {
  print("no")
} // Prints 'Yes'
```

## Loops

```dart
// For loop
for (int i = 0; i < 10; i++) {
  // do something
}

// While loop
int i = 1;
while(i < 10) {
  // do something
}
```

## Classes

```dart
class Module {
  // Member variables
  String id = " ";
  String name = " ";
  String email = " ";
  String course = " ";
  
  // Setter for the map
  set map(Map<String, dynamic> map) {
    id = map['id'];
    name = map['name'];
    email = map['email'];
    course = map['course'];
  }
  
	// Getter for the map
  Map<String, dynamic> get module {
    return {
      'id': id,
      'name': name,
      'email': email,
      'course': course,
    };
  }

	// Constructor
  Module(studentID, studentName, studentEmail, studentCourse) {
    id = studentID;
    name = studentName;
    email = studentEmail;
    course = studentCourse;
  }
  // Class Method
  void enrol(String id) {
    String gNum = "G" + id;
    print("Student id: $gNum is enrolled");
  }
}

void main() {
  // Object declaration
  Module newStudent =
      Module("001", "Jack", "email@emai.com", "Software Engineering");
	
  // Accessing class methods
  print(newStudent.module);
  newStudent.enrol(newStudent.id);
}
```

### Abstract Classes

Objects cannot be created from an Abstract Class, but it can be sub-classed. An abstract class allows you to create functionality that subclasses can implement or override.

- The word **abstract** precedes a class definition
- Typical classes can extend abstract classes, but they must override all of its abstract methods
- Similarly, abstract methods, exist within an abstract class
- Semi-colons are used instead of a method body

```dart
// Definition of an abstract class
abstract class Course {
  void courseWelcome();
}
```

```dart
// Classes inherit from the abstract class with 'extend'
class Module extends Course
```

```dart
// Override the method within the child class to implement its method
@override
  void courseWelcome() {
    print('Welcome to the course');
  }
```

```dart	
// Abstract class method called using the object of a child class
newStudent.courseWelcome();
```



### Inheritance

```dart
class Module {
  String title = " ";

  void status() {
    print('module is running');
  }

  String get moduleTitle {
    return title;
  }

  set moduleTitle(String moduleTitle) {
    title = moduleTitle;
  }
}
```

The `student` class inherits from `Module`, thus inheriting all of its methods and data members.

```dart
class Student extends Module {
  String id = " ";
  String name = " ";
  String email = " ";
  String course = " ";

  set map(Map<String, dynamic> map) {
    id = map['id'];
    name = map['name'];
    email = map['email'];
    course = map['course'];
  }

  Map<String, dynamic> get module {
    return {
      'id': id,
      'name': name,
      'email': email,
      'course': course,
    };
  }

  Student(studentID, studentName, studentEmail, studentCourse) {
    id = studentID;
    name = studentName;
    email = studentEmail;
    course = studentCourse;
  }
  void enrol(String id) {
    String gNum = "G" + id;
    print("Student id: $gNum is enrolled");
  }
	// override allows this different implementation of the status method in Module class
  @override
  void status() {
    // Super is used to refer to the parent class
    super.status();
    print('module is finished');
  }
}

```

**Super** is a reference variable which is used to refer immediate parent class objects. It is used to refer to the parent class **properties and methods**. Its most common use is to remove any ambiguity between the parent class and subclass that has methods and properties of the same name.

- <u>Usage:</u>
  1. The **super** keyword can be used to access data members of the parent class where both parent and child class have members of the same name.
  2. The **super** keyword can be used to access the method of the parent class when the child class has overridden that method
  3. Can be used to explicitly call the constructor of the parent class

**@override** is used so a **child class** can give its own implementation to a method which already exists within the **parent class**. This is known as **Method Overriding**. 

