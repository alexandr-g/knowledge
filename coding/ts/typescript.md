# BASICS

## Variables

```ts
/**
 * (1) x is a string, b/c we’ve initialized it
 */
let x = 'hello world'

/**
 * (2) reassignment is fine
 */
x = 'hello mars'

/**
 * (3) but if we try to change type
 */
x = 42 // 🚨 ERROR

/**
 * (4) let's look at const. The type is literally 'hello world'
 */
const y = 'hello world'

/**
 * This is called a 'string literal type'. y can never be reassigned since it's a const,
 * so we can regard it as only ever holding a value that's literally the string 'hello world'
 * and no other possible value
 */
```

### Reference

All the code examples are coming from [Mike's TypeScript Fundamentals Course](https://github.com/mike-works/typescript-fundamentals)

### Types

_Type_ is an easy way to refer to the different properties and functions that a value has.

A _value_ in JS is anything that we can assign to a _variable_.

#### What can we assign to variables

1. String
2. Number
3. Boolean
4. null
5. undefined
6. Object {}
7. Function
8. Array
9. Classes

#### Types in TS

##### Primitive Types

- number
- boolean
- void
- undefined
- null
- string
- symbol

##### Object Types

- functions
- arrays
- classes
- objects

#### Type annotations and Type Inference

_Type annotations_ is a code we add to tell TypeScript what type of value a variable will refer to.
_Type inference:_ TypeScript tries to figure out what type of value a variable refers to.

#### Annotations with Variables

```ts
let apples: number = 5;

apples = 10; // valid
apples = ’some’ // error
```

##### Different type annotations

```ts
let apples: number = 5;
let speed: string = ‘fast’;
let hasName: boolean = true;

let nothingMuch: null = null;
let nothing: undefined = undefined;

// built in objects
let now: Date = new Date();

// Array
let colors: string[] = ["red", "green", "blue"];
let myNumbers: number[] = [1, 2, 3];
let truths: boolean[] = [true, true, false];

// Classes
class Car {

}

let car: Car = new Car();

// Object literal
let point: { x: number; y: number } = {
    x: 10,
    y: 20
};

// Function
const logNumber: (i: number) => void = (i: number) => {
    console.log(i)
};
```

#### Type inference

If declaration and initialization are done on the same line, TypeScript will figure our the type for us

```ts
let apples = 5 // inferred type ’string’

let apples
apples = 5 // inferred type ‘any'
```
