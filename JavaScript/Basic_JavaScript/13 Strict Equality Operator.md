---
tags: [FCC/JavaScript/Basic_JavaScript/13_Strict_Equality_Operator]
---
Strict equality `===` is the counterpart to the equality operator `==`. However, unlike the equality operator, which attempts to convert both values being compared to a common type, the strict equality operator does not perform a type conversion.

If the values being compared have different (data) types, they are considered unequal, and the strict equality operator will return false.

Examples

```js

3 ===  3  // true

3 === '3' // false

```

3 == '3' returns true because JavaScript performs type conversion from string to number. 3 === '3' returns false because the types are different and type conversion is not performed.

### typeof

You can determine the type of a variable or a value with the 'typeof' operator.