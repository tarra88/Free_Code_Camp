---
tags: [FCC/JavaScript/Basic_Algorithm_Scripting/139_Confirm_the_Ending]
---
Check if a string (first argument, `str`) ends with the given target string (second argument, `target`).

This challenge _can_ be solved with the `.endsWith()` method, which was introduced in ES2015. But for the purpose of this challenge, we would like you to use one of the JavaScript substring methods instead.
```js
function confirmEnding(str, target) {
  // Convert both to arrays
let splitStr = str.split("");
let splitTarget = target.split("");
// console.log(splitStr);
console.log(splitTarget);
// count length of target array and str array
let strLength = splitStr.length;
let targetLength = splitTarget.length;
// get the target no. of characters from the end of the str
let cutStr = splitStr.slice(strLength-targetLength,strLength);
console.log(cutStr);
// convert this array back into a string so can compare with target
let joinStr = cutStr.join("");
console.log(joinStr);
if (joinStr == target) {
  return true;
}
  return false;
}

console.log(confirmEnding("Open sesame", "same"));
```

After all this, I watched a YT vid with their solution, and they didn't convert to an array and back again! They just kept it as a string the whole way and it was fine. Argh. So this more simple answer works:
```js
function confirmEnding(str, target) {
let length = str.length;
let targetLength = target.length;
let cutStr = str.slice(length-targetLength,length);
console.log(cutStr);
if (cutStr == target) {
  return true;
}
  return false;
}

console.log(confirmEnding("Open sesame", "same"));
```
