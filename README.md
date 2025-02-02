# Node.js Server Unresponsiveness Bug

This repository demonstrates a common Node.js issue: server unresponsiveness caused by a long-running synchronous operation within the request handler.  The `bug.js` file contains the problematic code.  The solution, preventing this issue, is presented in `bugSolution.js`.

## Problem

The server uses a `while` loop to simulate a 5-second task. During this time, the server cannot handle new requests, leading to unresponsiveness. This is because Node.js uses a single-threaded event loop.  A long-running synchronous task blocks this loop.

## Solution

The solution involves using asynchronous operations or offloading long-running tasks to worker threads or other processes to prevent blocking the event loop and maintaining server responsiveness.