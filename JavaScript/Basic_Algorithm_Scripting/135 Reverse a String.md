---
tags: [FCC/JavaScript/Basic_Algorithm_Scripting/135_Reverse_a_String]
---
Reverse the provided string.

You may need to turn the string into an array before you can reverse it.

Your result must be a string.

3 methods according to [FFC article](https://www.freecodecamp.org/news/how-to-reverse-a-string-in-javascript-in-3-different-ways-75e4763c68cb/). 

```js
function reverseString(str) {

  return str.split("").reverse().join("");
}
// split will split the string into individual sting letters, reverse will reverse the order of those individual strings, and then join to put them all back together.
reverseString("hello");
```

```js
function reverseString(str) {
    var newString = "";
    for (var i = str.length - 1; i >= 0; i--) { //start at the end and decrement by 1 each round
        newString += str[i];
    }
    return newString;
}
reverseString('hello');
```

And the looooong method:
```js
function reverseString(str) {
  if (str === "")
    return "";
  else
    return reverseString(str.substr(1)) + str.charAt(0);
}
reverseString("hello");
```
