---
tags: [FCC/JavaScript/Basic_Algorithm_Scripting/147_Where_do_I_Belong]
---
Return the lowest index at which a value (second argument) should be inserted into an array (first argument) once it has been sorted. The returned value should be a number.

For example, `getIndexToIns([1,2,3,4], 1.5)` should return `1` because it is greater than `1` (index 0), but less than `2` (index 1).

Likewise, `getIndexToIns([20,3,5], 19)` should return `2` because once the array has been sorted it will look like `[3,5,20]` and `19` is less than `20` (index 2) and greater than `5` (index 1).

## Use the Sort function (see notes [here](https://forum.freecodecamp.org/t/freecodecamp-challenge-guide-where-do-i-belong/16094):)
```js
 arr.sort((a, b) => a - b);

  for (let i = 0; i < arr.length; i++) {
    if (arr[i] >= num) return i;
  }

  return arr.length;
```

## Method 2
```javascript
function getIndexToIns(arr, num) {
  return arr.filter(val => num > val).length;
}
```

#### [Code Explanation](https://forum.freecodecamp.org/t/freecodecamp-challenge-guide-where-do-i-belong/16094#code-explanation-10)

-   Count the number of entries that are smaller than the new value `num`
-   The new value would be inserted after these values

## Method 3

```javascript
function getIndexToIns(arr, num) {
  return arr
    .concat(num)
    .sort((a, b) => a - b)
    .indexOf(num);
}

getIndexToIns([1, 3, 4], 2);
```

#### [Code Explanation](https://forum.freecodecamp.org/t/freecodecamp-challenge-guide-where-do-i-belong/16094#code-explanation-13)

-   We use method-chaining to invoke one method after another to solve the problem in a single line. First we create a new array with the contents of `arr` and `num` by using the `concat()` method
-   Then we use `sort()` with the callback **arrow function** `(a, b) => return a-b` to sort the numbers in ascending order
-   Lastly we return the position or index of `num` in the array with the `indexOf()` method