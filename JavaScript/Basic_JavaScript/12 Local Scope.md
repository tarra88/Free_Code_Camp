---
tags: [FCC/JavaScript/Basic_JavaScript/12_Local_Scope]
---
Variables which are declared within a function, as well as the function parameters, have local scope. That means they are only visible within that function.

It is possible to have both local and global variables with the same name. When you do this, the local variable takes precedence over the global variable.

In this example:
```js

const someVar = "Hat";

  

function myFun() {

  const someVar = "Head";

  return someVar;

}

```

The function myFun will return the string Head because the local version of the variable is present.

```js

let processed = 0;

  

function processArg(num) {

  return (num + 3) / 5;

}

  

processed = processArg(7);

  

console.log(processed) // will return the new value for processed, i.e. 2

```