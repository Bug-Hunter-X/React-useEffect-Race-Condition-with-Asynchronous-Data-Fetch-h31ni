# React useEffect Race Condition

This repository demonstrates a common race condition in React applications involving asynchronous data fetching and the `useEffect` hook.  The issue arises when a component unmounts before an asynchronous operation completes, leading to potential warnings or errors.

## Problem

The `bug.js` file contains a React component that fetches data asynchronously. If the component is unmounted before the data arrives, the state update triggered by the `useEffect` hook might still occur, causing React to issue a warning about updating an unmounted component.

## Solution

The `bugSolution.js` file demonstrates a solution using a cleanup function within the `useEffect` hook. This function ensures that any pending asynchronous operations are cancelled when the component unmounts, preventing the race condition. The solution also includes improved error handling, demonstrating better practices in dealing with potential fetch failures.