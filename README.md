# Express.js Route Handler Missing Error Handling for Invalid User ID

This repository demonstrates a common error in Express.js route handlers: missing error handling for invalid input.  Specifically, the provided code fails to handle cases where the user ID is not a valid integer, potentially leading to unexpected behavior or application crashes.

## Bug Description

The `bug.js` file contains an Express.js route handler that fetches a user based on their ID. However, it lacks proper error handling. If the `userId` parameter is not a valid integer (e.g., a string or a non-numeric value), `parseInt(userId)` will return `NaN`, leading to a failure in the search and potential errors.

## Solution

The `bugSolution.js` file provides a corrected version of the route handler. It includes checks to ensure that `userId` is a valid number before attempting to parse and use it.

## How to Reproduce the Bug

1. Clone this repository.
2. Run `npm install express` to install the necessary dependency.
3. Run `node bug.js`.
4. Send a request to `/users/abc` (or any non-numeric ID).

## How to fix the Bug

1. Add input validation to your route handlers. Check for the type and value of parameters before using them in your application logic.
2. Handle potential errors gracefully. Return appropriate HTTP status codes (like 400 Bad Request or 422 Unprocessable Entity) with meaningful error messages to inform the client about problems.
3. Always test your code thoroughly, paying attention to edge cases and potential sources of errors.