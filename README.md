# Infinite Render Loop in React Component

This repository demonstrates a common React bug: an infinite render loop caused by a missing dependency in the `useEffect` hook.  The `MyComponent` initially renders correctly, but subsequently enters an infinite loop because the `useEffect` hook is called after every render.

## Bug
The bug is in `bug.js`. The `useEffect` hook lacks the `count` variable in its dependency array.  This causes the effect to run on every render, triggering a state update, which in turn triggers another render, and so on.

## Solution
The solution is provided in `bugSolution.js`. Adding `count` to the dependency array ensures that the `useEffect` hook only runs when the `count` value changes.