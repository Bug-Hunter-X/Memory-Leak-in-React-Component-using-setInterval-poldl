# React setInterval Memory Leak
This repository demonstrates a common memory leak in React applications caused by improper use of `setInterval` within a `useEffect` hook.

The `bug.js` file shows the faulty code, while `bugSolution.js` provides the corrected version.

## Problem
The problem lies in the `useEffect` hook.  The `setInterval` function is called every second without a cleanup function, causing a new interval to be created every render. This leads to multiple intervals running simultaneously, consuming memory and potentially causing performance issues.

## Solution
The solution involves returning a cleanup function from the `useEffect` hook. This function clears the interval when the component unmounts or when the dependencies change, preventing memory leaks.

## How to reproduce
1. Clone the repository.
2. Run `npm install` to install dependencies.
3. Run `npm start` to start the development server.
4. Observe the increasing counter and verify the problem.
5. Run the corrected solution and verify that the memory leak is resolved.