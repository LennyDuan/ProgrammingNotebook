``# Data Structure

Here will talk about the how to implement different data structure in JavaScript.

### Stack
A stack follows the Last-In First-Out (LIFO) paradigm: an item added last will be removed first. JavaScript have a _buid-in stack_ via array - use Array to implement basic stack function. The __Array class__ has 2 methods that provide stack functionality. _.push()_ appends an item to the end of the array, and _.pop()_ removes and returns the last item in the array. 

```
var stack = [];       // stack is an array in js
stack.push(1);        // top -> 1
stack.push(2);        // top -> 2 -> 1
stack.push(3);        // top -> 3 -> 2 -> 1
var i = stack.pop();  // top -> 2 -> 1
```

Code Example & Test: [Array as __Stack__](https://github.com/LennyDuan/LeetCode/blob/master/node/test/util/buidin/array_test.js)

### Queue
A queue follows the First-In First-Out (FIFO) paradigm: the first item added will be the first item removed. Same as stack, an __array__ can be turned into a __queue__ by using the push() and shift() methods. _.push()_ inserts the passed argument at the end of the array, and _.shift()_ removes and returns the first item.

```
var queue = [];        // queue is an array in js
queue.push(1);         // rear -> 1 -> front
queue.push(2);         // rear -> 1 -> 2 -> front
queue.push(3);         // rear -> 1 -> 2 -> 3 -> front
var i = queue.shift(); // rear -> 2 -> 3 -> front
```

Code Example & Test: [Array as __Queue__](https://github.com/LennyDuan/LeetCode/blob/master/node/test/util/buidin/array_test.js)

### LinkedList




---
##### Some useful online resourse:

* [9 JavaScript Tips You May Not Know](http://codetunnel.com/9-javascript-tips-you-may-not-know/)