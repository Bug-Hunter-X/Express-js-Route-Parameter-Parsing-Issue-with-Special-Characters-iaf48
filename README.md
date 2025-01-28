# Express.js Route Parameter Parsing Issue

This repository demonstrates a bug in Express.js route parameter parsing where special characters in parameters are not handled correctly.  The bug occurs when attempting to access a route with parameters containing characters like '+' or '%'.  These characters are often part of URL-encoded data and their incorrect parsing leads to errors or unexpected behavior.

## Bug Description

The `/users/:id` route incorrectly handles parameters containing special characters, causing a 404 error or other unexpected behaviors.  The solution uses the `decodeURIComponent` function to properly decode the URL-encoded parameter before using it.

## Solution

The solution involves using `decodeURIComponent` to correctly decode URL-encoded parameters before using them in your code. This ensures that special characters are handled correctly, resolving the parsing issue.

## How to Reproduce

1. Clone this repository.
2. Install dependencies: `npm install`.
3. Run the server: `node bug.js`.
4. Attempt to access a route with a parameter containing special characters, such as `/users/+123` or `/users/%2B123`.  Observe the error.
5. Run the corrected version: `node bugSolution.js` and test with the same parameters. The corrected version should correctly handle special characters.
