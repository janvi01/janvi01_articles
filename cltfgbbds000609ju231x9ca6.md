---
title: "var vs let vs const in depth in JavaScript"
datePublished: Wed Mar 06 2024 07:02:08 GMT+0000 (Coordinated Universal Time)
cuid: cltfgbbds000609ju231x9ca6
slug: var-vs-let-vs-const-in-depth-in-javascript
cover: https://cdn.hashnode.com/res/hashnode/image/upload/v1709708454547/17868f49-88cd-4176-9a8c-891bf6f627c6.png
tags: javascript, developer

---

Let's explore how to declare variables in JavaScript and understand the key differences between them.

There are three ways to declare a variable in JavaScript.

1. **var** - The Old-School Way
    
2. **let** - The Block-Scoped Champion
    
3. **const** - For Values That Won't Change
    

Before the release of ES6, variable declarations using `var` were the norm. However, there were problems associated with variables declared using the `var` keyword. This is why new methods of declaring variables were needed. The introduction of `let` and `const` in the ES6 2015 specification has completely transformed the usage of variables, providing advantages over traditional `var` declarations. Let's take a closer look at the key difference between these variable declaration methods.

## Key Differences

1. ### Hoisting:
    
    * **var:** Variables declared with `var` are hoisted to the top of their scope (function or global). This means you can access a `var` variable before its declaration line, but its value will be `undefined`.
        
    * **let & const:** Variables declared with `let` and `const` are also hoisted, but they are not initialized. Accessing them before their declaration line results in a `ReferenceError`.  
        let and const declarations are hoisted. But it's different from var. Let's understand it in depth using an example.
        
        ```javascript
        console.log(a); // ReferenceError: Cannot access 'a' before initialization
        console.log(b); // prints undefined as expected
        let a = 10;
        console.log(a); // 10
        var b = 15;
        console.log(window.a); // undefined as a is not present in window object
        console.log(window.b); // 15
        ```
        
    
    It looks like let isn't hoisted, **but it is**, let's understand how.  
    
    During the hoisting stage, both variable 'a' and variable 'b' are initialized as undefined. However, variable 'b' is stored in the global or window storage space, while variable 'a' is stored in a separate memory object called a script. This means that 'a' can only be accessed after it has been assigned a value. Attempting to access 'a' before it has been assigned a value will throw an error.  
    
    There is a term known as Temporal Dead Zone. It refers to the time between when a let variable is hoisted and when it is initialized with a value.  
    
    Any line of code before the "let a = 10" line in the above example is considered the temporal dead zone for the variable 'a'. This means that since the variable 'a' is not accessible on a global scale, it is also not accessible in the context of window/this also.
    
2. ### Scoping:
    
    * **var:** Function-scoped or globally-scoped (if declared outside any function). This means variables declared with `var` are accessible within the entire function where they are defined (or globally), even if they are declared within blocks like `if` statements or loops.
        
    * **let & const:** Block-scoped. Variables declared with `let` or `const` are only accessible within the block of code where they are defined (e.g., within an `if` statement, `for` loop, or simply enclosed in curly braces `{}`).
        
    
3. ### Reassignment:
    
    * **var:** Variables declared with `var` can be reassigned (changed) at any point.
        
    * **let:** Variables declared with `let` can also be reassigned to a different value.
        
    * **const:** Variables declared with `const` cannot be reassigned after their initialization. An attempt to do so will result in an error.
        
    

## Best Practices: When to Use Which

**Avoid using var (generally):** Due to its less intuitive scoping behavior, it's recommended to avoid using the `var` keyword in modern JavaScript.

**Use const by default:** Whenever you know a variable's value won't change after initialization, declare it using `const`. This enforces immutability and makes your code easier to reason about.

**Use let for reassignments:** If you need to change a variable's value, use `let`. This gives you the flexibility of reassignment while maintaining block scoping.

Thanks for reading! I hope you find this blog post useful. You can connect with me on [**Twitter**](https://twitter.com/janvibajo01) or [**LinkedIn**](https://www.linkedin.com/in/janvi01/). 🚀