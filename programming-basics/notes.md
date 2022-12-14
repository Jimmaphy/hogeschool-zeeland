# Programming Basics Notes

Course Code: CU75003V1

## Hello World

Programming Basics teaches the creations of programs using the impirative programming JavaScript. The first instruction to cover is.

```js
document.write('Hello World!');
```

The *function* `write()` is called from the `document` *object*. This function takes as input a *string* of characters which is surrounded by single qoutes, in case of the example: `'Hello World!'`. The instruction is ended with a semicolon.

## Expressions

An expression is an a combination of values and operations that eventually evaluate into a single value. Let's demonstrate this with some simple mathematics.

Expression  | Evaluates to  | Operation         |
------------|---------------|-------------------|
4           | 4             | None              |
5           | 5             | None              |
4 + 5       | 9             | Addition          |
4 * 5       | 20            | Multiplication    |
20 / 5      | 4             | Division          |
4 % 3       | 1             | Modulo            |

As seen in the last three rows of the table: most operations have three parts: a left operand, an operator and a right operand. We can use these in code just like we can in mathematics.

```js
document.write(9 / 3);
```

## Variables

Computers use memory to store data. Variables are containers for this data. Veriables can be created, read and updated whenever you feel like it. A variable is defined using the `let` keyword. There is also the `const` keyword for declaring constant values, these values cannot be updated.

```js
// This line is a comment, ignored dring execution
// Creation of variables and constant
let number = 5;
const letter = 'w';

// Reading of variables and constants
console.log(number);
console.log(letter);

// Updating variables
number = number * 2;
```

When used in expressions, the variable get replaced by the value it's holding. This happens before anything else. JavaScript has an option for string templating. This replaces the single qoutes with back ticks. This allows for direct intergration with variables like: `${name}`.

A variable can also point to a collection of values, known as an *array*. A string for example, can be seen as a collection of characters. Each item in an array has it's own index, starting at 0. An array is created by assigning values between `[ ]`, seperated by commas. An array is considered an object and has some important properties and functions.

```js
let productList = ['Tooth brush', ' Crips', ' Deodorant', 'Tomato'];    // Create
console.log(productList[2]);                                            // Read
productList[1] = 'Chips';                                               // Update
productList.splice(2, 1);                                               // Delete
productList.push('Chicken');                                            // Add
```

## Proposition & Logic

Propositions are expressions that evaluate to either true or false. There are special operators to help for this scenario. A true or false value is called a *boolean*. Propositions in code are therefore known as *boolean expressions*. In code they're used the same as other expressions.

Operator    | Meaning                   |
------------|-------------------------- |
==          | Equals (Type insensitive) |
===         | Equals (Type sensitive)   |
<           | Smaller than              |
\>          | Greater than              |
<=          | Smaller than or equal     |
\>=         | Greater than or equal     |

Boolean expressions can be combined using logic operators. This allows us to create more complex condition for the application to meet. Available options are `&&` (AND), `||` (OR) & `^` (XOR). Boolean expression can be represented in truth tables, in which we specify all options for expressions and the result.

A       | B      | A\|\|B | A&&B   | A^B    | !A     |
--------|--------|--------|--------|--------|--------|
true    | true   | true   | true   | false  | false  |
true    | false  | true   | false  | true   | false  |
false   | true   | true   | false  | true   | true   |
false   | false  | false  | false  | false  | true   |

In order to use this power the ES gods have given us, we use something called an *if-statement*. Using this in your code allows the computer to decide whether or not to run the included statements. The block of code can be spotted fairly easily, it's surrounded by `{` and `}`. If the boolean expression evaluates to false, the code within the if-statement is simply skipped.

When the conditions evaluates to false isn't the point where our options stop. We can actually write code for these situation. The `else if` is another codition that will be checked if the original `if` statement fails. The `else` is the place were the code goes if all other conditions fail. You can add as many `else if` statements as you want before defining the `else` statement.

```js
let a = 20;

// Here we check a specific condition
if (a < 10) {
    // Everything in here get's executed if the boolean expression evaluates to true
    a = a + 10;
} else if (a > 20) {
    // This condition is checked if the first one fails
    a = a - 10;
} else {
    // This executes when all other conditions fail
    a = a * 2;
}

a = a - 1;
```

## Loops

After being able to make descisions within our code, now we want to repeat certain actions. There are three different kind of *loops* that we can use while writing our applications: the `for`-loop, the `while`-loop and the `do-while`-loop. For loops are great at iterating collections or series, while is used to check a condition before executing code & a do-while loop runs the code once and checks for a condition afterwards.

```js
// For loop
numbers = [2, 4, 6, 8];
for (let i = 0; i < numbers.length; i++>) {
    console.log(numbers[i]);
}

// While loop
let number = 0;
while (number < 10) {
    console.log(number);
    number += 1;
}

// Do-while loop
do {
    number -= 1;
    console.log(number);
} while (number > 0)
```

## The Web API

Every browser supports a set of features that can be accessed using JavaScript. These features are called the Web API (Application Programming Interface). The simplest way to use the Web API is by using a script-tag inside HTML, this is called *inline scripting*. We can also reference a JavaScript file inside the HTML tag. This seperates the visuals of the website from the logic and is considered good practice. The script-tag uses the source (`src`) attribute for that.

```html
<!-- Inline scripting -->
<script>
    const message = 'Hello JavaScript!';
    document.write(message);
</script>

<!-- External scripting -->
<script src="app.js"></script>
```

The `document`, `window` and `console` variables are special in regards to the Web API. They refer to instances of objects containing many function, including `log()` and `write()` shown earlier. `window.prompt()` is a new function, one that prompt the user for a value, which can be used in JavaScript for processing. This function is limited since it can only append to an existing HTML document, not change it.

The *Document Object Model* (DOM) is a tree structure containing the elements from an HTML page. The Web API can manipulate the entire DOM using various functions. The first step is finding an element on the DOM, this is done using two function: `document.querySelector()` & `document.getElementById()`. The next step is to change their properties, for example: `innerHTML` and `className`.

```js
// Get elements
const image = documnet.querySelector('.ul.active');
const summary = document.getElementById('summary');

// Manipulate elements
image.className = 'thumbnail';
summary.innerHTML = 'A summary of the image';
```

## Important Functions

function                    | result                            |
----------------------------|-----------------------------------|
array.pop()                 | Get and remove item from an array |
array.push()                | Add element to array              |
array.slice()               | Split the array up (or remove)    |
console.log()               | Write something to the console    |
document.getElementById()   | Retrieve element using an ID      |
document.querySelector()    | Retrieve element with selector    |
document.write()            | Write something to HTML document  |
windows.prompt()            | Ask the user for input via popup  |
