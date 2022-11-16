---
tags: [FCC/JavaScript/Basic_JavaScript/36_Use_the_parseInt_Function]
---
The parseInt() function parses a string and returns an integer. Here's an example:

```js

const a = parseInt("007");

```

The above function converts the string 007 to the integer 7. If the first character in the string can't be converted into a number, then it returns NaN.

As a function:

```js

function convertToInteger(str) {

 return parseInt(str);

}

convertToInteger("56");

```

## Use the parseInt Function with a Radix

The parseInt() function parses a string and returns an integer. It takes a second argument for the radix, which specifies the base of the number in the string. The radix can be an integer between 2 and 36.

The function call looks like:

```js

parseInt(string, radix);

```

And here's an example:

```js

const a = parseInt("11", 2);

```

The radix variable says that 11 is in the binary system, or base 2. This example converts the string 11 to an integer 3.

As a function:

```js

function convertToInteger(str) {

  return parseInt(str, 2);

}

console.log(

convertToInteger("10011"));

```