---
tags: [FCC/JavaScript/Basic_Algorithm_Scripting/148_Mutations]
---
Return `true` if the string in the first element of the array contains all of the letters of the string in the second element of the array.

For example, `["hello", "Hello"]`, should return `true` because all of the letters in the second string are present in the first, ignoring case.

The arguments `["hello", "hey"]` should return `false` because the string `hello` does not contain a `y`.

Lastly, `["Alien", "line"]`, should return `true` because all of the letters in `line` are present in `Alien`.

```js
function mutation(arr) {
  let firstStr = arr[0].toLowerCase();
  let secondStr = arr[1].toLowerCase();
  console.log(firstStr);
 for (let i = 0; i < secondStr.length; i++) {
   if (firstStr.indexOf(secondStr[i]) < 0) return false;
 }
   return true;
}
console.log(mutation(["hello", "hey"]));
```

Another solution from [here](https://forum.freecodecamp.org/t/freecodecamp-challenge-guide-mutations/16025):

**Declarative**

```js
function mutation(arr) {
  return arr[1]
    .toLowerCase()
    .split("")
    .every(function(letter) {
      return arr[0].toLowerCase().indexOf(letter) !== -1;
    });
}
```

#### [Code Explanation](https://forum.freecodecamp.org/t/freecodecamp-challenge-guide-mutations/16025#code-explanation-11)
Grab the second string, lowercase and turn it into an array; then make sure _every_ one of its _letters_ is a part of the lowercased first string.

`Every` will basically give you letter by letter to compare, which we do by using `indexOf` on the first string. `indexOf` will give you -1 if the current `letter` is missing. We check that not to be the case, for if this happens even once `every` will be false.

And found another solution [here](https://dev.to/virenb/solving-mutations-freecodecamp-algorithm-challenges-1gja):

```js
const mutation = ( [ first, second ] ) =>
  second
  .toLowerCase()
  .split('')
  .every( e => 
         first
         .toLowerCase()
         .includes(e)
  )
```
