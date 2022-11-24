---
tags: [FCC/JavaScript/Basic_Algorithm_Scripting/136_Factorialize_a_Number]
---
Return the factorial of the provided integer.

If the integer is represented with the letter `n`, a factorial is the product of all positive integers less than or equal to `n`.

Factorials are often represented with the shorthand notation `n!`

For example: `5! = 1 * 2 * 3 * 4 * 5 = 120`

Only integers greater than or equal to zero will be supplied to the function.

#### Exercise
```js
function factorialize(num) {
  let i = 1;

  while (num > 0) {
    i *= num;
    num -= 1;
  }
  return i;
}

console.log(factorialize(5));
```
Another option is with a `for` loop:
```js
function factorialize(num) {
 let i = 1;
 for (let p = num; p > 0; p -= 1) {
  i *= p;
 }
 return i;
}
```