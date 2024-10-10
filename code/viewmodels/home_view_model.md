---
layout: page
---

# HomeViewModel Documentation

The `HomeViewModel` class is responsible for managing the state and logic of the home screen in a Flutter application. It extends `ChangeNotifier` for state management and handles user authentication status and sign-out functionality.

## Properties

**`_authService`**
- **Type:** `AuthService`
- **Description:** Instance of `AuthService` for handling authentication operations.

**`errorMessage`**
- **Type:** `String?`
- **Description:** Stores any error message that occurs during sign-out process.

**`_isLoading`**
- **Type:** `bool`
- **Description:** Indicates whether a sign-out operation is in progress.

## Getters

**`currentUser`**
- **Return Type:** `User?`
- **Description:** Returns the current user object from the `AuthService`. It may be null if no user is signed in.

**`isLoading`**
- **Return Type:** `bool`
- **Description:** Returns the current loading state.

## Methods

**`signOut`**
- **Return Type:** `Future<bool>`
- **Description:** Initiates the sign-out process. It returns `true` if sign-out is successful, `false` otherwise. During the process, it manages the loading state and error handling.

## Usage

This view model is designed to be used with a home screen in a Flutter application. It provides information about the current user's authentication status and handles the sign-out process.

Example usage in a widget:

```dart
final viewModel = HomeViewModel(authService);
// ...
Text('Welcome, ${viewModel.currentUser?.email ?? 'Guest'}'),
ElevatedButton(
  onPressed: viewModel.isLoading ? null : () async {
    if (await viewModel.signOut()) {
      // Navigate to login screen
    } else {
      // Show error message
      ScaffoldMessenger.of(context).showSnackBar(
        SnackBar(content: Text(viewModel.errorMessage ?? 'Sign out failed')),
      );
    }
  },
  child: Text('Sign Out'),
),
```