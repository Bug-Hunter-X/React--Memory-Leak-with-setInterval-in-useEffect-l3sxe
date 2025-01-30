# React Memory Leak with setInterval in useEffect

This repository demonstrates a common mistake in React applications: using `setInterval` within the `useEffect` hook without providing a cleanup function. This leads to a memory leak because the interval continues to run even after the component is unmounted.

## Bug
The `bug.js` file contains a React component that uses `setInterval` to increment a counter every second. However, it lacks a cleanup function to stop the interval when the component is unmounted.

## Solution
The `bugSolution.js` file provides the corrected version. It uses the return value of `useEffect` to define a cleanup function that calls `clearInterval` to stop the interval before the component is unmounted.

## How to reproduce
1. Clone the repository
2. Run `npm install`
3. Run `npm start`
4. Observe the counter behavior.  In the buggy version, the counter will continue to increase even after navigating away from the page.  The fixed version stops the counter correctly.