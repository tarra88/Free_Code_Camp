---
tags: [FCC/JavaScript/Basic_JavaScript/39_Use_Recursion_to_Create_a_Range_of_Numbers]
---
(Exercise from FCC)

```js

function rangeOfNumbers(startNum, endNum) {

  if (endNum < startNum) {

    return [];

  } else {

  var countArray = rangeOfNumbers(startNum, endNum - 1);

  countArray.push(endNum);

  return countArray;

  }

};

console.log(rangeOfNumbers(1,5));

```
