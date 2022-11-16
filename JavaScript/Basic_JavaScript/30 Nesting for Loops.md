---
tags: [FCC/JavaScript/Basic_JavaScript/30_Nesting_for_Loops]
---
If you have a multi-dimensional array, you can use the same logic as the prior waypoint to loop through both the array and any sub-arrays. Here is an example:

```js

const arr = [

  [1, 2], [3, 4], [5, 6]

];

  

for (let i = 0; i < arr.length; i++) {

  for (let j = 0; j < arr[i].length; j++) {

    console.log(arr[i][j]);

  }

}

```

This outputs each sub-element in arr one at a time. Note that for the inner loop, we are checking the .length of arr[i], since arr[i] is itself an array.

### Exercise:

Modify function multiplyAll so that it returns the product of all the numbers in the sub-arrays of arr.

```js

function multiplyAll(arr) {

  var product = 1;

  // Only change code below this line

  for (var i = 0; i < arr.length; i++) { // starts with the first number in the array and continues to the last number (as it only continues while i is less than the number of items in the array)

    for (var j = 0; j < arr[i].length; j++) { // this is the same for the arrays within the main array. For each number of the array it goes through this.

      product = product * arr[i][j]; // this multiplies each number in each array together, then the totals against each other.

    }

  }

  // Only change code above this line

  return product;

}

  

// Modify values below to test your code

multiplyAll([[1, 2], [3, 4], [5, 6, 7]]);

```
