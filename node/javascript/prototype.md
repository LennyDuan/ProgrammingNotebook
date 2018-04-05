# JavaScript Object Prototypes

##### Explain and understand what is Prototype and how Prototype chain works in JS
All JavaScript objects inherit properties and methods from a prototype. JavaScript is a bit confusing for developers experienced in class-based languages (like Java or C++), as it is dynamic and does not provide a class implementation（the class keyword is introduced in ES2015, but is syntactical sugar, JavaScript remains __prototype-based__).

For example: Date objects inherit from Date.prototype. Array objects inherit from Array.prototype. Person objects inherit from Person.prototype. The __Object.prototype__ is on the __top__ of the prototype inheritance chain: Date objects, Array objects, and Person objects inherit from Object.prototype.
```
* var o = {a: 1};  o ---> Object.prototype ---> null
* var b = ['yo', 'whadup', '?']; b ---> Array.prototype ---> Object.prototype ---> null
* function f() { return 2; } f ---> Function.prototype ---> Object.prototype ---> null
```
### Inheritance with the prototype chain
JavaScript objects are dynamic "bags" of properties (referred to as own properties). __JavaScript objects__ have a __link__ to a __prototype object__. When trying to access a property of an object, the property will _not only be sought on the object but on the prototype of the object_, the prototype of the prototype, and so on _until either a property with a matching name is found or the end of the prototype chain is reached_.
#### Inheriting properties Example:

```
// Initialize a class
let Person = function () {
   this.name = 'a';
   this.age = 25;
}
let o = new Person(); 
// o -> { name: 'a', age: 25 }

//add properties in Person function's prototype
 Person.prototype.age = 30;
 Person.prototype.home = 'cn';

// __Notice__: do not set the prototype Person.prototype = { a:1, b:2 }; this will break the prototype chain
// o.[[Prototype]] has properties 'age' and 'home'.
// o.[[Prototype]].[[Prototype]] is Object.prototype.
// Finally, o.[[Prototype]].[[Prototype]].[[Prototype]]`/`Object.prototype.prototype is null. This is the end of the prototype chain, as null,
// Thus, the full prototype chain looks like:
// { name: 'a', age: 25 } ---> {age: 30, home: 'cn'} ---> Object.prototype ---> null

console.log(o.name); 
// -> 'a'
// Is there an 'name' own property on o? Yes, and its value is 'a'

console.log(o.age); 
// -> 25
// Is there a 'age' own property on o? Yes, and its value is 25.
// The prototype _also has a 'age property_, but it's __not visited__. This is called __"property shadowing."__

console.log(o.home); 
// -> 'cn'
// Is there a 'home' own property on o? No, check its prototype.
// Is there a 'home' own property on o.[[Prototype]]? Yes, its value is 'cn'.

console.log(o.d); // undefined
// Is there a 'd' own property on o? No, check its prototype.
// Is there a 'd' own property on o.[[Prototype]]? No, check its prototype.
// o.[[Prototype]].[[Prototype]] is null, stop searching,
// no property found, return undefined.
```
#### Inheriting "methods" example:
JavaScript does not have "methods" in the form that class-based languages define them. In JavaScript, any function can be added to an object in the form of a property. An __inherited function__ acts just as any other __property__.

```
var o = {
  a: 2,
  m: function() {
    return this.a + 1;
  }
};

console.log(o.m()); 
// o -> { a: 2, m: [Function: m] }
// 3
// When calling o.m in this case, 'this' refers to o

var p = Object.create(o);
// p is an object that inherits from o
// p -> {}

console.log(p.a); 
// Is there a 'a' own property on p? No, check its inherits o -> { a: 2, m: [Function: m] }. 
// p.a -> 2

p.a = 4; 
// creates a property 'a' on p
// p -> { a: 4 }
console.log(p.m()); 
// 5
// when p.m is called, 'this' refers to p.
// So when p inherits the function m of o, 
// 'this.a' means p.a, the property 'a' of p

p.c = function() { return 1 + 2 }; 
// creates a method 'c' on p
// p -> { a: 4, c: [Function: c] }
console.log(p.c()); 
// -> 1 + 2 -> 3

```

### Adding Properties and Methods to Objects
* Sometimes you want to add new properties (or methods) to all existing objects of a given type.

* Sometimes you want to add new properties (or methods) to an object constructor.

* Object.prototype.\_\_proto\_\_: The `__proto__` property of Object.prototype is an accessor property (a getter function and a setter function) that exposes the internal [[Prototype]] (either an object or null) of the object through which it is accessed. 
__NOTICE__: The use of `__proto__` is controversial, and has been discouraged.

---
* MDN [Inheritance and the prototype chain](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Inheritance_and_the_prototype_chain)
* W3C [JavaScript Object Prototypes](https://www.w3schools.com/js/js_object_prototypes.asp)