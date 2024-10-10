---
layout: page
---

## 1. Project Overview

**Project Name:** Subleasy 

**Description:** A mobile application designed to facilitate subleasing processes.

**Target Platforms:** iOS and Android

## 2. Technology Stack

- **Frontend:** Flutter 3.24.1
- **Backend:** Firebase
- **Version Control:** Git

## 3. Development Environment Setup

### Flutter SDK Installation

1. Download and install Flutter 3.24.1 from the official Flutter website.
2. Add Flutter to your PATH.
3. Run `flutter doctor` to verify the installation and set up any missing dependencies.

### Xcode Setup (for iOS)

1. Install Xcode from the Mac App Store.
2. Install iOS Simulator.
3. Configure Xcode command-line tools.

### Android Studio Setup (for Android)

1. Download and install Android Studio.
2. Install the Flutter and Dart plugins.
3. Set up Android SDK and create an Android Virtual Device (AVD).

### Firebase Project Setup

1. Create a new Firebase project in the Firebase Console.
2. Add iOS and Android apps to the Firebase project.
3. Download and integrate the necessary configuration files (GoogleService-Info.plist for iOS, google-services.json for Android).

### Git Repository Setup

1. Initialize a Git repository in your project folder.
2. Create a .gitignore file to exclude sensitive information and build artifacts.
3. Make an initial commit with the project structure.


## 4. Code Style Guide

### Naming Conventions

- Use `camelCase` for variable and function names.
- Use `PascalCase` for class names and type parameters.
- Use `lowercase_with_underscores` for file names.

### File Organization

- Keep related files in the same directory.
- Use meaningful directory names that reflect the contents.

### Comment Practices

- Use `///` for documentation comments.
- Write clear, concise comments explaining "why" rather than "what".

## 5. Building and Running the App

### Debug Build

```
flutter run
```

### Release Build

For Android:
```
flutter build apk
```

For iOS:
```
flutter build ios
```

### Running on iOS Simulator/Device

1. Open iOS Simulator or connect an iOS device.
2. Run `flutter devices` to verify the device is recognized.
3. Run `flutter run -d <device_id>`.

### Running on Android Emulator/Device

1. Open Android Emulator or connect an Android device.
2. Run `flutter devices` to verify the device is recognized.
3. Run `flutter run -d <device_id>`.
