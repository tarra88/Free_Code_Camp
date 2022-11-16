---
tags: [FCC/JavaScript/Debugging/109_Catch_Missing_Open_and_Closing_Parenthesis_After_a_Function_Call]
---
When a function or method doesn't take any arguments, you may forget to include the (empty) opening and closing parentheses when calling it. Often times the result of a function call is saved in a variable for other use in your code. This error can be detected by logging variable values (or their types) to the console and seeing that one is set to a function reference, instead of the expected value the function returns.

The variables in the following example are different:

```js
function myFunction() {
  return "You rock!";
}
let varOne = myFunction;
let varTwo = myFunction();
```

Here `varOne` is the function `myFunction`, and `varTwo` is the string `You rock!`.