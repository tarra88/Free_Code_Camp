---
tags: [FCC/JavaScript/Basic_Algorithm_Scripting/142_Finders_Keepers]
---
Create a function that looks through an array `arr` and returns the first element in it that passes a 'truth test'. This means that given an element `x`, the 'truth test' is passed if `func(x)` is `true`. If no element passes the test, return `undefined`.
```js
function findElement(arr, func) {
  let num = 0;

  for (let i = 0; i < arr.length; i++) {
    num = arr[i];
    if (func(num)) {
      return num;
    }
  }

  return undefined;
}
findElement([1, 2, 3, 4], num => num % 2 === 0);
```

## Solution 2
```js
function findElement(arr, func) {
  return arr.find(func);
}
```
Notes on find function from [here](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Array/find):
>The `find()` method returns the first element in the provided array that satisfies the provided testing function. If no values satisfy the testing function, `undefined` is returned.

## Solution 3
```js
function findElement(arr, func) {
  return arr[arr.map(func).indexOf(true)];
}
```
**Code Explanation**
1.  Look through the array given in the 1st paramater “arr” using the .map() method
2.  Use the function in the 2nd parameter as the callback function in arr.map()
3.  Acquire the index of the first number that meets the condition in the function.
4.  Use that index to display the first available number that meets the condition.

## Solution 4
**recursive solution**
```js
function findElement(arr, func) {
  if (arr.length > 0 && !func(arr[0])) {
    return findElement(arr.slice(1), func);
  } else {
    return arr[0];
  }
}
```

Help for solutions from [here](https://forum.freecodecamp.org/t/freecodecamp-challenge-guide-finders-keepers/16016).