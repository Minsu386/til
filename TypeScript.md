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

