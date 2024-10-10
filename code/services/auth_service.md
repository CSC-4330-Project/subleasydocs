---
layout: page
---

## Class: AuthService

#### Methods:

1. `signUp`
   - Parameters:
     - `email` (String): User's email address
     - `password` (String): User's password
     - `firstName` (String): User's first name
     - `lastName` (String): User's last name
   - Returns: `Future<UserCredential>`
   - Description: Creates a new user account with the provided email and password, then stores additional user information in Firestore.

2. `storeUserData`
   - Parameters:
     - `userID` (String): The unique identifier for the user
     - `firstName` (String): User's first name
     - `lastName` (String): User's last name
     - `email` (String): User's email address
   - Returns: `Future<void>`
   - Description: Stores the user's information in the Firestore 'users' collection.

3. `signIn`
   - Parameters:
     - `email` (String): User's email address
     - `password` (String): User's password
   - Returns: `Future<UserCredential>`
   - Description: Signs in a user with the provided email and password.

4. `sendUserVerificationEmail`
   - Parameters: None
   - Returns: `Future<bool>`
   - Description: Sends a verification email to the currently signed-in user.

5. `signOut`
   - Parameters: None
   - Returns: `Future<void>`
   - Description: Signs out the current user.

6. `getCurrentUser`
   - Parameters: None
   - Returns: `User?`
   - Description: Returns the currently signed-in user or null if no user is signed in.

7. `sendPasswordResetEmail`
   - Parameters:
     - `email` (String): The email address to send the password reset link to
   - Returns: `Future<void>`
   - Description: Sends a password reset email to the specified email address.

8. `handleFirebaseAuthException`
   - Parameters:
     - `e` (FirebaseAuthException): The exception thrown by Firebase Authentication
   - Returns: `String`
   - Description: Translates Firebase Auth exceptions into user-friendly error messages.
