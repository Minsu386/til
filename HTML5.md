# FSA Notes
----
## ES6 Primer
----
Before ES2015, the traditional way to declare a variable was with the `var` keyword. Any variable declared with `var` was either scoped to the global scope of your program or function scoped. This means that everything in your program has access to the variable, or that variables declared in the function are only accessible within the function. ES2015 added a few new features to the language, including the `const` and `let` variables.

We will dive into more details about `const` and `let` in later sections. For now, you should be aware that `const` and `let` can declare variables. The `let` keyword behaves most like the `var` keyword, with some differences.

### `let`

`let` allows you to create a new variable. You can also reassign a new value to the variable declared with `let` (or `var`). For example, review the following code:
```JavaScript
let myFristVariableWithLet = 'let';
myFIrstVariableWithLet = 'var'
```
The variable reassignment on the second line of the code above would be valid.

`Let` us provide the link to the let keyword documentation if you would like to learn more about it: [let - JavaScript | MDNLinks to an external site.](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Statements/let)

### `const`

One of the key differences between `const` and `let` is that variables created with `const` cannot be reassigned. For example, review the following code:
```JavaScript
const myFirstVariableWithConst = 55;
myFirstVariableWithConst = 22;
```
The second line in the code above would result in this error:

```
Uncaught TypeError: Assignment to constant variable
```

`const` is short for constant, which means once the variable is assigned using `const` it may not be changed. It is constant. An error is thrown if you use the assignment operator after assigning `myFirstVariableWithConst` a value. Here is the documentation for the [const keywordLinks to an external site.](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Statements/const).

### `const` OR `let`?

There are a lot of great features `const` and `let` brought to the language, but it also brought one minor drawback. You need to think about what keyword to use when creating a variable. Here is a widely accepted practice in the JavaScript when deciding between `const` and `let`:

- Use `const` by default. It is your go-to option.
- Only use `let` if re-assignment is needed.
- Do not use `var`.

There are many more concepts to discuss regarding `let` and `const`, which we will discuss in another section:

- Scope (and Block Scope)
- Hoisting
- Temporal Deadzone

## Template Literals
----

```
'Is' + ' ' + 'this' + ' ' + 'hard' + ' ' + 'to' + ' ' + 'read' + '?'
```

No need to fear, template literals are here. You may know from your own experience that concatenating string values can be tedious and error prone. It has always been a pain point in JavaScript.

The following is an example of a function that concatenates string values together with a variable.

```
function sayHello(name) {  return 'Hello, ' + name + '!';}sayHello('Tiffany') // RETURNS: 'Hello, Tiffany!'
```

It is also common to evaluate an expression before concatenating the resulting value into a string. In the following example code, the expression `(numOne + numTwo)` is evaluated and then the result is added to the string before the string is returned:

```
function printSum(numOne, numTwo) {  // the addition expression evaluates before the sum is added to the string  return numOne +  " + " + numTwo + " = " + (numOne + numTwo);}printSum(5,7) // RETURNS: '5 + 7 = 12'
```

Let us compare how to write the same two functions using template literals. Template literals use backticks, also known as grave accents, to surround characters at the start and end of the string.

To evaluate a variable or expression in the template literal, place the expression inside of a dollar sign and curly braces. For example:  `${expression || variable }`. Here are our function examples from above refactored with template literals:

```
function sayHello(name) { return `Hello, ${name}!`;}sayHello('Tiffany') // PRINTS: 'Hello, Tiffany!'function printSum(numOne, numTwo) {                                          return `${numOne} + ${numTwo} = ${numOne + numTwo}`;}printSum(5,7) // PRINTS: '5 + 7 = 12'
```

To learn more about template literals, read the documentation: [Template literals (Template strings) - JavaScript | MDNLinks to an external site.](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Template_literals). Moving forward, familiarize yourself with the template literal syntax.

For practice, refactor the examples below. You can practice refactoring the examples by making a new code file in VS Code and copying in the code below, or you can use this CodePen: [Template Literal RefactorLinks to an external site.](https://codepen.io/FullstackAcademy/pen/b3580f43daa79a6394ffea8c012ce8a9/).

```JavaScript
// open the console and compare your refactored output with the original
// refactor greeter to use a template literal
function greeter(firstName, middleName, lastName, greeting){ return greeting + " " + firstName + " " + middleName + " "  +lastName + "!"}

console.log(greeter('Wade', 'Owen','Watts', 'Hello'));

// refactor personData to use a template literal
function personData(person){ '<div><span>' + person.name + '</span><span>' + person.favoriteBook + '</span><span>' + person.age + '</span></div>'}

console.log(personData({name: 'Wade Owen Watts', favoriteBook: 'ReadyPlayerOne', age: 18}));
```
### Solution Code
----
```JavaScript
// refactor greeter to use a template literal
function greeter(firstName, middleName, lastName, greeting){
  return `${greeting} ${firstName} ${middleName} ${lastName}!`}
  
console.log(greeter('Wade', 'Owen','Watts', 'Hello'));
// refactor personData to use a template literal
function personData(person) {
  return `<div>
<span> ${person.name} </span>
<span> ${person.favoriteBook} </span>
<span> ${person.age} </span> 
  </div>`}
console.log(personData({name: 'Wade Owen Watts', favoriteBook: 'ReadyPlayerOne', age: 18}));
```

NOTE: Making a new line for each HTML element is not strictly required in this solution. However, another great feature included in template literals is that they take new lines into account on their own. You do not have to use `\n` in the string to create a new line. Reference the documentation for more details: [Template literals (Template strings) > Multi-line strings](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Template_literals#multi-line_strings)


## Arrow Function
----
Arrow functions were added to ES2015 and generally have the same behavior as a standard `function` declaration, with a few additional benefits:

- Shorter Functions (less syntax)
- `this` is bound to the enclosing execution context

We will cover the `this` keyword, and all the benefits and trade-offs with arrow functions, throughout TestFirst. We will mainly cover this in the third section of Foundations. For now, familiarize yourself with the arrow function syntax, as you will encounter it in examples moving forward.

Review the following code example of a standard function declaration using the `function` keyword:

```
function timesFive (x) {  return x * 5}
```

Next, check out this code example of the same `timesFive` function using arrow function syntax:

```
const timesFive = (x) => {  return x * 5;}
```

Both function statements are almost identical, with the exception of the use of the “fat arrow” (`=>`). An arrow function can be written in numerous ways. For now, we are purposely sticking to a format that is similar to a traditional function declaration. We want to focus on learning concepts, not syntax. Alternative and cleaner syntax is easier to learn after you are fluent in the core concepts.

For future reference, check out the following variations of alternative ways we can write the `timesFive` function more concisely using arrow function syntax.

**Omitting the return keyword:** The `return` keyword is not necessary if the function evaluates a single expression. This form of arrow functions is referred to as the "concise" body. It is also referred to as an “implicit return.” Review the example code:

```
const timesFive = (x) => x * 5
```

**Omitting the parentheses:** If there is only one parameter, parenthesis around the parameters are not needed in an arrow function. This example code also has an implicit return. Review the example code:

```
const timesFive x => x * 5
```

As you progress through TestFirst, we encourage you to use the `function` keyword in your own code if you do not have familiarity with arrow functions. There are certain situations where arrow functions will behave differently than standard function declarations. With that in mind, you should use standard function declarations in your own code until these situations are covered in TestFirst and the Junior Phase. It will take time and exposure to use arrow functions to gain the intuition on when to use an arrow function versus a standard function declaration.









# Anatomy of an HTML document
----

```html
<!DOCTYPE html>
<html lang="en-US">
	<head>
		<meta charset="utf-8" />
		<title>My test page</title>
	</head>
	<body>
		<p>This is my page</p>
	</body>
<html>
```

1. `<!DOCTYPE html>` : historic artifact that needs to be included for everything to work right. `<DOCTYPE html>` is the shortest string that counts as a valid doctype.
2. `<html></html>`: wraps all content - aka the root element
3. `<head></head>`: Acts as the container for item you want included in your HTML page that isn't content for the viewer. Can include keywords and page description that would appear in search results, CSS to style, etc....
4. `<meta charset=utf-8`> specifies character encoding as UTF-8
5. `<title></title>`: This sets the title of the page. Appears in the browser tab. 
6. `<body></body>`: Contains all the content that displays on the page.


# Void Elements
----
Self closing tags. Such as 
```html
<img src="#" alt="#" />
```
These insert / embed something in the document

# Meta
----
```html
<meta name="author" content="Phillip Choi" />
<meta
	  name="description"
	  content="What you want to show users in a search" />
```


# Favicon
----
icon shown in bookmarks and in a tab in a browser, left of the title. 

Can support `.ico` , `.gif`, or `.png`

```html
<link rel="icon" href="favicon.ico" type="image/xicon" />
```


# Apply CSS & JS Scripts
----

```html
<link rel="stylesheet" href="my-css-file.css" />
```

```html
<script src="my-js-file.js" defer></script>
```

defer loads the script after the html page ( this way you do not have to place your script on the bottom of your page.)

  













# Backlinks
-----
[Web Development](Web%20Development.md)
[Frontend](Frontend)

