``# Data Structure

Here will talk about the how to implement different data structure in JavaScript.

### Queue


### Stack
A stack follows the Last-In First-Out (LIFO) paradigm: an item added last will be removed first. JavaScript have a _buid-in stack_ via array - use Array to implement basic stack function. The __Array class__ has 2 methods that provide stack functionality. _.push()_ appends an item to the end of the array, and _.pop()_ removes and returns the last item in the array. 

```
var stack = [];       // stack is an array
stack.push(1);        // top -> 1
stack.push(2);        // top 2 -> 1
stack.push(3);        // top 3 -> 2 -> 1
var i = stack.pop();  // top 2 -> 1
```

Code Example & Test: [Array as __Stack__](https://github.com/LennyDuan/LeetCode/blob/master/node/test/util/buidin/array_test.js)


### LinkedList




---
##### Some useful online resourse:

* [9 JavaScript Tips You May Not Know](http://codetunnel.com/9-javascript-tips-you-may-not-know/)