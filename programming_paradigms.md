# Programming Paradigms
> Object-Oriented Programming (OOP) vs. Functional Programming

## Overview
**Object-oriented programming (OOP):**\
Basic principle: OOP is based on the concept of objects that combine data (attributes) and methods (functions) for manipulating this data. A program in OOP consists of a collection of objects that interact with each other.
Core concepts: classes, inheritance, polymorphism, abstraction, encapsulation.

**Functional programming:**\
Basic principle: Functional programming views calculations as evaluations of functions and avoids mutable states and variable data. Functions in functional programming are so-called "first-class citizens", which means that they can be treated like other data.
Core concepts: Immutability, higher-order functions, recursion, functions as arguments and return values.

## Comparison
**Object-oriented programming (OOP):**\
`animal.ts`
```ts
export class Animal {
  private name: string;

  constructor(name: string) {
    this.name = name;
  }

  getName(): string {
    return this.name;
  }

  makeSound(): void {
    console.log("Generic animal sound");
  }
}

export class Dog extends Animal {
  makeSound(): void {
    console.log("Woof! Woof!");
  }
}
```
`index.ts`
```ts
import {Animal, Dog} from './animal.ts';

const myAnimal = new Animal("Animal");
console.log(myAnimal.getName()); // Buddy
myAnimal.makeSound(); // Generic animal sound

const myDog = new Dog("Buddy");
console.log(myDog.getName()); // Buddy
myDog.makeSound(); // Woof! Woof!
```

**Functional programming:**\
`animal.ts`
```ts
export function createAnimal(name: string) {
  return {
    getName: () : string => {
      return name;
    }
    makeSound: () : void => {
      console.log("Generic animal sound");
    }
  }
}

export function createDog(name : string) {
  ...Animal(name),
  makeSound(): void {
    console.log("Woof! Woof!");
  }
}
```
`index.ts`
```ts
import {createAnimal, createDog} from './animal.ts';

const myAnimal = createAnimal("Animal");
console.log(myAnimal.getName()); // Buddy
myAnimal.makeSound(); // Generic animal sound

const myDog = createDog("Buddy");
console.log(myDog.getName()); // Buddy
myDog.makeSound(); // Woof! Woof!
```
