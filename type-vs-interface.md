# Type Aliases vs Interfaces in Simple Words

### Introduction
When I started learning TypeScript, I was very confused between "type" and "interface". Both of them look almost identical because we use both to define the shape of an object. But after practicing, I noticed some clear differences between them.

### What is the Difference?
The easiest difference to remember is that an "interface" is mainly for objects and can be reopened to add new fields. This is called declaration merging. If you write two interfaces with the exact same name, TypeScript combines them into one.


// Interface merging example
interface User {

name: string;
}

interface User {
age: number;
}
