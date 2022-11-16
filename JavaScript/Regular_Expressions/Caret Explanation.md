---
tags: [FCC/JavaScript/Regular_Expressions/Caret_Explanation]
---
From [Stack Overflow](https://stackoverflow.com/questions/16944357/carets-in-regular-expressions)

When it's inside `[]` but **not** at the start, it means the actual `^` character.

When it's escaped (`\^`), it also means the actual `^` character.

In all other cases it means start of the string / line (which one is language / setting dependent).

So in short:

-   `[^abc]` -> not a, b or c
-   `[ab^cd]` -> a, b, ^ (character), c or d
-   `\^` -> a `^` character
-   Anywhere else -> start of string / line.

So `^[b-d]t$` means:

-   Start of line
-   b/c/d character
-   t character
-   End of line

## Exercise 99 from JavaScript > Regular Expressions
Use capture groups in `reRegex` to match a string that consists of only the same number repeated exactly three times separated by single spaces.

---
```js
let repeatNum = "42 42 42";

let reRegex = /^(\d+)\s\1\s\1$/; // ^ means start of the line and $ means end.

let result = reRegex.test(repeatNum);

console.log(result);
```

