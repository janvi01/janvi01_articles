---
title: "How the JavaScript code is executed?"
datePublished: Wed Dec 20 2023 07:15:22 GMT+0000 (Coordinated Universal Time)
cuid: clqdfvqud000g08ky1horauc0
slug: how-the-javascript-code-is-executed
cover: https://cdn.hashnode.com/res/hashnode/image/upload/v1703056455530/5cd7c3f4-c217-4a0d-8a68-8e4c178bb92a.png
tags: javascript, web-development

---

Do you know? When you run a JavaScript program there are a lot of things happening behind the scenes inside the JavaScript engine. In this article, I'll demystify the process and shed light on how the JavaScript code is executed inside **Execution Context** – the fundamental environment in which JavaScript code operates.

<mark>"Everything in JavaScript happens inside an Execution Context"</mark>

Now you must be wondering what this execution context is. Let's deep dive into this.

## Execution context

In JavaScript, the term "**Execution Context**" refers to the environment in which a piece of code is executed. It consists of variables, functions, and the scope chain, which determines the accessibility of variables and functions.

There are three types of execution contexts in JavaScript:

1. **Global Execution Context -** The default or outermost execution context that is associated with the entire script and contains global variables and functions.
    
2. **Function Execution Context -** It is created every time a function is invoked.
    
3. **Eval** **Execution Context -** It is created when code is executed inside the `eval` function.
    

## What happens when you run a JavaScript program?

A global execution context is created. The execution context is created in two phases.

* **Memory Creation Phase** - JavaScript will allocate memory to variables and functions.
    
* **Code Execution Phase**
    

Let's consider a code snippet and its code execution steps:

```javascript
var x = 10;

function multiplyByTwo(value) {
  var result = value * 2;
  return result;
}

var y = multiplyByTwo(x);
var z = multiplyByTwo(5);
```

The above JavaScript code example defines a variable `x`. It also defines a function `multiplyByTwo` that takes a parameter, multiplies it by 2, and returns the result. The function is then called with `x` and `5` as arguments, and the results are stored in variables `y` and `z`. Now let's understand its code execution steps.

The very first thing that JavaScript does is the **Memory Creation Phase**, so it goes to line one of the above code snippets, allocates memory space for the variable `x`, and then goes to line two, and allocates memory space for the function `multiplyByTwo`. When allocating memory for `x` , it stores `undefined`, a special value for `x`. For `multiplyByTwo`, it stores the whole code of the function inside its memory space. Then, as `y` and `z` are variables as well, it allocates memory and stores `undefined` for them, and this is the end of the first phase which is the memory creation phase.

Now, let's see what the execution context diagram would look like.

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1703055650168/45740339-be10-4c16-9bde-f8cf9eff4a18.jpeg align="center")

Now, the second phase is the **Code Execution Phase**, it starts going through the whole code line by line. As it encounters `var x = 10`, it assigns 10 to `x`. Until now, the value of `x` was `undefined`. For function, there is nothing to execute. These lines were already dealt with during the memory creation phase.

Coming to line `var y = multiplyByTwo(x)` , a new execution context is created altogether. Again in this new execution context, in the memory creation phase, we allocate memory to `value` and `result` , the two variables and the value `undefined` is placed in them. Now, in the code execution phase of this execution context, the first value 10 is assigned to `value`. Then `var result = value * 2` will store 20 in `result`. After that, `return result` return the control of the program to where this function was invoked from.

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1703055664984/234d1c34-73d1-40b3-acad-73e589d61ad5.jpeg align="center")

When the **return** keyword is encountered, it returns the control to the called line, and also the function execution context is deleted. The same thing will be repeated for the `variable z` and then after the code execution is finished, the global execution context will be destroyed.

This is how the JavaScript code is executed step by step.

JavaScript utilizes the **Call Stack** to manage the creation and removal of execution contexts during code execution. The Call Stack serves as a crucial mechanism for tracking the script's position when calling multiple functions.

This stack method preserves the sequential order of execution contexts and goes by various names such as Program Stack, Control Stack, Runtime Stack, Machine Stack, and Execution Context Stack.

## Conclusion

In summary, when you run a JavaScript program, it operates within environments called Execution Context.

The program's execution involves two phases: Memory Creation, where space is allocated for variables and functions, and Code Execution, where the actual code is processed. The Call Stack plays a crucial role in managing these contexts, ensuring a step-by-step execution order.

Thanks for reading! I hope you find this blog post useful. You can connect with me on [**Twitter**](https://twitter.com/janvibajo01) or [**LinkedIn**](https://www.linkedin.com/in/janvi01/). 🚀