---
tags: [FCC/JavaScript/Basic_JavaScript/22_Accessing_Object_Properties_with_Variables]
---
Another use of bracket notation on objects is to access a property which is stored as the value of a variable. This can be very useful for iterating through an object's properties or when accessing a lookup table.

Here is an example of using a variable to access a property:

```js

const dogs = {

  Fido: "Mutt",

  Hunter: "Doberman",

  Snoopie: "Beagle"

};

  

const myDog = "Hunter";

const myBreed = dogs[myDog];

console.log(myBreed);

```

The string Doberman would be displayed in the console.