---
tags: [FCC/JavaScript/Basic_Algorithm_Scripting/146_Falsy_Bouncer]
---
Remove all falsy values from an array. Return a new array; do not mutate the original array.

Falsy values in JavaScript are `false`, `null`, `0`, `""`, `undefined`, and `NaN`.

Hint: Try converting each value to a Boolean.

Hints taken from [here](https://forum.freecodecamp.org/t/freecodecamp-challenge-guide-falsy-bouncer/16014):
```js
function bouncer(arr) {
  const filteredArr = [];
  for (let i = 0; i < arr.length; i++) {
    if (arr[i]) filteredArr.push(arr[i]);
  }
  return filteredArr;
}
```


#### Code Explanation

-   We create a new empty array (`filteredArr`).
-   We use a for cycle to iterate over all elements of the provided array (`arr`).
-   We use the if statement to check if the current element is [truthy 2.9k](http://forum.freecodecamp.com/t/javascript-truthy-value/15975) or [falsy 4.7k](https://guide.freecodecamp.org/javascript/falsy-values/).
-   If the element is truthy, we push it to the new array (newArray). This result in the new array (`filteredArr`) containing only truthy elements.
-   We return the new array (`filteredArr`).

More information on falsy and truthy [here](https://www.sitepoint.com/javascript-truthy-falsy/).
