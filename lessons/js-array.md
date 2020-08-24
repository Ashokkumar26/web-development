---
path: "/js-array"
title: "Concepts of Array"
section: "JS_INTRODUCTION"
order: 3
description: Welcome to Foundations of Design Systems!
---

Arrays are generally described as "list-like objects"; they are basically single objects that contain multiple values stored in a list. Array objects can be stored in variables and dealt with in much the same way as any other type of value, the difference being that we can access each value inside the list individually, and do super useful and efficient things with the list, like loop through it and do the same thing to every value. Maybe we've got a series of product items and their prices stored in an array, and we want to loop through them all and print them out on an invoice, while totaling all the prices together and printing out the total price at the bottom.

If we didn't have arrays, we'd have to store every item in a separate variable, then call the code that does the printing and adding separately for each item. This would be much longer to write out, less efficient, and more error-prone. If we had 10 items to add to the invoice it would already be annoying, but what about 100 items, or 1000? We'll return to this example later on in the article.

As in previous articles, let's learn about the real basics of arrays by entering some examples into [browser developer console](https://developer.mozilla.org/en-US/docs/Learn/Common_questions/What_are_browser_developer_tools).

### Creating arrays

Arrays consist of square brackets and elements that are separated by commas.

1.  Suppose we want to store a shopping list in an array. Paste the following code into the console:

    ```js
    let shopping = ["bread", "milk", "cheese", "hummus", "noodles"];
    shopping;
    ```

2.  In the above example, each element is a string, but in an array we can store various data types — strings, numbers, objects, and even other arrays. We can also mix data types in a single array — we do not have to limit ourselves to storing only numbers in one array, and in another only strings. For example:

    ```js
    let sequence = [1, 1, 2, 3, 5, 8, 13];
    let random = ["tree", 795, [0, 1, 2]];
    ```

3.  Before proceeding, create a few example arrays.

### Accessing and modifying array items

You can then access individual items in the array using bracket notation, in the same way that you [accessed the letters in a string](https://developer.mozilla.org/en-US/Learn/JavaScript/First_steps/Useful_string_methods#Retrieving_a_specific_string_character).

1.  Enter the following into your console:

    ```js
    shopping[0];
    // returns "bread"
    ```

2.  You can also modify an item in an array by simply giving a single array item a new value. Try this:

    ```js
    shopping[0] = "tahini";
    shopping;
    // shopping will now return [ "tahini", "milk", "cheese", "hummus", "noodles" ]
    ```

    **Note**: We've said it before, but just as a reminder — computers start counting from 0!

3.  Note that an array inside an array is called a multidimensional array. You can access an item inside an array that is itself inside another array by chaining two sets of square brackets together. For example, to access one of the items inside the array that is the third item inside the `random` array (see previous section), we could do something like this:

    ```js
    random[2][2];
    ```

4.  Try making some more modifications to your array examples before moving on. Play around a bit, and see what works and what doesn't.

### Finding the length of an array

You can find out the length of an array (how many items are in it) in exactly the same way as you find out the length (in characters) of a string — by using the [`length`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Array/length) property. Try the following:

```js
shopping.length;
// should return 5
```

This has other uses, but it is most commonly used to tell a loop to keep going until it has looped through all the items in an array. So for example:

```js
let sequence = [1, 1, 2, 3, 5, 8, 13];
for (let i = 0; i < sequence.length; i++) {
  console.log(sequence[i]);
}
```

You'll learn about loops properly later on (in our [Looping code](https://developer.mozilla.org/en-US/docs/Learn/JavaScript/Building_blocks/Looping_code) article), but briefly, this code is saying:

1.  Start looping at item number 0 in the array.
2.  Stop looping at the item number equal to the length of the array. This works for an array of any length, but in this case it stops looping at item number 7 (this is good, as the last item — which we want the loop to include — is item 6).
3.  For each item, print it out to the browser console with [console.log()](https://developer.mozilla.org/en-US/docs/Web/API/Console/log).

## Some useful array methods

In this section we'll look at some rather useful array-related methods that allow us to split strings into array items and vice versa, and add new items into arrays.

### Converting between strings and arrays

Often you'll be presented with some raw data contained in a big long string, and you might want to separate the useful items out into a more useful form and then do things to them, like display them in a data table. To do this, we can use the [`split()`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/String/split) method. In its simplest form, this takes a single parameter, the character you want to separate the string at, and returns the substrings between the separator as items in an array.

**Note**: Okay, this is technically a string method, not an array method, but we've put it in with arrays as it goes well here.

1.  Let's play with this, to see how it works. First, create a string in your console:

    ```js
    let myData = "Manchester,London,Liverpool,Birmingham,Leeds,Carlisle";
    ```

2.  Now let's split it at each comma:

    ```js
    let myArray = myData.split(",");
    myArray;
    ```

3.  Finally, try finding the length of your new array, and retrieving some items from it:

    ```js
    myArray.length;
    myArray[0]; // the first item in the array
    myArray[1]; // the second item in the array
    myArray[myArray.length - 1]; // the last item in the array
    ```

4.  You can also go the opposite way using the [`join()`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Array/join) method. Try the following:

    ```js
    let myNewString = myArray.join(",");
    myNewString;
    ```

5.  Another way of converting an array to a string is to use the [`toString()`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Array/toString) method. `toString()` is arguably simpler than `join()` as it doesn't take a parameter, but more limiting. With `join()` you can specify different separators, whereas `toString()` always uses a comma. (Try running Step 4 with a different character than a comma.)

    ```js
    let dogNames = ["Rocket", "Flash", "Bella", "Slugger"];
    dogNames.toString(); // Rocket,Flash,Bella,Slugger
    ```

### Adding and removing array items

We've not yet covered adding and removing array items — let us look at this now. We'll use the `myArray` array we ended up with in the last section. If you've not already followed that section, create the array first in your console:

```js
let myArray = [
  "Manchester",
  "London",
  "Liverpool",
  "Birmingham",
  "Leeds",
  "Carlisle"
];
```

First of all, to add or remove an item at the end of an array we can use [`push()`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Array/push) and [`pop()`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Array/pop) respectively.

1.  Let's use `push()` first — note that you need to include one or more items that you want to add to the end of your array. Try this:

    ```js
    myArray.push("Cardiff");
    myArray;
    myArray.push("Bradford", "Brighton");
    myArray;
    ```

2.  The new length of the array is returned when the method call completes. If you wanted to store the new array length in a variable, you could do something like this:

    ```js
    let newLength = myArray.push("Bristol");
    myArray;
    newLength;
    ```

3.  Removing the last item from the array is as simple as running `pop()` on it. Try this:

    ```js
    myArray.pop();
    ```

4.  The item that was removed is returned when the method call completes. To save that item in a new variable, you could do this:

    ```js
    let removedItem = myArray.pop();
    myArray;
    removedItem;
    ```

[`unshift()`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Array/unshift) and [`shift()`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Array/shift) work in exactly the same way as `push()` and `pop()`, respectively, except that they work on the beginning of the array, not the end.

1.  First `unshift()` — try the following commands:

    ```js
    myArray.unshift("Edinburgh");
    myArray;
    ```

2.  Now `shift()`; try these!

    ```js
    let removedItem = myArray.shift();
    myArray;
    removedItem;
    ```

# Array Iteration Methods

Array iteration methods operate on every array item.

## Array.forEach()

The `forEach()` method calls a function (a callback function) once for each array element.

### Example

```
var  txt =  "";
var  numbers = [45,  4,  9,  16,  25];
numbers.forEach(myFunction);

function  myFunction(value, index, array) {
txt = txt + value +  "<br>";
}
```

Note that the function takes 3 arguments:

- The item value
- The item index
- The array itself

The example above uses only the value parameter. The example can be rewritten to:

### Example

```
var  txt =  "";
var  numbers = [45,  4,  9,  16,  25];
numbers.forEach(myFunction);

function  myFunction(value) {
txt = txt + value +  "<br>";
}
```

## Array.map()

The `map()` method creates a new array by performing a function on each array element.

The `map()` method does not execute the function for array elements without values.

The `map()` method does not change the original array.

This example multiplies each array value by 2:

### Example

```
var  numbers1 = [45,  4,  9,  16,  25];
var  numbers2 = numbers1.map(myFunction);

function  myFunction(value, index, array) {
return  value *  2;
}
```

Note that the function takes 3 arguments:

- The item value
- The item index
- The array itself

When a callback function uses only the value parameter, the index and array parameters can be omitted:

### Example

```
var  numbers1 = [45,  4,  9,  16,  25];
var  numbers2 = numbers1.map(myFunction);

function  myFunction(value) {
return  value *  2;
}
```

## Array.filter()

The `filter()` method creates a new array with array elements that passes a test.

This example creates a new array from elements with a value larger than 18:

### Example

```
var  numbers = [45,  4,  9,  16,  25];
var  over18 =  numbers.filter(myFunction);

function  myFunction(value, index, array) {
return  value >  18;
}
```

Note that the function takes 3 arguments:

- The item value
- The item index
- The array itself

In the example above, the callback function does not use the index and array parameters, so they can be omitted:

### Example

```
var  numbers = [45,  4,  9,  16,  25];
var  over18 =  numbers.filter(myFunction);

function  myFunction(value) {
return  value >  18;
}
```

## Array.reduce()

The `reduce()` method runs a function on each array element to produce (reduce it to) a single value.

The `reduce()` method works from left-to-right in the array. See also `reduceRight()`.

The `reduce()` method does not reduce the original array.

This example finds the sum of all numbers in an array:

### Example

```
var  numbers1 = [45,  4,  9,  16,  25];
var  sum = numbers1.reduce(myFunction);

function  myFunction(total, value, index, array) {
return  total + value;
}
```

Note that the function takes 4 arguments:

- The total (the initial value / previously returned value)
- The item value
- The item index
- The array itself

The example above does not use the index and array parameters. It can be rewritten to:

### Example

```
var  numbers1 = [45,  4,  9,  16,  25];
var  sum = numbers1.reduce(myFunction);

function  myFunction(total, value) {
return  total + value;
}
```

The `reduce()` method can accept an initial value:

### Example

```
var  numbers1 = [45,  4,  9,  16,  25];
var  sum = numbers1.reduce(myFunction,  100);

function  myFunction(total, value) {
return  total + value;
}
```

## Array.find()

The `find()` method returns the value of the first array element that passes a test function.

This example finds (returns the value of) the first element that is larger than 18:

### Example

```
var  numbers = [4,  9,  16,  25,  29];
var  first =  numbers.find(myFunction);

function  myFunction(value, index, array) {
return  value >  18;
}
```

## Array.some()

The `some()` method check if some array values pass a test.

This example check if some array values are larger than 18:

### Example

```
var  numbers = [45,  4,  9,  16,  25];
var  someOver18 = numbers.some(myFunction);

function  myFunction(value, index, array) {
return  value >  18;
}
```

## Array.every()

The `every()` method check if all array values pass a test.

This example check if all array values are larger than 18:

### Example

```
var  numbers = [45,  4,  9,  16,  25];
var  allOver18 =  numbers.every(myFunction);

function  myFunction(value, index, array) {
return  value >  18;
}
```

## Array.indexOf()

The `indexOf()` method searches an array for an element value and returns its position.

**Note:** The first item has position 0, the second item has position 1, and so on.

### Example

Search an array for the item "Apple":

```
var  fruits = ["Apple",  "Orange",  "Apple",  "Mango"];
var  a = fruits.indexOf("Apple");
```

## References

[https://developer.mozilla.org/en-US/docs/Learn/JavaScript/First_steps/Arrays](https://developer.mozilla.org/en-US/docs/Learn/JavaScript/First_steps/Arrays)
[https://eloquentjavascript.net/04_data.html](https://eloquentjavascript.net/04_data.html)
[https://www.w3schools.com/js/js_array_iteration.asp](https://www.w3schools.com/js/js_array_iteration.asp)
