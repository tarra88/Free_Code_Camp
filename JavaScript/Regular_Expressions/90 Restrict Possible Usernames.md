---
tags: [FCC/JavaScript/Regular_Expressions/90_Restrict_Possible_Usernames]
---
Usernames are used everywhere on the internet. They are what give users a unique identity on their favorite sites.

You need to check all the usernames in a database. Here are some simple rules that users have to follow when creating their username.

1.  Usernames can only use alpha-numeric characters. `^[a-z]`
2.  The only numbers in the username have to be at the end so we use:  `\d` There can be zero or more of them at the end, so we use: `*`, along with `$` do designate the end. Username cannot start with the number. 
3.  Username letters can be lowercase and uppercase. *(i flag)*
4.  Usernames have to be at least two characters long. A two-character username can only use alphabet letters as characters. `/^[a-z][a-z]+\d$|^[a-z]\d\d+$/i`

Thinking for point 4:
```js
/*
aa is permitted (two character usernames)
or aba3 (more than two characters, with number alowed at the end)
but not: a11 (less than 2 alphabet characters at the beginning)
*/
```

---

Change the regex `userCheck` to fit the constraints listed above.

```js
let username = "JackOfAllTrades";

let userCheck = /^[a-z][a-z]+\d*$|^[a-z]\d\d+$/i; // Change this line

let result = userCheck.test(username);
```
