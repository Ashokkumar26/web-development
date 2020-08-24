---
path: "/js-basic-concepts"
title: "Data types - basic concepts"
section: "JS_INTRODUCTION"
order: 2
description: Welcome to Foundations of Design Systems!
---

JavaScript variables can hold many **data types**: numbers, strings, objects and more:

```
var  length =  16; // Number
var  lastName =  "Johnson"; // String
var  x = {firstName:"John", lastName:"Doe"}; // Object
```

## The Concept of Data Types

In programming, data types is an important concept.

To be able to operate on variables, it is important to know something about the type.

Without data types, a computer cannot safely solve this:
`var x = 16 + "Volvo";`
Does it make any sense to add "Volvo" to sixteen? Will it produce an error or will it produce a result?

JavaScript will treat the example above as:
`var x = "16" + "Volvo";`
When adding a number and a string, JavaScript will treat the number as a string.

### Example

`var x = 16 + "Volvo";`

### Example

var x = "Volvo" + 16;

JavaScript evaluates expressions from left to right. Different sequences can produce different results:

### Example:

`var x = 16 + 4 + "Volvo";`

Result: `20Volvo`

### Example:

var x = "Volvo" + 16 + 4;

Result:

`Volvo164`

In the first example, JavaScript treats 16 and 4 as numbers, until it reaches "Volvo".

In the second example, since the first operand is a string, all operands are treated as strings.

## JavaScript Types are Dynamic

JavaScript has dynamic types. This means that the same variable can be used to hold different data types:

### Example

```
var  x; // Now x is undefined
x =  5; // Now x is a Number
x =  "John"; // Now x is a String
```

## JavaScript Strings

A string (or a text string) is a series of characters like "John Doe".

Strings are written with quotes. You can use single or double quotes:

### Example

```
var  carName1 =  "Volvo XC60"; // Using double quotes
var  carName2 =  'Volvo XC60'; // Using single quotes
```

You can use quotes inside a string, as long as they don't match the quotes surrounding the string:

### Example

```
var  answer1 =  "It's alright"; // Single quote inside double quotes
var  answer2 =  "He is called 'Johnny'"; // Single quotes inside double quotes
var  answer3 =  'He is called "Johnny"'; // Double quotes inside single quotes
```

You will learn more about strings later in this tutorial.

## JavaScript Numbers

JavaScript has only one type of numbers.

Numbers can be written with, or without decimals:

### Example

```
var  x1 =  34.00; // Written with decimals
var  x2 =  34; // Written without decimals
```

Extra large or extra small numbers can be written with scientific (exponential) notation:

### Example

```
var  y =  123e5; // 12300000
var  z =  123e-5; // 0.00123
```

You will learn more about numbers later in this tutorial.

## JavaScript Booleans

Booleans can only have two values: `true` or `false`.

### Example

```
var  x =  5;
var  y =  5;
var  z =  6;
(x == y) // Returns true
(x == z) // Returns false
```

Booleans are often used in conditional testing.

You will learn more about conditional testing later in this tutorial.

## JavaScript Arrays

JavaScript arrays are written with square brackets.

Array items are separated by commas.

The following code declares (creates) an array called `cars`, containing three items (car names):

### Example

`var cars = ["Saab", "Volvo", "BMW"];`
Array indexes are zero-based, which means the first item is [0], second is [1], and so on.

You will learn more about arrays later in this tutorial.

## JavaScript Objects

JavaScript objects are written with curly braces `{}`.

Object properties are written as name:value pairs, separated by commas.

### Example

```
var  person = {firstName:"John", lastName:"Doe", age:50, eyeColor:"blue"};
```

The object (person) in the example above has 4 properties: firstName, lastName, age, and eyeColor.

You will learn more about objects later in this tutorial.

## References

[https://developer.mozilla.org/en-US/docs/Web/JavaScript/Data_structures](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Data_structures)
[https://www.w3schools.com/js/js_datatypes.asp](https://www.w3schools.com/js/js_datatypes.asp)
