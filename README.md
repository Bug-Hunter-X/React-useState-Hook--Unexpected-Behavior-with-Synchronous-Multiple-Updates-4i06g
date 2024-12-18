# React useState Hook: Unexpected Behavior with Synchronous Multiple Updates

This repository demonstrates a subtle bug in React applications related to the `useState` hook when updating state multiple times synchronously within a single event handler.  The issue stems from how React batches state updates.  Calling `setCount` twice in quick succession may result in one or more updates being missed or having unexpected results.

## Bug Description

The `bug.js` file contains a component that increments a counter using `useState`. The `handleClick` function attempts to increment the counter by 2 using two consecutive calls to `setCount`. However, only one increment might be reflected in the UI, or the updates might be applied in an unpredictable manner. This is because React often batches state updates for performance reasons.

## Solution

The `bugSolution.js` file shows a corrected implementation. Instead of making multiple calls to `setCount`, we utilize a functional update pattern. This ensures that the update always uses the most recent state value.

## How to Reproduce the Bug

1. Clone the repository.
2. Navigate to the `bug` directory.
3. Run `npm install`.
4. Run `npm start`. 
5. Click the "Increment" button. Observe the output console, the counter value may not always increase by 2.

## How to run the Solution

1. Clone the repository.
2. Navigate to the `bugSolution` directory.
3. Run `npm install`.
4. Run `npm start`. 
5. Click the "Increment" button. Observe that the counter reliably increases by 2 every time.