# Unhandled Promise Rejection in Node.js Express Server

This repository demonstrates a common error in Node.js Express applications: unhandled promise rejections.  The `bug.js` file shows an Express server that performs an asynchronous operation without properly handling potential errors. This can lead to unexpected crashes.  The `bugSolution.js` file provides a corrected version with robust error handling.

## Problem

The `doSomethingAsync` function simulates an operation that can fail randomly.  The main server code lacks a proper `catch` block to handle rejections from this promise.  If the promise rejects, the error is unhandled, causing the entire application to crash without informative logs.

## Solution

The solution involves adding comprehensive error handling using a `catch` block within the asynchronous operation's `.then()` chain. This ensures that any errors are caught gracefully, logged, and potentially handled with more sophisticated recovery strategies (such as returning a 500 error to the client).