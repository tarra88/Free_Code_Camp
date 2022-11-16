---
tags: [FCC/JavaScript/Basic_JavaScript/09_Arrays]
---
You can nest arrays within other arrays:

Unlike strings, the entries of arrays are mutable and can be changed freely, even if the array was declared with const.

One way to think of a multi-dimensional array, is as an array of arrays. When you use brackets to access your array, the first set of brackets refers to the entries in the outer-most (the first level) array, and each additional pair of brackets refers to the next level of entries inside.

Example

```js

const arr = [

  [1, 2, 3],

  [4, 5, 6],

  [7, 8, 9],

  [[10, 11, 12], 13, 14]

];

  

const subarray = arr[3];

const nestedSubarray = arr[3][0];

const element = arr[3][0][1];

```

In this example, subarray has the value [[10, 11, 12], 13, 14], nestedSubarray has the value [10, 11, 12], and element has the value 11 .