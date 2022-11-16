---
tags: [FCC/JavaScript/Basic_JavaScript/15_Comparisons_with_the_Logical_and_Operator_or_using_&&]
---
Sometimes you will need to test more than one thing at a time. The logical and operator (&&) returns true if and only if the operands to the left and right of it are true.

The same effect could be achieved by nesting an if statement inside another if:

```js

if (num > 5) {

  if (num < 10) {

    return "Yes";

  }

}

return "No";

```

will only return Yes if num is greater than 5 and less than 10. The same logic can be written as:

```js

if (num > 5 && num < 10) {

  return "Yes";

}

return "No";

```

The logical or operator (`||`) returns true if either of the operands is true. Otherwise, it returns false.

The pattern below should look familiar from prior waypoints:

```js

if (num > 10) {

  return "No";

}

if (num < 5) {

  return "No";

}

return "Yes";

```

will return Yes only if num is between 5 and 10 (5 and 10 included). The same logic can be written as:

```js

if (num > 10 || num < 5) {

  return "No";

}

return "Yes";

```