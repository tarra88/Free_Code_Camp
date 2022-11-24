---
tags: [FCC/JavaScript/Basic_Algorithm_Scripting/138_Return_Largest_Numbers_in_Arrays]
---
Return an array consisting of the largest number from each provided sub-array. For simplicity, the provided array will contain exactly 4 sub-arrays.

Remember, you can iterate through an array with a simple for loop, and access each member with array syntax `arr[i]`.

```js
function largestOfFour(arr) {
  let answer = [];
  for (let i = 0; i < arr.length; i += 1) {
    let innerArray = arr[i];
    let highest = -Infinity;
    for (let j = 0; j < innerArray.length; j += 1) {
      if (highest < innerArray[j]) {
      highest = innerArray[j];
      }
    }
    answer.push(highest);
  }
   return answer;
}

console.log(largestOfFour([[4, 5, 1, 3], [13, 27, 18, 26], [32, 35, 37, 39], [1000, 1001, 857, 1]]));
```
