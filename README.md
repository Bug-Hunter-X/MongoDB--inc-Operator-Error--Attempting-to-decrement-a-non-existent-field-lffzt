# MongoDB $inc Operator Error: Decrementing a Non-Existent Field

This repository demonstrates a common error when using the `$inc` operator in MongoDB: attempting to decrement a field that does not yet exist.  The `$inc` operator is designed to increment (or decrement) numeric fields.  If the field doesn't exist, it throws an error rather than creating it.

## The Problem
The provided `bug.js` file contains code that attempts to decrement a counter field using `$inc`.  If the counter field is not present, MongoDB returns an error.

## The Solution
The `bugSolution.js` file offers a solution by using the `$setOnInsert` operator in conjunction with `$inc`. This ensures that the field is created with an initial value if it doesn't already exist, and then it proceeds with increment/decrement.