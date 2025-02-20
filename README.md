# React useEffect Infinite Loop Bug

This repository demonstrates a common bug in React applications involving the `useEffect` hook.  The bug arises from a missing dependency array in the `useEffect` call, leading to an infinite loop of re-renders.

## Bug Description

A React component uses `useState` to manage a counter.  The `useEffect` hook logs the current count to the console. However, because the `count` variable is not included in the dependency array for `useEffect`, the effect runs after every render.  This causes `count` to change, triggering another re-render, and so on, resulting in an infinite loop.

## Solution

The solution involves adding `count` to the dependency array. This ensures that the `useEffect` hook only runs when the `count` value changes.