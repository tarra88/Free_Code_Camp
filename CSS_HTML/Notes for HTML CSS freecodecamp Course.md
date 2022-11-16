---
title: Notes for HTML CSS freecodecamp Course
tags: [FCC/HTML_CSS]
created: '2022-10-18T01:21:47.137Z'
modified: '2022-11-03T21:09:38.307Z'
---

# Notes for HTML CSS freecodecamp Course

# Setting a method for a form to post results: 
```html
<form action="https://freecodecamp.org/practice-project/accessibility-quiz" method="post">
```
# CSS - pattern to set CSS properties for screen reading only text:
```css
position: absolute;
width: 1px;
height: 1px;
padding: 0;
margin: -1px;
overflow: hidden;
clip: rect(0, 0, 0, 0);
white-space: nowrap;
border: 0;
```
# Nesting an input element within a label
It is not required to explicitly link the label with the input, but it is best practice to do it. (for.. to id...).

## From coding the Balance Sheet in Responsive Web Design:
Style the text within your `#years` element by creating a `#years` span[class] selector. The span[class] syntax will target any span element that has a class attribute set, regardless of the attribute's value.

FYI - "years" is an id.

The [attribute="value"] selector targets any element that has an attribute with a specific value. Create a tr[class="total"] selector to target specifically your tr elements with the total class.

The :nth-of-type() pseudo-selector is used to target specific elements based on their order among siblings of the same type. E.g.:

```css
tr.total td:nth-of-type(3) {
	padding-right: 0.5rem;
}
```
# Variables in CSS
Create a variable by putting -- in front of the variable name. E.g.
```css
.bb1 {
width: 10%;
--building-color1: green;
}
```
However, good practice is to put all the variables in a root at the beginning of the css file. E.g.:
```css
:root {
  --building-color1: #aa80ff;
  --building-color2: #66cc99;
  --building-color3: #cc6699;
}
```
# Comments in CSS
Comments look like this:
```css
/* Comment here */
```
# Comments in HTML
```html
<!-- Write your comments here -->
```
# CSS Gradients
Gradients in CSS are a way to transition between colors across the distance of an element. They are applied to the background property and the syntax looks like this:
```css
gradient-type(
  color1,
  color2
); 
```
In the example, color1 is solid at the top, color2 is solid at the bottom, and in between it transitions evenly from one to the next.

So in the "building a city skyline" task in FCC, the code was:
```css
.bb1a {
  width: 70%;
  height: 10%;
  background-color: var(--building-color1);
  background: linear-gradient(
    var(--building-color1),
    var(--window-color1)
    );
}
```
Can use percentages, and also do stripes:
```css
.bb2b {
   background: repeating-linear-gradient(
      var(--building-color2),
      var(--building-color2) 6%,
      var(--window-color2) 6%,
      var(--window-color2) 9%
    );
}
```
# CSS Place Items property for grids
The place-items property can be used to set the align-items and justify-items values at the same time. The place-items property takes one or two values. If one value is provided, it is used for both the align-items and justify-items properties. If two values are provided, the first value is used for the align-items property and the second value is used for the justify-items property.

# Head code for using Fontawesome
 ```html
    <link
      rel="stylesheet"
      href="https://use.fontawesome.com/releases/v5.15.4/css/all.css"
      crossorigin="anonymous"
    />
``` 
# Animation Property
As per the ferris-wheel project.
```css
.cabin {
  background-color: red;
  width: 20%;
  height: 20%;
  position: absolute;
  border: 2px solid;
  transform-origin: 50% 0%;
  animation: cabins 10s linear infinite;
}
```
With your .wheel selector, you created four different properties to control the animation. For your .cabin selector, you can use the animation property to set these all at once.

Set the animation property of the .cabin rule to cabins 10s linear infinite. This will set the animation-name, animation-duration, animation-timing-function, and animation-iteration-count properties in that order.

# Remove scroll bars & prevent programmatic scrolling:
```css
body {
  overflow: clip;
}
```
# Full width of viewport
```css
.some-class {
  width: 100vw;
}
```
