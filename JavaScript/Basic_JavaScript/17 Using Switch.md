---
tags: [FCC/JavaScript/Basic_JavaScript/17_Using_Switch]
---
```js

function switchOfStuff(val) {

  let answer = "";

switch (val) {

  case "a":

    answer = "apple";

    break;

  case "b":

    answer = "bird";

    break;

  case "c":

    answer = "cat";

    break;

  default:

    answer = "stuff";

    break;

}

  return answer;

}

  

switchOfStuff(1);

```

And using default:

```js

function chainToSwitch(val) {

  let answer = "";

switch (val) {

  case "bob":

    answer = "Marley";

    break;

  case 42:

    answer = "The Answer";

    break;

  case 1:

    answer = "There is no #1";

    break;

  case 99:

    answer = "Missed me by this much!";

    break;

  case 7:

    answer = "Ate Nine";

    break;

  default:

    answer = "";

}

  return answer;

}

  

chainToSwitch(7);

```