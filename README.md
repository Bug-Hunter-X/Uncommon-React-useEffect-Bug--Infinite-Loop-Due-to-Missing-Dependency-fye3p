# Uncommon React useEffect Bug: Infinite Loop Due to Missing Dependency

This repository demonstrates a subtle bug related to the React `useEffect` hook.  The issue arises from an incorrectly specified dependency array, leading to an infinite loop.  This is more likely to occur in complex components, making it a tricky bug to identify.

## Bug Description
The provided `MyComponent` uses `useEffect` to log a message to the console. However, the dependency array is missing, causing the effect to re-run on every render, triggering a loop.  This is because the `count` value is updated each time the button is clicked which leads to a re-render that re-runs the effect and the count is again updated.

## Solution
The solution involves correctly specifying the dependencies within the `useEffect` hook's dependency array. Adding `[count]` ensures the effect runs only when the `count` value changes, preventing the infinite loop.