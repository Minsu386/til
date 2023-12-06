# Learning TypeScript
----
By: Josh Goldberg

## Getting Started
`npm i -g typescript`

Now you are able to run TypeScript on the command line with **tsc** (TypeScript Compiler) command
`tsc --version`

### Running Locally
----

`tsc --init` in your project folder

## CH 01
### Kinds of Errors
Two types of errors we will come across most frequently are:
  - *Syntax*
    - Blocking TypeScript from being converted to JavaScript
  - *Type*
    - Something mismatched has been detected by the type checker
    
## Ch 03 Unions and Literals
----

- *Unions*
  - Expanding  a value's allowed type to be two or more possible types
- *Narrowing*
  - Reducing a value's allowed type to *not* be one or more possible types

TypeScript represents Union types using the | (pipe) operator between the possible values, or *constituents.*

```TypeScript
let mathematician = Math.random() > 0.5 ? undefined : "mark Goldberg";

// let mathematician: string | undefined
```

```TypeScript
// Declaring Union Types  
  
let thinker: string | null  = null;  
  
if (Math.random() > 0.5) {  
    thinker = 'Susanne Langer'; // ok  
}
```

Two types of Narrowing
- Assignment Narrowing
  - directly assign a value to a variable
  ```TypeScript
  let admiral: number | string;
  admiral = "grace hopper";
  admiral.toUpperCase(); // okay: string
  admiral.toFixed(); // error property toFixed does not exist on type 'string' 
   
```
- Conditional Checks
  - Write an `if` statement checking the variable for being equal to a known value
  ```TypeScript
  // Narrowing - Conditional *Typeof Checks  
  
let researcher = Math.random() > 0.5 ? 'Rosalind Franklin' : 51;  
if (typeof researcher === 'string') {  
    researcher.toUpperCase(); // ok: string  
}  
if(!(typeof researcher === 'string')) {  
    researcher.toFixed(); // ok: number  
} else {  
    researcher.toUpperCase(); // okay: string  
}  
  
// can be rewritten with a ternary statement  
typeof researcher === 'string' ? researcher.toUpperCase() : researcher.toFixed();
```








# Udemy
----
[JavaScript](JavaScript.md)
Interface - used to defined the structure of an object

Type - Easy way to refer to the different properties and function that a value has.

![[Excalidraw/Drawing 2023-11-15 10.51.32.excalidraw]]

Type Annotation - Code we add to tell Typescript what type of value a variable will refer too
	We (devs) tell typescript the type

Type inference - Typescript tries to figure out what type of value a variable refers to
	Typescript guesses the type
		If declaration and initialization are on the same line, Typescript will figure out the type for us. 
		`const  color = 'red'`
		const color is the variable declaration
		'red' is the variable initialization


When to use?
![[Excalidraw/Drawing 2023-11-15 14.02.15.excalidraw]]


What is the 'any' type?



## Arrays
----
- TS Can do type inference when extracting values from arrays
- TS Can prevent us from adding incompatible values to the array
- We can get help with 'map, 'forEach', 'reduce' functions
- Flexible - arrays can still contain multiple different types

When to use - Any time we need to represent a collection of records with some arbitrary sort order

## Tuples
----
Array like structure where each element represents some property of a record

```typescript
const drink = {

  color: 'brown',

  carbonated: true,

  sugar: 40

};

  

const pepsi: [string, boolean, number] = ['brown', true, 40]

  

type Drink =[string, boolean, number]

const sprite: Drink = ['clear', true, 40]
```

## Interfaces
----
Creates a new type, describing the property names and value types of an object

```TypeScript
%% const oldCivic = {
	name: 'civic',
	year: 2000,
	broken: true
	
}

const printVehicle = (vehicle: {name: string; year: number; broken: boolean}): void => {
	console.log(`Name: ${vehicle.name`});
	console.log(`Year: ${vehicle.year`});
	console.log('Broken: ${}vehicle.broken'})
} %%

// using interface
interface Vehicle {
	name: string,
	year: number,
	broken: boolean
	// functions inside 
	sumary(): string;
} 

const oldCivic = {
	name: 'civic',
	year: 2000,
	broken: true,
	summary(): string {
		return `Name: {this.name}`
	};
}

const printVehicle = (vehicle: Vehicle): void => {
	console.log(`Name: ${vehicle.name`});
	console.log(`Year: ${vehicle.year`});
	console.log('Broken: ${}vehicle.broken'})
	console.log(vehicle.summary())
}
printVehicle(oldCivic)
```

## Classes
----

Classes -> Blueprint to create an object with some fields (values) and methods (functions) to represent a 'thing'

Capital the name of the class

modifiers 
	Public  -> This method can be called anywhere anytime
	Private -> This method can only be called by other methods in this class
	Protected -> this method can be called by other methods in this class, or by other methods in child classes




## Google Maps
----
Required Update for New @types Library

The @types/googlemaps library that is installed in the next video has been deprecated. Instead, we need to install a different library:

`npm install @types/google.maps`

Also, you will still see a TS error in your code editor:

_Cannot find name 'google'.ts(2304)_

As the very first line in the index.ts file, you will need to add a triple slash directive:

1. /// `<reference types="@types/google.maps" />`

You can read about this in the official docs here:

[https://developers.google.com/maps/documentation/javascript/using-typescript#Module_Import](https://developers.google.com/maps/documentation/javascript/using-typescript#Module_Import)

[[Parcel]]