# AuthService Class Documentation

The `AuthService` class provides authentication functionality for a Flutter application using Firebase Authentication and Firestore. Below is a detailed documentation of its methods:

## signUp

**Function Name:** signUp
**Parameters:**
- user (Users): An object of the Users class containing user information

**Return Type:** Future<UserCredential>

**Description:** 
This function signs up a new user with email and password. It creates a new user account in Firebase Authentication and stores additional user data in Firestore.

## storeUserData

**Function Name:** storeUserData
**Parameters:**
- userID (String): The unique identifier of the user
- user (Users): An object of the Users class containing user information

**Return Type:** Future<void>

**Description:** 
This function stores additional user data in Firestore after successful authentication.

## signIn

**Function Name:** signIn
**Parameters:**
- email (String): The user's email address
- password (String): The user's password

**Return Type:** Future<UserCredential>

**Description:** 
This function signs in an existing user with their email and password.

## sendUserVerificationEmail

**Function Name:** sendUserVerificationEmail
**Parameters:** None

**Return Type:** Future<bool>

**Description:** 
This function sends a verification email to the current user's email address.

## signOut

**Function Name:** signOut
**Parameters:** None

**Return Type:** Future<void>

**Description:** 
This function signs out the current user.

## getCurrentUser

**Function Name:** getCurrentUser
**Parameters:** None

**Return Type:** User?

**Description:** 
This function returns the currently signed-in user or null if no user is signed in.

## sendPasswordResetEmail

**Function Name:** sendPasswordResetEmail
**Parameters:**
- email (String): The email address of the user requesting a password reset

**Return Type:** Future<void>

**Description:** 
This function sends a password reset email to the specified email address.

## handleFirebaseAuthException

**Function Name:** handleFirebaseAuthException
**Parameters:**
- e (FirebaseAuthException): The Firebase authentication exception to handle

**Return Type:** String

**Description:** 
This function handles various Firebase authentication exceptions and returns appropriate error messages.