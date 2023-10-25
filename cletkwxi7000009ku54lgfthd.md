---
title: "Unlocking the Power of Maps, Filters, and Reduces in JavaScript"
seoDescription: "This article explores the power of JavaScript's array functions - maps, filters, and reduces."
datePublished: Sat Mar 04 2023 06:24:06 GMT+0000 (Coordinated Universal Time)
cuid: cletkwxi7000009ku54lgfthd
slug: maps-filters-and-reduces-in-javascript
cover: https://cdn.hashnode.com/res/hashnode/image/upload/v1677668527204/b92950ff-b41c-4f00-9ca5-1e3adf4b3b43.png
tags: javascript, web-development, wemakedevs

---

If you're a JavaScript enthusiast, you've probably encountered the terms `maps`, `filters`, and `reduce` in your projects and coding endeavors.

In this article, we'll explore the different array functions that JavaScript provides us. We will discover how these methods can help you build better applications and create more efficient code. Learn how to use maps and filters to quickly filter out elements and apply transformations, and how to use reduce to reduce your array elements to a single value.

## Map

The map() method creates a new array with the results of calling a provided function on every element in the calling array. It is used to transform an array into a new array of the same size, where each element is the result of the callback function.

The callback function is invoked with three arguments: - The value of the element - The index of the element - The array object being traversed. It returns a new array and does not modify the original array.

Let's see two examples of how the map works...

```javascript
const numbers = [1, 4, 9];
const doubled = numbers.map(num => num * 2);
console.log(doubled); // [2, 8, 18]
```

```javascript
const users = [
  { name: "John", age: 20 },
  { name: "Jane", age: 30 },
  { name: "Bob", age: 40 },
];
const names = users.map(user => { return `${user.name} is ${user.age} years old`; });
console.log(names); // // ['John is 20 years old', 'Jane is 30 years old', 'Bob is 40 years old']
```

## Filter

The filter() method is used when we want to filter each array element based on certain conditions or criteria.

This code takes each element in an array and applies a conditional statement to it. If the statement evaluates to true, the element is added to a new array; if false, the element is removed from the new array.

> Note: The filter() function does not execute the provided function for empty elements.

Here's an example of the filter() method in action:

```javascript
const numbers = [2, 5, 6, 10, 15];
const result = numbers.filter(item => item % 5 === 0);
console.log(evens); // [5, 10, 15]
```

Here, we have filtered out the array elements that are not divisible by 5, thus resulting in a new array having elements that are divisible by 5.

The filter() method is often used in conjunction with the map() method. This combination allows us to quickly and easily filter an array and then transform it into a new array with the desired results.

For example - we could use the filter() method to filter out all array elements that are not divisible by 5 and then use the map() method to double each element in the new array.

## Reduce

The reduce() method can be used to reduce the elements of an array to a single value. This is done by implementing a specified reducer function on array elements.

The first time that the callback is run there is no "return value of the previous calculation". If supplied, an initial value may be used in its place. Otherwise, the array element at index 0 is used as the initial value and iteration starts from the next element (index 1 instead of index 0).

Using a reduce function is an alternative to looping and incrementally updating a result for every element that is scanned.

Here is an example of the reduce() method in action:

```javascript
const numbers = [1, 2, 3, 4, 5];
const sum = numbers.reduce((prev, curr) => { return prev + curr; }, 0);
console.log(sum); // 15
```

In this example, The reduce function takes two arguments: an accumulator (acc) and a current value (curr). The prev stores the previously returned value, while the current value is the current element being processed in the array. The initial value is set to 0. The reduce() method iterates through the array and for each element, it adds the current element to the prev and stores the result in the prev itself. Once the loop is complete, we will get the sum of elements of the array.

### Conclusion

In conclusion, maps, filters, and reduces are powerful array functions that can be used to quickly and efficiently transform and filter arrays in JavaScript. Maps can be used to transform an array into a new array of the same size, where each element is the result of the callback function. Filters can be used to filter out array elements that do not meet certain criteria. Finally, reduce can be used to reduce the elements of an array to a single value, by implementing a specified reducer function on array elements.

Thanks for reading! I hope you find this blog post useful. You can connect with me on [**Twitter**](https://twitter.com/janvibajo01) or [**LinkedIn**](https://www.linkedin.com/in/janvi01/). 🚀❤️

#WeMakeDevs