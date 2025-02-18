# React useEffect bug: Count always 0

This repository demonstrates a common bug in React's `useEffect` hook where the count variable is always 0, even though it's supposed to update. The issue stems from the useEffect's dependency array not including the `count` state variable.  This causes the effect to run on every render, making the count ineffective.

## Bug Description

The provided `MyComponent` uses `useState` to track a count. An `useEffect` hook attempts to log the count after every render; however, the log always shows 0.  This happens because the `useEffect` hook lacks a dependency array, causing it to run on every render, including the initial render where `count` is 0.  The effect then logs the value before `count` is updated, leading to the issue.