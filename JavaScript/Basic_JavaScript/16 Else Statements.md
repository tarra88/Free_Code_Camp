---
tags: [FCC/JavaScript/Basic_JavaScript/16_Else_Statements]
---
When a condition for an if statement is true, the block of code following it is executed. What about when that condition is false? Normally nothing would happen. With an else statement, an alternate block of code can be executed.

If you have multiple conditions that need to be addressed, you can chain if statements together with else if statements.

```js

if (num > 15) {

  return "Bigger than 15";

} else if (num < 5) {

  return "Smaller than 5";

} else {

  return "Between 5 and 15";

}

```