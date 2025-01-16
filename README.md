# JavaScript Bug: Loose Comparison with null and undefined

This repository demonstrates a common JavaScript bug involving loose comparison (==) with null and undefined. The issue arises when using == instead of === in conditional statements that handle null and undefined values.

## Bug Description

The `foo` function intends to return 0 if the input `x` is null and `x + 1` otherwise.  However, due to the loose comparison (`==`), `undefined` is also treated as falsy and evaluates to 0, leading to an unexpected NaN result when undefined is passed.

## How to Reproduce

1. Clone this repository.
2. Run `bug.js`. You'll observe that `foo(null)` returns 0, but `foo(undefined)` returns NaN because the addition of `undefined + 1` results in NaN.

## Solution

The `bugSolution.js` file demonstrates how to fix this issue using strict equality (`===`).  The strict equality ensures that only null values are evaluated as 0. 

## Lesson Learned

Always use strict equality (`===`) when comparing values in JavaScript to avoid unexpected behavior with null and undefined.