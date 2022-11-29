---
tags: [FCC/JavaScript/Basic_Algorithm_Scripting/149_Chunky_Monkey]
---
Write a function that splits an array (first argument) into groups the length of size (second argument) and returns them as a two-dimensional array.

## Solutions
#### Solution from [here](https://dev.to/virenb/solving-chunky-monkey-freecodecamp-algorithm-challenges-p9o):
```js
function chunkArrayInGroups(arr, size) {
  for (let i = 0; i < arr.length; i++) {
    let toSplice = arr.splice(i, size);
    arr.unshift(toSplice);
  }
  return arr.reverse();
}
```

Solutions from [FCC](https://forum.freecodecamp.org/t/freecodecamp-challenge-guide-chunky-monkey/16005):
```js
function chunkArrayInGroups(arr, size) {
  // Break it up.
  const newArr = [];
  for (let i = 0; i < arr.length; i += size) {
    newArr.push(arr.slice(i, i + size));
  }
  return newArr;
}
```

```js
function chunkArrayInGroups(arr, size) {
  const newArr = [];
  while (arr.length > 0) {
    newArr.push(arr.splice(0, size));
  }
  return newArr;
}
```

```js
function chunkArrayInGroups(arr, size) {
  let temp = [];
  const result = [];

  for (let a = 0; a < arr.length; a++) {
    if (a % size !== size - 1) temp.push(arr[a]);
    else {
      temp.push(arr[a]);
      result.push(temp);
      temp = [];
    }
  }

  if (temp.length !== 0) result.push(temp);
  return result;
}
```

```js
function chunkArrayInGroups(arr, size) {
  if (arr.length <= size) {
    return [arr];
  } else {
    return [arr.slice(0, size)].concat(
      chunkArrayInGroups(arr.slice(size), size)
    );
  }
}
```

