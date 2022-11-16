---
tags: [FCC/JavaScript/Basic_JavaScript/33_Memorise]
---
## Profile Lookup

We have an array of objects representing different people in our contacts lists.

A lookUpProfile function that takes name and a property (prop) as arguments has been pre-written for you.

The function should check if name is an actual contact's firstName and the given property (prop) is a property of that contact.

If both are true, then return the "value" of that property.

If name does not correspond to any contacts then return the string No such contact.

If prop does not correspond to any valid properties of a contact found to match name then return the string No such property.

```js

// Setup

const contacts = [

  {

    firstName: "Akira",

    lastName: "Laine",

    number: "0543236543",

    likes: ["Pizza", "Coding", "Brownie Points"],

  },

  {

    firstName: "Harry",

    lastName: "Potter",

    number: "0994372684",

    likes: ["Hogwarts", "Magic", "Hagrid"],

  },

  {

    firstName: "Sherlock",

    lastName: "Holmes",

    number: "0487345643",

    likes: ["Intriguing Cases", "Violin"],

  },

  {

    firstName: "Kristian",

    lastName: "Vos",

    number: "unknown",

    likes: ["JavaScript", "Gaming", "Foxes"],

  },

];

  

function lookUpProfile(name, prop) {

  // Only change code below this line

  

  // Only change code above this line

}

  

lookUpProfile("Akira", "likes");

```

### Solution 1:

```js

function lookUpProfile(name, prop) {

  for (let x = 0; x < contacts.length; x++) {

    if (contacts[x].firstName === name) {

      if (contacts[x].hasOwnProperty(prop)) {

        return contacts[x][prop];

      } else {

        return "No such property";

      }

    }

  }

  return "No such contact";

}

```

#### Code Explanation

- The for loop runs, starting at the first object in the contacts list.

- If the firstName parameter passed into the function matches the value of the "firstName" key in the first object, the if statement passes.

- Then, we use .hasOwnProperty() method (checks if there’s a given property and returns a boolean) with prop as an argument. If it’s true, the value of prop is returned.

- If the second if statement fails, No such property is returned.

- If the first if statement fails, the for loop continues on to the next object in the contacts list.

- If the firstName parameter isn’t matched by the final contacts object, the for loop exits and No such contact is returned.

### Solution 2:

```js

function lookUpProfile(name, prop) {

  for (let i = 0; i < contacts.length; i++) {

    if (contacts[i].firstName === name) {

      if (prop in contacts[i]) {

        return contacts[i][prop];

      } else {

        return "No such property";

      }

    }

  }

  return "No such contact";

}

```

#### Code Explanation

- This works as the last example but uses the in operator to look for prop instead of the hasOwnProperty() method.

### Tests

- lookUpProfile("Kristian", "lastName") should return the string Vos

- lookUpProfile("Sherlock", "likes") should return ["Intriguing Cases", "Violin"]

- lookUpProfile("Harry", "likes") should return an array

- lookUpProfile("Bob", "number") should return the string No such contact

- lookUpProfile("Bob", "potato") should return the string No such contact

- lookUpProfile("Akira", "address") should return the string No such property