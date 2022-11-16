---
tags: [FCC/JavaScript/Basic_JavaScript/18_Returning_Boolean_Values_from_Functions]
---
Sometimes people use an if/else statement to do a comparison, like this:

```js

function isEqual(a, b) {

  if (a === b) {

    return true;

  } else {

    return false;

  }

}

```

But there's a better way to do this. Since === returns true or false, we can return the result of the comparison:

```js

function isEqual(a, b) {

  return a === b;

}

```
