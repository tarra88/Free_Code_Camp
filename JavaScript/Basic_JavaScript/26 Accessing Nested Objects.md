---
tags: [FCC/JavaScript/Basic_JavaScript/26_Accessing_Nested_Objects]
---
The sub-properties of objects can be accessed by chaining together the dot or bracket notation.

Here is a nested object:

```js

const ourStorage = {

  "desk": {

    "drawer": "stapler"

  },

  "cabinet": {

    "top drawer": {

      "folder1": "a file",

      "folder2": "secrets"

    },

    "bottom drawer": "soda"

  }

};

  

ourStorage.cabinet["top drawer"].folder2;

ourStorage.desk.drawer;

```

Exercise:

```js

const myPlants = [

  {

    type: "flowers",

    list: [

      "rose",

      "tulip",

      "dandelion"

    ]

  },

  {

    type: "trees",

    list: [

      "fir",

      "pine",

      "birch"

    ]

  }

];

  

const secondTree = myPlants[1].list[1];

```