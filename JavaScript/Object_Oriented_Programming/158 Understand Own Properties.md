---
tags: [FCC/JavaScript/Object_Oriented_Programming/158_Understand_Own_Properties]
---
In the following example, the `Bird` constructor defines two properties: `name` and `numLegs`:

```js
function Bird(name) {
  this.name = name;
  this.numLegs = 2;
}

let duck = new Bird("Donald");
let canary = new Bird("Tweety");
```

`name` and `numLegs` are called own properties, because they are defined directly on the instance object. That means that `duck` and `canary` each has its own separate copy of these properties. In fact every instance of `Bird` will have its own copy of these properties. The following code adds all of the own properties of `duck` to the array `ownProps`:

```js
let ownProps = [];

for (let property in duck) {
  if(duck.hasOwnProperty(property)) {
    ownProps.push(property);
  }
}

console.log(ownProps);
```

The console would display the value `["name", "numLegs"]`.
