# JavaScript Closure Issue in setTimeout Loop

This example demonstrates a common issue in JavaScript related to closures and the `setTimeout` function within loops.  The expected output is to print numbers 0 through 9 sequentially.  However, due to how closures work in JavaScript, the output will be 10, 10, 10,... 10 (ten times). This is because the closure captures the *final* value of `i` (which is 10 after the loop completes) rather than the value of `i` at the time `setTimeout` is called.

## How to Reproduce
1. Copy and paste `bug.js` in a file.
2. Execute the script using a JavaScript engine (Node.js for example): `node bug.js`
3. Observe that the script outputs 10 ten times instead of the expected 0 to 9.

## Solution
The solution involves using `let` within the loop and creating an IIFE for each iteration, thus providing correct values for `i`.
