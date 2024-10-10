

The `ForgotPasswordViewModel` class is responsible for managing the state and logic of the forgot password feature in a Flutter application. It extends `ChangeNotifier` for state management.

## Properties

**`emailController`**
- **Type:** `TextEditingController`
- **Description:** Controls the email input field.

**`formKey`**
- **Type:** `GlobalKey<FormState>`
- **Description:** Key for the form widget, used for form validation.

**`_authService`**
- **Type:** `AuthService`
- **Description:** Instance of `AuthService` for handling authentication operations.

**`_isLoading`**
- **Type:** `bool`
- **Description:** Indicates whether a password reset operation is in progress.

**`_errorMessage`**
- **Type:** `String?`
- **Description:** Stores any error message that occurs during the password reset process.

**`_isEmailSent`**
- **Type:** `bool`
- **Description:** Indicates whether a password reset email has been successfully sent.

## Getters

**`isLoading`**
- **Return Type:** `bool`
- **Description:** Returns the current loading state.

**`errorMessage`**
- **Return Type:** `String?`
- **Description:** Returns the current error message, if any.

**`isEmailSent`**
- **Return Type:** `bool`
- **Description:** Returns whether a password reset email has been sent.

## Callback Properties

**`onResetSuccess`**
- **Type:** `void Function()?`
- **Description:** Callback function called when password reset is successful.

**`onResetFailure`**
- **Type:** `void Function(String)?`
- **Description:** Callback function called when password reset fails, with the error message as a parameter.

## Methods

**`validateEmail`**
- **Parameters:**
  - `value` (String?): The email input to validate
- **Return Type:** `String?`
- **Description:** Validates the email input. Returns an error message if invalid, null otherwise.

**`resetPassword`**
- **Return Type:** `Future<void>`
- **Description:** Initiates the password reset process. Validates the form, sends a password reset email, and updates the view model's state accordingly.

**`dispose`**
- **Return Type:** `void`
- **Description:** Disposes of the `emailController` when the view model is no longer needed.

## Usage

This view model is designed to be used with a forgot password screen in a Flutter application. It handles email validation, initiates the password reset process, and manages the UI state (loading, success, error) throughout the process.

Example usage in a widget:

```dart
final viewModel = ForgotPasswordViewModel(authService);
// ...
ElevatedButton(
  onPressed: viewModel.isLoading ? null : viewModel.resetPassword,
  child: Text('Reset Password'),
),
// ...
Text(viewModel.errorMessage ?? ''),
```

The view model should be provided with an instance of `AuthService` when created, and can be used with `ChangeNotifierProvider` for state management in the widget tree.