---
Tags: FCC/JavaScript/ES6/53_Destructuring_Assignment_to_Pass_Object_as_Functions_Parameters
---
In some cases, you can destructure the object in a function argument itself.

Consider the code below:

```js

const profileUpdate = (profileData) => {

  const { name, age, nationality, location } = profileData;

  

}

```

This effectively destructures the object sent into the function. This can also be done in-place:

```js

const profileUpdate = ({ name, age, nationality, location }) => {

  

}

```

When `profileData` is passed to the above function, the values are destructured from the function parameter for use within the function.