# React useEffect Hook with setInterval Memory Leak
This repository demonstrates a common mistake when using the `useEffect` hook with `setInterval` in React. Forgetting to return a cleanup function from the `useEffect` hook leads to memory leaks, as the interval continues to run even after the component unmounts.

## Bug Description
The bug lies in the `MyComponent` function's `useEffect` hook. The `setInterval` function is used to update the count state every second.  However, there's no cleanup function returned from `useEffect` to stop the interval when the component unmounts. This results in the interval continuing indefinitely, consuming resources even after the component is no longer needed.

## Solution
The solution involves returning a cleanup function from `useEffect`. This cleanup function will use `clearInterval` to stop the interval when the component is unmounted, preventing the memory leak.