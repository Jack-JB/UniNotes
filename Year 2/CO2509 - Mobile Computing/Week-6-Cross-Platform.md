# Cross Platform Development

## Introduction

Cross platform is exactly that, you develop f or multiple platforms using one code base.

For the purpose of this module we will target Android or the Web.

It is important to understand the architecture of the platform target as it will help development of that platform

## Android Stack

Google's Android is an open source software stack developed for a range of devices from mobile phones to car infotainment systems. each consisting of varying form factors.

- Apps
- Framework - provides fundamental services that support apps such as the Activity/Resources/Notification managers, content providers
- Libraries - open source additional libraries such as SQLite, WebKit, SSL etc.
  - Runtime - the architecture that handles the core memory management and threading etc. Uses the Dart Virtual Machine
- Hardware Abstraction Layer (HAL) - exposes device hardware capabilities to the high level API's
- Linux Kernel - the layer which handles the drivers for the specific hardware

## Flutter Architectural Overview

Independent layers and libraries.

Uses platform specific embedder language to package apps.

the engine supports the Framework by providing access to low-level core APs (dart up)

The Dart framework provides developers high-level access to core features.

<img src="C:\Users\jackj\AppData\Roaming\Typora\typora-user-images\image-20211109091143738.png" alt="image-20211109091143738" style="zoom:50%;" />

The Flutter Framework is relatively small. Access to the core features such as the Camera, WebView, location modules as well as non specific features like http, characters are added on top.

Other services such as in-app payments, apple authentication etc come from the broader ecosystems depending on the platform.

## Flutter Framework

The flutter framework is built on top of Dart.

Dart is:

- Still in it's infancy
- Compiled
- Statically-typed
- Object Oriented
- Procedural
- Similar to C#, Java, C++, C, Swift and JS

#### Final and Const

Final and const are Dart variable modifiers. They both mean once assigned, the value can not change. However, const variables are set at compile time and are bundled with the application. Whereas, final variables can't be reassigned but can change.

- **Dynamic** - Can store any data type and can change at any point
- **Var** - The data type is inferred from the value set
- **Final** - The variable is set once and cannot be reassigned
- **Const** - The variable is set at compile time, not runtime

#### Hot Reload

Remember Flutter has this feature that allows you to upgrade code whilst the app is running. this could be running on device, in the emulator or in the browser. this app will update with the change and even better it remembers the last state you were in.

## Foundation

Flutter is built around a process known as componentisation. componentisation is not new but we are recently using it as a way of developing software, the idea behind this is to break down a complex problem into smaller, simpler complex bits (**decomposition**). this helps us solve the problem as we focus on only a small part at a time. We then pull these components together into one larger component (**composition**).

In Flutter these components are referred to as '**Widgets**'.

Every app can be considered having two parts;

1. **Behaviour**: The software; logic, data reading/writing and processing
2. **Presentation**: How the software looks; the UI (buttons, labels, textboxes etc.)

## UI as Code

Flutter uses the same Dart code to create the UI (presentation) and it does to create the logic (behaviour).

Like many development platforms, a main function is present to load the app. this is named `runApp()` this function requires one widget to be provided. it can be named anything but it should extend `StatelessWidget`

- **Main function**: The first function that is required to launch your code
- **Extend**: Means the new class will inherit from another class
- **Class**: Is the blueprint, containing certain properties about a thing

## Developing in Flutter

When developing cross-platform here is a lot of moving parts that you need to assemble. the Flutter toolchain consists of the SDK, an IDE, IDE DevTools and an emulator

- **Flutter SDK**: compiler, project creator, device manager, test runner, diagnose and correct problems
- **IDE**: You can use pretty much any IDE. However, the most popular are VS Code from Microsoft and of course Android Studio from Google
- **IDE** DevTools: The tools are there to provide extra support for debugging in the Flutter development
- **Emulators**: is a virtual devices that lets you test your app without needing a device at hand. 

## Widget Keys

If you are familiar with programming for the Web you will have heard about the DOM. Document Object Model.

Virtual DOM? Flutter doesn't have a DOM. It does have something similar though. Flutter has an element tree. The element tree is a small copy of all the widgets in the view (active) and a changes version.

