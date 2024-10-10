## **Constructor**
- **Name:** LoginPage
- **Parameters:**
  - `key` (Key?): The widget's key

**What it does:**
LoginPage is a StatelessWidget that sets up the ChangeNotifierProvider for the LoginViewModel and renders the _LoginPageContent.

## **build**
- **Parameters:**
  - `context` (BuildContext): The build context
- **Return type:** Widget

**What it does:**
Creates a ChangeNotifierProvider with LoginViewModel and returns _LoginPageContent as its child.

# **_LoginPageContent**

**What it does:**
_LoginPageContent is a StatefulWidget that represents the main content of the login screen.

## **createState**
- **Return type:** _LoginPageContentState

**What it does:**
Creates the mutable state for the _LoginPageContent widget.

# **_LoginPageContentState**

**What it does:**
Manages the state and UI for the login screen, including animations and user interactions.

## **initState**
**What it does:**
Initializes the state of the widget. Sets up fade-in and slide animations for the content. Configures success and failure callbacks for sign-in attempts.

## **dispose**
**What it does:**
Cleans up resources when the widget is removed from the widget tree.

## **_navigateToForgotPassword**
- **Parameters:**
  - `context` (BuildContext): The build context
- **Return type:** void

**What it does:**
Navigates to the ForgotPassword screen.

## **_navigateToSignUp**
- **Parameters:**
  - `context` (BuildContext): The build context
- **Return type:** void

**What it does:**
Navigates to the SignUpPage screen.

## **build**
- **Parameters:**
  - `context` (BuildContext): The build context
- **Return type:** Widget

**What it does:**
Constructs the UI for the login screen. It includes:
- A gradient background
- An app logo
- Welcome text
- Email and password input fields
- Forgot password link
- Sign in button
- Sign up link
The build method uses the LoginViewModel to manage the state and handle user interactions. It also implements fade-in and slide animations for a smoother user experience.

## **_buildTextField**
- **Parameters:**
  - `controller` (TextEditingController): The controller for the text field
  - `hintText` (String): The placeholder text for the field
  - `obscureText` (bool): Whether to hide the input (for passwords)
  - `validator` (Function?): Optional validator function
- **Return type:** Widget

**What it does:**
Creates a custom text field with animation effects.

## **_buildSignInButton**
- **Parameters:**
  - `viewModel` (LoginViewModel): The current LoginViewModel instance
- **Return type:** Widget

**What it does:**
Creates an animated sign-in button that switches to a loading indicator when processing.