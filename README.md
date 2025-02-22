# React useEffect setInterval Memory Leak

This repository demonstrates a common bug in React applications involving the `useEffect` hook and the `setInterval` function.  The bug causes a memory leak because the interval is not properly cleared when the component unmounts.

## Bug Description
The `MyComponent` uses `setInterval` to update the count every second. However, it fails to include a cleanup function in the `useEffect` hook to stop the interval when the component is unmounted.  This leads to the interval continuing to run even after the component is no longer in the DOM, resulting in a memory leak. 

## Bug Solution
The solution involves adding a return function to the `useEffect` hook that calls `clearInterval` to clear the interval before the component is unmounted.