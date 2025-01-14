# React UseEffect setInterval Memory Leak

This repository demonstrates a common mistake in React components: using `setInterval` within the `useEffect` hook without proper cleanup.  This leads to memory leaks as the interval continues to run even after the component unmounts.

The `bug.js` file shows the problematic code. The `bugSolution.js` file provides the corrected version.

**Problem:** The `setInterval` function inside the `useEffect` hook lacks a cleanup function to stop the interval when the component unmounts.

**Solution:**  The solution involves using the return value of `useEffect` to provide a cleanup function that calls `clearInterval` to stop the interval before the component is unmounted.