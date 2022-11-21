---
tags: [FCC/JavaScript/Basic_Data_Structures/130_Check_if_an_Object_has_a_Property]
---
Now we can add, modify, and remove keys from objects. But what if we just wanted to know if an object has a specific property? JavaScript provides us with two different ways to do this. One uses the `hasOwnProperty()` method and the other uses the `in` keyword. If we have an object `users` with a property of `Alan`, we could check for its presence in either of the following ways:

```js
users.hasOwnProperty('Alan');
'Alan' in users;
```

Both of these would return `true`.

---
#### Exercise:

Finish writing the function so that it returns `true` if the object passed to it contains all four names, `Alan`, `Jeff`, `Sarah` and `Ryan` and returns `false` otherwise.

**This didn't work** 
```js
let users = {

  Alan: {

    age: 27,

    online: true

  },

  Jeff: {

    age: 32,

    online: true

  },

  Sarah: {

    age: 48,

    online: true

  },

  Ryan: {

    age: 19,

    online: true

  }

};

  

function isEveryoneHere(userObj) {

  // Only change code below this line

  if (

 ('Ryan', 'Alan', 'Sarah', 'Jeff') in users) 

 return true; {

   return false;

```
Didn't work. As would still return "true" if one of the members wasn't present. I tried changing `,` to `+` and also `&&` but these also didn't work. Edit: Oh I just realized that maybe I should try putting `userObj` instead of `users`! 

~~**This also didn't work**~~ (update: see final entry at the end of this page).
```js
function isEveryoneHere(userObj) {

  // Only change code below this line

  if (

 users.hasOwnProperty('Alan') && users.hasOwnProperty('Ryan') && users.hasOwnProperty('Jeff') && users.hasOwnProperty('Sarah')) 

 return true; {

   return false;

 } 

  // Only change code above this line

}
```
This also didn't work, as got the error "The `users` object should not be accessed directly".

**And... this didn't work** 
```js
function isEveryoneHere(userObj) {

  // Only change code below this line

 let everyone = ('Alan', 'Jeff', 'Sarah', 'Ryan');

   if (

 users.hasOwnProperty(everyone)) 

 return true; {

   return false;

 } 

  // Only change code above this line

}
```

I looked online, and got [this](https://www.youtube.com/watch?v=S08t6oz00Ew), which surprisingly also didn't work! Same error  "The `users` object should not be accessed directly".

```js
function isEveryoneHere(userObj) {

  // Only change code below this line

 let everyone = ['Alan', 'Jeff', 'Sarah', 'Ryan'];

 for (let i = 0; i < everyone.length; i++) {

   let student = everyone[i];

   if (users.hasOwnProperty(student) === false) {

   return false;

 }

 return true; {

  

 } 

 }

  // Only change code above this line

}

  

console.log(isEveryoneHere(users));
```

Then I watched a more recent video and suddenly realized that I was using `users` instead of `userObj`!!! OMG. So I went back to my first attempt and tried that - it still didn't work. But my 2nd attempt did! So this was correct once I put in the right word `userObj`:
```js
  if (

 userObj.hasOwnProperty('Alan') && userObj.hasOwnProperty('Ryan') && userObj.hasOwnProperty('Jeff') && userObj.hasOwnProperty('Sarah')) 

 return true; {

   return false;

 } 
```
