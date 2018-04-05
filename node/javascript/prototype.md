# JavaScript Object Prototypes

##### Explain and understand what is Prototype and how Prototype chain works in JS
All JavaScript objects inherit properties and methods from a prototype. JavaScript is a bit confusing for developers experienced in class-based languages (like Java or C++), as it is dynamic and does not provide a class implementation（the class keyword is introduced in ES2015, but is syntactical sugar, JavaScript remains __prototype-based__).

For example: Date objects inherit from Date.prototype. Array objects inherit from Array.prototype. Person objects inherit from Person.prototype. The __Object.prototype__ is on the __top__ of the prototype inheritance chain: Date objects, Array objects, and Person objects inherit from Object.prototype.

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
// {a: 1, b: 2} ---> {b: 3, c: 4} ---> Object.prototype ---> null

console.log(o.a); // 1
// Is there an 'a' own property on o? Yes, and its value is 1.

console.log(o.b); // 2
// Is there a 'b' own property on o? Yes, and its value is 2.
// The prototype also has a 'b' property, but it's not visited. 
// This is called "property shadowing."

console.log(o.c); // 4
// Is there a 'c' own property on o? No, check its prototype.
// Is there a 'c' own property on o.[[Prototype]]? Yes, its value is 4.

console.log(o.d); // undefined
// Is there a 'd' own property on o? No, check its prototype.
// Is there a 'd' own property on o.[[Prototype]]? No, check its prototype.
// o.[[Prototype]].[[Prototype]] is null, stop searching,
// no property found, return undefined.
```

### Adding Properties and Methods to Objects
* Sometimes you want to add new properties (or methods) to all existing objects of a given type.

* Sometimes you want to add new properties (or methods) to an object constructor.

* Object.prototype.\_\_proto\_\_: The `__proto__` property of Object.prototype is an accessor property (a getter function and a setter function) that exposes the internal [[Prototype]] (either an object or null) of the object through which it is accessed. 
__NOTICE__: The use of `__proto__` is controversial, and has been discouraged.

---
* MDN [Inheritance and the prototype chain](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Inheritance_and_the_prototype_chain)
* W3C [JavaScript Object Prototypes](https://www.w3schools.com/js/js_object_prototypes.asp)