# Node.js Server Unresponsiveness

This repository demonstrates a common Node.js issue: server unresponsiveness caused by a long-running synchronous operation that blocks the event loop.  The `bug.js` file contains the problematic code, while `bugSolution.js` provides a solution using asynchronous operations.

## Problem

The server in `bug.js` uses a `while` loop to simulate a long-running task. This blocks the event loop, preventing Node.js from handling other requests and leading to unresponsiveness.  You can observe this by making multiple requests to the server; only the first will be processed within a reasonable time.

## Solution

The solution in `bugSolution.js` demonstrates using asynchronous operations (e.g., `setTimeout`) to avoid blocking the event loop.  This allows the server to remain responsive even during long-running tasks.

## How to Run

1. Clone this repository.
2. Run `node bug.js` and `node bugSolution.js` separately to observe the difference in behavior.