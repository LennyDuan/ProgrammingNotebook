# JavaScript Object Prototypes

All JavaScript objects inherit properties and methods from a prototype. 

For example: Date objects inherit from Date.prototype. Array objects inherit from Array.prototype. Person objects inherit from Person.prototype. The __Object.prototype__ is on the __top__ of the prototype inheritance chain: Date objects, Array objects, and Person objects inherit from Object.prototype.

### Adding Properties and Methods to Objects
* Sometimes you want to add new properties (or methods) to all existing objects of a given type.

* Sometimes you want to add new properties (or methods) to an object constructor.