---
tags: [FCC/JavaScript/Basic_JavaScript/25_Testing_Objects_for_Properties]
---
Sometimes it is useful to check if the property of a given object exists or not. We can use the .hasOwnProperty(propname) method of objects to determine if that object has the given property name. .hasOwnProperty() returns true or false if the property is found or not.

Example

```js

const myObj = {

  top: "hat",

  bottom: "pants"

};

  

myObj.hasOwnProperty("top");

myObj.hasOwnProperty("middle");

```

The first hasOwnProperty returns true, while the second returns false.