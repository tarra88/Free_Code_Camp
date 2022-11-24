---
tags: [FCC/JavaScript/Basic_Algorithm_Scripting/140_Repeat_a_String]
---
Repeat a given string `str` (first argument) for `num` times (second argument). Return an empty string if `num` is not a positive number. For the purpose of this challenge, do _not_ use the built-in `.repeat()` method.

```js
function repeatStringNumTimes(str, num) {
  let repeatedString = "";
  if (num > 0) {
    for (let i = num; i > 0; i -=1) {
          repeatedString += str;
                                    }
              }
  return repeatedString;        
                                        }

console.log(repeatStringNumTimes("abc", 3));
```

And some other methods I found online [here](https://www.freecodecamp.org/news/three-ways-to-repeat-a-string-in-javascript-2a9053b93a2d/):

### While 
```js
function repeatStringNumTimes(string, times) {
  var repeatedString = "";
  while (times > 0) {
    repeatedString += string;
    times--;
  }
  return repeatedString;
}
repeatStringNumTimes("abc", 3);
```

### Recursion
```js
function repeatStringNumTimes(string, times) {
  if(times < 0) 
    return "";
  if(times === 1) 
    return string;
  else 
    return string + repeatStringNumTimes(string, times - 1);
}
repeatStringNumTimes("abc", 3);
```
