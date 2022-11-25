---
tags: [FCC/JavaScript/Basic_Algorithm_Scripting/141_Truncate_a_String]
---
Truncate a string (first argument) if it is longer than the given maximum string length (second argument). Return the truncated string with a `...` ending.

```js
function truncateString(str, num) {
  let newStr = str.slice(0, num);
  let otherStr = (newStr + "...")
  // console.log(newStr);
  if (str.length > num) {
    return otherStr;
  } else {
    return str;
  }
 
}
```

I did use substring in my first attempt, but it didn't seem to work, but I didn't actually test it. Maybe I should have...

So I put back in my substring and it worked fine!
```js
function truncateString(str, num) {
  let newStr = str.substr(0, num);
  let otherStr = (newStr + "...")
  // console.log(newStr);
  if (str.length > num) {
    return otherStr;
  } else {
    return str;
  }
 
}
```
