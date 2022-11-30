---
tags: [FCC/JavaScript/Object_Oriented_Programming/163_Remember_Set_Constructor_Property_when_Changing_Prototype]
---
There is one crucial side effect of manually setting the prototype to a new object. It erases the `constructor` property! This property can be used to check which constructor function created the instance, but since the property has been overwritten, it now gives false results:

```js
duck.constructor === Bird;
duck.constructor === Object;
duck instanceof Bird;
```

In order, these expressions would evaluate to `false`, `true`, and `true`.

To fix this, whenever a prototype is manually set to a new object, remember to define the `constructor` property:

```js
Bird.prototype = {
  constructor: Bird,
  numLegs: 2,
  eat: function() {
    console.log("nom nom nom");
  },
  describe: function() {
    console.log("My name is " + this.name); 
  }
};
```