# Node.js Server Hang
This repository demonstrates a common issue in Node.js where a long-running synchronous operation in a request handler can cause the server to hang, not responding to further requests.  The `server.js` file contains the buggy code, and `serverSolution.js` provides a solution using asynchronous operations.

## Bug
The `server.js` file uses a `while` loop to simulate a 5-second delay in processing each request. This blocks the event loop, preventing Node.js from handling other requests.  This results in the server becoming unresponsive.  The error is not immediately obvious; it will manifest itself as unresponsiveness of the server.

## Solution
The `serverSolution.js` file demonstrates how to solve this using asynchronous techniques. Instead of a synchronous `while` loop, we can use `setTimeout` to handle the delay asynchronously, allowing the event loop to continue processing other requests.