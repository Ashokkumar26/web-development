---
path: "/js-loops"
title: "Conditional Statements, Switch & Loops"
section: "JS_INTRODUCTION"
order: 4
description: Welcome to Foundations of Design Systems!
---

Conditional statements are used to perform different actions based on different conditions.

## Conditional Statements

Very often when you write code, you want to perform different actions for different decisions.

You can use conditional statements in your code to do this.

In JavaScript we have the following conditional statements:

- Use `if` to specify a block of code to be executed, if a specified condition is true
- Use `else` to specify a block of code to be executed, if the same condition is false
- Use `else if` to specify a new condition to test, if the first condition is false
- Use `switch` to specify many alternative blocks of code to be executed

The `switch` statement is described in the next chapter.

## The if Statement

Use the `if` statement to specify a block of JavaScript code to be executed if a condition is true.

### Syntax

```
if  (_condition_) {
// _block of code to be executed if the condition is true_}
```

### Example

Make a "Good day" greeting if the hour is less than 18:00:

```
if  (hour <  18) {
greeting =  "Good day";
}
```

## The else Statement

Use the `else` statement to specify a block of code to be executed if the condition is false.

```
if  (_condition_) {
// _block of code to be executed if the condition is true_}  else  {
// _block of code to be executed if the condition is false_}
```

### Example

If the hour is less than 18, create a "Good day" greeting, otherwise "Good evening":

```
if  (hour <  18) {
greeting =  "Good day";
}  else  {
greeting =  "Good evening";
}
```

## The else if Statement

Use the `else if` statement to specify a new condition if the first condition is false.

### Syntax

```
if  (_condition1_) {
// _block of code to be executed if condition1 is true_}  else  if  (_condition2_) {
// _block of code to be executed if the condition1 is false and condition2 is true_
}  else  {
// _block of code to be executed if the condition1 is false and condition2 is false_}
```

### Example

If time is less than 10:00, create a "Good morning" greeting, if not, but time is less than 20:00, create a "Good day" greeting, otherwise a "Good evening":

```
if  (time <  10) {
greeting =  "Good morning";
}  else  if  (time <  20) {
greeting =  "Good day";
}  else {
greeting =  "Good evening";
}
```

# JavaScript Switch Statement

The `switch` statement is used to perform different actions based on different conditions.

## The JavaScript Switch Statement

Use the `switch` statement to select one of many code blocks to be executed.

### Syntax

```
switch(_expression_) {
case  _x_:
_// code block
_break;
case  _y_:
_// code block
_break;
default:
//  _code block_
}
```

This is how it works:

- The switch expression is evaluated once.
- The value of the expression is compared with the values of each case.
- If there is a match, the associated block of code is executed.
- If there is no match, the default code block is executed.

### Example

The `getDay()` method returns the weekday as a number between 0 and 6.

If today is neither Saturday (6) nor Sunday (0), write a default message:

```
switch  (new  Date().getDay()) {
case  6:
text =  "Today is Saturday";
break;
case  0:
text =  "Today is Sunday";
break;
default:
text =  "Looking forward to the Weekend";
}
```

# Loops

Loops can execute a block of code a number of times.

## JavaScript Loops

Loops are handy, if you want to run the same code over and over again, each time with a different value.

Often this is the case when working with arrays:

### Instead of writing:

```
text += cars[0] +  "<br>";
text += cars[1] +  "<br>";
text += cars[2] +  "<br>";
text += cars[3] +  "<br>";
text += cars[4] +  "<br>";
text += cars[5] +  "<br>";
```

### You can write:

```
var  i;
for  (i =  0; i < cars.length; i++) {
text += cars[i] +  "<br>";
}
```

## Different Kinds of Loops

JavaScript supports different kinds of loops:

- `for` - loops through a block of code a number of times
- `for/in` - loops through the properties of an object
- `for/of` - loops through the values of an iterable object
- `while` - loops through a block of code while a specified condition is true
- `do/while` - also loops through a block of code while a specified condition is true

## The For Loop

The `for` loop has the following syntax:

```
for  (_statement 1_; _statement 2_; _statement 3_) {
//  _code block to be executed_
}
```

**Statement 1** is executed (one time) before the execution of the code block.

**Statement 2** defines the condition for executing the code block.

**Statement 3** is executed (every time) after the code block has been executed.

### Example

```
for  (i =  0; i <  5; i++) {
text +=  "The number is "  + i +  "<br>";
}
```

## The For/In Loop

The JavaScript `for/in` statement loops through the properties of an object:

### Example

```
var  person = {fname:"John", lname:"Doe", age:25};

var  text =  "";
var  x;
for  (x  in  person) {
text += person[x];
}
```

## The For/Of Loop

The JavaScript `for/of` statement loops through the values of an iterable objects

`for/of` lets you loop over data structures that are iterable such as Arrays, Strings, Maps, NodeLists, and more.

The `for/of` loop has the following syntax:

```
for  (_variable_  of  _iterable_) {
//  _code block to be executed_
}
```

_variable_ - For every iteration the value of the next property is assigned to the variable. _Variable_ can be declared with `const`, `let`, or `var`.

_iterable_ - An object that has iterable properties.

## The While Loop

The `while` loop loops through a block of code as long as a specified condition is true.

### Syntax

```
while  (_condition_) {
_// code block to be executed_
}
```

### Example

In the following example, the code in the loop will run, over and over again, as long as a variable (i) is less than 10:

### Example

```
while  (i <  10) {
text +=  "The number is "  + i;
i++;
}
```

## The Do/While Loop

The `do/while` loop is a variant of the while loop. This loop will execute the code block once, before checking if the condition is true, then it will repeat the loop as long as the condition is true.

### Syntax

```
do  {
_// code block to be executed
_}
while  (_condition_);
```

### Example

The example below uses a `do/while` loop. The loop will always be executed at least once, even if the condition is false, because the code block is executed before the condition is tested:

### Example

```
do  {
text +=  "The number is "  + i;
i++;
}
while  (i <  10);
```

## References

[https://developer.mozilla.org/en-US/docs/Learn/JavaScript/Building_blocks/Looping_code](https://developer.mozilla.org/en-US/docs/Learn/JavaScript/Building_blocks/Looping_code)
[https://www.w3schools.com/js/js_if_else.asp](https://www.w3schools.com/js/js_if_else.asp)
[https://www.w3schools.com/js/js_switch.asp](https://www.w3schools.com/js/js_switch.asp)
