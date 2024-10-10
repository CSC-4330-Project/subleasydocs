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


## 3. Git Branching Strategy

<div style="text-align: center;">
    <img src="{{site.baseurl}}/assets/git.jpg" alt="git branching" width="600" >
</div>

<br>

#### Master Branch
- The `master` branch represents the main line of development.
- It should always contain production-ready code.
- Direct commits to `master` are generally not allowed.

#### Development Branch
- The `dev` branch is created off the `master` branch.
- It serves as an integration branch for features.
- All feature development should be merged into `dev` first.

#### Feature Branches
- Feature branches are created off the `dev` branch.
- They are used for developing new features or making significant changes.
- Naming convention: `feature/[feature-name]`

### Workflow

1. Create a new feature branch from `dev`:
   ```
   git checkout dev
   git pull origin dev
   git checkout -b feature/new-feature
   ```

2. Develop your feature in the feature branch.

3. Once the feature is complete:
   - Ensure all tests pass
   - Update documentation if necessary

4. Merge the feature branch into `dev`:
   ```
   git checkout dev
   git pull origin dev
   git merge --no-ff feature/new-feature
   git push origin dev
   ```

5. Delete the feature branch (optional):
   ```
   git branch -d feature/new-feature
   ```

6. Periodically, `dev` will be merged into `master` for releases:
   ```
   git checkout master
   git pull origin master
   git merge --no-ff dev
   git push origin master
   ```

### Best Practices

- Keep feature branches short-lived and focused on a single feature or task.
- Regularly pull changes from `dev` into your feature branch to stay up-to-date.
- Use meaningful commit messages.
- Consider using pull requests for code review before merging into `dev`.

This branching strategy helps maintain a clean history and supports collaborative development while keeping the master branch stable.

## 4. Development Environment Setup

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


## 5. Code Style Guide

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

## 6. Building and Running the App

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
