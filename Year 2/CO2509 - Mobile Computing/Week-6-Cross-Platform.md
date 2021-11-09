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
- **Finish this**

