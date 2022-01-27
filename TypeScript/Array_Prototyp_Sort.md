# `Array.prototype.sort()`

To sort an array, the prototype has the `.sort()` method which can use a compare function as below. The sort function always receives two elements a and b to compare. If it returns

- < 0 a will receive a lower index than b
- = 0 a and b will keep their index in relation to each other
- \> 0 a will receive a higher index than b

```typescript
const numbers = [4, 2, 5, 1, 3];
numbers.sort((a, b) => a - b);
//1, 2, 3, 4, 5
```

### Note

- `.sort()` sorts the array in place.
- If no compare function is provided the values will be converted into strings and their UTF-16 codes will be sorted in ascending order

### [source](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Array/sort)
