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


### Billion-Dollar-Mistake
----
Programming languages that allow null values to be used in places that require a different type. 

### Type Aliases
```TypeScript
let rawDataFirst: boolean | number | string | null | undefined;
let rawDataSecond: boolean | number | string | null | undefined;
let rawDataThird: boolean | number | string | null | undefined;

// can be tiring to write the type repeatidly.  
// we can use Type keywoard to create a container for the type.
type RawData = boolean | number | string | null | undefined;

let rawDataFirst: RawData;
let rawDataSecond: RawData;
let rawDataThird: RawData;

```

## Ch04 Objects
----
### Excess Property Checking
----
#### Overview

- TypeScript employs excess property checking to ensure that variables declared with object types have only the expected fields.
- If an object literal contains more fields than its specified type, TypeScript raises a type error.

#### Example:
```Typescript
type Poet = {
  born: number;
  name: string;
}

// Ok: all fields match what's expected in Poet
const poetMatch: Poet = {
  born: 1928,
  name: "Maya Angelou"
};

const extraProperty: Poet = {
  activity: "walking",
  born: 1935,
  name: "Mary Oliver",
};
// Error: Type '{ activity: string; born: number; name: string; }'
// is not assignable to type 'Poet',
// Object literal may only specify known properties,
// and activity does not exist in type 'Poet'
```
#### Important Points

- Excess property checks trigger for object literals created in locations declared to be of an object type.
- Providing an existing object literal bypasses excess property checks if the structure matches the specified type.

##### Example:

```typescript
const existingObject = {
    activity: "walking",
    born: 1935,
    name: "Mary Oliver",
};

const extraPropertyButOk: Poet = existingObject; // Ok
```

#### Use Cases

- Excess property checks apply when creating new objects in locations expecting them to match an object type (e.g., array members, class fields, and function parameters).

#### Benefits

- Banning excess properties enhances code cleanliness and ensures code behaves as expected.
- Detects mistyped property names or unused code.

Understanding excess property checking is crucial for writing robust and error-free TypeScript code. It contributes to code quality by preventing potential issues related to unexpected properties in object literals.


----

### Nested Object Type
----
#### Overview
- TypeScript supports representing nested object types within the type system, allowing for complex structures of objects
#### Example:
```Typescript
type Poem = {
    author: {
        firstName: string;
        lastName: string;
    };
    name: string;
};

// Ok
const poemMatch: Poem = {
    author: {
        firstName: "Sylvia",
        lastName: "Plath",
    },
    name: "Lady Lazarus",
};

const poemMismatch: Poem = {
    author: {
        name: "Sylvia Plath",
    },
    // Error: Type '{ name: string; }' is not assignable
    // to type '{ firstName: string; lastName: string; }'.
    //   Object literal may only specify known properties, and 'name'
    //   does not exist in type '{ firstName: string; lastName: string; }'.
    name: "Tulips",
};

```

#### Nested Types Aliasing
- to enhance code readability and provide informative error messages, nested types can be extracted into their own aliases. 
- In the example, the `Author` type is created to represent the structure of the `author` property. 
#### Example
```typescript
type Author = {
    firstName: string;
    lastName: string;
};

type Poem = {
    author: Author;
    name: string;
};

const poemMismatch: Poem = {
    author: {
        name: "Sylvia Plath",
    },
    // Error: Type '{ name: string; }' is not assignable to type 'Author'.
    //     Object literal may only specify known properties,
    //     and 'name' does not exist in type 'Author'.
    name: "Tulips",
};

```
#### Tip
- It's recommended to move nested object types into their own type aliases for both code readability and clearer TypeScript error messages.

### Optional Properties
#### Overview
- Object Type properties in TypeScript can be designated as optional using the `?` syntax. 
- Optional properties allow flexibility in object structures, permitting their absence in declared variables. 
#### Example:
```Typescript
type Book = {
  author?: string;
  pages: number;
};

// Ok
const ok: Book = {
    author: "Rita Dove",
    pages: 80,
};

const missing: Book = {
    author: "Rita Dove",
};
// Error: Property 'pages' is missing in type
// '{ author: string; }' but required in type 'Book'.

```

#### Difference from Type Union with Undefined
- Optional properties, marked with `?`, are allowed to not exist in objects.
- A property with a type union that includes `undefined` must exist, even if its value is `undefined`
#### Example:
```Typescript
type Writers = {
  author: string | undefined;
  editor?: string;
};

// Ok: author is provided as undefined
const hasRequired: Writers = {
  author: undefined,
};

const missingRequired: Writers = {};
// Error: Property 'author' is missing in type
// '{}' but required in type 'Writers'.

```





### Inferred Object-Type Unions


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
# Udemy Portfolio Typescript
----
## ReactDOM warning with reactV18
-----
In the upcoming lecture, we will be adding code to our index.tsx file and running a test in our browser. You will likely see the following warning:

_react-dom.development.js:86 Warning: ReactDOM.render is no longer supported in React 18. Use createRoot instead. Until you switch to the new API, your app will behave as if it's running React 17._

You are free to ignore this warning, or, you may choose to update to use createRoot:

  

1. // 1) Import ReactDOM library
2. import ReactDOM from "react-dom/client";

4. // 2) Get a reference to the div with ID root
5. const el = document.getElementById("root");

7. // 3) Tell React to take control of that element
8. const root = ReactDOM.createRoot(el!);

10. // 4) Create a component
11. const App = () => {
12.   return (
13.     <div>
14.       <h1>Hi there!</h1>
15.     </div>
16.   );
17. };

19. // 5) Show the component on the screen
20. root.render(<App />);

  

**Important** - Due to a bug in the DefinitelyTyped ReactDOM definitions, you need to add the `**!**` operator here:

`const root = ReactDOM.createRoot(**el!**);`



## Standalone event handlers
----
when using typescript
```TypeScript
<div>
  <input onChange={onChange} />
</div>
```

we receive no typescript error. This is because inline is inferred. if we hover over onchange we recieve this information
```
(JSX Attribute)
React.InputHTMLAttributes<HTMLInputElement>.onChange((event: React.ChangeEvent<HTMLInputElement>) => void) | undefined

```

if we wanted to use this on a 
```TypeScript
const onChange = (event) => {
  console.log(event)
}
```

we would need to add
```TypeScript
const onChange = (event: React.ChangeEvent<HTMLInputElement>) => {
  console.log(event)
}
```

there are other events besides change that we handle in react. Such as hover, dragged etc.[TypeScript Redux Store](Excalidraw/TypeScript%20Redux%20Store.md)


![](Meta/Pasted%20image%2020231212104258.png)
# Udemy NPM Package Search
----
## Redux side of our project
----
![TypeScript Redux Store](Excalidraw/TypeScript%20Redux%20Store.md)

Step 1 - Reducer setup
  [[what is  enum?]]
1. } catch (err) {
2. if (err instanceof Error) {
3. dispatch({
4. type: ActionType.SEARCH_REPOSITORIES_ERROR,
5. payload: err.message,
6. });
7. }
8. }