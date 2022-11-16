---
tags: [FCC/JavaScript/Regular_Expressions/101_Remove_Whitespace_from_Start_and_End]
---
Sometimes whitespace characters around strings are not wanted but are there. Typical processing of strings is to remove the whitespace at the start and end of it.

---

Write a regex and use the appropriate string methods to remove whitespace at the beginning and end of strings.

**Note:** The `String.prototype.trim()` method would work here, but you'll need to complete this challenge using regular expressions.
```js
let hello = "   Hello, World!  ";

let wsRegex = /^\s+|\s+$/g; // The ^ denotes spaces at the start of the string, with or (|), and $ denotes spaces at the end of the string

let result = hello.replace(wsRegex,""); // Change this line

console.log(result);
```