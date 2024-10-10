---
layout: page
---

# Subleasing App Architecture Documentation

## 1. Overview

This document outlines the architectural design of our Subleasing app. We follow the MVVM (Model-View-ViewModel) architecture pattern to ensure a clean separation of concerns and maintain a scalable, testable codebase.

## 2. Directory Structure

Our project's main directory structure is organized as follows:

```
lib/
├── services/
├── viewmodels/
├── pages/
├── components/
├── models/
├── utils/
└── assets/
```

### 2.1 Services

The `services` directory contains classes that handle external interactions and business logic. For example:
- `auth_service.dart`: Manages authentication-related functions such as sign-in, sign-up, and password reset.

### 2.2 ViewModels

The `viewmodels` directory contains a separate ViewModel for each page in the application. ViewModels act as an intermediary between the Model (data) and the View (UI), handling the business logic and state management for each page.

### 2.3 Pages

The `pages` directory contains the main screens of the application. Each page is associated with a corresponding ViewModel.

### 2.4 Components

The `components` directory houses reusable UI elements used throughout the app, such as custom buttons, text fields, and progress indicators.

### 2.5 Models

The `models` directory contains data models that represent the structure of our data, such as the `Users` model.

### 2.6 Utils

The `utils` directory contains utility classes and constants used across the application, such as color schemes and validation functions.

### 2.7 Assets

The `assets` directory stores static resources like images and fonts used in the application.

## 3. MVVM Architecture

Our app follows the MVVM (Model-View-ViewModel) architecture:

- **Model**: Represents the data and business logic of the application. In our case, this involves the Firestore data model and local data models.
- **View**: Represents the UI of the application. In Flutter, this is typically a Widget.
- **ViewModel**: Acts as a bridge between the Model and the View. It handles the presentation logic and state management for the View.

## 4. Data Model

### 4.1 Local Data Models

- **Users**: Represents user information
  ```dart
  class Users {
    final String firstName;
    final String lastName;
    final String email;
    final String password;

    Users({required this.firstName, required this.lastName, required this.email, required this.password});
  }
  ```

### 4.2 Firestore Structure

Our Firestore database consists of a single collection:

- **users**: Stores user information
  - Fields:
    - first_name: String
    - last_name: String
    - email: String
    - created_at: Timestamp

## 5. Naming Conventions

We follow these naming conventions to maintain consistency across the project:

- File names: snake_case (e.g., `auth_service.dart`)
- Class names: PascalCase (e.g., `AuthService`)
- Variables and functions: camelCase (e.g., `userEmail`)
- Constants: SCREAMING_SNAKE_CASE (e.g., `PRIMARY_COLOR`)

## 6. Navigation

We use Flutter's built-in navigation system:

- `Navigator` for managing the navigation stack
- `MaterialPageRoute` for defining routes between pages

Navigation logic is kept in the View layer, with ViewModels communicating navigation needs through callbacks or streams.

## 7. State Management

We use a combination of state management techniques:

- `ChangeNotifier` for ViewModels to notify Views of state changes
- `Provider` for dependency injection and accessing ViewModels from Views
- Local state management using `setState()` for simple UI state changes within widgets

## 8. Authentication Flow

Our authentication flow includes:

1. Sign Up: Users can create a new account with email and password
2. Sign In: Existing users can sign in with their credentials
3. Password Reset: Users can request a password reset email

The `AuthService` handles these operations, interacting with Firebase Authentication.

## 9. Form Validation

Form validation is handled in the ViewModels, with validation logic for email and password fields. We use `FormKey` for structured form validation.

## 10. Error Handling

Errors are caught in the ViewModels and communicated to the Views through error messages or dedicated error streams. Views are responsible for displaying error messages to the user.

## 11. Animations

We use Flutter's animation system to enhance the user experience:

- Fade-in and slide animations for page transitions
- Loading indicators for asynchronous operations
