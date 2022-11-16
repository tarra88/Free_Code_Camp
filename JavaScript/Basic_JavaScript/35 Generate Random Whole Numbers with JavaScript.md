---
tags: [FCC/JavaScript/Basic_JavaScript/35_Generate_Random_Whole_Numbers_with_JavaScript]
---
It's great that we can generate random decimal numbers, but it's even more useful if we use it to generate random whole numbers.

1. Use Math.random() to generate a random decimal.

2. Multiply that random decimal by 20.

3. Use another function, Math.floor() to round the number down to its nearest whole number.

Remember that Math.random() can never quite return a 1 and, because we're rounding down, it's impossible to actually get 20. This technique will give us a whole number between 0 and 19.

Putting everything together, this is what our code looks like:

```js

Math.floor(Math.random() * 20);

```

We are calling `Math.random()`, multiplying the result by 20, then passing the value to `Math.floor()` function to round the value down to the nearest whole number.

To return the number in the console you need a "return" like this:

```js

function randomWholeNum() {

  return Math.floor(Math.random() * 10);

}

console.log(randomWholeNum())

```

## Generate Random Whole Numbers within a Range

Instead of generating a random whole number between zero and a given number like we did before, we can generate a random whole number that falls within a range of two specific numbers.

To do this, we'll define a minimum number min and a maximum number max.

Here's the formula we'll use. Take a moment to read it and try to understand what this code is doing:

```js

Math.floor(Math.random() * (max - min + 1)) + min

```