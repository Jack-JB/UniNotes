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
class Name() {
  String first;
  String last;
  String suffix;
}

class Person() {
  // properties
  int id;
  Name name;
  String email;
  String phone;
  
  // methods
  void save() {
    // do something
  }
  // Constructor
  person() {
    
  }
}
```



