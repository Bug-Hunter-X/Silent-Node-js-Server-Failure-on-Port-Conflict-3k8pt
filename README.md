# Silent Node.js Server Failure on Port Conflict

This repository demonstrates a subtle bug in a Node.js HTTP server where failure to start due to a port conflict goes unnoticed without careful error handling.  The default `server.listen()` method doesn't provide robust feedback when the target port is unavailable.

## Bug
The provided `bug.js` file contains a basic HTTP server. If you run this server and attempt to start another server on the same port (8080 in this case), the second server will likely start without any obvious error messages indicating the conflict. This can lead to debugging challenges.

## Solution
The `bugSolution.js` file illustrates how to enhance the error handling to explicitly check for port binding issues and provide more informative error messages. This improves the robustness and debuggability of the server.

## How to reproduce
1. Clone the repository.
2. Run `bug.js`.
3. Try to run `bug.js` again in a separate terminal.  Note the lack of clear error reporting.
4. Run `bugSolution.js`. Attempt to run `bugSolution.js` again, noticing the improved error message.