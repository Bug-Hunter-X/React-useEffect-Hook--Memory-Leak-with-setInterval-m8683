# React useEffect Hook: Memory Leak with setInterval

This example demonstrates a common mistake when using the `useEffect` hook with `setInterval` in React.  Forgetting to clear the interval in the cleanup function leads to memory leaks and potential unexpected behavior.

The `bug.js` file contains the buggy code.  The `bugSolution.js` file provides the corrected version, showing how to properly handle the cleanup of the interval.

## Bug
The bug is that the `setInterval` is not properly cleared in the `useEffect` cleanup function. This means that even after the component unmounts, the interval continues to run, leading to potential memory leaks and unnecessary computations.

## Solution
The solution involves adding a cleanup function to the `useEffect` hook that uses `clearInterval` to stop the interval when the component unmounts or when the dependencies change.