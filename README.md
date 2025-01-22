# React 19 useEffect setInterval memory leak
This repository demonstrates a common mistake when using the `useEffect` hook with `setInterval` in React 19, which leads to a memory leak.  The issue arises from failing to properly clean up the interval using the cleanup function returned by `useEffect`.  This results in continuously running intervals after the component unmounts, leading to potential performance degradation and memory leaks.

## Bug Description
The `bug.js` file shows a `MyComponent` that uses `setInterval` within the `useEffect` hook.  Because there is no cleanup function to stop the interval when the component unmounts, the interval continues to run indefinitely causing a memory leak.