# JavaScript Closure Issue in setTimeout Loop

This repository demonstrates a common JavaScript closure issue encountered when using `setTimeout` within a loop.  The expected behavior is to print numbers 0 through 9 with a one-second delay between each.  However, due to the way closures work in JavaScript, the loop completes before the `setTimeout` callbacks execute, resulting in all callbacks logging the final value of `i` (which is 10). 

**To Reproduce:** Clone this repository and run `bug.js`. Observe that the output is '10' printed ten times.

**Solution:** The `bugSolution.js` file provides a corrected version using an immediately invoked function expression (IIFE) to create a new scope for each iteration of the loop, preserving the correct value of `i` within each callback.