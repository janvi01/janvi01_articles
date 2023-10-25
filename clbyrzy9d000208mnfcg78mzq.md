---
title: "What is 'this' JavaScript?"
datePublished: Thu Dec 22 2022 07:42:08 GMT+0000 (Coordinated Universal Time)
cuid: clbyrzy9d000208mnfcg78mzq
slug: what-is-this-javascript
cover: https://cdn.hashnode.com/res/hashnode/image/upload/v1671531311498/ypXDfMOCS.webp
tags: javascript, frontend-development

---

Let's brainstorm on the most confusing thing in JavaScript - **The ‘this’ keyword.**

In this article, we will cover all of the basics you need to know about the JavaScript “this” keyword.

Before that, Let's see...

# What is JavaScript?

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1671694590803/yx4wvZa0K.png align="center")

**JavaScript** is a programming language that allows you to implement complex features on web pages. It is lightweight and most commonly used as a part of web pages, whose implementations allow client-side scripts to interact with the user and make dynamic pages. It is an interpreted programming language with object-oriented capabilities.

It is the third layer of the layer cake of standard web technologies, two of which are [HTML](https://developer.mozilla.org/en-US/docs/Learn/HTML) and [CSS](https://developer.mozilla.org/en-US/docs/Learn/CSS). [HTML](https://developer.mozilla.org/en-US/docs/Glossary/HTML) is the markup language that we use to structure and give meaning to our web content. [CSS](https://developer.mozilla.org/en-US/docs/Glossary/CSS) is a language of style rules that we use to apply styling to our HTML content and [JavaScript](https://developer.mozilla.org/en-US/docs/Glossary/JavaScript) enables you to create dynamically updating content, control multimedia, animate images, and pretty much everything else.

Now let's jump into...

# What is "this" keyword in JavaScript?

In simple terms, *<mark>this</mark>* keyword refers to an object. *(oh, is it this simple right, not at all)*

%[https://media.giphy.com/media/hS6j40PXTMQZhTrjWi/giphy.gif] 

*<mark>this</mark>* keyword refers to an object, but which object?? It depends on how *<mark>this</mark>* is being invoked or called. It also has some differences between [strict mode](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Strict_mode) and non-strict mode.

Let's see how `this` works in different contexts...

## "this" in a function

If the function being referenced is a regular function, `this` referred to the global object or points to the window object in the browser.

Let's see an example -

```javascript
var myName = "Janvi";

function printMe() {
    var myName = "Janvi Bajoria";
    alert("My Name = " + myName); // prints Janvi Bajoria
    alert("My Name = " + this.myName); // prints Janvi
}
printMe();
```

Here, Whenever we access the value of myName without the “this” keyword, it gets the value defined locally within that function. On the other hand, when we try to get the value of myName variable using the “this” keyword, it fetches the value defined outside the function (globally).

## "this" in a method

"this" in a method refers to the **object** that owns the method.

> If you are unaware of what is a **method** in JavaScript, a method is a property of an object that contains a function definition. Basically, Methods are functions stored as object properties.

Let's see an example of how we use "this" in a method -

```javascript
const person = {
  firstName: "Janvi",
  lastName: "Bajoria",
  id: 10,
  fullName : function() {
    return this.firstName + " " + this.lastName;
  }
}
//method call
person.fullName(); //returns Janvi Bajoria
```

Here, the `fullName()` is a function that is the property of `person` object and also the `fullName` is a method of the `person` object. Therefore, inside the `fullName()` function, the `this` references the `person` object.

## **"this"** in Event Handlers

In event handlers, 'this’ refers to the element which fired/received the event.

Let's see an example of how 'this' works in event handlers...

```javascript
<a id="link" href="#" onclick="this.style.color='blue'">click me</a>
```

Here, ‘this’ refers to the anchor tag element.

## "this" in strict mode

In the strict mode, JavaScript sets the `this` inside a function to `undefined` as strict mode doesn't allow default binding.

> To enable the strict mode, you use the directive `"use strict"` at the beginning of the JavaScript file. If you want to apply the strict mode to a specific function only, you place it at the top of the function body.

```javascript
"use strict";

function thisinstrict() {
    console.log(this === undefined);
}

thisinstrict(); // returns true
```

## "this" in arrow functions

In arrow functions, `this` is being set lexically means Arrow functions do not bind their own `this`, instead, they inherit the one from the parent scope where the arrow function is defined, which is called "lexical scoping".

Let's see an example ...

```javascript
let thisinarrowfunction = () => this;
console.log(thisinarrowfunction() === window); // returns true
```

In this example, the `this` value is set to the global object i.e. `window` in the web browser.  
Since the arrow function does not create its execution context, it inherits `this` from the parent scope, Due to this reason...

> This makes arrow functions to be a great choice in some scenarios but a very bad one in others.

Let's see an example of how `this` works in a method using an arrow function...

```javascript
const printMe = {
  name: "Janvi Bajoria",
  displayName: () => {
    return `${this.name} is my name.`;
  },
};
console.log(printMe.displayName());
```

The output is `undefined`...  
  
In the arrow function, `this` has nothing to do with the caller of the function. It refers to the scope where the function (the enclosing context) is present. That’s why we get undefined.

So that was all about the basics of `this` keywords in JavaScript...

Thanks for reading! I hope you find this blog post useful. Please check out my other blog posts [**here**](https://janvi01.hashnode.dev/).

You can connect with me on [**Twitter**](https://twitter.com/janvibajo01) or [**LinkedIn**](https://www.linkedin.com/in/janvi01/).