# Flutter Development

- Understand why dart was adopted for Flutter development
- Establish the fundamentals of the Dart programming language
- Begin to start formalising your knowledge of the subject area

## Dart

- Dart is ahead-of-time compiled to fast native x86 or ARM code (Android and iOS devices)
- Dart also offers just-in-time compilation which is useful for development as it allows 'hot reload'
- Fast garbage collection
- Object oriented
- Type inferencing
- Sound type system
- Dedicated threads for UI,GPU, IO task runners per instance
- Great IDE support IntelliJ, Android Studio,  VSC.
- Community supported
- Easy to learn

## Optional Parameters

In Dart we can also have functions that pass optional parameters. In some instances when you don't know how many parameters you will have to pass; you can make certain ones optional. This is achieved by encapsulating the parameter in square brackets `[ ]`

```dart
String myGradeCalc(int n, int n2, [int n3]) {
  print(n);
  print(n2);
  print(n3); // Optional
}
```

## Named

In Dart you can also have "named" optional parameters. This means you can pass the parameters to your function in any order. This is achieved by embracing the parameters with curly braces.

```dart
void main() {
  var result = myGradeCalc(63, n2:80, n3:74);
}

String myGradeCalc(int n, {int n2, int n3}) {
  print(n);
  print(n2);
  if (n3 != null) {
    print(n3);
  }
}
```

named optional parameters out of sequence

```dart
void main() {
  var result = myGradeCalc(63, n2:74, n3:80);
}

String myGradeCalc(int n, {int n2, int n3}) {
  print(n);
  print(n2);
  if (n3 != null) {
    print(n3);
  }
}
```



## Exceptions in Dart

You should always write your code to avoid any errors, but sometimes you will need to handle the unexpected. This is especially important when you are writing applications for mobile devices. There are a lot of data you will need to handle that you can not control. For example, the many sensors from the mobile devices may have issues on obtaining the data or it may provide the wrong information. One way we can handle this is by encapsulating our code in a **try and catch statement**.

1. **DefferedLoadException** is thrown when a deferred library fails to load.
2. **FormatExceptoion** is thrown when a string or some other data does not have an expected format and cannot me parsed or processed
3. **IntegerDivisionByZeroException** is thrown when a number is divided by zero
4. **IOException** is the base class for all input-output related exceptions
5. **IsolateSpawnException** is thrown when an isolate cannot be created
5. **Timeout** is thrown when a scheduled **timeout** happens while waiting for an async result

## Abstract/Interface

Abstract classes and Interfaces are closely related. However, there are minor differences and it is important to understand these.

| Abstract                                                   | Interface                                                    |
| ---------------------------------------------------------- | ------------------------------------------------------------ |
| Cannot be instantiated                                     | Can be instantiated                                          |
| Abstract methods can be created                            | Abstract methods can be created                              |
| When extended only abstract classes need to be overwritten | When implemented every class and instance variable needs to be overwritten |
| Only one abstract class can be extended                    | Multiple interfaces can be implemented                       |

## Static Variables

Static variables are variables that have be allocated statically. Even though static variables can be instantiated inside a class you can not access it by using the class object. Static variables can be present in the class and accessed by the following. Alongside, variables methods can be also declared as static. Static members are only instantiated once. This saves us memory as it can be reused. However, they aren't initialised until they are used within the code.

```dart
void main() {
  print(Student.isPerson);
}

class Student {
  static bool isPerson = true
}
```



