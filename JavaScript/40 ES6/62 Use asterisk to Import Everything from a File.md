---
tags: FCC/JavaScript/ES6/62_Use_Asterisk_to_Import_Everything_from_a_File
---
Suppose you have a file and you wish to import all of its contents into the current file. This can be done with the `import * as` syntax. Here's an example where the contents of a file named `math_functions.js` are imported into a file in the same directory:

```js
import * as myMathModule from "./math_functions.js";
```

The above `import` statement will create an object called `myMathModule`. This is just a variable name, you can name it anything. The object will contain all of the exports from `math_functions.js` in it, so you can access the functions like you would any other object property. Here's how you can use the `add` and `subtract` functions that were imported:

```js
myMathModule.add(2,3);
myMathModule.subtract(5,3);
```
