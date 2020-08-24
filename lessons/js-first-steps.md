---
path: "/js-first-steps"
title: "JavaScript on First Step"
section: "JS_INTRODUCTION"
order: 1
description: Welcome to Foundations of Design Systems!
---

In HTML, JavaScript code is inserted between `<script>` and `</script>` tags.
You can place any number of scripts in an HTML document.

Scripts can be placed in the `<body>`, or in the `<head>` section of an HTML page, or in both.

# JavaScript Statements

### Example

var x, y, z; // Statement 1  
x = 5; // Statement 2  
y = 6; // Statement 3  
z = x + y; // Statement 4

## JavaScript Programs

A **computer program** is a list of "instructions" to be "executed" by a computer.

In a programming language, these programming instructions are called **statements**.

A **JavaScript program** is a list of programming **statements**.

In HTML, JavaScript programs are executed by the web browser.

## JavaScript Statements

![Types of Statements in JavaScript - Programming Foundations #06](https://i1.wp.com/pandabunnytech.com/wp-content/uploads/2018/11/types-of-statements-in-javascript-e1543313160116.png)
JavaScript statements are composed of:

Values, Operators, Expressions, Keywords, and Comments.

This statement tells the browser to write "Hello World." inside an HTML element with id="demo":

### Example

```
document.getElementById("demo").innerHTML  =  "Hello World";
```

Most JavaScript programs contain many JavaScript statements.

The statements are executed, one by one, in the same order as they are written.

JavaScript programs (and JavaScript statements) are often called JavaScript code.

## Semicolons ;

Semicolons separate JavaScript statements.

Add a semicolon at the end of each executable statement:

```
var  a, b, c; // Declare 3 variables
a =  5; // Assign the value 5 to a
b =  6; // Assign the value 6 to b
c = a + b; // Assign the sum of a and b to c
```

When separated by semicolons, multiple statements on one line are allowed:

```
a =  5; b =  6; c = a + b;
```

On the web, you might see examples without semicolons.  
Ending statements with semicolon is not required, but highly recommended.

## JavaScript Display Possibilities

![Introduction to JavaScript (part1) - online presentation](https://cf.ppt-online.org/files/slide/q/qvg3WFLOiI6j7kmVElTNnZHox4e8wrPQb2tc09/slide-12.jpg)
JavaScript can "display" data in different ways:

- Writing into an HTML element, using `innerHTML`.
- Writing into the HTML output using `document.write()`.
- Writing into an alert box, using `window.alert()`.
- Writing into the browser console, using `console.log()`.

## Using innerHTML

To access an HTML element, JavaScript can use the `document.getElementById(id)` method.

The `id` attribute defines the HTML element. The `innerHTML` property defines the HTML content:

### Example

```
<!DOCTYPE html>
<html>
<body>

<h1>My First Web Page</h1>
<p>My First Paragraph</p>

<p id="demo"></p>

<script>
document.getElementById("demo").innerHTML  =  5  +  6;
</script>

</body>
</html>
```

Changing the innerHTML property of an HTML element is a common way to display data in HTML.

## Using document.write()

For testing purposes, it is convenient to use `document.write()`:

### Example

```
<!DOCTYPE html>
<html>
<body>

<h1>My First Web Page</h1>
<p>My first paragraph.</p>

<script>
document.write(5  +  6);
</script>

</body>
</html>
```

Using document.write() after an HTML document is loaded, will **delete all existing HTML**:

### Example

```
<!DOCTYPE html>
<html>
<body>

<h1>My First Web Page</h1>
<p>My first paragraph.</p>

<button type="button"  onclick="document.write(5 + 6)">Try it</button>

</body>
</html>
```

The document.write() method should only be used for testing.

## Using window.alert()

You can use an alert box to display data:

### Example

```
<!DOCTYPE html>
<html>
<body>

<h1>My First Web Page</h1>
<p>My first paragraph.</p>

<script>
window.alert(5  +  6);
</script>

</body>
</html>
```

You can skip the `window` keyword.

In JavaScript, the window object is the global scope object, that means that variables, properties, and methods by default belong to the window object. This also means that specifying the `window` keyword is optional:

### Example

```
<!DOCTYPE html>
<html>
<body>

<h1>My First Web Page</h1>
<p>My first paragraph.</p>

<script>
alert(5  +  6);
</script>

</body>
</html>
```

## Using console.log()

For debugging purposes, you can call the `console.log()` method in the browser to display data.

You will learn more about debugging in a later chapter.

### Example

```
<!DOCTYPE html>
<html>
<body>

<script>
console.log(5  +  6);
</script>

</body>
</html>
```

## JavaScript Print

JavaScript does not have any print object or print methods.

You cannot access output devices from JavaScript.

The only exception is that you can call the `window.print()` method in the browser to print the content of the current window.

### Example

```
<!DOCTYPE html>
<html>
<body>

<button onclick="window.print()">Print this page</button>

</body>
</html>
```

## References

[https://eloquentjavascript.net/02_program_structure.html](https://eloquentjavascript.net/02_program_structure.html)
[https://javascript.info/structure#statements](https://javascript.info/structure#statements)
[https://www.w3schools.com/js/js_syntax.asp](https://www.w3schools.com/js/js_syntax.asp)
