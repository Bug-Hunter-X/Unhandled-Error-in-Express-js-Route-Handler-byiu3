# Unhandled Error in Express.js Route Handler

This repository demonstrates a common error in Express.js route handlers: missing error handling for invalid input or missing data. The bug is in the `/users/:id` route, which fails to handle cases where the `userId` parameter is not a number or when no user with that ID exists.

## Bug

The `bug.js` file shows the problematic code.  The route handler attempts to parse the `userId` as an integer and then find a user in the `users` array.  However, if `userId` is not a number, `parseInt(userId)` returns `NaN`, leading to an incorrect search. Further, if no matching user is found, the route doesn't return an appropriate error response.

## Solution

The `bugSolution.js` file shows the corrected code with added error handling.  It checks that `userId` is a number, handles the `NaN` case, and returns a 404 status code when no user is found.