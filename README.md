# React Native useRef Hook Error: Cannot access a disposed object

This repository demonstrates a common error encountered when using the `useRef` hook in React Native: attempting to access a ref's current value after the component has unmounted.  This often manifests as a `Cannot access a disposed object` error.

## Problem
The provided `bug.js` file shows a component that uses `useRef` to manage a TextInput.  An asynchronous operation (simulated by `setTimeout`) attempts to focus the input after a delay.  If the user navigates away from this component before the timeout completes, the ref's `current` value is accessed after the component is unmounted, leading to the error.

## Solution
The `bugSolution.js` file demonstrates a solution using the `useIsFocused` hook (or similar logic) to check if the component is still mounted before accessing the ref.  This prevents the error by ensuring that the ref's current value is only accessed when the component is active.

This solution ensures that the `focus()` method is only called if the component is still mounted, thus resolving the "Cannot access a disposed object" error.