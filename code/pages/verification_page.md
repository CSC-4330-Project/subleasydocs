---
layout: page
---

# **VerificationPage**

## **Constructor**
- **Name:** VerificationPage
- **Parameters:**
  - `key` (Key?): The widget's key

**What it does:**
VerificationPage is a StatelessWidget that sets up the ChangeNotifierProvider for the VerificationViewModel and renders the _VerificationPageContent.

## **build**
- **Parameters:**
  - `context` (BuildContext): The build context
- **Return type:** Widget

**What it does:**
Creates a ChangeNotifierProvider with VerificationViewModel and returns _VerificationPageContent as its child.

# **_VerificationPageContent**

**What it does:**
_VerificationPageContent is a StatefulWidget that represents the main content of the email verification screen.

## **createState**
- **Return type:** _VerificationPageContentState

**What it does:**
Creates the mutable state for the _VerificationPageContent widget.

# **_VerificationPageContentState**

**What it does:**
Manages the state and UI for the email verification screen, including sending verification emails and checking verification status.

## **initState**
**What it does:**
Initializes the state of the widget. Sends a verification email and starts periodic checking for email verification.

## **_sendVerificationEmailAndStartChecking**
- **Return type:** void

**What it does:**
Sends a verification email and starts the periodic check for email verification.

## **_startPeriodicCheck**
- **Return type:** void

**What it does:**
Starts a timer that periodically checks if the email has been verified. If verified, cancels the timer and navigates to the home screen.

## **dispose**
**What it does:**
Cancels the timer when the widget is removed from the widget tree.

## **_navigateToHomeScreen**
- **Return type:** void

**What it does:**
Navigates to the HomePage and removes all previous routes from the navigation stack.

## **build**
- **Parameters:**
  - `context` (BuildContext): The build context
- **Return type:** Widget

**What it does:**
Constructs the UI for the email verification screen. It includes:
- A gradient background
- An email icon
- Verification instructions
- A button to resend the verification email
- Error message display (if any)
- Loading indicator when processing

The build method uses the VerificationViewModel to manage the state and handle user interactions. It also prevents the user from navigating back from this screen and automatically navigates to the home screen once the email is verified.