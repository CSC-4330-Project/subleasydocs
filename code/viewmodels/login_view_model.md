# LoginViewModel Documentation

The `LoginViewModel` class is responsible for managing the state and logic of the login screen in a Flutter application. It extends `ChangeNotifier` for state management and handles user authentication.

## Properties

**`_authService`**
- **Type:** `AuthService`
- **Description:** Instance of `AuthService` for handling authentication operations.

**`formKey`**
- **Type:** `GlobalKey<FormState>`
- **Description:** Key for the form widget, used for form validation.

**`emailController`**
- **Type:** `TextEditingController`
- **Description:** Controls the email input field.

**`passwordController`**
- **Type:** `TextEditingController`
- **Description:** Controls the password input field.

**`_isLoading`**
- **Type:** `bool`
- **Description:** Indicates whether a sign-in operation is in progress.

**`_errorMessage`**
- **Type:** `String?`
- **Description:** Stores any error message that occurs during the sign-in process.

## Getters

**`isLoading`**
- **Return Type:** `bool`
- **Description:** Returns the current loading state.

**`errorMessage`**
- **Return Type:** `String?`
- **Description:** Returns the current error message, if any.

## Callback Properties

**`onSignInSuccess`**
- **Type:** `void Function()?`
- **Description:** Callback function called when sign-in is successful.

**`onSignInFailure`**
- **Type:** `void Function()?`
- **Description:** Callback function called when sign-in fails.

## Methods

**`setLoading`**
- **Parameters:**
  - `loading` (bool): The new loading state
- **Description:** Updates the loading state and notifies listeners.

**`setErrorMessage`**
- **Parameters:**
  - `message` (String?): The new error message
- **Description:** Updates the error message and notifies listeners.

**`handleSignIn`**
- **Return Type:** `Future<void>`
- **Description:** Initiates the sign-in process. Validates the form, attempts to sign in, and handles success or failure.

**`_onSignInSuccess`**
- **Description:** Internal method to call the `onSignInSuccess` callback if set.

**`_onSignInFailure`**
- **Description:** Internal method to call the `onSignInFailure` callback if set.

**`validateEmail`**
- **Parameters:**
  - `value` (String?): The email input to validate
- **Return Type:** `String?`
- **Description:** Validates the email input. Returns an error message if invalid, null otherwise.

**`validatePassword`**
- **Parameters:**
  - `value` (String?): The password input to validate
- **Return Type:** `String?`
- **Description:** Validates the password input. Returns an error message if invalid, null otherwise.

**`clearSensitiveData`**
- **Description:** Clears the email and password controllers and notifies listeners.

**`dispose`**
- **Description:** Disposes of the email and password controllers when the view model is no longer needed.

## Usage

This view model is designed to be used with a login screen in a Flutter application. It handles email and password validation, initiates the sign-in process, and manages the UI state (loading, success, error) throughout the process.

Example usage in a widget:

```dart
final viewModel = LoginViewModel(authService);
// ...
TextFormField(
  controller: viewModel.emailController,
  validator: viewModel.validateEmail,
),
TextFormField(
  controller: viewModel.passwordController,
  validator: viewModel.validatePassword,
),
ElevatedButton(
  onPressed: viewModel.isLoading ? null : viewModel.handleSignIn,
  child: Text('Sign In'),
),
if (viewModel.errorMessage != null)
  Text(viewModel.errorMessage!),
```

The view model should be provided with an instance of `AuthService` when created, and can be used with `ChangeNotifierProvider` for state management in the widget tree.