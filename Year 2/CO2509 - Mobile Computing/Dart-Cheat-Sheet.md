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



