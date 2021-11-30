# Testing

Automated testing includes:

1. Unit test - test a single function, method or class
2. Widget test (component test) - test a single Widget
3. Integration test - tests a complete application or large part of an application

|                  | Unit  | Widget | Integration |
| ---------------- | ----- | ------ | ----------- |
| Confidence       | Low   | Higher | Highest     |
| Maintenance cost | Low   | Higher | Highest     |
| Dependencies     | Few   | More   | Most        |
| Execution speed  | Quick | Quick  | Slow        |

## Unit Tests

Test a single function, method or class. You are testing the logic under a variety of conditions.

Create a new test file inside the test directory (requires to have the `_test.dart` as the suffix)

In this example we are using the Arrange, Act, Asset test pattern.

```dart
// Import flutter test package
import 'package:flutter_test/flutter_test.dart';
 
void main() {
  test('Should get all items added to the list', ()) {
    // Arrange
    final todoViewModle = TodoViewModel();
    final item = TodoItem(
    id: 1,
    title: 'Test Title'),
    );
  // Act
  todoViewModel.addItemToList(item);
  todoViewModel.addItemToList(item);
  todoViewModel.addItemToList(item);
  
  // Assess
  expect(todoViewModel.todos.length, 3);
  });
}
```

This unit test adds items to the model and on success checks to see if the length of the model is 3 if correct ‘Should get all the items added to the list’ is printed.

- Arrange - Preparing the data to test, what operations are needed? etc
- Act - The main thing to be tested, calling a method, REST API, interaction etc
- Assert - Responses from the action, validating the outcomes (pass or fail)

> **Arrange**: This step creates the instance of the `todo` model, which is a `ChangeNotifier` subclass, and the item object
>
> **Act**: The step acts upon the `todo` model by calling the method `addItemToList`, which adds the same instance of the item object
>
> **Assert**: This step verifies that the `todos` have three items based on calling the method `addItemToList` three times 

## Widget Tests

In other programming environments it is often referred to as component testing. In Flutter, Widget testing, tests a single Widget.

The goal of the test is to verify that the Widget's UI looks and interacts as designed to/

Testing a Widget requires a deeper understanding of the Widgets journey and therefore requires multiple class and the appropriate lifecycle context. The Widget being tested should be able to:

- Receive and respond to user action and events
- Perform layout
- Instantiate child widgets

A widget test is therefore more comprehensive than a unit test. However, like a unit test, a widget test's environment is replaced with an implementation much simpler than a full-blown UI system.

```dart
import 'package:flutter_test/flutter_test.dart';

void main() {
  testWidgets('login button works', (WidgetTester tester) async {
    // Build out app and trigger a frame
    await tester.pumpWidget(const MyApp());
    // Tap the test button
    final emailField = find.byKey(const Key('email'));
    await tester.enterText(emailField, 'email@email.com');
    await tester.pumpAndSettle();
    
    final loginBtn = find.byKey(const Key('LoginButn'));
    await tester.tap(loginBtn);
    
    await tester.pump()
  });
}
```

## Integration Testing

Tests the complete app or a large part of the application. The goal is to verify all Widgets and services being tested work together as expected.

Integration testing occurs when you run the application on device or emulator.

# Debugging

## DevTools

In Flutter we use DevTools to debug applications.

DevTools run in  the browser and supports:

- Source-level debugger
- Widget inspector
- Memory profiler
- TimeLine view
- Logging view

Works in debug (or profile mode)

DevTools provide functionality for:

- Inspecting the UI layout and state of a Flutter app
- Diagnosing UI performance issues in a Flutter app
- Profiling CPU for a Flutter app
- Profiling Flutter app networking
- Debugging source-level of a Flutter app
- Viewing general log and diagnostics information about a running Flutter app
- Analysing code and app size

## Programmatically

You have many options for logging debug statements in your code.

- `stdout.writeln()` and `stderr.writeln()` - for debugging single statements
- `debugPrint()` - for debugging lots of output at once, this is a wrapper around print that throttles the output to a level that avoids being dropped by Android's Kernel.
- `log()` - from `dart:developer` library



