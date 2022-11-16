---
tags: [FCC/JavaScript/Basic_JavaScript/37_Use_the_Conditional_(Ternary)_Operator]
---
The conditional operator, also called the ternary operator, can be used as a one line if-else expression.

The syntax is a ? b : c, where a is the condition, b is the code to run when the condition returns true, and c is the code to run when the condition returns false.

The following function uses an if/else statement to check a condition:

```js

function findGreater(a, b) {

  if(a > b) {

    return "a is greater";

  }

  else {

    return "b is greater or equal";

  }

}

```

This can be re-written using the conditional operator:

```js

function findGreater(a, b) {

  return a > b ? "a is greater" : "b is greater or equal";

}

```

## Use Multiple Conditional (Ternary) Operators

In the previous challenge, you used a single conditional operator. You can also chain them together to check for multiple conditions.

The following function uses if, else if, and else statements to check multiple conditions:

```js

function findGreaterOrEqual(a, b) {

  if (a === b) {

    return "a and b are equal";

  }

  else if (a > b) {

    return "a is greater";

  }

  else {

    return "b is greater";

  }

}

```

The above function can be re-written using multiple conditional operators:

```js

function findGreaterOrEqual(a, b) {

  return (a === b) ? "a and b are equal"

    : (a > b) ? "a is greater"

    : "b is greater";

}

```

It is considered best practice to format multiple conditional operators such that each condition is on a separate line, as shown above.