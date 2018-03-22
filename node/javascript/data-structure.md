# Data Structure

Here will talk about the how to implement different data structure in JavaScript.

--- 

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

---

### Queue
A queue follows the First-In First-Out (FIFO) paradigm: the first item added will be the first item removed. Same as stack, an __array__ can be turned into a __queue__ by using the push() and shift() methods. _.push()_ inserts the passed argument at the end of the array, and _.shift()_ removes and returns the first item.

```
var queue = [];        // queue is an array in js
queue.push(1);         // rear -> 1 -> front
queue.push(2);         // rear -> 1 -> 2 -> front
queue.push(3);         // rear -> 1 -> 2 -> 3 -> front
var i = queue.shift(); // rear -> 2 -> 3 -> front
```

P.S. It's worth noting that Array also has a function named unshift(). This function adds the passed item to the beginning of an array. 

Code Example & Test: [Array as __Queue__](https://github.com/LennyDuan/LeetCode/blob/master/node/test/util/buidin/array_test.js)

---

### LinkedList
A linked list is a linear data structure where each element is a separate object. Each element (we will call it a __node__) of a list is comprising of two items - the data and a reference to the next node. The last node has a reference to _null_. The entry point into a linked list is called the __head__ of the list. It should be noted that head is not a separate node, but the reference to the first node.

There are 3 basic type of Linked list: 
* __A singly linked list__ is described in this chapter
* __A doubly linked list__ is a list that has two references, one to the next node and another to previous node.
* __A circular linked list__ where last node of the list points back to the first node (or the head) of the list.

##### Singly Linked List:
In Node, not like Java, it doesn't have build-in/default linkedList data structure. So we need to create a LinkedList Class if we want to use it:

```
class ListNode {
  constructor(value) {
    this.value = value;
    this.next = null;
  }
}

ListNode.prototype.toString = function () {
  let str = this.value;
  let nextNode = this.next;
  while (nextNode) {
    str += ` -> ${nextNode.value}`;
    nextNode = nextNode.next;
  }
  return str;
};

module.exports = {
  ListNode,
};
```

Code Example & Test: LinkedList [Example](https://github.com/LennyDuan/LeetCode/blob/master/node/src/util/class/linkedlist.js) and [Test](https://github.com/LennyDuan/LeetCode/blob/master/node/test/util/class/linkedlist_test.js)

---
##### Some useful online resourse
Some knowledge are learned from others study/blogs/comments. Thanks very much for the sharing community and culture
* [9 JavaScript Tips You May Not Know](http://codetunnel.com/9-javascript-tips-you-may-not-know/) - Ayman Hourieh