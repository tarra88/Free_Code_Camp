# Comments in JavaScript
Comments are lines of code that JavaScript will intentionally ignore. Comments are a great way to leave notes to yourself and to other people who will later need to figure out what that code does.

There are two ways to write comments in JavaScript:

Using // will tell JavaScript to ignore the remainder of the text on the current line. This is an in-line comment:

```javascript
// This is an in-line comment.
```
You can make a multi-line comment beginning with /* and ending with */. This is a multi-line comment:
```js
/* This is a
multi-line comment */
```
It appears that both "javascript" and "js" work in markdown to label code as JavaScript.

# Set Variables
Set like this:
```js
var myVar;
```
Then give myVar a value by:
```js
myVar = 5;
```
Or you can initialize a variable with an initial value:
```js
var myVar = 24;
```
You can initialize a variable using any of the 8 data types:  undefined, null, boolean, string, symbol, bigint, number, and object.
```js
var myName = "your name";
```
## Understanding Uninitialized Variables
When JavaScript variables are declared, they have an initial value of undefined. If you do a mathematical operation on an undefined variable your result will be NaN which means "Not a Number". If you concatenate a string with an undefined variable, you will get a string of undefined.

## Capitalization Matters
Best Practice

Write variable names in JavaScript in camelCase. In camelCase, multi-word variable names have the first word in lowercase and the first letter of each subsequent word is capitalized.

Examples:
```js
var someVariable;
var anotherVariableName;
var thisVariableNameIsSoLong;
```
## Using let instead of var
Using var it is easy to accidently overwrite a variable which you don't realize you've already used. To avoid this error you can use let. When using let a variable with the same name can only be declared once (so if you try to overwrite it later you'll raise an error).
```js
let camper = "James";
```
## Using const
const has all the awesome features that let has, with the added bonus that variables declared using const are read-only. They are a constant value, which means that once a variable is assigned with const, it cannot be reassigned.
```js
const FAV_PET = "Cats";
```
Note: It is common for developers to use uppercase variable identifiers for immutable values and lowercase or camelCase for mutable values (objects and arrays).
# Increment a Number
You can easily increment or add one to a variable with the ++ operator.
```js
i++;
```
is the equivalent of
```js
i = i + 1;
```
Note: The entire line becomes i++;, eliminating the need for the equal sign.

Same for decreasing by 1. E.g.
```js
i--; == i = i - 1;
```
## Floaties
Decimal numbers are sometimes referred to as floating point numbers or floats.

### Remainder
Remainder is not the same as modulus. It is similar to modulus but doesn't work with negative numbers. Remainder is found by using % instead of /. i.e.
```js
const remainder = 11 % 3;
```
# Compound Assignments
It is really common to use assignments to modify variables, e.g.:
```js
myVar = myVar + 5;
```
So a shorter way of writing this is:
```js
myVar += 5;
```
Similarly, -= will subtract.
```js
myVar -=5; == myVar = myVar = 5;
```
and *=
```js
myVar *= 5;
```
and /=
```js
myVar /= 5;
```
# Escape Sequences in Strings
```
Code	Output
\'	single quote
\"	double quote
\\	backslash
\n	newline
\t	tab
\r	carriage return
\b	word boundary
\f	form feed
```
# Concatenating Strings
In JavaScript, when the + operator is used with a String value, it is called the concatenation operator. You can build a new string out of other strings by concatenating them together.

# Zero based indexing
A programming language that starts counting at 0, not at 1. E.g.
```js
const firstName = "Charles";
const firstLetter = firstName[0];
```
This would return "C".

# Bracket notation to find last letter in a string
```js
const firstName = "Ada";
const lastLetter = firstName[firstName.length - 1];
```
lastLetter would have a value of the string 'a'.

# Arrays
You can nest arrays within other arrays:

Unlike strings, the entries of arrays are mutable and can be changed freely, even if the array was declared with const.

One way to think of a multi-dimensional array, is as an array of arrays. When you use brackets to access your array, the first set of brackets refers to the entries in the outer-most (the first level) array, and each additional pair of brackets refers to the next level of entries inside.

Example
```js
const arr = [
  [1, 2, 3],
  [4, 5, 6],
  [7, 8, 9],
  [[10, 11, 12], 13, 14]
];

const subarray = arr[3];
const nestedSubarray = arr[3][0];
const element = arr[3][0][1];
```
In this example, subarray has the value [[10, 11, 12], 13, 14], nestedSubarray has the value [10, 11, 12], and element has the value 11 .

## Push
.push will add data to the end of the array.
```js
const arr2 = ["Stimpson", "J", "cat"];
arr2.push(["happy", "joy"]);
```
arr2 now has the value ["Stimpson", "J", "cat", ["happy", "joy"]].

## Pop
.pop removes the last value of an array. This can be stored by assigning it to a variable. E.g.
```js
const threeArr = [1, 4, 6];
const oneDown = threeArr.pop();
```
oneDown = 6

## Shift
The opposite to this is shift, which removes the first value from the array.

unshift works like push, but adds elements to the beginning of an array, not the end.

# Functions
In JavaScript, we can divide up our code into reusable parts called functions.

Here's an example of a function:
```js
function functionName() {
  console.log("Hello World");
}
```
You can call or invoke this function by using its name followed by parentheses, like this: functionName();

## Parameters
Parameters are variables that act as placeholders for the values that are to be input to a function when it is called.

Here is a function with two parameters, param1 and param2:
```js
function testFun(param1, param2) {
  console.log(param1, param2);
}
```
Then we can call testFun like this: testFun("Hello", "World");

We can pass values into a function with arguments. You can use a return statement to send a value back out of a function.

Example
```js
function plusThree(num) {
  return num + 3;
}
```
const answer = plusThree(5);

answer has the value 8.

## Global Scope
In JavaScript, scope refers to the visibility of variables. Variables which are defined outside of a function block have Global scope. This means, they can be seen everywhere in your JavaScript code.

Variables which are declared without the let or const keywords are automatically created in the global scope. This can create unintended consequences elsewhere in your code or when running a function again. You should always declare your variables with let or const.

## Local Scope
Variables which are declared within a function, as well as the function parameters, have local scope. That means they are only visible within that function.

It is possible to have both local and global variables with the same name. When you do this, the local variable takes precedence over the global variable.

In this example:
```js
const someVar = "Hat";

function myFun() {
  const someVar = "Head";
  return someVar;
}
```
The function myFun will return the string Head because the local version of the variable is present.
```js
let processed = 0;

function processArg(num) {
  return (num + 3) / 5;
}

processed = processArg(7);

console.log(processed) // will return the new value for processed, i.e. 2
```
## Strict Equality Operator
Strict equality (===) is the counterpart to the equality operator (==). However, unlike the equality operator, which attempts to convert both values being compared to a common type, the strict equality operator does not perform a type conversion.

If the values being compared have different (data) types, they are considered unequal, and the strict equality operator will return false.

Examples
```js
3 ===  3  // true
3 === '3' // false
```
3 == '3' returns true because JavaScript performs type conversion from string to number. 3 === '3' returns false because the types are different and type conversion is not performed.

## typeof
You can determine the type of a variable or a value with the 'typeof' operator.

## Inequality Operator
The inequality operator (!=) is the opposite of the equality operator. It means not equal and returns false where equality would return true and vice versa. Like the equality operator, the inequality operator will convert data types of values while comparing.

Examples
```js
1 !=  2    // true
1 != "1"   // false
1 != '1'   // false
1 != true  // false
0 != false // false
```
```js
function testNotEqual(val) {
  if (val != 99) { 
    return "Not Equal";
  }
  return "Equal";
}

testNotEqual(10);
```
The strict inequality operator (!==) is the logical opposite of the strict equality operator. It means "Strictly Not Equal" and returns false where strict equality would return true and vice versa. The strict inequality operator will not convert data types.

Examples
```js
3 !==  3  // false
3 !== '3' // true
4 !==  3  // true
```
The greater than '>' and less than '<' operators also return true or false, converting data types of values when comparing.

Also the same for greater than or equal operator (>=).

## Comparisons with the Logical and Operator, or using &&
Sometimes you will need to test more than one thing at a time. The logical and operator (&&) returns true if and only if the operands to the left and right of it are true.

The same effect could be achieved by nesting an if statement inside another if:
```js
if (num > 5) {
  if (num < 10) {
    return "Yes";
  }
}
return "No";
```
will only return Yes if num is greater than 5 and less than 10. The same logic can be written as:
```js
if (num > 5 && num < 10) {
  return "Yes";
}
return "No";
```
The logical or operator (||) returns true if either of the operands is true. Otherwise, it returns false.

The pattern below should look familiar from prior waypoints:
```js
if (num > 10) {
  return "No";
}
if (num < 5) {
  return "No";
}
return "Yes";
```
will return Yes only if num is between 5 and 10 (5 and 10 included). The same logic can be written as:
```js
if (num > 10 || num < 5) {
  return "No";
}
return "Yes";
```
# Else Statements
When a condition for an if statement is true, the block of code following it is executed. What about when that condition is false? Normally nothing would happen. With an else statement, an alternate block of code can be executed.

If you have multiple conditions that need to be addressed, you can chain if statements together with else if statements.
```js
if (num > 15) {
  return "Bigger than 15";
} else if (num < 5) {
  return "Smaller than 5";
} else {
  return "Between 5 and 15";
}
```
## Using Switch
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
# Returning Boolean Values from Functions
Sometimes people use an if/else statement to do a comparison, like this:
```js
function isEqual(a, b) {
  if (a === b) {
    return true;
  } else {
    return false;
  }
}
```
But there's a better way to do this. Since === returns true or false, we can return the result of the comparison:
```js
function isEqual(a, b) {
  return a === b;
}
```
# Build Javascript Objects
Objects are similar to arrays, except that instead of using indexes to access and modify their data, you access the data in objects through what are called properties.

Objects are useful for storing data in a structured way, and can represent real world objects, like a cat.

Here's a sample cat object:
```js
const cat = {
  "name": "Whiskers",
  "legs": 4,
  "tails": 1,
  "enemies": ["Water", "Dogs"]
};
```
In this example, all the properties are stored as strings, such as name, legs, and tails. However, you can also use numbers as properties. You can even omit the quotes for single-word string properties.
## Accessing Object Properties with Dot Notation
Accessing Object Properties with Dot Notation
There are two ways to access the properties of an object: dot notation (.) and bracket notation ([]), similar to an array.

Dot notation is what you use when you know the name of the property you're trying to access ahead of time.

Here is a sample of using dot notation (.) to read an object's property:
```js
const myObj = {
  prop1: "val1",
  prop2: "val2"
};

const prop1val = myObj.prop1;
const prop2val = myObj.prop2;
```
prop1val would have a value of the string val1, and prop2val would have a value of the string val2.
## Accessing Object Properties with Bracket Notation
Accessing Object Properties with Bracket Notation
The second way to access the properties of an object is bracket notation ([]). If the property of the object you are trying to access has a space in its name, you will need to use bracket notation.

However, you can still use bracket notation on object properties without spaces.

Here is a sample of using bracket notation to read an object's property:
```js
const myObj = {
  "Space Name": "Kirk",
  "More Space": "Spock",
  "NoSpace": "USS Enterprise"
};

myObj["Space Name"];
myObj['More Space'];
myObj["NoSpace"];
```
myObj["Space Name"] would be the string Kirk.
## Accessing Object Properties with Variables
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
## Updating Object Properties
After you've created a JavaScript object, you can update its properties at any time just like you would update any other variable. You can use either dot or bracket notation to update.

For example, let's look at ourDog:
```js
const ourDog = {
  "name": "Camper",
  "legs": 4,
  "tails": 1,
  "friends": ["everything!"]
};
```
Since he's a particularly happy dog, let's change his name to the string Happy Camper. Here's how we update his object's name property: ourDog.name = "Happy Camper"; or ourDog["name"] = "Happy Camper"; Now when we evaluate ourDog.name, instead of getting Camper, we'll get his new name, Happy Camper.
## Delete Properties from a JavaScript Object
We can also delete properties from objects like this:
```js
delete ourDog.bark;
```
Example:
```js
const ourDog = {
  "name": "Camper",
  "legs": 4,
  "tails": 1,
  "friends": ["everything!"],
  "bark": "bow-wow"
};

delete ourDog.bark;
```
## Testing Objects for Properties
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
## Accessing Nested Objects
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
# Iterate with JavaScript While Loops
You can run the same code multiple times by using a loop.

The first type of loop we will learn is called a while loop because it runs while a specified condition is true and stops once that condition is no longer true.
```js
const ourArray = [];
let i = 0;

while (i < 5) {
  ourArray.push(i);
  i++;
}
```
In the code example above, the while loop will execute 5 times and append the numbers 0 through 4 to ourArray.
# Iterate with JavaScript For Loops
You can run the same code multiple times by using a loop.

The most common type of JavaScript loop is called a for loop because it runs for a specific number of times.

For loops are declared with three optional expressions separated by semicolons:

for (a; b; c), where a is the initialization statement, b is the condition statement, and c is the final expression.

The initialization statement is executed one time only before the loop starts. It is typically used to define and setup your loop variable.

The condition statement is evaluated at the beginning of every loop iteration and will continue as long as it evaluates to true. When the condition is false at the start of the iteration, the loop will stop executing. This means if the condition starts as false, your loop will never execute.

The final expression is executed at the end of each loop iteration, prior to the next condition check and is usually used to increment or decrement your loop counter.

In the following example we initialize with i = 0 and iterate while our condition i < 5 is true. We'll increment i by 1 in each loop iteration with i++ as our final expression.
```js
const ourArray = [];

for (let i = 0; i < 5; i++) {
  ourArray.push(i);
}
```
ourArray will now have the value [0, 1, 2, 3, 4].

We'll start at i = 0 and loop while i < 10. We'll increment i by 2 each loop with i += 2.
```js
const ourArray = [];

for (let i = 0; i < 10; i += 2) {
  ourArray.push(i);
}
```
ourArray will now contain [0, 2, 4, 6, 8]. 
# Iterate Through an Array with a For Loop
A common task in JavaScript is to iterate through the contents of an array. One way to do that is with a for loop. This code will output each element of the array arr to the console:
```js
const arr = [10, 9, 8, 7, 6];

for (let i = 0; i < arr.length; i++) {
   console.log(arr[i]);
}
```
Remember that arrays have zero-based indexing, which means the last index of the array is length - 1. Our condition for this loop is i < arr.length, which stops the loop when i is equal to length. In this case the last iteration is i === 4 i.e. when i becomes equal to arr.length - 1 and outputs 6 to the console. Then i increases to 5, and the loop terminates because i < arr.length is false.
# Nesting for Loops
If you have a multi-dimensional array, you can use the same logic as the prior waypoint to loop through both the array and any sub-arrays. Here is an example:
```js
const arr = [
  [1, 2], [3, 4], [5, 6]
];

for (let i = 0; i < arr.length; i++) {
  for (let j = 0; j < arr[i].length; j++) {
    console.log(arr[i][j]);
  }
}
```
This outputs each sub-element in arr one at a time. Note that for the inner loop, we are checking the .length of arr[i], since arr[i] is itself an array.

### Exercise: 
Modify function multiplyAll so that it returns the product of all the numbers in the sub-arrays of arr.
```js
function multiplyAll(arr) {
  var product = 1;
  // Only change code below this line
  for (var i = 0; i < arr.length; i++) { // starts with the first number in the array and continues to the last number (as it only continues while i is less than the number of items in the array)
    for (var j = 0; j < arr[i].length; j++) { // this is the same for the arrays within the main array. For each number of the array it goes through this.
      product = product * arr[i][j]; // this multiplies each number in each array together, then the totals against each other.
    }
  }
  // Only change code above this line
  return product;
}

// Modify values below to test your code
multiplyAll([[1, 2], [3, 4], [5, 6, 7]]);
```
# Iterate with JavaScript Do...While Loops
The next type of loop you will learn is called a do...while loop. It is called a do...while loop because it will first do one pass of the code inside the loop no matter what, and then continue to run the loop while the specified condition evaluates to true.
```js
const ourArray = [];
let i = 0;

do {
  ourArray.push(i);
  i++;
} while (i < 5);
```
The example above behaves similar to other types of loops, and the resulting array will look like [0, 1, 2, 3, 4]. However, what makes the do...while different from other loops is how it behaves when the condition fails on the first check. Let's see this in action. Here is a regular while loop that will run the code in the loop as long as i < 5:
```js
const ourArray = []; 
let i = 5;

while (i < 5) {
  ourArray.push(i);
  i++;
}
```
In this example, we initialize the value of ourArray to an empty array and the value of i to 5. When we execute the while loop, the condition evaluates to false because i is not less than 5, so we do not execute the code inside the loop. The result is that ourArray will end up with no values added to it, and it will still look like [] when all of the code in the example above has completed running. Now, take a look at a do...while loop:
```js
const ourArray = []; 
let i = 5;

do {
  ourArray.push(i);
  i++;
} while (i < 5);
```
In this case, we initialize the value of i to 5, just like we did with the while loop. When we get to the next line, there is no condition to evaluate, so we go to the code inside the curly braces and execute it. We will add a single element to the array and then increment i before we get to the condition check. When we finally evaluate the condition i < 5 on the last line, we see that i is now 6, which fails the conditional check, so we exit the loop and are done. At the end of the above example, the value of ourArray is [5]. Essentially, a do...while loop ensures that the code inside the loop will run at least once. Let's try getting a do...while loop to work by pushing values to an array.
# Replace Loops using Recursion
Recursion is the concept that a function can be expressed in terms of itself. To help understand this, start by thinking about the following task: multiply the first n elements of an array to create the product of those elements. Using a for loop, you could do this:
```js
  function multiply(arr, n) {
    let product = 1;
    for (let i = 0; i < n; i++) {
      product *= arr[i];
    }
    return product;
  }
```
However, notice that multiply(arr, n) == multiply(arr, n - 1) * arr[n - 1]. That means you can rewrite multiply in terms of itself and never need to use a loop.
```js
  function multiply(arr, n) {
    if (n <= 0) {
      return 1;
    } else {
      return multiply(arr, n - 1) * arr[n - 1];
    }
  }
```
The recursive version of multiply breaks down like this. In the base case, where n <= 0, it returns 1. For larger values of n, it calls itself, but with n - 1. That function call is evaluated in the same way, calling multiply again until n <= 0. At this point, all the functions can return and the original multiply returns the answer.

Note: Recursive functions must have a base case when they return without calling the function again (in this example, when n <= 0), otherwise they can never finish executing.
# Exercise: To memorise:
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
# Generate Random Fractions with JavaScript
Random numbers are useful for creating random behavior.

JavaScript has a Math.random() function that generates a random decimal number between 0 (inclusive) and 1 (exclusive). Thus Math.random() can return a 0 but never return a 1.

Note: Like Storing Values with the Assignment Operator, all function calls will be resolved before the return executes, so we can return the value of the Math.random() function.
## Exercise: Change randomFraction to return a random number instead of returning 0.
function randomFraction() {
return 1 - Math.random();
}
# Generate Random Whole Numbers with JavaScript
It's great that we can generate random decimal numbers, but it's even more useful if we use it to generate random whole numbers.

1. Use Math.random() to generate a random decimal.
2. Multiply that random decimal by 20.
3. Use another function, Math.floor() to round the number down to its nearest whole number.

Remember that Math.random() can never quite return a 1 and, because we're rounding down, it's impossible to actually get 20. This technique will give us a whole number between 0 and 19.

Putting everything together, this is what our code looks like:
```js
Math.floor(Math.random() * 20);
```
We are calling Math.random(), multiplying the result by 20, then passing the value to Math.floor() function to round the value down to the nearest whole number.

To return the number in the console you need a "return" like this:
```js
function randomWholeNum() {
  return Math.floor(Math.random() * 10);
}
console.log(randomWholeNum())
```
## Generate Random Whole Numbers within a Range
Instead of generating a random whole number between zero and a given number like we did before, we can generate a random whole number that falls within a range of two specific numbers.

To do this, we'll define a minimum number min and a maximum number max.

Here's the formula we'll use. Take a moment to read it and try to understand what this code is doing:
```js
Math.floor(Math.random() * (max - min + 1)) + min
```
# Use the parseInt Function
The parseInt() function parses a string and returns an integer. Here's an example:
```js
const a = parseInt("007");
```
The above function converts the string 007 to the integer 7. If the first character in the string can't be converted into a number, then it returns NaN.

As a function:
```js
function convertToInteger(str) {
 return parseInt(str);
}
convertToInteger("56");
```
## Use the parseInt Function with a Radix
The parseInt() function parses a string and returns an integer. It takes a second argument for the radix, which specifies the base of the number in the string. The radix can be an integer between 2 and 36.

The function call looks like:
```js
parseInt(string, radix);
```
And here's an example:
```js
const a = parseInt("11", 2);
```
The radix variable says that 11 is in the binary system, or base 2. This example converts the string 11 to an integer 3.

As a function:
```js
function convertToInteger(str) {
  return parseInt(str, 2);
}
console.log(
convertToInteger("10011"));
```
# Use the Conditional (Ternary) Operator
The conditional operator, also called the ternary operator, can be used as a one line if-else expression.

The syntax is a ? b : c, where a is the condition, b is the code to run when the condition returns true, and c is the code to run when the condition returns false.

The following function uses an if/else statement to check a condition:
```js
function findGreater(a, b) {
  if(a > b) {
    return "a is greater";
  }
  else {
    return "b is greater or equal";
  }
}
```
This can be re-written using the conditional operator:
```js
function findGreater(a, b) {
  return a > b ? "a is greater" : "b is greater or equal";
}
```
## Use Multiple Conditional (Ternary) Operators
In the previous challenge, you used a single conditional operator. You can also chain them together to check for multiple conditions.

The following function uses if, else if, and else statements to check multiple conditions:
```js
function findGreaterOrEqual(a, b) {
  if (a === b) {
    return "a and b are equal";
  }
  else if (a > b) {
    return "a is greater";
  }
  else {
    return "b is greater";
  }
}
```
The above function can be re-written using multiple conditional operators:
```js
function findGreaterOrEqual(a, b) {
  return (a === b) ? "a and b are equal" 
    : (a > b) ? "a is greater" 
    : "b is greater";
}
```
It is considered best practice to format multiple conditional operators such that each condition is on a separate line, as shown above.
# Use Recursion to Create a Countdown
In a previous challenge, you learned how to use recursion to replace a for loop. Now, let's look at a more complex function that returns an array of consecutive integers starting with 1 through the number passed to the function.

As mentioned in the previous challenge, there will be a base case. The base case tells the recursive function when it no longer needs to call itself. It is a simple case where the return value is already known. There will also be a recursive call which executes the original function with different arguments. If the function is written correctly, eventually the base case will be reached.

For example, say you want to write a recursive function that returns an array containing the numbers `1` through `n`. This function will need to accept an argument, `n`, representing the final number. Then it will need to call itself with progressively smaller values of n until it reaches 1. You could write the function as follows:
```js
function countup(n) {
  if (n < 1) {
    return [];
  } else {
    const countArray = countup(n - 1);
    countArray.push(n);
    return countArray;
  }
}
console.log(countup(5));
```
The value `[1, 2, 3, 4, 5]` will be displayed in the console.

At first, this seems counterintuitive since the value of n decreases, but the values in the final array are increasing. This happens because the push happens last, after the recursive call has returned. At the point where n is pushed into the array, `countup(n - 1)` has already been evaluated and returned `[1, 2, ..., n - 1]`.

To do the reverse, i.e. countdown, we'd need to use `unshift` rather than `push`.
# Use Recursion to Create a Range of Numbers
(Exercise from FCC)
```js
function rangeOfNumbers(startNum, endNum) {
  if (endNum < startNum) {
    return [];
  } else {
  var countArray = rangeOfNumbers(startNum, endNum - 1);
  countArray.push(endNum);
  return countArray;
  }
};
console.log(rangeOfNumbers(1,5));
```
# ES6
## Compare Scopes of the var and let Keywords
If you are unfamiliar with `let`, check out this challenge about the difference between `let` and `var`.

When you declare a variable with the `var` keyword, it is declared globally, or locally if declared inside a function.

The `let` keyword behaves similarly, but with some extra features. When you declare a variable with the `let` keyword inside a block, statement, or expression, its scope is limited to that block, statement, or expression.

For example:
```js
var numArray = [];
for (var i = 0; i < 3; i++) {
  numArray.push(i);
}
console.log(numArray);
console.log(i);
```
Here the console will display the values `[0, 1, 2]` and `3`.

With the `var` keyword, `i` is declared globally. So when `i++` is executed, it updates the global variable. This code is similar to the following:
```js
var numArray = [];
var i;
for (i = 0; i < 3; i++) {
  numArray.push(i);
}
console.log(numArray);
console.log(i);
```
Here the console will display the values `[0, 1, 2]` and `3`.

This behavior will cause problems if you were to create a function and store it for later use inside a for loop that uses the `i` variable. This is because the stored function will always refer to the value of the updated global `i` variable.
```js
var printNumTwo;
for (var i = 0; i < 3; i++) {
  if (i === 2) {
    printNumTwo = function() {
      return i;
    };
  }
}
console.log(printNumTwo());
```
Here the console will display the value `3`.

As you can see, `printNumTwo()` prints 3 and not 2. This is because the value assigned to `i` was updated and the `printNumTwo()` returns the global `i` and not the value `i` had when the function was created in the for loop. The `let` keyword does not follow this behavior:
```js
let printNumTwo;
for (let i = 0; i < 3; i++) {
  if (i === 2) {
    printNumTwo = function() {
      return i;
    };
  }
}
console.log(printNumTwo());
console.log(i);
```
Here the console will display the value `2`, and an error that `i is not defined`.

`i` is not defined because it was not declared in the global scope. It is only declared within the `for` loop statement. `printNumTwo()` returned the correct value because three different `i` variables with unique values (0, 1, and 2) were created by the `let` keyword within the loop statement.

## Mutate an Array Declared with const
If you are unfamiliar with const, check out this challenge about the `const` keyword.

The `const` declaration has many use cases in modern JavaScript.

Some developers prefer to assign all their variables using `const` by default, unless they know they will need to reassign the value. Only in that case, they use `let`.

However, it is important to understand that objects (including arrays and functions) assigned to a variable using `const` are still mutable. Using the `const` declaration only prevents reassignment of the variable identifier.
```js
const s = [5, 6, 7];
s = [1, 2, 3];
s[2] = 45;
console.log(s);
```
`s = [1, 2, 3]` will result in an error. After commenting out that line, the `console.log` will display the value `[5, 6, 45]`.

## Prevent Object Mutation
As seen in the previous challenge, const declaration alone doesn't really protect your data from mutation. To ensure your data doesn't change, JavaScript provides a function Object.freeze to prevent data mutation.

Any attempt at changing the object will be rejected, with an error thrown if the script is running in strict mode.
```js
let obj = {
  name:"FreeCodeCamp",
  review:"Awesome"
};
Object.freeze(obj);
obj.review = "bad";
obj.newProp = "Test";
console.log(obj); 
```
The obj.review and obj.newProp assignments will result in errors, because our editor runs in strict mode by default, and the console will display the value { name: "FreeCodeCamp", review: "Awesome" }.

## Use Arrow Functions to Write Concise Anonymous Functions
In JavaScript, we often don't need to name our functions, especially when passing a function as an argument to another function. Instead, we create inline functions. We don't need to name these functions because we do not reuse them anywhere else.

To achieve this, we often use the following syntax:
```js
const myFunc = function() {
  const myVar = "value";
  return myVar;
}
```
ES6 provides us with the syntactic sugar to not have to write anonymous functions this way. Instead, you can use arrow function syntax:
```js
const myFunc = () => {
  const myVar = "value";
  return myVar;
}
```
When there is no function body, and only a return value, arrow function syntax allows you to omit the keyword return as well as the brackets surrounding the code. This helps simplify smaller functions into one-line statements:
```js
const myFunc = () => "value";
```
This code will still return the string `value` by default

## Write Arrow Functions with Parameters
Just like a regular function, you can pass arguments into an arrow function.
```js
const doubler = (item) => item * 2;
doubler(4);
doubler(4) would return the value 8.
```
If an arrow function has a single parameter, the parentheses enclosing the parameter may be omitted.
```js
const doubler = item => item * 2;
```
It is possible to pass more than one argument into an arrow function.
```js
const multiplier = (item, multi) => item * multi;
multiplier(4, 2);
```
`multiplier(4, 2)` would return the value `8`.

The exercise is to rewrite the function into an arrow function:
```js
var myConcat = function(arr1, arr2) {
  return arr1.concat(arr2);
};

const myConcat = (arr1, arr2) => arr1.concat(arr2);
```
## Set Default Parameters for Your Functions
In order to help us create more flexible functions, ES6 introduces default parameters for functions.

Check out this code:
```js
const greeting = (name = "Anonymous") => "Hello " + name;

console.log(greeting("John"));
console.log(greeting());
```
The console will display the strings Hello John and Hello Anonymous.

The default parameter kicks in when the argument is not specified (it is undefined).

## Use the Rest Parameter with Function Parameters
In order to help us create more flexible functions, ES6 introduces the rest parameter for function parameters. With the rest parameter, you can create functions that take a variable number of arguments. These arguments are stored in an array that can be accessed later from inside the function.

Check out this code:
```js
function howMany(...args) {
  return "You have passed " + args.length + " arguments.";
}
console.log(howMany(0, 1, 2));
console.log(howMany("string", null, [1, 2, 3], { }));
```
The console would display the strings `You have passed 3 arguments`. and `You have passed 4 arguments.`.

The rest parameter eliminates the need to check the `args` array and allows us to apply `map()`, `filter()` and `reduce()` on the parameters array.

# Use the Spread Operator to Evaluate Arrays In-Place
ES6 introduces the spread operator, which allows us to expand arrays and other expressions in places where multiple parameters or elements are expected.

The ES5 code below uses apply() to compute the maximum value in an array:
```js
var arr = [6, 89, 3, 45];
var maximus = Math.max.apply(null, arr);
```
`maximus` would have a value of `89`.

We had to use `Math.max.apply(null, arr)` because `Math.max(arr)` returns `NaN`. `Math.max()` expects comma-separated arguments, but not an array. The spread operator makes this syntax much better to read and maintain.
```js
const arr = [6, 89, 3, 45];
const maximus = Math.max(...arr);
```
`maximus` would have a value of `89`.

`...arr` returns an unpacked array. In other words, it spreads the array. However, the spread operator only works in-place, like in an argument to a function or in an array literal. The following code will not work:
```js
const spreaded = ...arr;
```
## Use Destructuring Assignment to Extract Values from Objects
Destructuring assignment is special syntax introduced in ES6, for neatly assigning values taken directly from an object.

Consider the following ES5 code:
```js
const user = { name: 'John Doe', age: 34 };

const name = user.name;
const age = user.age;
```
`name` would have a value of the string `John Doe`, and `age` would have the number `34`.

Here's an equivalent assignment statement using the ES6 destructuring syntax:
```js
const { name, age } = user;
```
Again, `name` would have a value of the string `John Doe`, and `age` would have the number `34`.

Here, the `name` and `age` variables will be created and assigned the values of their respective values from the `user` object. You can see how much cleaner this is.

You can extract as many or few values from the object as you want.

## Use Destructuring Assignment to Assign Variables from Objects
Destructuring allows you to assign a new variable name when extracting values. You can do this by putting the new name after a colon when assigning the value.

Using the same object from the last example:
```js
const user = { name: 'John Doe', age: 34 };
```
Here's how you can give new variable names in the assignment:
```js
const { name: userName, age: userAge } = user;
```
You may read it as "get the value of `user.name` and assign it to a new variable named `userName`" and so on. The value of `userName` would be the string `John Doe`, and the value of `userAge` would be the number `34`.

### Exercise
Replace the two assignments with an equivalent destructuring assignment. It should still assign the variables `highToday` and `highTomorrow` the values of `today` and `tomorrow` from the `HIGH_TEMPERATURES` object.
```js
const HIGH_TEMPERATURES = {
  yesterday: 75,
  today: 77,
  tomorrow: 80
};

// Only change code below this line
  
const highToday = HIGH_TEMPERATURES.today; // existing code
const highTomorrow = HIGH_TEMPERATURES.tomorrow;  // existing code

const { today: highToday, tomorrow: highTomorrow } =  HIGH_TEMPERATURES; // my answer


// Only change code above this line
```
## Use Destructuring Assignment to Assign Variables from Nested Objects
You can use the same principles from the previous two lessons to destructure values from nested objects.

Using an object similar to previous examples:
```js
const user = {
  johnDoe: { 
    age: 34,
    email: 'johnDoe@freeCodeCamp.com'
  }
};
```
Here's how to extract the values of object properties and assign them to variables with the same name:
```js
const { johnDoe: { age, email }} = user; 
```
And here's how you can assign an object properties' values to variables with different names:
```js
const { johnDoe: { age: userAge, email: userEmail }} = user;
```

## Use Destructuring Assignment to Assign Variables from Arrays
ES6 makes destructuring arrays as easy as destructuring objects.

One key difference between the spread operator and array destructuring is that the spread operator unpacks all contents of an array into a comma-separated list. Consequently, you cannot pick or choose which elements you want to assign to variables.

Destructuring an array lets us do exactly that:
```js
const [a, b] = [1, 2, 3, 4, 5, 6];
console.log(a, b);
```
The console will display the values of `a` and `b` as `1, 2`.

The variable a is assigned the first value of the array, and b is assigned the second value of the array. We can also access the value at any index in an array with destructuring by using commas to reach the desired index:
```js
const [a, b,,, c] = [1, 2, 3, 4, 5, 6];
console.log(a, b, c);
```
The console will display the values of `a`, `b`, and `c` as `1, 2, 5`.

## Use Destructuring Assignment with the Rest Parameter to Reassign Array Elements
In some situations involving array destructuring, we might want to collect the rest of the elements into a separate array.

The result is similar to Array.prototype.slice(), as shown below:
```js
const [a, b, ...arr] = [1, 2, 3, 4, 5, 7];
console.log(a, b);
console.log(arr);
```
The console would display the values `1, 2` and `[3, 4, 5, 7]`.


Variables `a` and `b` take the first and second values from the array. After that, because of the rest parameter's presence, `arr` gets the rest of the values in the form of an array. The rest element only works correctly as the last variable in the list. As in, you cannot use the rest parameter to catch a subarray that leaves out the last element of the original array.

## Use Destructuring Assignment to Pass an Object as a Function's Parameters
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

## Create Strings using Template Literals
A new feature of ES6 is the template literal. This is a special type of string that makes creating complex strings easier.

Template literals allow you to create multi-line strings and to use string interpolation features to create strings.

Consider the code below:
```js
const person = {
  name: "Zodiac Hasbro",
  age: 56
};

const greeting = `Hello, my name is ${person.name}!
I am ${person.age} years old.`;

console.log(greeting);
```
The console will display the strings `Hello, my name is Zodiac Hasbro!` and `I am 56 years old.`.

A lot of things happened there. Firstly, the example uses backticks (\`), not quotes (' or "), to wrap the string. Secondly, notice that the string is multi-line, both in the code and the output. This saves inserting \n within strings. The `${variable}` syntax used above is a placeholder. Basically, you won't have to use concatenation with the + operator anymore. To add variables to strings, you just drop the variable in a template string and wrap it with `${ and }`. Similarly, you can include other expressions in your string literal, for example `${a + b}`. This new way of creating strings gives you more flexibility to create robust strings.

### Exercise
Use template literal syntax with backticks to create an array of list element (`li`) strings. Each list element's text should be one of the array elements from the `failure` property on the `result` object and have a `class` attribute with the value `text-warning`. The `makeList` function should return the array of list item strings.

Use an iterator method (any kind of loop) to get the desired output (shown below).
```js
[
  '<li class="text-warning">no-var</li>',
  '<li class="text-warning">var-on-top</li>',
  '<li class="text-warning">linebreak</li>'
]
```
### Solution
```js
const result = {
  success: ["max-length", "no-amd", "prefer-arrow-functions"],
  failure: ["no-var", "var-on-top", "linebreak"],
  skipped: ["no-extra-semi", "no-dup-keys"]
};
function makeList(arr) {
  // Only change code below this line
  const failureItems = [];
    for (let i = 0; i < arr.length; i++) {
      failureItems.push(`<li class="text-warning">${result.failure[i]}</li>`)
    }
   // Only change code above this line

  return failureItems;
}

const failuresList = makeList(result.failure);
console.log(makeList(result.failure)) 
```
## Write Concise Object Literal Declarations Using Object Property Shorthand
ES6 adds some nice support for easily defining object literals.

Consider the following code:
```js
const getMousePosition = (x, y) => ({
  x: x,
  y: y
});
```
`getMousePosition` is a simple function that returns an object containing two properties. ES6 provides the syntactic sugar to eliminate the redundancy of having to write `x: x`. You can simply write `x` once, and it will be converted to `x: x` (or something equivalent) under the hood. Here is the same function from above rewritten to use this new syntax:
```js
const getMousePosition = (x, y) => ({ x, y });
```

## Write Concise Declarative Functions with ES6
When defining functions within objects in ES5, we have to use the keyword function as follows:
```js
const person = {
  name: "Taylor",
  sayHello: function() {
    return `Hello! My name is ${this.name}.`; // 'this' refers to the object that contains this function
  }
};
```
With ES6, you can remove the `function` keyword and colon altogether when defining functions in objects. Here's an example of this syntax:
```js
const person = {
  name: "Taylor",
  sayHello() {
    return `Hello! My name is ${this.name}.`;
  }
};
```
## Use class Syntax to Define a Constructor Function
ES6 provides a new syntax to create objects, using the *class* keyword.

It should be noted that the `class` syntax is just syntax, and not a full-fledged class-based implementation of an object-oriented paradigm, unlike in languages such as Java, Python, Ruby, etc.

In ES5, an object can be created by defining a `constructor` function and using the `new` keyword to instantiate the object.

In ES6, a `class` declaration has a `constructor` method that is invoked with the new keyword. If the constructor method is not explicitly defined, then it is implicitly defined with no arguments.
```js
// Explicit constructor
class SpaceShuttle {
  constructor(targetPlanet) {
    this.targetPlanet = targetPlanet;
  }
  takeOff() {
    console.log("To " + this.targetPlanet + "!");
  }
}

// Implicit constructor 
class Rocket {
  launch() {
    console.log("To the moon!");
  }
}

const zeus = new SpaceShuttle('Jupiter');
// prints To Jupiter! in console
zeus.takeOff();

const atlas = new Rocket();
// prints To the moon! in console
atlas.launch();
```
It should be noted that the `class` keyword declares a new function, to which a constructor is added. This constructor is invoked when `new` is called to create a new object.

Note: UpperCamelCase should be used by convention for ES6 class names, as in `SpaceShuttle` used above.

The `constructor` method is a special method for creating and initializing an object created with a class. You will learn more about it in the Object Oriented Programming section of the JavaScript Algorithms And Data Structures Certification.

