---
tags: [FCC/JavaScript/Basic_Algorithm_Scripting/137_Find_the_Longest_Word_in_A_String]
---
Return the length of the longest word in the provided sentence.

Your response should be a number.

```js
function findLongestWordLength(str) {
  var strSplit = str.split(' ');
  var longestLength = 0;
  for (let i = 0; i < strSplit.length; i++) {
    if(strSplit[i].length > longestLength) {
      longestLength = strSplit[i].length;
    }
  }
  console.log(strSplit)
  console.log(strSplit.length)
  return longestLength;
}

console.log(findLongestWordLength("The quick brown fox jumped over the lazy dog"));
```
