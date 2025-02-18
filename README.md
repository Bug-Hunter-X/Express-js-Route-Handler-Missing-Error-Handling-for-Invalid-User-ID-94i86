# Express.js Route Handler Missing Error Handling for Invalid User ID

This repository demonstrates a common error in Express.js route handlers: missing error handling for invalid input. Specifically, the example shows a route that retrieves a user by ID, but fails to handle cases where the ID is not a valid number.

## Bug

The `bug.js` file contains the problematic code.  It attempts to parse the user ID as an integer without validating whether the ID is actually a number.  If the ID is not a number (e.g., a string, a negative number), the `parseInt()` function will return `NaN`, and the subsequent `users.find()` call will not find the user, resulting in a `null` value being assigned to the `user` variable.  The application will then proceed to use the `null` object as if it were a valid user. 

## Solution

The `bugSolution.js` file provides a corrected version of the code.  It adds input validation to ensure the user ID is a valid number before attempting to find the user. This ensures that any error is handled gracefully and that the application does not crash.