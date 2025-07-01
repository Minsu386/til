JavaScript [[Interview]] Questions
## Vocab
____

### Objects
____
console , Math

console.log() | Math.random()

Objects, including instances of data types, can have properties, stored infomration. The properties are denoted with a `.`  after the name of the object. 
Objects, including instances of data tyypes, can have methods which perform actions.


### Methods
----
log , random

console.log() | Math.random()

Methods are called by appending the object or instance with a period

methods ends in ()

### Properties
----
Math.E

Notice for properies it does NOT end with ()

## Parameters & Arguments
----
We use parameters as placeholders for information that will be passed to the function when it is called. 


```JavaScript
function calculateArea(width, height) {
	console.log(width * height);
}
```

`calculateArea(width, height)`  The parameters are specifed between the parenthesis as `width` `height`  In the function, these parameters act like regular variables.

When calling a fn that has parameters, we specify the values in the parentheses that follow the function name. The values PASSED to the fn when it is CALLED are called **Arguments** 

`calculateArea(5,4)`  the 5 and 4 are the arguements. 

## Types of Functions #functions
----
### Functions
```JavaScript
function calculateArea(width, height) {
	console.log(width * height);
}
```

### Function Expression
```JavaScript
const CalculateArea = function(width, height) {
	const area = width * height;
	return area;
}
```

unlike function declarations, fn expressions are not hoisted so they cannot be called before they are defined

### Arrow Function
```JavaScript
const calculateArea = (width, height) => {
	let area = width * height;
	return area;
};
```

1. Fn that take only a single parameter do not need the parameter to be enclosed in parentheses. However, if a fn takes 0 or multiple parameter, parentheses are required.
```JavaScript
//ZERO PARAMETER
const zeroParameter = () => {};

// ONE PARAMETER
const oneParameter = paramOne => {};

// TWO+ PARAMETER
const multiParameter = (paramOne, paramTwo) => {};
```

2. A fn body composed of a single-line block does not need curly braces. W/out the curly braces, whatever that line evaluates will auto return. The contents of the block should imediately follow the arrow `=>` and the `return` keyword can be removed. 
	1. This is refered to as implicit return
```javaScript
// SINGLE LINE BLOCK
const sumNum = number => number + number;

// MULTI LINE
const sumNum = number => {
	const sum = number + number;
	return sum;
}
```

Example refactor
```JavaScript
const plantNeedsWater = (day) => {
return day === 'Wednesday' ? true : false;
};
```
to a concise body
```JavaScript
const plantNeedsWater = day => day === 'Wednesday' ? true; false;
```



## BackLinks
----
[What is ES2015](What%20is%20ES2015.md)
[TypeScript](TypeScript.md)
