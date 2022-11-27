---
tags: [FCC/JavaScript/Basic_Algorithm_Scripting/143_Boo_who testing_boolean typeof]
---
Check if a value is classified as a boolean primitive. Return true or false.

Boolean primitives are true and false.

```js
function booWho(bool) { return typeof bool === "boolean"; }
```

#### Code Explanation
From [here](https://forum.freecodecamp.org/t/freecodecamp-challenge-guide-boo-who/16000).
-   Uses the operator `typeof` to check if the variable is a boolean. If it is, it will return `true`. Otherwise, if it is any other type it will return `false`.