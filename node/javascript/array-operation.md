# Collection Operation

Here will talk about the how to quick operate/modify the collection (__Array or Objects__) via _build-in_ & _elegant_ ES6 features. 

There have lots of third-party API/Modules about operate the Array such as [Lodash](https://lodash.com), [Underscores](http://underscorejs.org) _(WTF! Can anyone tell me why they all start with_ __\_.__?) and etc to help developer to operate the collections. But here, I  wanna talk about ___build-in ES6+___ Collection operation which have 90% coverage of normally usages. 

More info can be checked in [official doc](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Array)

---

### `.map()`
#### Return a new array of objects 
###### -> every element will be modified by provided function
```
const origin = [1, 2, 3, 4, 5];
// origin -> [1, 2, 3, 4, 5]
const result = origin.map(ele => ele * 2);
// result -> [2, 4, 6, 8, 10]
```
---

### `.filter()`
#### Return a new array of objects 
###### -> elements will pass the function
```
const origin = [1, 2, 3, 4, 5];
// origin -> [1, 2, 3, 4, 5]
const result = origin.filter(ele => ele > 3)
// result -> [4, 5]
```
---

### `.slice()`
#### Return a new array of objects 
###### -> from `begin` to `end`(end not included)
```
const origin = [1, 2, 3, 4, 5];
// origin -> [1, 2, 3, 4, 5]
const result = origin.slice(1, 4)
// result -> [2, 3, 4]
```
---

### `.reverse()`
#### Return a new array of objects
###### -> reverse an array
```
const origin = [1, 2, 3, 4, 5];
// origin -> [1, 2, 3, 4, 5]
const result = origin.reverse();
// result -> [5, 4, 3, 2, 1]
// origin -> [5, 4, 3, 2, 1]

```
__Notice__: The original array will be reversed as well

---

### `.reverse()`
#### Return a new array of objects
###### -> reverse an array
```
const origin = [1, 2, 3, 4, 5];
// origin -> [1, 2, 3, 4, 5]
const result = origin.reverse();
// result -> [5, 4, 3, 2, 1]
// origin -> [5, 4, 3, 2, 1]

```
__Notice__: The original array will be reversed as well

---


### `.every()`
#### Return a boolean 
###### -> all elements pass the function
```
const origin = [1, 2, 3, 4, 5];
// origin -> [1, 2, 3, 4, 5]

const result = origin.every(ele => ele > 0);
// result -> true

const result_sec = origin.every(ele => ele > 1);
// result_sec -> false

```

---

### `.some()`
#### Return a boolean 
###### -> at least one element pass the function
```
const origin = [1, 2, 3, 4, 5];
// origin -> [1, 2, 3, 4, 5]

const result = origin.some(ele => ele > 1);
// result -> true

const result_sec = origin.some(ele => ele > 5);
// result_sec -> false

```

---

### `.includes()`
#### Return a boolean 
###### -> an collection includes an element or not
```
const origin = [1, 2, 3, 4, 5];
// origin -> [1, 2, 3, 4, 5]

const result = origin.includes(1);
// result -> true

const result_sec = origin.includes(6);
// result_sec -> false

```

---

### `.find()` OR `.findIndex()`
#### Return object 
###### -> first element that satisfies the function
```
const origin = [1, 2, 3, 4, 5];
// origin -> [1, 2, 3, 4, 5]

const result = origin.find(ele => ele * 2 == 8);
// result -> 4

const result = origin.findIndex(ele => ele * 3 == 3);
// result -> 0
```

---

### `.reduce()` OR `.reduceRight`
#### Return object 
###### -> return a value for each element operated by provided function left-to-right or right-to-left
```
const origin = [1, 2, 3, 4, 5];
// origin -> [1, 2, 3, 4, 5]

const result = origin.reduce((a, b) => a * b);
// result -> 120
// explain -> 1 * 2 * 3 * 4 * 5

const result_sec = origin.reduceRight((a, b) => a * b);
// result_sec -> 120
// explain -> 5 * 4 * 3 * 2 * 1

```

---

### `.join()`
#### Return string
###### -> join all elements into a string
```
const origin = [1, 2, 3, 4, 5];
// origin -> [1, 2, 3, 4, 5]
const result = origin.join(' -> ');
// result -> '1 -> 2 -> 3 -> 4 -> 5'
```

---

### `.forEach()`
#### Return nothing
```
const origin = [1, 2, 3, 4, 5];
// origin -> [1, 2, 3, 4, 5]
origin.forEach(ele => console.log(`Ele: ${ele}`))
// Ele: 1
// Ele: 2
// Ele: 3
// Ele: 4
// Ele: 5

```

---

















