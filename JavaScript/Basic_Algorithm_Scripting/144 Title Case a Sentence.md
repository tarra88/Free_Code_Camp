---
tags: [FCC/JavaScript/Basic_Algorithm_Scripting/144_Title_Case_a_Sentence toLowerCase toUpperCase Change-Case]
---
Return the provided string with the first letter of each word capitalized. Make sure the rest of the word is in lower case.

For the purpose of this exercise, you should also capitalize connecting words like `the` and `of`.

I took advice from [here](https://www.freecodecamp.org/news/three-ways-to-title-case-a-sentence-in-javascript-676a9175eb27):

```js
function titleCase(str) {
  str = str.toLowerCase().split(' ').map(function(word) {
    return word.replace(word[0], word[0].toUpperCase());
  }).join(' ');
  return str
}

```

A really nice explanation of JS.map() [here](https://www.freecodecamp.org/news/javascript-map-how-to-use-the-js-map-function-array-method/).

