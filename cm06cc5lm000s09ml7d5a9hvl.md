---
title: "Optimize performance using useMemo"
datePublished: Fri Aug 23 2024 06:38:49 GMT+0000 (Coordinated Universal Time)
cuid: cm06cc5lm000s09ml7d5a9hvl
slug: optimize-performance-using-usememo
cover: https://cdn.hashnode.com/res/hashnode/image/upload/v1724395063900/d019fb58-207a-415c-b539-ebe00cc9dca5.png
tags: javascript, reactjs

---

Hey everyone!

This article will help you learn how to improve your web app's performance to make it run seamlessly.

What will we cover below?

* purpose of `useMemo`
    
* Basic syntax and examples of `useMemo`
    
* How `useMemo` helps in optimizing performance
    
* Misusing and Debugging common issues with `useMemo`
    
* How it is different from `useCallback`?
    

### What is useMemo?

According to [react.dev](http://react.dev), `useMemo` is a React Hook that lets you cache the result of a calculation between re-renders.

In simple words, `useMemo` is a React Hook that stores the result of a function call and reuses it when the function's dependencies haven't changed, rather than recalculating the value on every render.

It helps optimize performance but sometimes it may be overlooked or misunderstood if not properly used.

For example, imagine a React component in your app with a function that calculates a heavy algorithm. Normally, React recalculates this function every time it renders the component, even if the input, variable, state, or anything related to that function remains the same which may cause hindrance to your app and slow down the performance and it may not work seamlessly.

### Syntax and Examples

Below is the syntax of the useMemo React hook -

`const memoizedValue = useMemo(calculations, [dependencies])`

Let's see an example:

```javascript
import React, { useState, useMemo } from "react";

const DemoComponent = () => {
  const [count, setCount] = useState(0);
  const [input, setInput] = useState("");

  // expensive calculation function
  const expensiveCalculation = (num) => {
    for (let i = 0; i < 1000000000; i++) {}
    return num * 2;
  };

  // Memoize the result of the expensive calculation using its dependency count
  const memoizedValue = useMemo(() => expensiveCalculation(count), [count]);

  return (
    <div>
      <h1>useMemo Example</h1>
      <div>
        <button onClick={() => setCount(count + 1)}>Increment Count</button>
        <p>Count: {count}</p>
        <p>Memoized Value: {memoizedValue}</p>
      </div>
      <div>
        <input
          type="text"
          value={input}
          onChange={(e) => setInput(e.target.value)}
          placeholder="Type something..."
        />
        <p>Input: {input}</p>
      </div>
    </div>
  );
};

export default ExpensiveCalculationComponent;
```

### How `useMemo` helps in optimizing performance?

In the example above, there is a function `expensiveCalculation` that simulates a heavy computation. It loops a billion times and then returns twice the input number (`num`). `useMemo` has a dependency `[count]`, so the memoized value will only be recomputed when `count` changes even if the component re-renders.

Typing in the input field updates the `input` state and triggers a re-render, but it does not trigger the expensive calculation, demonstrating the efficiency of `useMemo`.

This simply gives you an edge in rendering components faster even if it has expensive or heavy algorithms written inside it. This can drastically improve your app's performance.

### Misusing and Debugging common issues with `useMemo`

* These hooks should only be used if you want to memoize expensive calculations or prevent unnecessary re-renders, not everywhere. Memoizing lightweight or simple computations doesn’t give a noticeable performance benefit and adds unnecessary complexity to your code.
    
* A common mistake is to either provide an incorrect dependency array or to omit it entirely. If the dependency array is incorrect, the memoized value may not update when it should, leading to stale or incorrect data.
    
* The `useMemo` hook should not be used for side effects, as it’s intended to memoize a value, not to perform side effects.
    

### How it is different from `useCallback`?

| **Aspect** | `useMemo` | `useCallback` |
| --- | --- | --- |
| **Purpose** | Caches the result of a function. | Caches the function itself. |
| **Use Case** | Avoids recalculating a value unless dependencies change (e.g., expensive computations). | Prevents a function from being recreated unless dependencies change (e.g., passing stable functions to child components). |
| **Return Value** | Returns the cached result of the function. | Returns the cached function itself. |
| **When to Use** | When you have a heavy computation that shouldn’t run on every render. | When you want to pass a stable function to a child component to avoid unnecessary re-renders. |