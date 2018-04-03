## Tips

Here I will record some useful tips when do the JS development.

### Value Type
#### Convert String to Int
__HIGH RECOMMENDATION: __ Use `unary plus` to convert a string to int.

```
const str = '100';
// str = '100'
const num = +str;
// num -> 100
```

__Options__: Use `Numer()` and `parseInt()`
```
const str = '100';
// str = '100'

const num = Number(str);
// num -> 100

const num = parseInt(str, 10);
// num -> 100


```
