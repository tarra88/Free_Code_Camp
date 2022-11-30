---
tags: [FCC/JavaScript/Object_Oriented_Programming/152_Create_a_Method_of_an_Object]
---
Objects can have a special type of property, called a method.

Methods are properties that are functions. This adds different behavior to an object. Here is the `duck` example with a method:

```js
let duck = {
  name: "Aflac",
  numLegs: 2,
  sayName: function() {return "The name of this duck is " + duck.name + ".";}
};
duck.sayName();
```

