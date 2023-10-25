---
title: "Asynchronous JavaScript"
datePublished: Tue Jun 27 2023 10:11:53 GMT+0000 (Coordinated Universal Time)
cuid: clje4otpp000i09jl6t5iblla
slug: asynchronous-javascript
cover: https://cdn.hashnode.com/res/hashnode/image/upload/v1687860623421/96808fed-b58f-4d68-a802-a171b45ef09b.png
tags: javascript, development

---

Let's start this article by diving deep into what JavaScript is...

### What is JavaScript?

In general, JavaScript (JS) is a programming language used to make websites and applications dynamic and interactive.

Talking conceptually, below is the definition to understand -

> JavaScript is a synchronous, blocking, and single-threaded programming language with lots of flexibility and the ability to convert itself into asynchronous mode.

To avoid any confusion, let's see the brief explanation of the main words mentioned in the definition.

* **Synchronous** - Synchronous means to be in a sequence, i.e. every statement of the javascript code gets executed one by one. So, a statement has to wait for the earlier statement to get executed.
    
* **Blocking** - It means no matter how long a previous process takes, the subsequent processes won't kick off until the former is completed in JavaScript.
    
* **Single-threaded** - A thread is simply a process that your JavaScript program can use to run a task and each thread can do only one task at a time. JavaScript has just one thread called the main thread for executing any code.
    

Let's understand synchronous code with an example -

```javascript
function A(){
   console.log('A')
}
function B(){
   console.log('B')
}
A()
B()

/*The above code executes top-down with only one line executing 
at any given time i.e. it logs function A and then B.*/
```

If you think this is what JavaScript is all about, it is not.

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1687762356953/0120723a-7592-4366-9b50-2c0f989dcbf1.png align="center")

*image inspired from:* [*https://www.freecodecamp.org/news/synchronous-vs-asynchronous-in-javascript/*](https://www.freecodecamp.org/news/synchronous-vs-asynchronous-in-javascript/)

The question is how do we cater to **asynchronous programming** in JavaScript?

Well, as it turns out just JavaScript is not enough to achieve that. We need new pieces outside of JavaScript to help us write asynchronous code which is where web browsers come into play.

Web Browsers define functions and APIs that allow us to register functions that should not be executed synchronously, and should instead be invoked asynchronously when some event occurs.

For example - this could be the passage of time (setTimeout or setInterval), the user's interaction with the mouse (addEventListener, the arrival of data over the network (callbacks, promises), etc.

Let's understand asynchronous code with an example

```javascript
console.log('One');
setTimeout(() => console.log('Two'), 100);
console.log('Three');
// The above code logs: 'One', 'Three', 'Two'
```

We can let our code do several things simultaneously without stopping or blocking the main thread.

This was all about Asynchronous JavaScript. Stay tuned for my upcoming article simplifying timeout and intervals in Asynchronous JavaScript.

Thanks for reading! I hope you find this blog post useful. You can connect with me on [**Twitter**](https://twitter.com/janvibajo01) or [**LinkedIn**](https://www.linkedin.com/in/janvi01/).