# SignUpViewModel Documentation

The `SignUpViewModel` class is responsible for managing the state and logic of the sign-up screen in a Flutter application. It extends `ChangeNotifier` for state management and handles user registration.

## Properties

**`_authService`**
- **Type:** `AuthService`
- **Description:** Instance of `AuthService` for handling authentication operations.

**`formKey`**
- **Type:** `GlobalKey<FormState>`
- **Description:** Key for the form widget, used for form validation.

**`firstNameController`**
- **Type:** `TextEditingController`
- **Description:** Controls the first name input field.

**`lastNameController`**
- **Type:** `TextEditingController`
- **Description:** Controls the last name input field.

**`emailController`**
- **Type:** `TextEditingController`
- **Description:** Controls the email input field.

**`passwordController`**
- **Type:** `TextEditingController`
- **Description:** Controls the password input field.

**`confirmPasswordController`**
- **Type:** `TextEditingController`
- **Description:** Controls the confirm password input field.

**`_isLoading`**
- **Type:** `bool`
- **Description:** Indicates whether a sign-up operation is in progress.

**`_errorMessage`**
- **Type:** `String?`
- **Description:** Stores any error message that occurs during the sign-up process.

**`_isSignUpSuccessful`**
- **Type:** `bool`
- **Description:** Indicates whether the sign-up process was successful.

## Getters

**`isLoading`**
- **Return Type:** `bool`
- **Description:** Returns the current loading state.

**`errorMessage`**
- **Return Type:** `String?`
- **Description:** Returns the current error message, if any.

**`isSignUpSuccessful`**
- **Return Type:** `bool`
- **Description:** Returns whether the sign-up process was successful.

## Methods

**`setLoading`**
- **Parameters:**
  - `loading` (bool): The new loading state
- **Description:** Updates the loading state and notifies listeners.

**`setSignUpSuccessful`**
- **Parameters:**
  - `isSignUpSuccessful` (bool): The new sign-up success state
- **Description:** Updates the sign-up success state and notifies listeners.

**`setErrorMessage`**
- **Parameters:**
  - `message` (String?): The new error message
- **Description:** Updates the error message and notifies listeners.

**`signUp`**
- **Return Type:** `Future<bool>`
- **Description:** Initiates the sign-up process. Creates a new user, sends a verification email, and handles the result.

**`validateEmail`**
- **Parameters:**
  - `value` (String?): The email input to validate
- **Return Type:** `String?`
- **Description:** Validates the email input. Returns an error message if invalid, null otherwise.

**`validatePassword`**
- **Parameters:**
  - `password` (String?): The password input to validate
- **Return Type:** `String?`
- **Description:** Validates the password input against multiple criteria (length, uppercase, lowercase, digit, special character). Returns error messages if invalid, null otherwise.

**`validateConfirmPassword`**
- **Parameters:**
  - `value` (String?): The confirm password input to validate
- **Return Type:** `String?`
- **Description:** Validates that the confirm password matches the password. Returns an error message if invalid, null otherwise.

**`dispose`**
- **Description:** Disposes of all TextEditingControllers when the view model is no longer needed.

## Usage

This view model is designed to be used with a sign-up screen in a Flutter application. It handles input validation, initiates the sign-up process, and manages the UI state throughout the process.

Example usage in a widget:

```dart
final viewModel = SignUpViewModel(authService);
// ...
TextFormField(
  controller: viewModel.emailController,
  validator: viewModel.validateEmail,
),
TextFormField(
  controller: viewModel.passwordController,
  validator: viewModel.validatePassword,
),
TextFormField(
  controller: viewModel.confirmPasswordController,
  validator: viewModel.validateConfirmPassword,
),
ElevatedButton(
  onPressed: viewModel.isLoading ? null : () async {
    if (await viewModel.signUp()) {
      // Navigate to next screen
    }
  },
  child: Text('Sign Up'),
),
if (viewModel.errorMessage != null)
  Text(viewModel.errorMessage!),
```

The view model should be provided with an instance of `AuthService` when created, and can be used with `ChangeNotifierProvider` for state management in the widget tree.