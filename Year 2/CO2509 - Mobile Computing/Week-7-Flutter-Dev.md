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

## Exceptions in Dart

1. **DefferedLoadException** is thrown when a deferred library fails to load.
2. **FormatExceptoion** is thrown when a string or some other data does not have an expected format and cannot me parsed or processed
3. **IntegerDivisionByZeroException** is thrown when a number is divided by zero
4. **IOException** is the base class for all input-output related exceptions
5. **IsolateSpawnException** is thrown when **TODO: finish**

## Abstract/Interface

Abstract classes and Interfaces are closely related. However, there are minor differences and it is important to understand these.

| Abstract                        | Interface                       |
| ------------------------------- | ------------------------------- |
| Cannot be instantiated          | Can be instantiated             |
| Abstract methods can be created | Abstract methods can be created |
| When extended only              |                                 |
|                                 |                                 |

**TODO: Finish**

## Static Variables

Static variables are variables that have be allocated statically. Even though static variables can be instantiated inside a class you can not access it by using the class object. Static variables can be present in the class and accessed by the following. Alongside, variables methods can be also declared as static. Static members are only instantiated once. This saves us memory as it can be reused. However, they aren't initialised until they are used within the code.

```dart
void main() {
  //T
}
```



