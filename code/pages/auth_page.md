---
layout: page
---

# **AuthPage**

## **Constructor**
- **Name:** AuthPage
- **Parameters:**
  - `key` (Key?): The widget's key

**What it does:**
AuthPage is a StatelessWidget that serves as an authentication gate in the application. It determines whether to show the home page or the login page based on the user's authentication state.

## **build**
- **Parameters:**
  - `context` (BuildContext): The build context
- **Return type:** Widget

**What it does:**
The build method constructs and returns a Scaffold widget containing a StreamBuilder. This setup allows for real-time updates based on the authentication state:

- It listens to the `FirebaseAuth.instance.authStateChanges()` stream, which emits events whenever the user's sign-in state changes.
- If the snapshot has data (indicating a signed-in user), it returns the HomePage.
- If the snapshot doesn't have data (indicating no signed-in user), it returns the LoginPage.

This approach provides a seamless transition between authenticated and non-authenticated states, automatically routing the user to the appropriate page based on their current authentication status.