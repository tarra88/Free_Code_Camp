---
tags: [FCC/JavaScript/Basic_JavaScript/14_Inequality_Operator]
---
The inequality operator (!=) is the opposite of the equality operator. It means not equal and returns false where equality would return true and vice versa. Like the equality operator, the inequality operator will convert data types of values while comparing.

Examples

```js

1 !=  2    // true

1 != "1"   // false

1 != '1'   // false

1 != true  // false

0 != false // false

```

```js

function testNotEqual(val) {
  if (val != 99) {
    return "Not Equal";
  }
  return "Equal";
}

testNotEqual(10);

```

The strict inequality operator `!==` is the logical opposite of the strict equality operator. It means "Strictly Not Equal" and returns false where strict equality would return true and vice versa. The strict inequality operator will not convert data types.

Examples

```js

3 !==  3  // false

3 !== '3' // true

4 !==  3  // true

```

The greater than '>' and less than '<' operators also return true or false, converting data types of values when comparing.

Also the same for greater than or equal operator (>=).