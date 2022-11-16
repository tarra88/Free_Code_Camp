---
tags: FCC/JavaScript/ES6/68_Handle_a_Rejected_Promise_with_catch
---
`catch` is the method used when your promise has been rejected. It is executed immediately after a promise's `reject` method is called. Here’s the syntax:

```js
myPromise.catch(error => {
  
});
```

`error` is the argument passed in to the `reject` method.